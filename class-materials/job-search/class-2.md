# Class 2 · Resume page

## Prompt 1A · Resume page

````text
Build me a one-page website called resume.html. Use ONLY the resume text I paste at the bottom of this message. Do not invent anything.

The page has 4 parts:
1. Top: my name (big), my job title, my city, phone and email (as in my resume), and a circle with my initials. No photo.
2. My resume, neatly laid out: each job with dates, short bullet points, skills as small tags. Show numbers in the accent color.
3. A "Tailor for a job" tool. Fields: "Job link" and "Or paste the job text". A button "Tailor my resume". When I click it:
   a. It gets the job text: the pasted text if there is any, else it reads the job link.
   b. It sends one prompt to the AI: "Tailor my resume for the job below. Use ONLY facts from my resume. Do not invent skills, numbers, dates or jobs. Reply in exactly 3 parts with these headings: TAILORED RESUME, WHAT CHANGED, CHECK THESE. In TAILORED RESUME, put {{ and }} around every word or phrase you changed or added. WHAT CHANGED: a short list of the changes and the words from the job you matched. CHECK THESE: any line I should check." Then my full resume text, then the job text.
   c. It shows the answer under the box as a section "Tailored for this job", in my style: the tailored resume with every {{...}} shown highlighted, then the two short lists. Put the answer on the page as text (textContent), never as HTML.
   d. Under it, three buttons: "Hide changes" (turns the highlights off and on, for printing), "Copy tailored resume" (plain text, without {{ }}) and "Print".
   e. While it works, the button says "Tailoring..." and cannot be clicked. Any error shows in one short line under the button.
   How the page talks to the AI:
   - In the class (window.sparecycle exists): read the link with await window.sparecycle.readLink(link), which gives {text}, and get the answer with await window.sparecycle.complete(prompt), which gives the answer text. No key is needed.
   - Anywhere else (window.sparecycle does not exist): show a field "Your OpenRouter key" with "Save key" and "Forget key" buttons. Under it, show this note: "A free OpenRouter key works (no card needed, about 50 tailors a day). When you click Tailor, your resume and the job text go to OpenRouter, and free models may keep what you send." Also show a button "Copy tailor prompt" (works with or without a key): it copies the same tailor prompt, with my full resume and the job text, so I can paste it into any free AI chat. When there is no key, Tailor my resume shows "No key yet. Click Copy tailor prompt and paste it into a free AI chat." Keep the key only in this browser, in localStorage as "resume-openrouter-key". Wrap every localStorage use in try/catch. Read the link with fetch("https://r.jina.ai/" + link, {headers: {"X-Return-Format": "text"}}); if that fails, show "Could not read that link. Paste the job text instead." Get the answer with fetch("https://openrouter.ai/api/v1/chat/completions"), method POST, headers Authorization: "Bearer " + key and Content-Type: application/json, and a JSON body with model "openrouter/free" and messages holding one message: role "user", content the prompt. The answer is the content of the first choice's message.
4. A small "Job tracker" table: company, role, date, status (Saved, Applied, Interview, Offer). Add a "Copy tracker as text" button. Do not save the tracker in the browser.

Rules:
- Every copy button: if copying is blocked, select the text and show "Press Ctrl+C to copy".
- One HTML file. CSS and JavaScript inside the file. No outside libraries. Google Fonts are OK.
- Keep the file short: under 300 lines in all. Short CSS, no code comments, no example data.
- No sign-in. Never write an API key in the code. The only outside calls are the ones in part 3.
- Works on a phone. Prints cleanly on 1 or 2 pages, black text on white.
- My style: [PICK ONE: Ink and Paper / Blueprint / Studio Pop / Velvet Night / Poster Bold]
  Use ONLY the style I picked, exactly as written here:
  Ink and Paper: background #F5F2EB, text #1A1714, accent #C1521E. Fraunces headings with one italic accent word, Work Sans body. Generous white space, hairline rules.
  Blueprint: background #FFFFFF, text #10265F, accent #2458E6. Outfit headings, Instrument Sans body. A faint blueprint grid, everything aligned.
  Studio Pop: background #D8D1C5, text #000000, accent #F0F15E on pill buttons and chips. Archivo Black headings, Hanken Grotesk body. Rounded corners, soft glass cards.
  Velvet Night: background #16121E, text #F4EFE6 (ivory), accent #E2B54B (gold). Gloock headings, Outfit body. A soft warm glow behind my name.
  Poster Bold: background #FFFFFF, text #000000, accent #FF2E00. Archivo Black headings in uppercase, Bricolage Grotesque body. Hard 2px black borders, square corners, big numbers.
- If my resume looks cut off, or is not a resume, stop and tell me in one short message.
- If something important is missing, ask ALL your questions in ONE message.
- Give me the complete file. Write the file name resume.html on its own line, just before the code.

MY RESUME (paste your my-resume.txt text below this line):
[PASTE YOUR RESUME TEXT HERE]
````

## Prompt 1B · Tailor for a job

````text
Tailor my resume for the job below. Use ONLY facts from my resume. Do not invent skills, numbers, dates or jobs.

Give me 3 things:
1. The tailored resume, as plain text I can copy.
2. A short list: what you changed, and which words from the job you matched.
3. Any line you were not sure about, so I can check it.

Privacy: I removed my street address, phone number, and any ID, visa, A-number or case numbers. If you still see any of these below, do not use them, and tell me to remove them.

THE JOB POSTING (paste the full job text):
[PASTE THE JOB POSTING HERE]

MY RESUME (paste your my-resume.txt text):
[PASTE YOUR RESUME TEXT HERE]
````

## Prompt 1C · One small change

````text
Change ONE thing on my resume.html page. Keep everything else exactly the same.

The change: [WRITE ONE CHANGE]
Examples: "make my name smaller" / "use dark blue instead of orange" / "fix the date of my second job to 2019-2022"

Give me the complete updated file. Write the file name resume.html on its own line, just before the code.

If you cannot see my page in this chat, tell me. I will paste the code below.

MY PAGE CODE (only if this is a new chat; copy it from resume.html on GitHub):
[PASTE CODE HERE, OR DELETE THIS LINE]
````
