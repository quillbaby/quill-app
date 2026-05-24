# Quill website

The marketing + support + privacy site for the Quill baby tracker app.
Lives at quillbaby.com.

## What's in this folder

- `index.html` — landing page
- `privacy.html` — privacy policy (required by App Store)
- `support.html` — contact + FAQ
- `style.css` — shared styling
- `README.md` — this file

## Local preview

To preview the site on your Mac before deploying:

```bash
cd ~/Desktop/nest/docs/website
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser.

Press `Ctrl+C` in the terminal to stop the preview server.

---

## Deployment to GitHub Pages

### One-time setup

1. **Create GitHub account** at github.com if you don't have one.
2. **Create a new repository:**
   - Click + (top right) → New repository
   - Name: `quillbaby-website` (or any name you prefer)
   - Make it **Public** (required for free GitHub Pages)
   - Don't initialize with README/license — we'll upload files directly
3. **Upload files:**
   - On the new empty repo page, click "uploading an existing file"
   - Drag all 5 files from this folder (`index.html`, `privacy.html`, `support.html`, `style.css`, `README.md`) into the browser
   - Commit message: "Initial site"
   - Click "Commit changes"
4. **Enable GitHub Pages:**
   - Repository → Settings → Pages (left sidebar)
   - Under "Source", select **Deploy from a branch**
   - Branch: **main**, folder: **/ (root)**
   - Click Save
   - Within 30-60 seconds, GitHub will show a green box with your live URL: `https://YOUR_USERNAME.github.io/quillbaby-website/`
5. **Test the URL** in your browser. Site should load.

### Connect your custom domain (quillbaby.com)

After buying quillbaby.com from your registrar (Namecheap, Cloudflare, Porkbun, etc.):

1. **In your registrar's DNS settings**, add these records:

   **For root domain (quillbaby.com):**

   Add 4 A records, all with name `@` (or blank, depending on registrar):
   ```
   A    @    185.199.108.153
   A    @    185.199.109.153
   A    @    185.199.110.153
   A    @    185.199.111.153
   ```

   **For www subdomain:**
   ```
   CNAME    www    YOUR_USERNAME.github.io
   ```
   (Replace YOUR_USERNAME with your actual GitHub username, no trailing slash.)

2. **In GitHub repo settings → Pages:**
   - Under "Custom domain", enter: `quillbaby.com`
   - Click Save
   - Wait. GitHub will verify DNS — can take 15 minutes to 2 hours.
   - Once verified, check "Enforce HTTPS" (provides free SSL)

3. **Done.** Visit quillbaby.com in your browser — you'll see your site with a 🔒 padlock indicator.

---

## Updating the site later

Two ways:

### Option A: Edit via GitHub web UI (easiest)
1. Go to your repo on github.com
2. Click any file (e.g., `index.html`)
3. Click the pencil icon to edit
4. Make changes
5. Click "Commit changes" at bottom
6. Site updates within a minute

### Option B: Edit locally, upload changes
1. Edit files in this folder on your Mac
2. Go to repo on github.com
3. "Add file" → "Upload files" → drag updated files
4. Commit

---

## Things to update before launch

Find-and-replace across all HTML files:

- [ ] `hello@quillbaby.com` → your actual support email (if different)
- [ ] App Store URL placeholder (`#coming-soon`) → real App Store URL once approved
- [ ] Add real screenshots if desired (currently text-only feature descriptions)
- [ ] Verify "Last updated" date on privacy.html matches actual launch date

---

## Email forwarding setup (when ready)

If you want `hello@quillbaby.com` to forward to your real email (free, professional):

- **Namecheap:** Domain List → Manage → Advanced DNS → Email Forwarding
- **Cloudflare:** Email Routing → enable, add rule: `hello@quillbaby.com` → your real email
- **Porkbun:** Email Forwarding tab → add forward

Both Cloudflare and Porkbun forward email for free. Namecheap includes basic forwarding free with most domain registrations.

---

## Costs

- Domain: ~$10–15/year (whoever you bought from)
- GitHub Pages hosting: $0
- SSL certificate: $0 (GitHub provides automatically)
- Email forwarding: $0
- **Total: ~$12/year**

Apple Developer Program (separate, only needed to submit to App Store): $99/year.
