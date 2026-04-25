# 🏠 Zameen Clone — UI/UX Spec

## Design Vision

A modern Pakistani property portal — professional, trustworthy, and fast. Think Zameen's functionality with a fresh, cleaner aesthetic.

## Color Palette

| Role | Color | Hex |
|------|-------|-----|
| Primary | Deep Green | `#0D6E3F` (Pakistani real estate trust) |
| Primary Light | Light Green | `#10B981` |
| Accent | Gold | `#F59E0B` (premium/titanium agencies) |
| Background | Off-white | `#F8FAFC` |
| Surface | White | `#FFFFFF` |
| Text Primary | Dark Slate | `#1E293B` |
| Text Secondary | Gray | `#64748B` |
| Border | Light Gray | `#E2E8F0` |
| Error | Red | `#EF4444` |
| Success | Green | `#22C55E` |

## Typography

- **Headings:** Inter (700, 600)
- **Body:** Inter (400, 500)
- **Urdu fallback:** Noto Nastaliq Urdu (for locale)

## Layout

### Homepage
```
┌─────────────────────────────────────────┐
│ Header: Logo | Buy | Rent | Projects |  │
│         Agents | Tools | Login           │
├─────────────────────────────────────────┤
│ Hero: Full-width gradient + search bar   │
│       Tabs: Buy | Rent | Projects       │
│       City dropdown + Search button     │
├─────────────────────────────────────────┤
│ Quick Filters: Type chips (Homes/Plots/ │
│ Commercial) + Popular cities            │
├─────────────────────────────────────────┤
│ Featured Listings: 3-col grid           │
├─────────────────────────────────────────┤
│ Popular Locations: Image cards          │
├─────────────────────────────────────────┤
│ Tools Section: Loan Calc | Area Conv    │
├─────────────────────────────────────────┤
│ New Projects: Horizontal scroll cards   │
├─────────────────────────────────────────┤
│ Footer: Links | Social | Copyright      │
└─────────────────────────────────────────┘
```

### Listings Page
```
┌──────────────────────────────────────────┐
│ Header (sticky on scroll)                │
├──────────────┬───────────────────────────┤
│ Filters      │ Listings Grid             │
│ (sticky)     │ ┌────┐ ┌────┐ ┌────┐     │
│ Price range  │ │Card│ │Card│ │Card│     │
│ Beds         │ └────┘ └────┘ └────┘     │
│ Type         │ ┌────┐ ┌────┐ ┌────┐     │
│ Area size    │ │Card│ │Card│ │Card│     │
│ City/Loc     │ └────┘ └────┘ └────┘     │
│ More filters │ Pagination               │
│              │ View toggle: Grid / Map   │
└──────────────┴───────────────────────────┘
```

### Property Card
```
┌───────────────────────┐
│ [IMAGE]          ♥    │  ← thumbnail + favorite
│  PKR 2.5 Crore       │  ← price (formatted)
│ 3 Bed | 3 Bath | 5 Marla│  ← specs
│ House in F-7, Islamabad │  ← location
│ Zameen.com ⭐ 4.2     │  ← agency rating
└───────────────────────┘
```

### Property Detail Page
```
┌──────────────────────────────────────────┐
│ Photo Gallery (large main + thumbnails)   │
├──────────────────────────────────────────┤
│ PKR 2.5 Crore           ┌─────────────┐ │
│ 3 Bed House in F-7      │ Agent Card  │ │
│                         │ Call | Msg  │ │
├──────────────────────────────────────────┤
│ Overview | Specs | Description | Map    │ ← tabs
│                                         │
│ Price: PKR 2,50,00,000                 │
│ Type: House | Status: For Sale          │
│ Location: F-7, Islamabad                │
│ Area: 5 Marla | Beds: 3 | Baths: 3     │
│ Year Built: 2020                        │
├──────────────────────────────────────────┤
│ Description text...                      │
├──────────────────────────────────────────┤
│ Map showing location                     │
└──────────────────────────────────────────┘
```

## Components

| Component | States |
|-----------|--------|
| PropertyCard | default, hover (shadow lift), favorited |
| SearchBar | collapsed, expanded, focused |
| FilterChip | unselected, selected |
| PriceSlider | default, dragging, range |
| Button | primary, secondary, ghost, disabled, loading |
| Input | default, focused, error, disabled |
| Select | closed, open, selected |
| Tabs | active, inactive |
| Pagination | page numbers, prev/next, current |
| AgentCard | default, hover |

## Mobile Design

- Bottom navigation bar (Home, Search, Favorites, Profile)
- Filters in bottom sheet (slide up)
- Swipeable image gallery
- Sticky "Call Agent" button on detail page
- Full-screen map option

## Animations

- Page transitions: fade 200ms
- Card hover: translateY(-4px) + shadow, 150ms ease
- Image gallery: slide with 300ms ease
- Filter open: slide up 250ms ease-out
- Skeleton loaders while data fetches
