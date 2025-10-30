# Deployment Checklist - demo-saas

**Site Domain:** `demo-saas.pages.dev`
**Cloudflare Project:** `demo-saas`
**Deployment Type:** Automatic (GitHub Push)

## Pre-Deployment

- [ ] Hugo version is 0.152.2+ (current: 0.152.2)
- [ ] `baseURL` in `hugo.toml` is correct: `https://demo-saas.pages.dev`
- [ ] All images are optimized
- [ ] `static/_headers` file exists
- [ ] `robots.txt` exists
- [ ] Local build succeeds: `bash .cloudflare/deploy.sh`
- [ ] No console errors

## Cloudflare Pages Setup

- [ ] Repository connected to Cloudflare Pages
- [ ] Build command configured: `hugo --minify --gc`
- [ ] Build output directory: `public`
- [ ] Environment variable set: `HUGO_VERSION=0.152.2`
- [ ] Environment variable set: `HUGO_ENV=production`
- [ ] Project name: `demo-saas`

## Post-Deployment Verification

- [ ] Site loads successfully at `https://demo-saas.pages.dev`
- [ ] Check security headers: `curl -I https://demo-saas.pages.dev`
- [ ] Test all internal links
- [ ] Test responsive design on mobile
- [ ] Verify images load correctly
- [ ] Check Lighthouse score (should be 90+)
- [ ] Verify sitemap is accessible: `/sitemap.xml`
- [ ] Verify robots.txt is accessible: `/robots.txt`

## Commands for Testing

```bash
# Test local build
bash .cloudflare/deploy.sh

# Verify build output
ls -la public/
find public -type f | wc -l

# Check headers file
cat public/_headers
```
