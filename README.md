# Portfolio Website

One file: `index.html`. It uses plain HTML, CSS and JavaScript, with no build step.

## Run locally
Double-click `index.html`, or serve the folder:
```
npx serve .
```

## Customise
Log in as admin (🔒 in the menu bar) and click **✏️ Edit website** to change your name, initials, city/location, role, intro, bio, email, résumé and links, the "What I do" list, skills (add or delete groups and individual skills), the experience timeline, and the admin password.
- The default password is `admin123` until you change it in the editor.
- To use a résumé, put `resume.pdf` next to `index.html`.
- To change the accent colour, edit `--accent` in `:root` and in `[data-theme="dark"]`.

## Admin mode
Click the 🔒 icon in the navbar and enter the password. While logged in you can:
- add a project with the **+ Add project** button
- **Edit** or **Delete** a project
- move a project with **↑ / ↓**
- feature a project with **⭐ Feature** (featured projects show first)

### Important: how saving works
Projects are saved in **localStorage**, so they live **only in the browser you edited them in**. Visitors to your deployed site will see the 3 sample projects, not your edits. The admin password is also only a soft lock, because anyone can read it in the page source.

To make your projects public, choose one of these:
1. **Quick option:** in the browser console run `copy(localStorage.getItem("portfolio.profile.v1"))` and paste the result over the `PROFILE` object in `index.html`. Then run `copy(localStorage.getItem("portfolio.projects.v1"))` and paste it over `SAMPLE_PROJECTS`. Save and redeploy.
2. **Proper option:** switch to Supabase or Firebase. Only the `Store` object (`getAll`, `saveAll`, `reset`) needs rewriting; a Supabase example is in the comments. Store images in Supabase Storage instead of as data URLs, and use Supabase Auth instead of the hard-coded password.

## Contact form
By default the form opens the visitor's email app. To get real messages, sign up at formspree.io, set
`<form id="contactForm" action="https://formspree.io/f/XXXX" method="POST">`, and delete the `contactForm.onsubmit` handler.

## Deploy for free
- **GitHub Pages:** push this folder to a repo, then go to Settings → Pages → Deploy from branch → `main` / root.
- **Netlify:** drag the folder onto app.netlify.com/drop.
- **Vercel:** run `npx vercel` in this folder.
