# 🏠 Zameen.com Clone — Project Plan

## 1. What is Zameen.com?

Pakistan's biggest property portal. Users search for properties to **buy, rent, or invest** in residential and commercial real estate across cities in Pakistan.

---

## 2. Core Functionalities

### User Side
- [ ] **Property Search** — Buy / Rent / Projects tabs
- [ ] **City Selection** — Islamabad, Lahore, Karachi, etc.
- [ ] **Location Filtering** — Sub-locations within cities
- [ ] **Property Type** — Homes, Plots, Commercial
- [ ] **Size Filter** — Area in Marla / Kanal / Square Feet
- [ ] **Price Range Filter** — Min/Max price slider
- [ ] **Bedrooms Filter** — 1, 2, 3, 4, 5+ bedrooms
- [ ] **More Filters** — Corner plot, Park facing, Possession status, etc.
- [ ] **Property ID Search** — Direct search by listing ID
- [ ] **Property Listing Cards** — Price, location, beds, area, photo
- [ ] **Property Detail Page** — Full description, photos gallery, specs, map location
- [ ] **Map View** — Property locations on map
- [ ] **Saved Searches / Favorites** — Save listings
- [ ] **Agent Contact** — Inquiry form, call/message agent
- [ ] **New Projects** — Developer projects with payment plans

### Tools (Utility Pages)
- [ ] **Home Loan Calculator**
- [ ] **Area Unit Converter** (Marla ↔ Kanal ↔ Sq Ft)
- [ ] **Land Record Pages**
- [ ] **Construction Cost Calculator**

### Admin / Agency Side
- [ ] **Property Listing Form** — Add/edit/delete property
- [ ] **Agency Profile** — Agency info, listed properties
- [ ] **Titanium Agencies** showcase

---

## 3. Tech Stack

### Proposed
| Layer | Technology |
|-------|-----------|
| **Frontend** | Next.js 14 (App Router) + TypeScript |
| **Styling** | Tailwind CSS + Shadcn/UI |
| **State** | Zustand / React Query |
| **Maps** | Leaflet / Mapbox GL |
| **Backend** | Node.js + Express or Fastify |
| **Database** | PostgreSQL + Prisma ORM |
| **Auth** | JWT + bcrypt |
| **File Storage** | Cloudinary (images) |
| **Deployment** | Docker + VPS or Railway/Render |
| **Domain** | .com (similar to Zameen) |

---

## 4. Database Schema (High-Level)

```
users           → buyers, agents, admins
agencies        → agency profiles, verified status
properties      → title, price, type, city, location, specs, description
property_images → gallery
projects        → new housing projects
favorites       → user saved properties
inquiries       → messages to agents
```

---

## 5. Pages

| Page | Route |
|------|-------|
| Homepage | `/` |
| Buy Properties | `/buy` |
| Rent Properties | `/rent` |
| New Projects | `/projects` |
| Property Detail | `/property/[id]` |
| Agent Profile | `/agent/[id]` |
| Add Property | `/add-property` |
| Map Search | `/map` |
| Tools | `/tools/loan-calculator`, `/tools/area-converter` |
| Login / Register | `/auth` |

---

## 6. UI/UX Direction

- Clean, modern, mobile-first
- Card-based listings with thumbnail photos
- Sticky filter sidebar on desktop, bottom sheet on mobile
- Map view toggle alongside list view
- Fast search with real-time filtering
- Pakistani real estate specific: Marla/Kanal units, PKR currency, city-based

---

## 7. Phases

### Phase 1 — MVP (2-3 weeks)
- Homepage with hero search
- Buy listings with filters
- Property detail page
- Basic auth (email/password)
- Contact agent form

### Phase 2 — Core Features (2-3 weeks)
- Rent listings
- New Projects page
- Favorites / saved searches
- Agent dashboard
- Add property form
- Map view

### Phase 3 — Tools + Polish (1-2 weeks)
- Home Loan Calculator
- Area Unit Converter
- Responsive mobile app-quality UI
- Performance optimization

### Phase 4 — Scale (ongoing)
- Admin panel
- Payment integration
- Advanced search / AI recommendations
- Mobile apps (React Native)

---

## 8. Zameen.com Pages Scraped

- Homepage: Search bar, Buy/Rent/Projects tabs, category chips, popular locations
- Buy Listing: Filters (price, area, beds, type), property cards
- Property Detail: Price, specs, description, photos, agent contact
- New Projects: Project listings with developer info
- Rent Listing: Similar to Buy with rental-specific filters
- Tools: Loan calculator, area converter, land records

---

## 9. Notes

- Zameen uses dynamic JS rendering — our Next.js app will use ISR (Incremental Static Regeneration) for SEO
- Images: use lazy loading + WebP optimization
- Currency: PKR (Lakh / Crore formatting)
- Area units: Marla (most popular), Kanal, Square Foot

## 10. Progress

- ✅ Database seeded with sample data (users, agency, properties)
- ✅ Authentication flow (register, login, JWT)
- ✅ Property listing page (`/buy`) fetches real data
- ✅ Property detail page (`/property/[id]`) fetches real data
- ✅ Image upload backend route (`/api/upload`) with Cloudinary integration
- ✅ Frontend upload helper and API proxy
- ✅ Favorites toggle uses centralized API client with JWT
