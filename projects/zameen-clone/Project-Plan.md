# 🏠 Zameen.com Clone — Project Plan

## 1. What is Zameen.com?

Pakistan's biggest property portal. Users search for properties to **buy, rent, or invest** in residential and commercial real estate across cities in Pakistan.

---

## 2. Core Functionalities

### User Side
- [x] **Property Search** — Buy / Rent / Projects tabs
- [x] **City Selection** — Islamabad, Lahore, Karachi, etc.
- [x] **Location Filtering** — Sub-locations within cities
- [x] **Property Type** — Homes, Plots, Commercial
- [x] **Size Filter** — Area in Marla / Kanal / Square Feet
- [x] **Price Range Filter** — Min/Max price slider
- [x] **Bedrooms Filter** — 1, 2, 3, 4, 5+ bedrooms
- [x] **More Filters** — Corner plot, Park facing, Possession status, etc.
- [x] **Property ID Search** — Direct search by listing ID
- [x] **Property Listing Cards** — Price, location, beds, area, photo
- [x] **Property Detail Page** — Full description, photos gallery, specs, map location
- [x] **Map View** — Property locations on map
- [x] **Saved Searches / Favorites** — Save listings
- [x] **Agent Contact** — Inquiry form, call/message agent
- [x] **New Projects** — Developer projects with payment plans

### Tools (Utility Pages)
- [ ] **Home Loan Calculator**
- [ ] **Area Unit Converter** (Marla Kanal Sq Ft)
- [ ] **Land Record Pages**
- [ ] **Construction Cost Calculator**

### Admin / Agency Side
- [x] **Property Listing Form** — Add/edit/delete property
- [x] **Agency Profile** — Agency info, listed properties
- [x] **Titanium Agencies** showcase

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
- [x] Homepage with hero search
- [x] Buy listings with filters
- [x] Property detail page
- [x] Basic auth (email/password)
- [x] Contact agent form

### Phase 2 — Core Features (2-3 weeks)
- [x] Rent listings
- [x] New Projects page
- [x] Favorites / saved searches
- [x] Agent dashboard
- [x] Add property form
- [x] Map view

### Phase 3 — Tools + Polish (1-2 weeks)
- [ ] Home Loan Calculator
- [ ] Area Unit Converter
- [ ] Responsive mobile app-quality UI
- [ ] Performance optimization

### Phase 4 — Scale (ongoing)
- [ ] Admin panel
- [ ] Payment integration
- [ ] Advanced search / AI recommendations
- [ ] Mobile apps (React Native)

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

- [x] Database seeded with sample data (users, agency, properties)
- [x] Authentication flow (register, login, JWT)
- [x] Property listing page (`/buy`) fetches real data
- [x] Property detail page (`/property/[id]`) fetches real data
- [x] Image upload backend route (`/api/upload`) with Cloudinary integration
- [x] Frontend upload helper and API proxy
- [x] Favorites toggle uses centralized API client with JWT
- [x] Dashboard UI with sidebar navigation (Overview, Properties, Favorites, Inquiries, Profile)

### Remaining Tasks
- [ ] Implement Edit Property form (PUT `/api/properties/:id`)
- [ ] Implement Delete Property (DELETE `/api/properties/:id`)
- [ ] Add Map view to property cards (Leaflet integration)
- [ ] Implement Profile update API call
- [ ] Add responsive sidebar collapse on mobile
- [ ] Home Loan Calculator tool
- [ ] Area Unit Converter tool
