# Our Science in Visuals — how to edit and publish this site

This site is a single web page (`index.html`) plus a folder of PDFs (`papers/`).
There is no software to install and nothing to "build" — you edit text directly
in the browser and the live site updates within about a minute.

---

## 1. One-time setup (do this once, ~10 minutes)

1. **Create a free GitHub account** at [github.com/join](https://github.com/join) —
   whoever sets this up first (e.g. Paco). Anyone else who will edit content
   should also create their own free account (2 minutes each).
2. **Create a new repository**: click the **+** (top right) → *New repository*.
   Name it e.g. `our-science-in-visuals`. Keep it **Public** (required for free
   GitHub Pages hosting). Click *Create repository*.
3. **Upload the site files**: on the repository page, click *Add file* →
   *Upload files*, then drag in `index.html`, the `papers` folder, and this
   guide. Commit the upload.
4. **Turn on the live site**: go to *Settings* → *Pages* (left sidebar).
   Under *Build and deployment* → *Source*, choose **Deploy from a branch**,
   branch **main**, folder **/(root)**. Click *Save*.
   GitHub will give you a URL that looks like:
   `https://<your-username>.github.io/our-science-in-visuals/`
   That's the live site — share this link with the cohort.
5. **Add the rest of the team as editors**: *Settings* → *Collaborators* →
   *Add people*, and enter each teammate's GitHub username or email
   (Hafsa, Lou, Kai, Abdelrahman, Abderrahman). They'll get an email invite.

That's it — no separate login system, no monthly fees, nothing to maintain.

---

## 2. How to make an edit (every time after that)

1. Go to the repository on github.com and open `index.html`.
2. Click the **pencil icon** (top right of the file view) to edit.
3. Use **Ctrl+F / Cmd+F** in your browser to jump to the text you want to
   change (e.g. search for a name, a title, or a link).
4. Type your change directly.
5. Scroll to the bottom, add a one-line description of what you changed
   (e.g. "Update workshop date"), and click **Commit changes directly to
   the `main` branch**.
6. Wait about 30–60 seconds, then refresh the live site — your change is up.

You cannot break anything permanently: GitHub keeps the full history, so any
change can always be undone (open the *History* tab on the file, and revert).

---

## 3. Where to edit what — the file is labeled

Open `index.html` and look for comments that look like this:

```html
<!-- EDIT ZONE — ... -->
   ... content you can safely change ...
<!-- END EDIT ZONE -->
```

Everything between an `EDIT ZONE` and its matching `END EDIT ZONE` is meant
to be edited. Everything else (the code starting with `<style>`, or lines
with lots of `class="..."` and no visible words) controls layout and design —
leave that alone unless you're comfortable with HTML/CSS.

### Common tasks

**Change a paragraph of text** — find the sentence with Ctrl+F, edit the
words between the `<p>` and `</p>` tags. Don't delete the tags themselves.

**Add a new tool card** (Room I, "General Resources") — copy one whole
block that starts with `<div class="tool-card">` and ends at the matching
`</div>`, paste it just before the tool grid's closing `</div>`, then edit:
the tag word (Free / Paid / Freemium), the tool name, the "For:" / "Against:"
lines, and the link.

**Add a new tutorial/video card** — same idea: copy a whole
`<a class="tut-card">...</a>` or `<a class="video-card">...</a>` block,
paste it before the section's closing `</div>`, change the link and text.

**Add a new paper to a reading list** — copy a whole
`<div class="reading-item">...</div>` block, paste it before the reading
list's closing `</div>`, then:
  - Edit the citation text (`<span class="cite">...`).
  - If you have a PDF: upload it to the `papers/` folder (on GitHub:
    open the `papers` folder → *Add file* → *Upload files*), then set the
    link to `papers/your-file-name.pdf` (use hyphens, no spaces, no accents
    in the file name).
  - If it's an external link instead, paste the full URL.

**Replace an example image** (poster / graphical abstract / infographic) —
this is the one part that needs a small extra step, because images are
embedded directly in the page. Send the new image to whoever manages the
repo, or ask an AI assistant (ChatGPT, Claude, Gemini) to "convert this image
to a base64 data URI" and paste the result in place of the existing
`src="data:image/...` value on the matching `<img>` tag.

**Replace the INITIATE logo** — same base64 approach, on the `<img>` tag
inside the `masthead` section near the top of the file.

---

## 4. If the team outgrows this workflow

This GitHub-editing approach is genuinely free forever and has no accounts
to manage beyond a GitHub login. If later on the team wants a more
point-and-click editor (form fields instead of raw HTML), a tool called
**Decap CMS** can be added on top of this same repository — worth
revisiting then, since its most common setup (via Netlify Identity) has
been in flux and it's not worth the extra setup for a page this size today.
