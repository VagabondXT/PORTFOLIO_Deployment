=========================================
  Mohammad Bin Tarique — Portfolio Site
  README & Deployment Guide
=========================================

FILE STRUCTURE
--------------
portfolio/
└── index.html       ← The entire website (single self-contained file)

All CSS, JavaScript, and content are embedded in index.html.
No build tools, no dependencies, no npm — just open the file.


HOW TO CUSTOMIZE CONTENT
--------------------------

1. YOUR EMAIL
   Search for: md.modhu210s@gmail.com
   Replace with your actual email. Appears in two places:
   - The contact link button
   - The footer

2. YOUR LINKEDIN URL
   Search for: href="https://linkedin.com"
   Replace with your full LinkedIn profile URL:
   e.g., https://www.linkedin.com/in/your-username

3. YOUR GITHUB URL
   Search for: href="https://github.com"
   Replace with your GitHub profile URL:
   e.g., https://github.com/your-username

4. JOB DATES & COMPANY NAMES
   Search for each company name (MetaMix3D, Lilipur Digital, EDGE) to
   find and update the timeline section with accurate dates or details.

5. AVAILABILITY BADGE (Hero Section)
   Change "Available for opportunities in Europe" to whatever suits your
   current situation. It's in the <div class="hero-badge"> tag.

6. CONTACT FORM (Making it functional)
   The form currently shows a success message on submit but doesn't
   actually send email. To make it work:

   Option A — Formspree (free, easy):
     1. Sign up at https://formspree.io
     2. Create a new form and get your endpoint URL
     3. Replace the handleSubmit() function in the <script> section with:
        
        async function handleSubmit() {
          const form = {
            name: document.getElementById('name').value,
            email: document.getElementById('email').value,
            subject: document.getElementById('subject').value,
            message: document.getElementById('message').value,
          };
          const res = await fetch('https://formspree.io/f/YOUR_ID', {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(form),
          });
          if (res.ok) { /* show success */ }
        }

   Option B — Netlify Forms (if hosting on Netlify):
     Add netlify attribute to the form and remove the JS handler.


DEPLOYMENT INSTRUCTIONS
------------------------

OPTION 1 — GitHub Pages (Free, Recommended)
  1. Create a new GitHub repository named: yourusername.github.io
  2. Upload index.html to the root of that repository
  3. Go to Settings → Pages → set source to "main" branch
  4. Your site will be live at: https://yourusername.github.io

OPTION 2 — Netlify (Free, Drag & Drop)
  1. Go to https://app.netlify.com
  2. Drag the "portfolio" folder onto the Netlify dashboard
  3. Your site is live instantly with a netlify.app domain
  4. You can connect a custom domain in settings

OPTION 3 — Vercel (Free)
  1. Go to https://vercel.com
  2. Import from GitHub or drag & drop
  3. Deploy with one click

CUSTOM DOMAIN
  Once deployed, you can connect a custom domain like:
  mohammadtarique.com or tarique.dev
  Both Netlify and GitHub Pages support this for free.


FONTS
------
The site loads two Google Fonts:
- Syne (headings) — bold, editorial, distinctive
- Outfit (body) — clean, modern, highly readable

These are loaded from Google's CDN. If you need an offline/self-hosted
version, download the fonts from fonts.google.com and update the
@font-face declarations in the <style> section.


PERFORMANCE NOTES
------------------
- Single file: zero external CSS/JS dependencies
- Canvas animation auto-reduces particle count on smaller screens
- Images: none used (intentional — keeps load time near-instant)
- Fonts: only 2 Google Fonts families (minimal FOUT)
- Estimated PageSpeed score: 90+ on mobile, 95+ on desktop


ACCESSIBILITY
--------------
- Semantic HTML5 (section, nav, footer, h1/h2, ul/li)
- Color contrast ratios meet WCAG AA on all text
- Keyboard navigable (standard HTML links and buttons)
- All interactive elements have focus styles via browser defaults


Good luck with your Erasmus applications and European job search!
This site was built to tell your story powerfully. Go make it yours.

=========================================
