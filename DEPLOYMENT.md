# Cloudflare Pages Deployment Guide - demo-saas

**Live Domain:** `https://demo-saas.pages.dev`

This site is configured for automatic deployment on Cloudflare Pages.

## Quick Start

```bash
git add .
git commit -m "Update demo content"
git push origin main
```

Cloudflare Pages will automatically build and deploy within 1-2 minutes.

## Setup Instructions

### 1. Connect Repository to Cloudflare Pages

1. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. Navigate to **Pages** → **Create a project** → **Connect to Git**
3. Select repository: `MatthewJamisonJS/demo-saas`

### 2. Build Configuration

| Setting | Value |
|---------|-------|
| **Production branch** | `main` |
| **Build command** | `hugo --minify --gc` |
| **Build output directory** | `public` |

### 3. Environment Variables

Add in Cloudflare Pages settings:

```
HUGO_VERSION = 0.152.2
HUGO_ENV = production
```

## Test Build Locally

```bash
bash .cloudflare/deploy.sh
```

## Verification

```bash
curl -I https://demo-saas.pages.dev
```

## Resources

- [Cloudflare Pages Docs](https://developers.cloudflare.com/pages/)
- [Hugo Documentation](https://gohugo.io/documentation/)
