# Golden Glow Studio — Vue App

A premium beauty & wellness studio web app built with Vue 3, Vite, and Tailwind CSS.

## Stack
- **Frontend**: Vue 3 + Vue Router + Pinia
- **Styling**: Tailwind CSS v4 (via `@tailwindcss/vite`)
- **Animations**: AOS (scroll animations), GSAP
- **Icons**: Font Awesome Free
- **API**: Osimart (`https://api.osimart.com`) — requires `VITE_OSIMART_STORE_ID`

## Running the App
```bash
npm run dev      # starts dev server on port 5000
npm run build    # production build
npm run preview  # preview production build
```

The dev workflow is configured as **Dev Server** → `npm run dev`.

## Required Environment Variables
| Variable | Description |
|---|---|
| `VITE_OSIMART_STORE_ID` | Osimart store identifier (set in Replit Secrets) |

## Project Structure
```
src/
  assets/         # main.css (Tailwind entry point)
  components/
    layout/       # Navbar.vue, Footer.vue
    home/         # Hero, Services, Products, Specialists, etc.
    specialists/  # SpecialistCard, SpecialistsGrid
  composables/    # auth.js, useCart.js, wishlist.js
  services/       # API layer (osimart, banner, product, service, etc.)
  views/          # All page-level components
  router/         # Vue Router config
  data/           # Static data (specialists)
```

## Pages / Routes
| Route | View |
|---|---|
| `/` | HomeView |
| `/services/:type` | ServiceView (hair, nails, makeup, massage, laser) |
| `/products` | ProductsView |
| `/specialists` | SpecialistsView |
| `/cart` | CartView |
| `/checkout` | CheckoutView |
| `/wishlist` | WishlistView |
| `/account` | AccountView (auth required) |
| `/login` | LoginView |
| `/vip` | VIPView (auth required) |
| `/giftcards` | GiftCardsForm |
| `/booking` | BookView |

## User Preferences
- Keep the existing luxury design style (gold `#D4AF37` / `#bd9c30`, Playfair Display headings, stone color palette)
- Do not remove or restructure existing features
- Mobile-first responsive approach
