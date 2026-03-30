# Deployment Guide

## GitHub Pages Setup

### 1. Push to GitHub

Open terminal in this folder:

```bash
cd C:\Users\chazh\OneDrive\Documents\GitHub\signalharbor

git config user.name "chazhyseni"
git config user.email "chaz.hyseni@gmail.com"

git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/chazhyseni/signalharbor.git
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to `github.com/chazhyseni/signalharbor/settings/pages`
2. Under **Custom domain**, enter: `signalharbor.org`
3. Click **Save**

### 3. Configure DNS (Squarespace)

In your Squarespace domain settings:

| Type | Host | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | chazhyseni.github.io |

Wait 24-48 hours for DNS propagation, then enable HTTPS in GitHub Pages settings.

---

## Local Testing

Just open `index.html` in your browser. No build step required.

```bash
open index.html
```
