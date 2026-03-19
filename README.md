# TOTPBOX Documentation

> Comprehensive documentation for the TOTPBOX TOTP authentication platform.

[![Website](https://img.shields.io/badge/website-totpbox.com-blue)](https://totpbox.com)
[![Back to Meta Repo](https://img.shields.io/badge/meta-totpbox%2Ftotpbox-purple)](https://github.com/TOTPBOX/totpbox)

---

## Table of Contents

- [Getting Started](#getting-started)
- [Setup Guides](#setup-guides)
- [API Reference](#api-reference)
- [Changelog](#changelog)
- [FAQ](#faq)
- [Support](#support)

---

## Getting Started

TOTPBOX provides TOTP (Time-based One-Time Password) authentication compliant with [RFC 6238](https://datatracker.ietf.org/doc/html/rfc6238) and [RFC 4226](https://datatracker.ietf.org/doc/html/rfc4226).

### Prerequisites

- An active TOTPBOX account (sign up at [totpbox.com](https://totpbox.com))
- Your preferred platform: Web or API

---

## Setup Guides

### Web App Setup

1. Log in to your dashboard at [totpbox.com](https://totpbox.com)
2. Navigate to **Settings > Security > Two-Factor Authentication**
3. Scan the QR code with any TOTP-compatible authenticator app
4. Enter the 6-digit code to confirm and enable 2FA

---

## API Reference

> **Note:** The TOTPBOX REST API is currently under development and not yet publicly available.
> This section documents the planned API design. Endpoints will be activated when the API launches.
> Subscribe to releases or watch this repo to be notified.

### Planned Base URL

```
https://api.totpbox.com/v1
```

### Authentication

All API requests will require a Bearer token in the `Authorization` header.

### Planned Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/totp/generate` | Generate a new TOTP secret |
| `POST` | `/totp/verify` | Verify a TOTP token |
| `GET` | `/totp/qr` | Get QR code for secret |
| `DELETE` | `/totp/{id}` | Revoke a TOTP secret |
| `GET` | `/account/status` | Check account/API status |

### Planned Rate Limits

| Plan | Requests/min |
|---|---|
| Free | 30 |
| Pro | 300 |
| Enterprise | Unlimited |

---

## Changelog

### v0.1.0 — 2026-03-19 (Private Beta)

- Platform infrastructure set up
- Web dashboard (early access)
- TOTP generation and verification — web interface only
- REST API and mobile apps are in development

---

## FAQ

**Q: Which authenticator apps are compatible?**  
A: Any RFC 6238-compliant authenticator works, including Google Authenticator, Authy, 1Password, Bitwarden, and others.

**Q: What hash algorithm does TOTPBOX use?**  
A: HMAC-SHA1 by default (RFC 4226 standard), with SHA-256 and SHA-512 planned for future releases.

**Q: Is there a public API available?**  
A: The REST API is currently in development. See the [API Reference](#api-reference) section for planned endpoints.

**Q: How do I report a security vulnerability?**  
A: See [SECURITY.md](https://github.com/TOTPBOX/security/blob/main/SECURITY.md) — please do **not** open a public issue.

---

## Support

- **Email:** [totpbox@gmail.com](mailto:totpbox@gmail.com)
- **Issues:** [github.com/TOTPBOX/totpbox/issues](https://github.com/TOTPBOX/totpbox/issues)
- **Website:** [totpbox.com](https://totpbox.com)
- **X / Twitter:** [@totpbox](https://x.com/totpbox)

---

<sub>&copy; 2026 TOTPBOX. See [LICENSE](./LICENSE) for documentation license terms.</sub>
