Canteen Roulette is a campus‑first food decision engine with a slot‑machine picker, canteen explorer, and simulated order tracking so people stop overthinking what to eat and just spin, pick, and go 🎰

## What this is

Built originally as a college hackathon project for Somaiya Vidyavihar’s canteens and hostel messes, this can easily live on as a general tool:

- Designed for university campuses with multiple canteens / messes, but also works off‑campus via a Maps handoff.  
- Uses a 3‑reel roulette to suggest items based on veg preference, canteen, and price range.  
- Lets you browse everything with search + filters, add items to a bag, and track “orders” with OTP‑style status updates.  
- Campus Specfic: Aggregates menus from Engineering, Aurobindo, Management, Eklavya Café, Maggi House, and hostels into one place.

Tech stack: **React + TypeScript + Vite + Firebase** (Auth, Firestore, Hosting) with Tailwind and an Inter‑based design system.  

## Main features

- **Roulette** – Slot‑machine picker with on‑campus / off‑campus modes, rarity‑weighted items, and a “near me” search via Google Maps for general use.  
- **Explore** – Search and filter hundreds of items across canteens by canteen, category (Snack / Beverage / Meal etc.), and veg preference.  
- **Bag & Orders** – Add multiple items, place one combined “order”, and watch it move through queued → preparing → ready → picked up with an OTP and ETA (purely simulated).  
- **Profile & Preferences** – Google login, veg/anything toggle, theme switcher (dark / light / system), and small stats like spins and items discovered.  

**Disclaimer:**
- Data models and flows are optimized for a campus environment; if you use this outside that context, you’ll want to plug in your own menus and ordering backend. 
- This is a hackathon‑stage project. The order system is a simulation only (no real payments or integrations with actual vendors).

## Running it locally

Short version; standard React + Firebase workflow:

```bash
git clone https://github.com/manasvitwr/canteen-roulette.git
cd canteen-roulette
npm install
npm run dev
```

You’ll need a Firebase project and Firestore set up with collections for `users`, `canteens`, `menu_items`, and `orders`. Put your config in `.env.local`:

```env
VITE_FIREBASE_API_KEY=...
VITE_FIREBASE_AUTH_DOMAIN=...
VITE_FIREBASE_PROJECT_ID=...
VITE_FIREBASE_STORAGE_BUCKET=...
VITE_FIREBASE_MESSAGING_SENDER_ID=...
VITE_FIREBASE_APP_ID=...
```

Deploy:

```bash
npm run build
firebase deploy
```

- **Google bits:** Firebase Auth, Cloud Firestore, Firebase Hosting, and Google Maps search URLs for the off‑campus mode

Trying to make picking food on campus as quick as hitting a roulette button.

On a side note, this is very much a work‑in‑progress hackathon build rn, more refinement and features will follow.

**made w ❤ by manasvi**
