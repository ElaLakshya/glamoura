# Glamoura — Delhi Bridal Beauty Booking Platform
### SuperXgen AI Startup Buildathon 2026 · Submission

---

## 🏆 Challenge
**SuperXgen AI Startup Buildathon 2026** — 48-hour online hackathon  
**Category:** City-based Beauty Salon Marketplace  
**Chosen City:** Delhi — Bridal & Luxury Beauty Booking Platform  
**Target Audience:** Women seeking bridal, hair, skin, and beauty services across South, Central, and East Delhi

---

## 🔗 Live Links

| | |
|---|---|
| **Live Website** | `https://glamoura.vercel.app` |
| **Admin Panel** | `https://glamoura.vercel.app` → click Admin tab |
| **Admin Login** | Username: `admin` · Password: `admin` |

---

## 📱 What Is Glamoura?

Glamoura is a full-stack luxury salon discovery and booking platform for Delhi. It lets customers find salons near them on a live interactive map, read reviews, compare services and prices, book appointments instantly, and get AI-powered booking assistance — all from a single page that works on any device.

It also ships with a complete admin dashboard for salon owners and platform managers to manage listings, view bookings, moderate reviews, and monitor platform security in real time.

---

## ✨ Features

### Customer Side
| Feature | Details |
|---------|---------|
| **Live Interactive Map** | Leaflet.js + CartoDB Dark Matter tiles — real Delhi geography, no API key required. Gold custom markers for each salon, green/red open/closed dot, GPS user location pin |
| **12 Curated Salons** | South Delhi (GK, Hauz Khas, Saket), Central Delhi (Connaught Place, Karol Bagh), East Delhi (Preet Vihar, Laxmi Nagar) |
| **Salon Discovery** | Browse by area, filter by badge (Bridal / Luxury / Premium), sort by rating / distance / price, live search |
| **Salon Detail Cards** | Full info — address, hours, phone, GPS distance from your location, services & rates, customer reviews with star ratings |
| **Appointment Booking** | Date picker, time slot, service selection, name & phone — conflict detection prevents double-booking the same time slot |
| **My Bookings** | View and cancel all active bookings in one place, with booking reference numbers |
| **AI Booking Assistant** | Powered by Groq (llama-3.3-70b-versatile) — chat to find salons, book appointments, cancel bookings, get recommendations. Understands natural language like "Book Lakmé for Saturday 3pm for my wedding look" |
| **Directions** | One tap opens Google Maps navigation to any salon's exact GPS coordinates |
| **PWA** | Installable as a mobile app — "Add to Home Screen" on both Android and iOS |
| **Mobile Responsive** | Fully responsive across all screen sizes — phone, tablet, desktop |

### Admin Panel
| Feature | Details |
|---------|---------|
| **Secure Login** | Username/password with shake animation on failure, failed attempt counter, session timer |
| **Dashboard** | Live stats (total salons, open now, active bookings, security alerts), area bar chart, badge breakdown, activity log |
| **Salon Management** | Add, edit, delete salons. Toggle open/closed status live. Full form with GPS coordinates, specialities, services & pricing |
| **Booking Management** | View all customer bookings in a table, cancel any booking, export all bookings as CSV |
| **Review Moderation** | Approve or remove customer reviews |
| **Promotions** | Create, activate/deactivate, and delete promotional offers |
| **Site Banners** | Toggle customer-facing announcement banners on/off |
| **Security Log** | Real-time log of all admin actions, login attempts, booking events, and system events |
| **Settings** | Toggle AI assistant, booking system, PWA banner, maintenance mode |

---

## 🤖 AI Integration

The AI assistant is built on **Groq's API** using the **llama-3.3-70b-versatile** model — one of the fastest LLMs available, with near-instant response times.

The system prompt dynamically includes:
- All 12 salon listings with real-time data (open/closed status, services, prices, ratings)
- The user's current active bookings
- Today's date for scheduling context

The AI can:
- Recommend salons based on service type, area preference, or budget
- Book appointments end-to-end by parsing structured `ACTION:{}` JSON from its own response
- Cancel existing bookings
- Detect and warn about scheduling conflicts
- Answer questions about any salon's services, hours, or location

---

## 🗺️ Salons Listed

