# Security Policy

## Reporting a Vulnerability

We take security seriously. If you discover a security vulnerability in this project, please report it responsibly by emailing security@demo-saas.pages.dev instead of using the public issue tracker.

Please include the following information in your report:

- Description of the vulnerability
- Steps to reproduce the issue
- Potential impact
- Suggested fix (if available)

We will acknowledge your report within 48 hours and work to provide a fix as soon as possible.

## Security Measures

This project implements the following security best practices:

### Content Security Policy (CSP)
- Strict CSP headers prevent XSS attacks
- Whitelist approach for all resource loading
- Configured in `static/_headers`

### HTTP Security Headers
- **X-Frame-Options**: SAMEORIGIN prevents clickjacking
- **X-Content-Type-Options**: nosniff prevents MIME sniffing
- **X-XSS-Protection**: 1; mode=block provides XSS protection
- **Referrer-Policy**: strict-origin-when-cross-origin protects privacy
- **Permissions-Policy**: Strict restrictions on sensitive APIs (geolocation, microphone, camera)

### Code Security
- **Unsafe HTML Disabled**: Goldmark renderer configured with `unsafe = false`
- **No inline scripts**: All functionality uses safe, external scripts
- **Regular dependency updates**: Hugo modules and theme updates reviewed

### Data Protection
- **No sensitive data in repository**: Environment files and API keys excluded
- **Comprehensive .gitignore**: Prevents accidental exposure of sensitive files
- **HTTPS enforcement**: All resources loaded over HTTPS

## Supported Versions

| Version | Supported          |
|---------|-------------------|
| 1.0.x   | Supported         |
| < 1.0   | Not supported     |

## Security Updates

Security patches are released as needed. Users are encouraged to:

1. Keep Hugo updated to the latest version
2. Regularly update theme dependencies: `hugo mod get -u`
3. Review and apply security header recommendations
4. Monitor GitHub for security advisories

## Contact

For security concerns, please contact: security@demo-saas.pages.dev

---

Last updated: 2025-10-30
