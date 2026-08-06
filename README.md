# Terry knocks the bastard off — website

A simple, no-code-required website for weekly updates. This README covers two things:
1. **One-time setup** — getting the site live on your own domain (about 20–30 minutes)
2. **Publishing a new update** — takes about 2 minutes each time, no technical skill needed

---

## PART 1 — One-time setup

### Step 1: Create a GitHub account
Go to **github.com** and sign up (free). This is where your site's files live.

### Step 2: Create a new repository
- Click the **+** icon top-right → **New repository**
- Name it something like `terry-updates`
- Set it to **Public**
- Click **Create repository**

### Step 3: Upload these files
- On your new repository's page, click **Add file → Upload files**
- Drag in everything from this folder (`index.html`, the `posts` folder with everything inside it, and this README)
- Scroll down, click **Commit changes**

### Step 4: Connect to Netlify (this makes it a live website)
- Go to **netlify.com** and sign up (free) — easiest is to sign up using your GitHub account, one click
- Click **Add new site → Import an existing project**
- Choose **GitHub**, then select your `terry-updates` repository
- Leave all the build settings blank/default (this site doesn't need any build step)
- Click **Deploy site**
- Within a minute, Netlify gives you a live URL like `random-name-123.netlify.app` — that's your site, live, right now

### Step 5: Add your own domain (optional but recommended)
- Buy a domain from any registrar — Namecheap, GoDaddy, or similar (~$20–25/year). Something like `terrysjourney.co.nz` or similar
- In Netlify, go to **Domain settings → Add a domain**, type in the domain you bought
- Netlify will show you 1–2 DNS records to add — go to your domain registrar's DNS settings and add exactly what Netlify shows you
- This can take a few hours to fully activate, but from here it's automatic

**That's it — the site is live and connected.** From now on, any change you make in GitHub automatically republishes the live site within about 30 seconds.

---

## PART 2 — Publishing a new update (every time, going forward)

1. Go to your repository on GitHub, open the **posts** folder
2. Click **TEMPLATE.json** to open it, then click the **pencil icon** (top right) to edit
3. Change the three lines:
   - `"date"` — today's date, format `2026-08-10`
   - `"title"` — a short title
   - `"body"` — the update itself
4. Instead of saving over the template, click the dropdown next to "Commit changes" and choose **"Create a new branch... "** — actually, simpler: use **Add file → Create new file** instead of editing the template directly (see note below)
5. Go back to the **posts** folder → **Add file → Create new file**
6. Name it something like `2026-08-10-good-week.json` (date first, so files sort nicely)
7. Paste in the same three-line format as the template, filled in with your update
8. Scroll down, click **Commit changes**
9. Open the **manifest.json** file, click the pencil icon to edit, and add your new filename to the list (comma-separated, matching the existing format)
10. Commit changes

Within about 30 seconds, your new update appears live on the site.

**Tip:** keep every post's JSON simple — three lines, no special characters like curly quotes or emoji that might break the formatting. Plain text works best.

---

## If anything goes wrong

- If the site shows "No updates posted yet" — check that the filename in `manifest.json` exactly matches the filename in the `posts` folder (including `.json` at the end).
- If a post doesn't show correctly — open its file and check it has exactly three lines (`date`, `title`, `body`) with commas after the first two, and quotation marks around all the text.
- Netlify has a **Deploys** tab showing the history of every change and whether it succeeded — useful for checking if something didn't publish.
