# Security policy

Kovelo Studio is designed for Vercel deployment with public client-side source code. Never commit credentials, API keys, tokens, private client material, or local environment files.

## Reporting a vulnerability

Please report potential vulnerabilities privately to [kovelostudio@gmail.com](mailto:kovelostudio@gmail.com). Do not include exploit details in a public issue or social post. Include a concise description, affected route or component, reproduction steps, and potential impact.

## Form integrations

The website has no built-in server-side form endpoint. Before setting `VITE_CONTACT_FORM_ENDPOINT`, the chosen server-side endpoint must validate an allowlisted payload, cap field sizes, reject honeypot submissions, rate-limit requests, and keep all provider credentials server-side.

## Scope

Public frontend configuration is not secret. Any variable prefixed with `VITE_` is visible in the browser and must only contain public values.
