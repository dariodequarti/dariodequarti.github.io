# Your Academic Website

A minimal, elegant personal site for economists. Zero dependencies, no build step, pure HTML/CSS/JS.

## 🚀 Get live in 15 minutes

### Step 1 — Create a GitHub repo
1. Go to github.com → New repository
2. Name it **exactly**: `yourusername.github.io` (replace with your GitHub username)
3. Set it to **Public**
4. Click Create repository

### Step 2 — Upload your files
Option A (easier for beginners):
- In your new repo, click "Add file" → "Upload files"
- Drag `index.html` into the window → Commit

Option B (with Git):
```bash
git init
git add .
git commit -m "initial site"
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages
1. Go to repo Settings → Pages
2. Source: "Deploy from a branch" → main → / (root)
3. Save → wait 1–2 minutes
4. Your site is live at: **https://yourusername.github.io**

### Step 4 (optional) — Add a custom domain
1. Buy a domain from Namecheap or Google Domains (~$12/yr)
2. In repo Settings → Pages → Custom domain → enter yourname.com
3. In your domain registrar, add these DNS records:
   - A records pointing to: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
4. Check "Enforce HTTPS"

---

## ✏️ Customising your site

Everything you need to edit is clearly labelled in `index.html`. 
Search for these placeholders and replace them:

| Placeholder | What to put |
|---|---|
| `Your Name` | Your actual name |
| `your.name` (nav) | Your name initials/handle |
| `[your research fields]` | e.g. "development economics and political economy" |
| `[your methods]` | e.g. "field experiments and causal inference" |
| `[your theme]` | e.g. "how institutions shape economic behavior" |
| `Geneva Graduate Institute` | Keep or update |
| `cv.pdf` | Upload your CV as `cv.pdf` in the same folder |
| `photo.jpg` | Add your photo, replace the placeholder div with `<img src="photo.jpg" alt="Your Name">` |
| Paper titles/abstracts | Replace with your actual papers |
| Email/social links | Update in the contact section |

---

## 📄 Adding your CV

Just drop your CV file as `cv.pdf` in the same folder as `index.html`.
The download button already links to it.

## 🖼️ Adding your photo

1. Save your photo as `photo.jpg` in the site folder
2. In `index.html`, find the `photo-placeholder` div and replace it with:
   ```html
   <img src="photo.jpg" alt="Your Name" style="width:100%;height:100%;object-fit:cover;" />
   ```

## 📝 Adding a new paper

Copy this block and paste it inside the `paper-list` div, then edit:

```html
<div class="paper-item reveal" onclick="togglePaper(this)">
  <div>
    <div class="paper-title">Your Paper Title</div>
    <div class="paper-coauthors">with Co-Author (Institution) — 2024</div>
    <div class="paper-abstract-preview">
      Your abstract here.
    </div>
    <div class="paper-links">
      <a href="paper.pdf" class="paper-link-btn" onclick="event.stopPropagation()">PDF</a>
    </div>
  </div>
  <div style="display:flex;flex-direction:column;align-items:flex-end;gap:0.5rem;">
    <span class="paper-status status-wp">Working Paper</span>
    <span class="paper-expand-icon">+</span>
  </div>
</div>
```

Status badge options:
- `class="paper-status status-wp"` + text `Working Paper`
- `class="paper-status status-pub"` + text `Published` + journal name
- `class="paper-status status-prog"` + text `In Progress`

---

## 🎨 Changing the colour accent

In the `:root` CSS block, change `--accent` and `--accent2`:
```css
--accent:  #2a4a7f;   /* main blue — nav links, headings */
--accent2: #c8502a;   /* warm rust — italic name in hero */
```
Any CSS colour works: hex, rgb, hsl.

---

## ➕ Adding a scrollytelling page (Dev Patel style)

Once you have a paper with a clear visual/spatial component:
1. Create a new file: `floods.html` (or `paper1.html`)
2. Ask Claude Code: *"Build me a scrollytelling explainer page for my paper on [topic]. 
   The key visual is [describe your map/chart/mechanism]. Use the same fonts and 
   colour scheme as index.html."*
3. Link from your paper entry: `<a href="floods.html" class="paper-link-btn">Interactive Guide</a>`

---

## 🤖 Working with Claude Code to update the site

Claude Code can edit files on your computer directly. Just say things like:

- *"Add a new working paper called X by me and Y, with this abstract: [paste abstract]"*
- *"Change the accent colour to a deep green"*  
- *"Add a Teaching section after Research with these courses: [list]"*
- *"Make the hero section taller with a subtle animated background"*
- *"Add a Google Scholar citation count badge next to each paper"*

You never need to understand the HTML to update the site.
