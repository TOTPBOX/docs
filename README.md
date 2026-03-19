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
- Your preferred platform: Web, iOS, Android, or API

---

## Setup Guides

### Web App Setup

1. Log in to your dashboard at [totpbox.com](https://totpbox.com)
2. Navigate to **Settings > Security > Two-Factor Authentication**
3. Scan the QR code with any TOTP-compatible authenticator app
4. Enter the 6-digit code to confirm and enable 2FA

### API Setup

```bash
# Generate a TOTP secret
POST https://api.totpbox.com/v1/totp/generate
Authorization: Bearer <YOUR_API_KEY>
Content-Type: application/json

{
  "account": "user@example.com",
  "issuer": "YourApp",
  "digits": 6,
  "period": 30
}
```

**Response:**
```json
{
  "secret": "BASE32ENCODEDSECRET",
  "otpauth_url": "otpauth://totp/YourApp:user@example.com?secret=...",
  "qr_code_url": "https://api.totpbox.com/v1/qr/..."
}
```

### Verify a TOTP Code

```bash
POST https://api.totpbox.com/v1/totp/verify
Authorization: Bearer <YOUR_API_KEY>
Content-Type: application/json

{
  "secret": "BASE32ENCODEDSECRET",
  "token": "123456"
}
```

---

## API Reference

### Base URL

```
https://api.totpbox.com/v1
```

### Authentication

All API requests require a Bearer token in the `Authorization` header.

### Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/totp/generate` | Generate a new TOTP secret |
| `POST` | `/totp/verify` | Verify a TOTP token |
| `GET` | `/totp/qr` | Get QR code for secret |
| `DELETE` | `/totp/{id}` | Revoke a TOTP secret |
| `GET` | `/account/status` | Check account/API status |

### Rate Limits

| Plan | Requests/min |
|---|---|
| Free | 30 |
| Pro | 300 |
| Enterprise | Unlimited |

---

## Changelog

### v1.0.0 — 2026-03-19

- Initial public release
- TOTP generate & verify endpoints
- QR code generation
- Web dashboard
- iOS & Android apps

---

## FAQ

**Q: Which authenticator apps are compatible?**  
A: Any RFC 6238-compliant authenticator works, including Google Authenticator, Authy, 1Password, Bitwarden, and others.

**Q: What hash algorithm does TOTPBOX use?**  
A: HMAC-SHA1 by default (RFC 4226 standard), with SHA-256 and SHA-512 options available on Pro and Enterprise plans.

**Q: How do I report a security vulnerability?**  
A: See [SECURITY.md](https://github.com/TOTPBOX/security/blob/main/SECURITY.md) — please do **not** open a public issue.

---

## Support

- **Email:** [totpbox@gmail.com](mailto:totpbox@gmail.com)
- **Issues:** [github.com/TOTPBOX/totpbox/issues](https://github.com/TOTPBOX/totpbox/issues)
- **Website:** [totpbox.com](https://totpbox.com)
- **X / Twitter:** [@totpbox](https://x.com/totpbox)

---

<sub>&copy; 2026 TOTPBOX. Documentation is licensed under CC BY 4.0.</sub>
