# SignalHarbor Setup Guide

## Quick Start (5 minutes)

### 1. Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `signalharbor`
3. Visibility: **Public**
4. Do NOT initialize with README
5. Click **Create repository**

### 2. Push Files to GitHub

Open terminal and run:

```bash
cd C:\Users\chazh\OneDrive\Documents\signal-scout

git config user.name "chazhyseni"
git config user.email "chaz.hyseni@gmail.com"

git init
git add .
git commit -m "Initial commit - SignalHarbor"
git branch -M main
git remote add origin https://github.com/chazhyseni/signalharbor.git
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to: `github.com/chazhyseni/signalharbor/settings/pages`
2. Under **Custom domain**, enter: `signalharbor.org`
3. Click **Save**
4. Wait 24-48 hours for DNS propagation
5. Once verified, check **Enforce HTTPS**

### 4. Buy Domain

Purchase at one of these registrars:

| Registrar | URL |
|-----------|-----|
| Namecheap | https://namecheap.com |
| Porkbun | https://porkbun.com |
| Cloudflare | https://cloudflare.com |

Search for: **signalharbor.org**

### 5. Configure DNS

At your domain registrar, add these records:

| Type | Host/Name | Value |
|------|-----------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | chazhyseni.github.io |

---

## Stripe Payment Setup

### What You Need

1. **Stripe Account**: Sign up at [dashboard.stripe.com](https://dashboard.stripe.com)
2. **Business Info**:
   - Business name: SignalHarbor (or your legal name for sole proprietor)
   - Email: chaz.hyseni@gmail.com
   - Business type: Individual/Sole Proprietor (to start)
   - Address: Your business address
   - SSN or EIN (for US)

### Create Products & Payment Links

1. Go to **Products** → **Add Product**

**Product 1: Starter Plan**
```
Name: SignalHarbor Starter
Price: $99 USD / month (recurring)
Description: Up to 5 data sources, daily reports, basic sentiment
```

**Product 2: Professional Plan**
```
Name: SignalHarbor Professional
Price: $299 USD / month (recurring)
Description: Up to 25 data sources, hourly reports, real-time alerts
```

**Product 3: Enterprise**
```
Name: SignalHarbor Enterprise
Price: Custom (use contact form, no payment link needed)
```

2. For each product, click **Create Payment Link**
3. Copy the URL (looks like: `https://buy.stripe.com/xxxxx`)

### Update Website with Stripe Links

In `index.html`, replace these placeholders:

```html
<!-- Starter Plan Button -->
href="https://buy.stripe.com/YOUR_STARTER_LINK"

<!-- Professional Plan Button -->
href="https://buy.stripe.com/YOUR_PRO_LINK"

<!-- CTA Section Button -->
href="https://buy.stripe.com/YOUR_STARTER_LINK"
```

Search for `buy.stripe.com/test_` and replace with your actual links.

---

## Post-Launch Checklist

- [ ] Domain purchased (signalharbor.org)
- [ ] DNS records configured
- [ ] GitHub Pages enabled with custom domain
- [ ] HTTPS enforced
- [ ] Stripe account created
- [ ] Products created in Stripe
- [ ] Payment links added to website
- [ ] Test checkout flow works
- [ ] Update social media handles (@signalharbor)
- [ ] Set up hello@signalharbor.org email forwarding

---

## Optional: Email Forwarding

Set up email forwarding so `hello@signalharbor.org` forwards to `chaz.hyseni@gmail.com`:

1. In your domain registrar, add MX records for email forwarding
2. Or use a service like [ImprovMX](https://improvmx.com) (free)

---

## Need Help?

- GitHub Pages docs: https://docs.github.com/en/pages
- Stripe docs: https://stripe.com/docs
- DNS propagation check: https://dnschecker.org
