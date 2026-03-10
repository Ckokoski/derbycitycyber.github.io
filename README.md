# Derby City Cyber — Website

Professional website for Derby City Cyber, hosted on GitHub Pages at [derbycitycyber.com](https://derbycitycyber.com).

---

## Setup Instructions

### 1. Create the GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Name the repository: `derbycitycyber.github.io`
3. Set it to **Public**
4. Do NOT initialize with a README (we already have one)
5. Click **Create repository**

### 2. Push This Code to GitHub

```bash
cd derbycitycyber.github.io
git init
git add .
git commit -m "Initial site launch"
git branch -M main
git remote add origin https://github.com/Ckokoski/derbycitycyber.github.io.git
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select **Deploy from a branch**
3. Branch: **main**, folder: **/ (root)**
4. Click **Save**
5. GitHub will show your site URL (initially `https://ckokoski.github.io/derbycitycyber.github.io/`)

### 4. Configure Custom Domain — DNS Records at Namecheap

1. Log into [Namecheap](https://www.namecheap.com/) and go to your domain's **Advanced DNS** settings
2. **Delete** any existing records (parking page records, etc.)
3. Add these **A Records** (point `@` to GitHub Pages IPs):

   | Type | Host | Value | TTL |
   |------|------|-------|-----|
   | A Record | @ | 185.199.108.153 | Automatic |
   | A Record | @ | 185.199.109.153 | Automatic |
   | A Record | @ | 185.199.110.153 | Automatic |
   | A Record | @ | 185.199.111.153 | Automatic |

4. Add a **CNAME Record** for `www`:

   | Type | Host | Value | TTL |
   |------|------|-------|-----|
   | CNAME | www | ckokoski.github.io | Automatic |

5. **Important:** Make sure Namecheap's "Redirect Domain" section is OFF/disabled

### 5. Set Custom Domain in GitHub Pages

1. Go to repo → **Settings** → **Pages**
2. Under **Custom domain**, enter: `derbycitycyber.com`
3. Click **Save**
4. Wait for DNS check to pass (can take up to 24 hours, usually 10-30 minutes)
5. Check **Enforce HTTPS** once the DNS check passes

### 6. Set Up Formspree (Contact Form)

1. Go to [formspree.io](https://formspree.io/) and create a free account
2. Click **New Form** and name it "Derby City Cyber Contact"
3. Copy your form endpoint (looks like `https://formspree.io/f/xAbCdEfG`)
4. In `index.html`, find this line:
   ```html
   <form class="contact-form" action="https://formspree.io/f/PLACEHOLDER" method="POST">
   ```
5. Replace `PLACEHOLDER` with your actual form ID (e.g., `xAbCdEfG`)
6. Commit and push the change

### 7. Verify Everything Works

- [ ] Site loads at `https://derbycitycyber.com`
- [ ] Site loads at `https://www.derbycitycyber.com`
- [ ] HTTPS is working (padlock icon in browser)
- [ ] All navigation links scroll smoothly
- [ ] Contact form submits successfully
- [ ] Site looks good on mobile (test in browser dev tools)
- [ ] Favicon appears in browser tab

---

## File Structure

```
derbycitycyber.github.io/
├── index.html      ← Main website (all sections)
├── style.css       ← All styles (dark theme, responsive)
├── favicon.svg     ← Shield/checkmark favicon
├── CNAME           ← Custom domain config
└── README.md       ← This file
```

## Making Changes

The HTML is well-commented with section markers (`<!-- ============ SECTION NAME ============ -->`). To update text content, edit `index.html` and push to GitHub — changes go live automatically.

---

© 2026 Derby City Cyber
