# LocalLoop — Phone-ready local marketplace

A real full-stack, mobile-first PWA starter for local products/services. It has a React/Vite frontend, Express API, Prisma/SQLite database, secure server-side sessions, customer/seller/admin roles, cart and order flow, seeded demo accounts, responsive UI and PWA install support.

## Run on a laptop
1. Install Node.js 20+.
2. Extract this folder.
3. Copy `.env.example` to `.env` and set a long `SESSION_SECRET`.
4. Run `npm install`.
5. Run `npm run db:push`.
6. Run `npm run db:seed`.
7. Run `npm run dev`.
8. Open `http://localhost:5173`.

## Use from your phone on the same Wi-Fi
Run `npm run dev` on the laptop. Find the laptop's LAN IPv4 address (Windows: `ipconfig`). On the phone, open `http://LAPTOP-IP:5173`. Both devices must be on the same Wi-Fi. If Windows Firewall asks, allow Node.js on Private networks.

## Production deployment
Build with `npm run build`; run with `npm start`. Set `NODE_ENV=production`, a strong `SESSION_SECRET`, and a persistent database volume. For production scale, change Prisma's datasource from SQLite to PostgreSQL and use a managed database. The current app is deliberately deployable as one web service for simple hosting.

## Demo accounts
- Customer: customer@localloop.local / Demo@12345
- Seller: seller@localloop.local / Demo@12345
- Admin: admin@localloop.local / Demo@12345

## Security foundations
Passwords are bcrypt-hashed. Authentication uses server-side sessions in HTTP-only cookies; no auth token is stored in localStorage. API inputs are validated with Zod and role checks protect seller/admin endpoints.

## Scope note
This package is a working MVP foundation, not a finished commercial marketplace. Payment gateway, SMS/email OTP provider, maps/geocoding, image storage/CDN, advanced coupons/offers, service booking workflows, moderation, and production observability require external providers/configuration before a public launch.
