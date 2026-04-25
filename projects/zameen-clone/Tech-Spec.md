# 🏠 Zameen Clone — Tech Spec

## Stack Details

### Frontend
- **Next.js 14** — App Router, Server Components, ISR for SEO
- **TypeScript** — strict mode
- **Tailwind CSS** — utility-first, responsive
- **Shadcn/UI** — accessible component primitives
- **React Query (TanStack Query)** — server state, caching, pagination
- **Zustand** — client state (filters, UI state)
- **Leaflet** — open-source map (no API key needed for MVP)
- **next/image** — optimized images

### Backend
- **Node.js + Express** — REST API
- **Prisma** — ORM (type-safe queries, migrations)
- **PostgreSQL** — primary database
- **JWT (jsonwebtoken)** — stateless auth
- **bcryptjs** — password hashing
- **Zod** — request validation
- **Cloudinary** — image upload + CDN
- **multer** — file upload handling

### DevOps
- **Docker + Docker Compose** — local dev, production container
- **GitHub Actions** — CI/CD pipeline
- **Railway / Render / VPS** — deployment target
- **Sentry** — error tracking

---

## API Design

### Auth
```
POST /api/auth/register      → create account
POST /api/auth/login         → get JWT
GET  /api/auth/me            → current user
```

### Properties
```
GET  /api/properties          → list (paginated, filtered)
GET  /api/properties/:id      → detail
POST /api/properties          → create (agent only)
PUT  /api/properties/:id      → update (owner only)
DELETE /api/properties/:id   → delete (owner only)
```

### Filters (query params)
```
?city=Islamabad
&type=Homes&type=Plots
&minPrice=5000000&maxPrice=50000000
&minArea=5&maxArea=10
&beds=3
&cityId=5
&locationId=12
&sort=price_asc|price_desc|newest
&page=1&limit=20
```

### Projects (New Developments)
```
GET  /api/projects            → list
GET  /api/projects/:id        → detail
```

### Agencies
```
GET  /api/agencies            → list
GET  /api/agencies/:id        → profile + properties
```

### Favorites
```
GET  /api/favorites           → user's saved
POST /api/favorites           → add property
DELETE /api/favorites/:id     → remove
```

### Inquiries
```
POST /api/inquiries           → send message to agent
```

---

## Data Model

### users
| field | type |
|-------|------|
| id | uuid |
| email | string (unique) |
| password | string (hashed) |
| name | string |
| phone | string |
| role | enum (buyer, agent, admin) |
| agencyId | uuid (nullable) |
| createdAt | timestamp |

### agencies
| field | type |
|-------|------|
| id | uuid |
| name | string |
| logo | string (url) |
| description | text |
| phone | string |
| email | string |
| city | string |
| verified | boolean |
| tier | enum (regular, titanium) |

### properties
| field | type |
|-------|------|
| id | uuid |
| title | string |
| description | text |
| price | integer (PKR) |
| type | enum (home, plot, commercial) |
| status | enum (sale, rent) |
| city | string |
| location | string |
| lat | float |
| lng | float |
| bedrooms | integer |
| bathrooms | integer |
| areaSize | float |
| areaUnit | enum (marla, kanal, sqft) |
| userId | uuid (owner/agent) |
| agencyId | uuid (nullable) |
| images | string[] |
| features | string[] |
| yearBuilt | integer |
| isActive | boolean |
| createdAt | timestamp |

### projects
| field | type |
|-------|------|
| id | uuid |
| title | string |
| developer | string |
| description | text |
| city | string |
| location | string |
| minPrice | integer |
| maxPrice | integer |
| paymentPlan | text |
| completionDate | date |
| images | string[] |
| isActive | boolean |

### favorites
| field | type |
|-------|------|
| id | uuid |
| userId | uuid |
| propertyId | uuid |
| createdAt | timestamp |

### inquiries
| field | type |
|-------|------|
| id | uuid |
| propertyId | uuid |
| userId | uuid (sender) |
| message | text |
| phone | string |
| createdAt | timestamp |

---

## Key Implementation Notes

1. **ISR** — Use `revalidate` in Next.js pages for SEO-friendly dynamic content
2. **Image optimization** — Upload to Cloudinary, serve via their CDN with transformations
3. **Map** — Store lat/lng on properties, show pins on Leaflet map
4. **Search** — PostgreSQL `ILIKE` for MVP, upgrade to Elasticsearch/Typesense later
5. **Pagination** — cursor-based for performance at scale
6. **Auth** — HTTP-only cookie for JWT, refresh token rotation
7. **Validation** — Zod schemas shared between frontend and backend
8. **Area units** — Store as Marla internally, convert for display (1 Kanal = 20 Marla)
9. **Price formatting** — Display in Lakh (e.g., PKR 25 Lac) not raw numbers
