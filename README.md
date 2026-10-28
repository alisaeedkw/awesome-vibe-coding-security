# Awesome Vibe-Coding Security [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Curated resources for securing apps built with AI tools — Lovable, Bolt, v0, Cursor, Replit, and the Supabase and Firebase backends behind them.

AI builders optimize for "it works," not "it's safe," and the two are not the same thing. A weekend app can ship with a database anyone can read, a live API key sitting in the page source, or no security headers at all. This list collects the guides, references, and tools that help you find those problems and fix them, no security background required.

## Contents

- [The core risk: exposed databases](#the-core-risk-exposed-databases)
- [By platform](#by-platform)
- [Secrets and API keys](#secrets-and-api-keys)
- [HTTP security headers](#http-security-headers)
- [Transport and email](#transport-and-email)
- [Dependencies and supply chain](#dependencies-and-supply-chain)
- [Tools](#tools)
- [Standards and learning](#standards-and-learning)
- [Related resources](#related-resources)

## The core risk: exposed databases

The most common leak in AI-built apps is a database table with row-level security turned off. When RLS is off, the public "anon" key that ships in your front-end can read that table directly, so a logged-out stranger can pull your users table with a two-line fetch.

- [CVE-2025-48757 explained](https://www.bleek.dev/cve-2025-48757) - The Lovable and Supabase RLS leak, how it works and how to check yours.
- [Supabase Row Level Security](https://supabase.com/docs/guides/database/postgres/row-level-security) - Official guide to enabling RLS and writing policies.
- [Firebase Security Rules](https://firebase.google.com/docs/rules) - Access-control rules for Firestore and Realtime Database.
- [OWASP Broken Access Control](https://owasp.org/Top10/A01_2021-Broken_Access_Control/) - The number-one web risk, and the category this leak falls under.

## By platform

Security notes and common footguns per builder:

- [Lovable security](https://www.bleek.dev/lovable-security) - Risks and fixes for apps built with Lovable.
- [Supabase security](https://www.bleek.dev/supabase-security) - Locking down the most common vibe-coding backend.
- [Firebase security](https://www.bleek.dev/firebase-security) - Rules and pitfalls for Firestore and Realtime Database.
- [Bolt security](https://www.bleek.dev/bolt-security) - What to check on Bolt.new apps.
- [v0 security](https://www.bleek.dev/v0-security) - Notes for apps generated with v0.
- [Cursor security](https://www.bleek.dev/cursor-security) - Guardrails for Cursor-built projects.
- [Replit security](https://www.bleek.dev/replit-security) - Common exposures on Replit deployments.

## Secrets and API keys

- [GitHub Secret Scanning](https://docs.github.com/en/code-security/secret-scanning/about-secret-scanning) - Detects committed credentials across supported providers.
- [Stripe API keys](https://docs.stripe.com/keys) - Which keys are safe for the client and which must stay server-side.
- [OWASP Secrets Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html) - How to store and rotate credentials properly.
- [jwt.io](https://jwt.io/) - Decode a JWT to see what a token actually exposes.

## HTTP security headers

- [MDN: Content-Security-Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) - The reference for the most important header.
- [OWASP Secure Headers Project](https://owasp.org/www-project-secure-headers/) - What each security header does and sensible defaults.
- [OWASP CSP Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html) - Practical guidance for writing a policy that holds.

## Transport and email

- [Qualys SSL Labs](https://www.ssllabs.com/ssltest/) - Deep TLS and certificate grader for any hostname.
- [Mozilla HTTP Observatory](https://developer.mozilla.org/en-US/observatory) - Free header and TLS scorecard.
- [DMARC overview](https://dmarc.org/overview/) - How SPF, DKIM, and DMARC stop email spoofing.

## Dependencies and supply chain

- [npm audit](https://docs.npmjs.com/cli/commands/npm-audit) - Flags known vulnerabilities in your Node dependencies.
- [GitHub Dependabot](https://docs.github.com/en/code-security/dependabot) - Automated dependency and security updates.
- [OSV](https://osv.dev/) - A queryable database of vulnerabilities across open-source ecosystems.

## Tools

- [bleek scanner](https://www.bleek.dev/scan) - Runs 26 checks against a live URL, no signup.
- [Security headers checker](https://www.bleek.dev/tools/security-headers) - Grades the response headers on any page.
- [SSL / TLS checker](https://www.bleek.dev/tools/ssl-checker) - Certificate and protocol check for a hostname.
- [Email security checker](https://www.bleek.dev/tools/email-security) - Verifies SPF, DKIM, and DMARC records.
- [rooGBotVC](https://vc.roogbotai.com) - Free read-only scan of a live app for leaked keys, open .env and .git files, missing security headers and SEO gaps, with no account needed.
- [Have I Been Pwned](https://haveibeenpwned.com/) - Checks whether an email has appeared in a known breach.
- [Pwned Passwords](https://haveibeenpwned.com/Passwords) - Checks a password against billions of breached credentials.

## Standards and learning

- [OWASP Top 10](https://owasp.org/www-project-top-ten/) - Web application security risks.
- [OWASP API Security Top 10](https://owasp.org/www-project-api-security/) - Risks specific to the APIs behind your app.
- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/) - Practical, per-topic security guidance.
- [OWASP Web Security Testing Guide](https://owasp.org/www-project-web-security-testing-guide/) - How professionals test an app end to end.
- [MDN Web Security](https://developer.mozilla.org/en-US/docs/Web/Security) - Headers, CORS, and the browser security model.
- [MITRE CWE](https://cwe.mitre.org/) - The catalog of software weakness types findings map to.

## Related resources

- [Vibe-Coding Security Checklist](https://github.com/alisaeedkw/vibe-coding-security-checklist) - A pre-launch checklist that puts this list into practice.
- [Awesome Security](https://github.com/sbilly/awesome-security) - A broad collection of security tools and resources.
- [Awesome AppSec](https://github.com/paragonie/awesome-appsec) - Resources for learning application security.
- [Awesome Web Security](https://github.com/qazbnm456/awesome-web-security) - A curated list of web security materials and research.

## Contributing

Pull requests are welcome. Add resources that are genuinely useful and specific to AI-built apps, keep each entry to one line, and place it in the right section. See [CONTRIBUTING.md](CONTRIBUTING.md) for the format. Please do not add low-quality or purely promotional links.

---

Maintained by the team at [bleek.dev](https://www.bleek.dev) — we find the security leaks in vibe-coded apps.
