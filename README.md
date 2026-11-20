# Sparecycle classroom kit

Sparecycle is a platform that lets nonprofits run classes using a small open model.
This kit holds two things that another organization can copy today:

1. `setup/`: how we serve a small open model for a class with Mozilla's llamafile.
2. `class-materials/job-search/`: the prompts from our job-search classes.

The Sparecycle platform code is not in this kit.

## What we run

| Part | What we use |
|---|---|
| Model | Gemma 4 26B-A4B, an open model with about 4 billion active parameters, quantized (UD-Q4_K_M) |
| Server | Mozilla llamafile 0.10.6 |
| Computer | One Apple M4 Mac mini with 32 GB of memory |

## What we do not know yet

- How many learners one computer can support in a live class. Our settings allow 8 requests
  at once. We have not yet measured this under real classroom demand.
- How well the setup works on other hardware. We have only run it on the Mac mini above.

## Licenses

- Files in `setup/` are under the Apache License 2.0. See `LICENSE`.
- Files in `class-materials/` are under Creative Commons Attribution 4.0 International
  (CC BY 4.0). See `class-materials/LICENSE.md`.

## Contact

Marcus Anum, sparecycle.org
