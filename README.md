
# NeonCovenant Full Stack Platform

A secure, modular, and production-ready platform to generate high-fidelity financial documents using GANs, powered by Flask, Firebase Auth, Stripe/Coinbase integration, and a full observability stack.

---

## Overview

This repository powers `neoncovenant.com` and includes:

- **API** – Flask GAN generator + Stripe/Coinbase payment + Firebase token validation
- **Portal** – SvelteKit UI with Firebase login + live doc previews
- **Admin** – Secure Firebase-protected admin panel for logs
- **Finder** – Internal tool for searching document/account data
- **Monitoring** – Grafana, Prometheus, Loki observability
- **Cloudflare Zero Trust** – Secured access via tunnels

---

## Features

- **GAN-powered Document Generation**
- **Secure Token Auth via Firebase**
- **Stripe + Crypto Payment Verification**
- **Cloudflare Tunnel Deployment**
- **Real-time Monitoring with Grafana**
- **Dockerized Services + GitHub CI/CD**

---

## Tech Stack

| Layer        | Tools/Frameworks                                 |
|--------------|--------------------------------------------------|
| Frontend     | SvelteKit, Firebase Auth                         |
| Backend API  | Flask, Keras (TensorFlow), Stripe, Coinbase      |
| Database     | Firebase Firestore (external)                    |
| DevOps       | Docker, Docker Compose, GitHub Actions           |
| Monitoring   | Grafana, Prometheus, Loki                        |
| Security     | Cloudflare Access, Firebase Token, HTTPS         |

---

## Local Development (Staging)

```bash
# Clone and enter the directory
git clone https://github.com/JoftheV/neoncovenant-full-stack.git
cd neoncovenant-full-stack

# Add secrets to .env (see DEPLOYMENT_GUIDE.md)
cp .env.example .env  # and fill in your keys

# Build and run the stack
docker-compose -f docker-compose.full.yml up --build -d
```

Then visit:
- `http://localhost:5000` – Flask API
- `http://localhost:5173` – Portal
- `http://localhost:3001` – Admin Panel
- `http://localhost:3002` – Finder
- `http://localhost:3003` – Grafana

---

## Production Deployment

See [`DEPLOYMENT_GUIDE.md`](./DEPLOYMENT_GUIDE.md) for full instructions.

- Launch with `cloudflared`
- Connect Firebase + Stripe
- Lock down access with Cloudflare Zero Trust
- Set CI/CD in GitHub Actions

---

## Subdomains

| Subdomain               | Purpose                         |
|-------------------------|----------------------------------|
| api.neoncovenant.com    | API + GAN generation             |
| portal.neoncovenant.com | Public UI for users              |
| admin.neoncovenant.com  | Admin dashboard (protected)      |
| finder.neoncovenant.com | Internal lookup tool             |
| metrics.neoncovenant.com| Grafana observability dashboard  |

---

## License

© 2025 Neon Covenant Inc. | All Rights Reserved.