| # | Salon | Area | Badge | Rating |
|---|-------|------|-------|--------|
| 1 | Lakmé Salon | South Delhi · GK-I | Bridal | 4.8 ★ |
| 2 | Jean-Claude Biguine | South Delhi · Saket | Luxury | 4.6 ★ |
| 3 | Schwarzkopf Professional | South Delhi · Hauz Khas | Premium | 4.5 ★ |
| 4 | Shahnaz Husain Beauty | Central Delhi · CP | Bridal | 4.9 ★ |
| 5 | Enrich Salon | Central Delhi · Karol Bagh | Premium | 4.4 ★ |
| 6 | Purple Panache | East Delhi · Preet Vihar | Premium | 4.3 ★ |
| 7 | Truefitt & Hill | Central Delhi · CP | Luxury | 4.7 ★ |
| 8 | Glam Studios | East Delhi · Laxmi Nagar | Premium | 4.2 ★ |
| 9 | VLCC Wellness | South Delhi · Saket | Premium | 4.5 ★ |
| 10 | Aarav Salon & Spa | East Delhi · Preet Vihar | Bridal | 4.4 ★ |
| 11 | TONI&GUY | South Delhi · GK-II | Luxury | 4.6 ★ |
| 12 | Naturals Salon | Central Delhi · Karol Bagh | Premium | 4.3 ★ |

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | Vanilla HTML5, CSS3, JavaScript (ES2022) — zero framework, zero build step |
| **Map** | Leaflet.js 1.9.4 + CartoDB Dark Matter tiles (OpenStreetMap, free, no API key) |
| **AI** | Groq API — llama-3.3-70b-versatile |
| **Fonts** | Google Fonts — Playfair Display (headings) + Inter (body) |
| **Icons** | Tabler Icons webfont |
| **Hosting** | Vercel (static deployment) |
| **PWA** | Web App Manifest + "Add to Home Screen" support |

No Node.js, no database, no build tools required. The entire product is a single `index.html` file.

---

## 🔒 Security Measures

Even as a self-contained frontend, Glamoura implements real security practices:

| Measure | Implementation |
|---------|---------------|
| Admin authentication | Username + password gate with session management |
| Failed login tracking | Counts and logs every failed attempt in the security log |
| Session timer | Live session clock visible in admin topbar |
| Security audit log | Every action (login, booking, salon edit, deletion) is timestamped and logged |
| Input validation | All booking form fields validated before submission |
| Booking conflict detection | Server-side-style conflict check prevents double-booking |
| `noindex` on admin | Admin panel behaviour prevents indexing |
| robots.txt | Instructs crawlers to avoid admin routes |

---

## 📂 Project Structure

```
glamoura/
├── index.html        ← Entire application (customer site + admin panel)
└── vercel.json       ← Vercel deployment config
```

The entire product ships as a **single HTML file** — no dependencies to install, no build process, no server to configure. Open it in any browser and it works.

---

## 🚀 Running Locally

```bash
# Option 1 — just open the file
# Double-click index.html in your file explorer

# Option 2 — local server (recommended, enables all features)
npx serve .
# Open http://localhost:3000
```

---

## 🌐 Deployment (Vercel)

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
cd glamoura
vercel
```

Or drag and drop the `glamoura/` folder at **vercel.com/new**.

---

## 🧪 Demo Guide for Judges

**1. Browse the marketplace**
- Open the live URL
- Scroll through the salon grid on the Discover tab
- Click any salon card to open the full detail modal

**2. Try the live map**
- Click the Map tab in the nav
- Click any gold pin to see a popup
- Use the area filter pills (South Delhi / Central Delhi / East Delhi)
- Click "My Location" to drop your GPS pin

**3. Book an appointment**
- Click any salon → "Book Appointment"
- Fill in name, phone, date, time, service
- Click "Confirm Booking" — see the success state
- Try booking the same slot again — conflict detection triggers

**4. Try the AI assistant**
- Click the gold sparkle button (bottom right)
- Try: *"Find me a bridal salon in South Delhi"*
- Try: *"Book Lakmé Salon for tomorrow at 11am, name is Priya, phone 9810012345"*
- Try: *"Cancel my booking"*

**5. Explore the admin panel**
- Click **Admin** in the top navigation
- Login: `admin` / `admin`
- Dashboard shows live stats and charts
- Go to Salons → Edit any salon, toggle open/closed
- Go to Bookings → see any bookings made on the customer side
- Go to Security Log → see a real-time audit trail of everything

---

## 👤 Built By

**Lakshya** — Independent developer  
Built for SuperXgen AI Startup Buildathon 2026  
*Delhi Bridal Beauty Booking Platform*

---

*Glamoura — Beauty Redefined in Every Borough*
