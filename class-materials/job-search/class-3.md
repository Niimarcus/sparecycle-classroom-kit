# Class 3 · Story bank and cover letter

## Prompt 2A · Story bank

````text
Help me build a "story bank" for cover letters and interviews. Use ONLY my resume below.

1. Write my 3 strongest achievements as short stories, 3 to 4 sentences each. Simple, confident English. Keep every number.
2. Then give me a numbered FACT LIST of every fact you used. I will answer each one with TRUE or FALSE. If FALSE, I will type the correction.
3. Then an ADD? list: up to 3 extras that could help (for example, a language I speak, or my journey to the U.S. told as a strength). I answer ADD or SKIP.
4. End with ONE reply line I can copy, change, and send back, with everything set to TRUE and SKIP. Example: 1 TRUE · 2 TRUE · 3 TRUE · ADD 1 SKIP · ADD 2 SKIP

After my reply, give me the final story bank as plain text, with the title STORY BANK at the top.
Do not ask open questions. Do not invent facts. If my resume does not say it, put it in the ADD? list.

Privacy: I removed my street address, phone number, and any ID, visa, A-number or case numbers. If you still see any of these below, do not use them, and tell me to remove them.

MY RESUME (paste your my-resume.txt text):
[PASTE YOUR RESUME TEXT HERE]
````

## Prompt 2B · Cover letter

````text
Write a cover letter for the job below. Use ONLY facts from my story bank and my resume.

- 250 to 320 words. Confident, specific and warm. Simple English.
- No cliches like "I am writing to express my interest".
- Do not include my street address, my phone number, or any ID or visa number.
- Do not mention immigration or visa status.
- After the letter, list every fact you used, so I can check each one.

Privacy: I removed my street address, phone number, and any ID, visa, A-number or case numbers. If you still see any of these below, do not use them, and tell me to remove them.

COMPANY NAME:
[COMPANY]

THE JOB POSTING (paste the full job text):
[PASTE THE JOB POSTING HERE]

MY STORY BANK (paste your story-bank.txt text):
[PASTE YOUR STORY BANK HERE]

MY RESUME (paste your my-resume.txt text):
[PASTE YOUR RESUME TEXT HERE]
````

## Prompt 2E · Cover letter on resume page

````text
Here is my resume page, resume.html. Add a cover letter part at the bottom of it. Keep everything else exactly the same: my style, my resume, the tailor tool, Print, Start over, the key field and the job tracker. Copy every line you do not need to change. Put the new CSS at the end of my style tag, and the new script at the end of my script.

The new part is a section "Cover letter", under everything else, in my page's style (same fonts, colours, buttons and boxes as the tailor tool). It has:
1. Two fields, like the tailor tool: "Job link" and "Or paste the job text". A button "Write my letter".
2. When I click it:
   a. It gets the job text: the pasted text if there is any, else it reads the job link.
   b. It sends one prompt to the AI: "Write a cover letter for the job below. Use ONLY facts from my resume. Do not add skills, jobs, schools or numbers that are not in my resume. 200 to 300 words, 4 short paragraphs, plain text. Paragraph 1: the job title, the company, and one reason I fit. Paragraphs 2 and 3: two examples from my resume that match the job, with my own numbers. Paragraph 4: thank them and ask for an interview. No address block. No cliches like 'I am writing to express my interest'. Do not mention immigration or visa status. End with 'Sincerely,' and my first name. Then write CHECK THESE: and list any line I should check before I send it." Then my full resume text (the same text the tailor tool sends), then the job text.
   c. It shows the letter in a large text box I can edit, and the CHECK THESE list under it. Split the answer at "CHECK THESE". Put the answer on the page as text, never as HTML.
   d. While it works, the button says "Writing..." and cannot be clicked. Any error shows in one short line under the button.
3. Under the letter, three buttons:
   - "Copy letter": copies the letter with my edits.
   - "Print letter": prints only the letter with my edits, black text on white, 1 page. Add a class to the body, call window.print(), and remove the class in afterprint.
   - "Clear letter": do not use confirm() or alert(). Show a small box on the page: "Clear the letter?" with "Yes, clear it" and "Cancel". On Yes, clear the job link, the job text, the letter and the CHECK THESE list.
4. How it talks to the AI:
   - In the class (window.sparecycle exists): read the link with await window.sparecycle.readLink(link), which gives {text}, and get the answer with await window.sparecycle.complete(prompt), which gives the answer text. Do this even if my tailor tool reads links another way.
   - Outside the class: read the link and call the AI the same way my page's tailor tool already does, with my saved key. Do not add a second key field. Also show a button "Copy letter prompt" (works with or without a key): it copies the same letter prompt, with my full resume and the job text, so I can paste it into any free AI chat. When there is no key, Write my letter shows "No key yet. Click Copy letter prompt and paste it into a free AI chat."

Print (my Print button and Ctrl+P): keep what my page prints now. Never print the cover letter fields, buttons or the CHECK THESE list. If I wrote a letter, print it after my resume, on a new page, with my edits. If I did not write one, print no letter. After any print, my letter, my edits and my tailored resume stay on the screen. If my page reloads or rebuilds itself after printing (for example location.reload()), change that so nothing is lost.

Rules:
- Every copy button: if copying is blocked, select the text and show "Press Ctrl+C to copy".
- Do not save the letter or the job text in the browser. Never write an API key in the code.
- No outside libraries. No code comments. Works on a phone. Add about 110 new lines at most.
- Never stop to ask me a question: make the page. Only if my page is cut off, or is not my resume page, stop and tell me in one short message.
- Give me the complete file, ending with </html>. Write the file name resume.html on its own line, just before the code. Write nothing after </html>.

MY PAGE:
[PASTE YOUR resume.html CODE HERE]
````
