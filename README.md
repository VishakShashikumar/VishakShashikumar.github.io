# Vishak Shashikumar — personal site

Static site. No build step, no dependencies. Everything is in `index.html`.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole site — HTML, CSS, JS and the portrait, in one file |
| `vishak-shashikumar-resume.pdf` | Linked from the hero and footer. Replace it, keep the filename |
| `favicon.svg` / `favicon.ico` / `apple-touch-icon.png` | Browser tab and phone home-screen icon |
| `og-card.png` | The preview image LinkedIn shows when you share the link |

## Run it locally

```bash
cd ~/Sites/vishak-site        # wherever you put this folder
python3 -m http.server 8000
```

Then open http://localhost:8000

Opening `index.html` by double-clicking also works, but use the server —
it matches how the live site behaves.

## Put it online (GitHub Pages — free, ~5 minutes)

```bash
cd ~/Sites/vishak-site
git init
git add .
git commit -m "Personal site"
git branch -M main
git remote add origin https://github.com/VishakShashikumar/VishakShashikumar.github.io.git
git push -u origin main
```

First create the repo on GitHub named exactly **`VishakShashikumar.github.io`**
(public). Then in the repo: **Settings → Pages → Source: Deploy from a branch →
Branch: `main` / root → Save**.

Two minutes later it's live at:

```
https://vishakshashikumar.github.io
```

That is the URL for your LinkedIn profile.

### Updating it later

```bash
git add .
git commit -m "Update projects"
git push
```

Live within a minute.

## Add it to LinkedIn

1. Profile → **Edit intro** (pencil icon) → **Website** → paste the URL,
   label it *Portfolio*.
2. Also put it in **Contact info** and in your **About** section — the intro
   link is easy to miss.
3. Paste the URL into a post once. LinkedIn will render `og-card.png` as the
   preview image.

## Custom domain (optional, ~$12/year)

Buy e.g. `vishak.dev` from Namecheap or Cloudflare, then:

1. Create a file named `CNAME` in this folder containing just: `vishak.dev`
2. At your registrar add a CNAME record: `www` → `vishakshashikumar.github.io`
   and four A records for the apex pointing to `185.199.108.153`,
   `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
3. GitHub → Settings → Pages → Custom domain → enter it → tick **Enforce HTTPS**

## Editing content

Open `index.html` and search for the `CASES` array near the top of the
`<script>` block — every project lives there. Experience is plain HTML in the
`#experience` section. Nothing is minified; it is meant to be edited by hand.
