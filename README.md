# Project-E-Commerce-Product-Catalog
Project: E-Commerce Product Catalog

ecommerce-catalog/
├── public/
│   ├── _redirects                 # Fallback routing for Netlify
│   └── placeholder.webp
├── src/
│   ├── components/
│   │   ├── common/                # Navbar, Footer, Button, SkeletonLoader
│   │   └── product/               # ProductCard, ProductGrid, PriceFilter
│   ├── context/
│   │   └── CartContext.tsx        # Global client state
│   ├── hooks/
│   │   └── useProducts.ts         # Data fetching & memoized filtering
│   ├── pages/
│   │   ├── CatalogPage.tsx        # Paginated catalog & filters
│   │   ├── ProductDetailPage.tsx  # Dynamic route view
│   │   └── CartPage.tsx           # Checkout overview
│   ├── routes/
│   │   └── AppRouter.tsx          # Lazy-loaded route definitions
│   ├── types/
│   │   └── index.ts               # Shared TypeScript schemas
│   ├── App.tsx
│   └── main.tsx
├── vercel.json                    # Single Page App rewrite for Vercel
└── vite.config.ts                 # Chunking & minification rules

Scaffold the Modular Architecture
Prerequisite: Node.js 18 or newer installed
•
Initialize a Vite application with TypeScript and Tailwind CSS (or your chosen styling solution):
•
Define strong typing for entities under src/types/index.ts:
•
Isolate business logic from lUI using custom hooks. For instance, src/hooks/useProducts.ts should handle state, search terms, and category filters while exposing purely memoized results:

Expected BehaviorVerification Method
Direct Route RefreshReloading /product/1 renders the page without 404 errorsBrowser refresh on a nested subpage
Code SplittingInitial JS payload contains only shared layouts and the home bundleChrome DevTools Network Tab (.js files)
