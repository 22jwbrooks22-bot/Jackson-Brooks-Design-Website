# Architecture Portfolio — Setup Guide

## File Structure

```
portfolio/
├── index.html              ← Homepage
├── css/
│   └── style.css           ← All styles (one file)
├── js/
│   └── main.js             ← Interactions (nav, fade-ins)
├── images/                 ← Put your images here
└── pages/
    ├── work.html           ← All projects grid (with filter)
    ├── project.html        ← Single project template (duplicate per project)
    ├── about.html          ← About / bio / CV
    ├── blog.html           ← Writing list
    ├── post.html           ← Single post template (duplicate per post)
    ├── library.html        ← Books + courses + influences
    └── contact.html        ← Contact form + links
```

---

## How to Customize

### 1. Replace "Your Name" everywhere
Search for `Your Name` in all HTML files and replace with your actual name.
Also replace `[Your School]`, `[City]`, `[Year]`, and email placeholders.

### 2. Add your photo (About page)
In `pages/about.html`, find the comment `<!-- Replace this div with an <img> tag -->`.
Replace the placeholder div with:
```html
<img src="../images/your-photo.jpg" alt="Your Name" style="width:220px; height:280px; object-fit:cover;" />
```

### 3. Add project images
In each `project.html`, find the `.project-image-cell` divs.
Replace the background color with an image:
```html
<div class="project-image-cell tall" style="background:none;">
  <img src="../images/project-plan.jpg" alt="Floor Plan" />
  <div class="placeholder-label">Ground Floor Plan · 1:100</div>
</div>
```

### 4. Create new project pages
Duplicate `pages/project.html` and rename it (e.g. `pavilion.html`).
Update all the content inside. Then update the links in `work.html` to point to it.

### 5. Add blog posts
Duplicate `pages/post.html` and rename (e.g. `post-rome.html`).
Write your post. Then add a new `.blog-row` entry in `blog.html`.

### 6. Update the Library
Open `pages/library.html` and edit the book cards and course entries directly.
Each book just needs a title, author, and a dark background color for the spine.

---

## Making the Contact Form Work

The form currently shows a success message but doesn't send email.
To make it real, use **Formspree** (free, no backend needed):

1. Sign up at https://formspree.io
2. Create a new form — copy the endpoint URL
3. In `pages/contact.html`, update the `<form>` tag:
   ```html
   <form id="contact-form" action="https://formspree.io/f/YOUR_ID" method="POST">
   ```
4. Remove the `e.preventDefault()` line in `js/main.js`, or follow Formspree's AJAX guide.

---

## Hosting for Free

### Option A — Netlify (Recommended)
1. Go to https://netlify.com and create a free account
2. Drag and drop the entire `portfolio/` folder onto the deploy area
3. Your site goes live instantly at a `.netlify.app` URL
4. To connect a custom domain: Site settings → Domain management

### Option B — GitHub Pages
1. Create a GitHub account and a new repository
2. Upload all files (maintain the folder structure)
3. Go to Settings → Pages → set source to `main` branch
4. Live at `yourusername.github.io/portfolio`

### Option C — Vercel
1. Push to GitHub, connect at https://vercel.com
2. Deploys automatically on every git push

---

## Custom Domain
Once hosted, you can connect a domain like `yourname.com`.
Domains cost ~$10–15/year from Namecheap or Porkbun.
Both Netlify and Vercel have guides for connecting custom domains (it takes ~10 minutes).

---

## Next Steps

- [ ] Replace all `[Your Name]` placeholders
- [ ] Add your photo to About page
- [ ] Add real project images
- [ ] Write 1–2 real blog posts
- [ ] Fill in your actual books and courses
- [ ] Connect contact form to Formspree
- [ ] Deploy to Netlify
- [ ] (Optional) Connect a custom domain
