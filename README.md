# E-Commerce Storefront Engine

**Course:** Software Engineering
**Topic:** Frontend Development, DOM Manipulation & Client-Side Pagination
**Tech Stack:** HTML5, CSS3, JavaScript (ES6+), Vite
**Total Points:** 20 Points

---

## Overview

For this project, you will build a responsive, interactive storefront for an e-commerce business across three core pages: a **Home Page**, an **About Page**, and a **Store Page**.

You get to choose the domain for your store! You get to choose what kind of store this is, the name, and the products.

Your Store Page will load a catalog of 15 products from a local JSON file. You must implement dynamic client-side pagination on the Store Page (5 products per page across 3 pages) so users can navigate between pages of products without triggering full browser reloads.

> **Note:** You do **not** need to implement shopping cart or checkout functionality for this assignment. Focus entirely on page layout, styling, DOM manipulation, and dynamic client-side pagination logic. There should be no backend components.

---

## ⚠️ Crucial Requirement: Relative Paths & Local Assets

To ensure your project runs seamlessly across local development, Vite dev server, and grading environments:

- **All file references must use relative paths.** This applies to stylesheet imports (`<link rel="stylesheet" href="./src/styles/main.css">`), script tags, navigation links (`<a href="...">`), and image sources (`<img src="...">`).
- **Product images must be stored locally** within your project directory (e.g., inside `public/images/`). **Do not use external image URLs or placeholder API links.**

---

## 🚀 Getting Started

### Step 1: Environment Setup

Clone or extract your starter repository and navigate into the project director.

Review the provided project structure:

```text
├── public/
│   └── images/               # Store your local product images here
├── src/
│   ├── data/
│   │   └── products.json     # Mock product data array (you will populate with 15 items)
│   ├── styles/
│   │   └── main.css          # Main stylesheet (blank)
│   └── main.js               # Main JavaScript file (blank)
├── index.html                # Home Page (blank)
├── about.html                # About Page (blank)
├── store.html                # Store Page (blank)
├── package.json
└── vite.config.js

```

---

### Step 2: Install Dependencies

Install the project development dependencies:

```bash
npm install

```

---

### Step 3: Start the Development Server

Start the local Vite development server:

```bash
npm run dev

```

Open your browser and navigate to `http://localhost:5173` to view your application.

---

### Step 4: Code Quality & Scripts

Additional scripts available in `package.json`:

- **Format Code:** `npm run format`
- **Check Formatting:** `npm run format:check`
- **Build Production Bundle:** `npm run build`
- **Preview Production Build:** `npm run preview`

---

## Part 1: Site Architecture, Layout & Pages (10 Points)

Your first goal is to establish your store domain, create your mock data with local images, and construct the responsive layouts across your three pages.

### 1. Store Domain & Data Schema (`src/data/products.json`)

Define your store's brand and populate `src/data/products.json` with **exactly 15 local product items** (3 pages of 5 products each).

Each product object must conform to the following JSON structure:

```json
{
  "id": 1,
  "name": "Product Name",
  "price": 29.99,
  "category": "Category Name",
  "description": "Short 1-2 sentence description of the product.",
  "imageUrl": "./images/product1.jpg"
}
```

> **Reminder:** All image files must exist locally within your repository (e.g. `public/images/`).

### 2. Shared Navigation Header & Footer

Each HTML page (`index.html`, `about.html`, `store.html`) must contain a consistent header and footer:

- **Header / Navbar:** Branding/Logo and navigation links connecting **Home**, **About**, and **Store**.
- **Footer:** Copyright, social links, or mock store hours.
- **Relative Pathing:** Ensure all `<script>`, `<link>`, anchor `href`, and image paths use relative paths.

### 3. Page Content Requirements

- **Home Page (`index.html`):** Must feature a hero banner, a brief introduction to your store, and a "Featured Categories" or "Call to Action" section directing users to the store page.
- **About Page (`about.html`):** Must highlight the store’s mission statement, brand story, and basic contact/location info.
- **Store Page (`store.html`):** Structures the layout container for the product grid and pagination control elements.

### 4. Responsive CSS Styling (`src/styles/main.css`)

Apply CSS styling (Flexbox, CSS Grid, or utility frameworks) across all pages to ensure:

- Product grids adjust seamlessly across mobile, tablet, and desktop screen widths.
- Clear visual cues for interactive elements (hover states on buttons and navigation links).
- Styling for disabled pagination button states (`:disabled`).

---

## Part 2: Store Page Dynamic Client-Side Pagination (10 Points)

In this part, you will write client-side JavaScript (`src/main.js`) to dynamically update the product list on the Store Page without reloading the page.

### 1. Product Cards Rendering

When visiting the Store page:

- Render product cards inside a responsive grid using data imported from `src/data/products.json`.
- Each product card must display the local product image, title, price, category badge, and short description.

### 2. Dynamic Client-Side Pagination (5 Products / Page)

Implement pagination logic on the frontend with the following business rules:

- **Products per Page:** Display exactly 5 products at a time.
- **Total Pages:** With 15 total items, your catalog spans exactly 3 pages.
- **Dynamic Updates:** Clicking **Next** or **Previous** controls must slice the product dataset and update the DOM **dynamically on the frontend without reloading the browser page**.
- **Page Indicator:** Display current pagination status (e.g., "Page 1 of 3").

### 3. Pagination Boundary Guardrails

- **Page 1:** The **Previous** button must be disabled or inactive.
- **Page 3:** The **Next** button must be disabled or inactive.

---

## Grading Rubric

### Part 1: Site Architecture, Layout & Pages (10 Points Total)

- **Store Domain, Schema & Local Images (2 points):** `products.json` contains 15 well-structured product objects referencing valid local image assets. All asset paths use relative URL paths.
- **Home & About Pages (3 points):** Both pages are fully constructed with relevant text, branding elements, hero banner, and structured sections.
- **Layout & Responsive Styling (3 points):** CSS cleanly handles multi-column layouts using Grid/Flexbox; visual styling is clean, coherent, and responsive across mobile and desktop viewports.
- **Navigation Header & Footer (2 points):** Persistent header and footer present across all three pages with functional, relative navigation links.

### Part 2: Store Page Dynamic Client-Side Pagination (10 Points Total)

- **Product Grid Rendering (3 points):** Products render cleanly inside a structured grid showing local image, title, price, category, and description imported from `products.json`.
- **Dynamic Client-Side Pagination (4 points):** Clicking **Next** and **Previous** buttons updates the visible 5 products on the DOM instantly without reloading the browser.
- **Boundary Guards & State Controls (3 points):** Previous button is properly disabled on Page 1; Next button is properly disabled on Page 3. Current page number indicator ("Page X of Y") accurately reflects state.
