# Serving a small open model for a class

This is how we run the small model for Sparecycle classes. It is one Mac, one file to
download for the server, one file for the model, and one service definition.

## What you need

- An Apple Silicon Mac. We use an M4 Mac mini with 32 GB of memory.
- llamafile 0.10.6 from Mozilla: https://github.com/mozilla-ai/llamafile
- The model file `gemma-4-26B-A4B-it-UD-Q4_K_M.gguf` and, for image input, `mmproj-F16.gguf`,
  from the Hugging Face repository `unsloth/gemma-4-26B-A4B-it-GGUF`.
- A key file: a text file with one long random key. Keep it on the Mac only.

## The service

`llamafile.plist` is a launchd user agent. Put your own paths in it, copy it to
`~/Library/LaunchAgents/`, and load it. It starts at login and restarts if it stops.

| Setting | Why we use it |
|---|---|
| `--host 127.0.0.1` | The server cannot be reached from the network directly. Only the tunnel reaches it. |
| `--api-key-file` | A request with no key is refused. Never put the key in a repository. |
| `-c 131072 -np 8` | 8 requests at once, about 16,000 tokens each. |
| `--alias gemma-4-26b-a4b` | The public model list shows this name, not a file path on the Mac. |
| `--mmproj mmproj-F16.gguf` | Turns on image input. Leave it out if you do not need it. |
| `--reasoning off` | Turns off the model's thinking output. Answers start sooner. |
| `--no-webui` | No chat page on the Mac. |
| `--no-slots` | No endpoint that shows what a request slot holds. |
| Output to `/dev/null` | Server logs are not kept, so prompt and answer text cannot reach a log file. |

A request's text is held in memory while the model answers. It is not written to disk by
this setup.

## Reaching the Mac from your class software

We use Tailscale Funnel. It gives the Mac a public HTTPS name, and the key still guards
the server.

```bash
tailscale funnel --bg 8089
```

Your class software then calls that HTTPS name with the key, using the OpenAI-style
`/v1/chat/completions` endpoint that llamafile serves.

## Power

Set the Mac to restart after a power cut and not to sleep:

```bash
sudo pmset -a autorestart 1
```

## Limits we know about

- Long answers are slow. A full web page can take several minutes.
- We have not yet measured how many learners one computer supports in a live class.
