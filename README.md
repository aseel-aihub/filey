# Filey ✦

A cozy, single-page website for sharing certificates through **one link**.
Visitors see a dreamy landing page, then a clean board of verified certificates they can search, filter, open and download.

> **Status:** prototype. Built to be simple, free to host, and usable by anyone.

**Live demo:** https://aseel-aihub.github.io/filey/

![Filey landing page](preview.png)

---

## Features

**For visitors**
- Animated landing page: twinkling stars, shooting stars, a glowing moon, and characters that blink and follow the cursor
- The owner's name, headline and LinkedIn / GitHub / website links at the top
- Certificate cards with title, issuer, category, year, a verification link and a **View certificate** button for the attached image or PDF
- Search and category filters
- A direct link to every certificate (`…/filey/#cert-ID`)
- **Download all (ZIP)**: a summary page, a CSV file, the data file and any attached certificate files. Works offline

**For the owner** (edit mode)
- Add, **edit** and delete certificates, with an optional PDF or image file
- Edit your profile (name, headline, links)
- Images are compressed automatically so the site stays fast
- Duplicate warning and automatic category matching ("AI", "ai" and "A.I" count as one category)
- Export and import `certificates.json` as a backup or to move between devices
- **Preview as visitor**: see your draft exactly as visitors will, without the owner tools
- A status bar that shows which changes are not published yet

---

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole website (design, images and code in one file) |
| `certificates.json` | Your profile and certificates, which every visitor sees. Starts empty: `[]` |
| `preview.png` | The image shown when the link is shared on WhatsApp, LinkedIn, X and similar apps |
| `README.md` | This guide |
| `LICENSE` | MIT License |

---

## Get your own copy

1. **Fork** this repository, or download all the files and upload them to a new repository.
2. Open the repository **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**, then **main** and **/ (root)**, and save.
4. After a minute or two your site is live at `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`.
5. In `index.html`, change the two links in the **link preview** block (`og:url` and `og:image`) to your own site address, so the preview image shows when you share the link.

---

## Add your certificates

1. Open your site with `?edit` at the end of the link:
   `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/?edit`
2. Click **Edit profile** and add your name, headline and links.
3. Click **Add certificate** and fill in the details. Use the pencil icon on a card to edit it later.
4. Click **Export certificates.json**.
5. In GitHub, upload the exported file to replace the old `certificates.json`.
6. Refresh the site. Everyone with the link now sees the update.

Share the link **without** `?edit`. The **Copy page link** button does that for you.

> Changes made in edit mode stay in your browser as a draft until you export and upload the file.

---

## Privacy and security

- **Everything in `certificates.json` is public**, including attached files. Remove personal details such as ID numbers, phone numbers or addresses before uploading.
- **GitHub keeps file history.** A certificate you delete later still exists in older versions of the repository.
- `?edit` only shows the owner tools. It is not a password. Nobody can publish to your site without your GitHub account, so turn on **two-factor authentication**.
- The page blocks external scripts and outside connections with a Content Security Policy. All text is escaped before it is shown, and only `http` and `https` links are accepted.

---

## Test on your computer

Opening `index.html` directly works for the landing page and edit mode, but the browser blocks reading `certificates.json` from disk. To test everything locally, run a small server in the project folder:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000` (or `http://localhost:8000/?edit`).

---

## Limits of the prototype

- One owner per site. Each person makes their own copy to show their own certificates.
- No login or database. Publishing is done by uploading `certificates.json` to GitHub.
- Images are resized to 1600px and saved as JPG. PDFs must be 1 MB or smaller.

---

## Data format

`certificates.json` holds your profile and your certificates:

```json
{
  "profile": {
    "name": "Your name",
    "headline": "What you do",
    "links": { "linkedin": "https://…", "github": "https://…", "website": "" }
  },
  "certificates": [
    { "id": "c1", "title": "…", "issuer": "…", "category": "…", "year": 2026, "url": "https://…" }
  ]
}
```

A plain list of certificates (the older format) still works.

---

## License

Released under the [MIT License](LICENSE). You are free to use, copy and change it.
The illustrations are not covered by this license; see Credits.

---

## Credits

- Character illustration generated with Gemini AI 

Made by **Aseel**.
