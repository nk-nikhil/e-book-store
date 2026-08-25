# 📚 BookStore — E-Bookstore Platform

A full-featured e-bookstore single-page application built with **React 19**, **TypeScript**, **Vite**, and **React Router v7**.  
Designed and developed as part of the IBM BOB Agentic IDE workshop.

---

## 🖥️ Live Preview

> Run locally by following the steps below.

---

## 📋 Table of Contents

- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Features](#-features)
- [Prerequisites](#-prerequisites)
- [Getting Started](#-getting-started)
- [Available Scripts](#-available-scripts)
- [Page Routes](#-page-routes)
- [Coupon Codes (Demo)](#-coupon-codes-demo)
- [Screenshots](#-screenshots)

---

## 🛠️ Tech Stack

| Technology | Version | Purpose |
|---|---|---|
| [React](https://react.dev/) | 19.x | UI library |
| [TypeScript](https://www.typescriptlang.org/) | 6.x | Type safety |
| [Vite](https://vite.dev/) | 8.x | Build tool & dev server |
| [React Router DOM](https://reactrouter.com/) | 7.x | Client-side routing |
| CSS Modules | — | Scoped component styling |

> No external UI library used — all components are hand-crafted.

---

## 📁 Project Structure

```
e-store-app/
├── index.html                  # HTML entry point
├── vite.config.ts              # Vite + React plugin config
├── tsconfig.json               # TypeScript configuration
├── package.json
└── src/
    ├── main.tsx                # React entry — mounts <App /> with BrowserRouter
    ├── App.tsx                 # App shell: Header, Sidebar, Routes
    ├── App.module.css
    ├── vite-env.d.ts           # CSS module type declarations
    │
    ├── styles/
    │   └── global.css          # CSS custom properties (design tokens), reset
    │
    ├── types/
    │   └── index.ts            # Book, Review, Author, CartItem interfaces
    │
    ├── data/
    │   └── books.ts            # Seed data — 13 books with full detail
    │
    ├── context/
    │   └── CartContext.tsx     # Global cart state (add, remove, update qty, clear)
    │
    ├── components/
    │   ├── Header/             # Fixed top bar: brand, nav, search, filters, cart icon
    │   ├── Sidebar/            # Collapsible left nav: page links + category filter
    │   ├── BookCard/           # Reusable book card (cover, price, Add to Cart)
    │   └── BookSection/        # Horizontal scroll row of BookCards with section title
    │
    └── pages/
        ├── HomePage/           # Landing: Recommended, Bestsellers, New Launches
        ├── CataloguePage/      # Full filterable grid (category, brand, price, sort)
        ├── BookDetailPage/     # Book detail: description, author bio, reviews, related reads
        ├── CheckoutPage/       # Cart items, address form, payment method, grand total
        ├── PaymentPage/        # Payment screen: Credit/Debit Card, UPI, Wallet
        ├── PaymentConfirmPage/ # Order confirmation with animated green tick
        └── PlaceholderPage/    # Generic stub for Orders, Wishlist, Profile
```

---

## ✨ Features

### 🏠 Home Page
- Three curated book sections: **Recommended for You**, **Bestsellers this Month**, **New Launches**
- Each book card is clickable → navigates to the book detail page
- Toast notification on "Add to Cart"

### 📚 Catalogue Page
- Full book grid with **live search** (title / author)
- **Category filter** via sidebar or in-page pills (Fiction, Mystery, Self Help, etc.)
- **Brand filter** strip (Penguin, HarperCollins, Bloomsbury, etc.)
- **Price range** and **sort** dropdowns (rating, popularity, price)
- Results count and "Reset Filters" button

### 📖 Book Detail Page
- Full book cover, title, author, publisher, language, pages
- Star rating + sold count
- Description, format metadata
- **Add to Cart** (shows live quantity) + **Add to Wishlist** toggle
- **About the Author** with bio and avatar
- **Reviews** — read existing reviews, submit a new one with star picker
- **Related Reads** sidebar — same-category book suggestions

### 🛒 Checkout Page
- Cart line items with **quantity stepper** (+ / −) and **remove** button
- **Address form**: First/Last name, Address, Email, City, PIN, Phone (with dial code), State, Country
- "Use Saved Address" toggle
- **Payment method selector**: Credit/Debit Card 💳, UPI 📱, Wallet 👛, Gift Points 🎁
- **Grand Total panel**: itemised price + 2% tax + delivery (free above ₹300)
- **Coupon code** input with Apply button
- Total amount with discount applied

### 💳 Payment Page
- Full-screen illustrated book background
- Tabbed payment modal: Credit Card / Debit Card / UPI / Wallet
- Card number auto-formatting (XXXX-XXXX-XXXX-XXXX), CVV masking, expiry formatting
- Client-side field validation with inline error messages
- Processing spinner animation before confirmation

### ✅ Order Confirmation Page
- Animated SVG green tick (stroke-draw animation)
- Purchased book cards with cover, title, price, delivery date
- "Continue your Shopping" button

### 🔒 Cart Context
- Global cart state shared across all pages via React Context
- Persists across navigation within the session
- Cart badge in Header updates live

---

## ✅ Prerequisites

Make sure you have the following installed before proceeding:

| Tool | Minimum Version | Check |
|---|---|---|
| [Node.js](https://nodejs.org/) | **18.x** or higher | `node --version` |
| [npm](https://www.npmjs.com/) | **9.x** or higher | `npm --version` |
| Git | any recent version | `git --version` |

---

## 🚀 Getting Started

Follow these steps exactly to run the project locally.

### Step 1 — Clone the repository

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
```

> Replace `<your-username>` and `<your-repo-name>` with your actual GitHub username and repository name.

---

### Step 2 — Navigate into the project folder

```bash
cd <your-repo-name>/e-store-app
```

> The React app lives inside the `e-store-app` subdirectory.

---

### Step 3 — Install dependencies

```bash
npm install
```

This will install all required packages listed in `package.json` into a local `node_modules/` folder.  
Expected output: `added X packages` with **0 vulnerabilities**.

---

### Step 4 — Start the development server

```bash
npm run dev
```

Expected output:

```
  VITE  v8.x.x  ready in Xms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
```

---

### Step 5 — Open in browser

Open your browser and go to:

```
http://localhost:5173
```

The BookStore app should load with the dark theme home page.

---

## 📜 Available Scripts

Run these from inside the `e-store-app/` directory:

| Script | Command | Description |
|---|---|---|
| Development server | `npm run dev` | Starts Vite dev server with HMR at `localhost:5173` |
| Production build | `npm run build` | Type-checks with `tsc` then bundles to `dist/` |
| Preview build | `npm run preview` | Serves the production `dist/` build locally |

---

## 🗺️ Page Routes

| Route | Page | Description |
|---|---|---|
| `/` | Home | Landing page with book sections |
| `/catalogue` | Catalogue | Full filterable book grid |
| `/catalogue?category=mystery` | Catalogue (filtered) | Pre-filtered by category |
| `/book/:id` | Book Detail | Detail view for a specific book |
| `/checkout` | Checkout | Cart review + address + payment method |
| `/payment?amount=XXX` | Payment | Payment form with card/UPI/wallet |
| `/payment/confirm` | Order Confirmation | Success screen with purchased books |
| `/orders` | My Orders | Placeholder (coming soon) |
| `/wishlist` | My Wishlist | Placeholder (coming soon) |
| `/profile` | My Profile | Placeholder (coming soon) |

---

## 🏷️ Coupon Codes (Demo)

These coupon codes can be applied on the Checkout page:

| Code | Discount |
|---|---|
| `SAVE50` | ₹50 flat off |
| `BOOKFEST` | ₹100 flat off |
| `NEWUSER` | 10% off the subtotal |

---

## 🧭 Quick Navigation Guide

```
Home  ──────────────────►  Click any book card  ──►  Book Detail
                                                          │
                                                   Add to Cart
                                                          │
                                               Click 🛒 in Header
                                                          │
                                                       Checkout
                                                          │
                                              Fill address + Pay Now
                                                          │
                                                    Payment Screen
                                                          │
                                               Enter card details + Pay Now
                                                          │
                                                Order Confirmation ✅
```

---

## 🎨 Design System

All colours and spacing are defined as CSS custom properties in [`src/styles/global.css`](./src/styles/global.css):

| Token | Value | Usage |
|---|---|---|
| `--bg-primary` | `#1a1a2e` | Page background |
| `--bg-secondary` | `#16213e` | Cards, panels |
| `--bg-surface` | `#0f3460` | Active states |
| `--accent` | `#e94560` | Buttons, tags, highlights |
| `--text-primary` | `#e2e8f0` | Main text |
| `--text-muted` | `#94a3b8` | Secondary text |
| `--header-height` | `56px` | Fixed header offset |
| `--sidebar-width` | `200px` | Sidebar width |

---

## 📄 License

This project was built for educational purposes as part of the **Applied AI Specialist-Experience Front End** Reskill (Entry) program.

---
