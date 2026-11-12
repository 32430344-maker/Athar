# Athar

A responsive store website for **fragrance, beauty and more**, built with React.
Visitors can browse products by category, open a product to see its details, read about the store and contact it.
The store owner can add products with a photo, a price and a category, and edit the store profile.

> Course project: Web Programming (ReactJS frontend).

## Live demo

`https://YOUR-PROJECT.vercel.app` (replace with your link after deployment)

## Features

- 9 routes, including 2 dynamic pages (`/categories/:slug` and `/product/:id`)
- Responsive layout: side menu on desktop, top bar with a menu button on phones
- Add products with a photo, name, price and category (form validation included)
- Newest products always appear first, on the Profile page and inside each category
- Profile page shows only the photos of all products, in a square grid
- Data is saved in the browser with `localStorage` (JSON), so it stays after a refresh
- Photos are resized before saving so the browser storage does not fill up
- Profile page with a photo menu (View Photo / Upload a New Photo) and a description that opens with an arrow
- Contact page for brand owners (name, phone, subject and message, with validation)
- Custom 404 page

## Pages

| Page | Address | What it does |
| --- | --- | --- |
| Profile (first page) | `/` | Store info and the photos of all products, newest first |
| Edit profile | `/edit-profile` | Change name, phone, email, description and photo |
| Categories (Services / Features) | `/categories` | The four categories with product counts |
| Category (dynamic) | `/categories/:slug` | Products of one category |
| Product details (dynamic) | `/product/:id` | Big photo, price, category, date and related products |
| Add Photos | `/add` | Form to publish a new product |
| Contact | `/contact` | Contact form for brand owners with validation |
| About | `/about` | About the store and what visitors can do |
| Not found | any other address | 404 page |

## Technologies

- React (Vite)
- React Router (`react-router-dom`)
- Hooks: `useState`, `useEffect`, `useRef`, `useContext`
- Plain CSS (one CSS file per component)
- Browser `localStorage` with `JSON.parse` / `JSON.stringify`
- Fonts: Plus Jakarta Sans and Tajawal (Google Fonts)
- Icons: simple SVG icons drawn in `src/components/Icon.jsx`

## Setup

You need Node.js installed.

```bash
git clone https://github.com/YOUR-USERNAME/athar.git
cd athar
npm install
npm run dev
```

Open the address shown in the terminal (usually `http://localhost:5173`).

To make a production build:

```bash
npm run build
npm run preview
```

## Project structure

```
src/
  main.jsx            starts the app
  App.jsx             routes, shared data and actions
  App.css             colors and layout used everywhere
  data.js             categories, contact phone and the default profile
  helpers.js          image resizing and price format
  context/
    StoreContext.js   shares data between pages (useContext)
  components/         small reusable parts (Sidebar, PhotoGrid, ProductGrid, Footer, ...)
  pages/              one file per page, each with its own CSS
```

## Screenshots

| Profile | Categories |
| --- | --- |
| ![Profile](screenshots/profile.png) | ![Categories](screenshots/categories.png) |

| Product details | Add Photos |
| --- | --- |
| ![Product details](screenshots/product-details.png) | ![Add Photos](screenshots/add-photos.png) |

| Contact | About |
| --- | --- |
| ![Contact](screenshots/contact.png) | ![About](screenshots/about.png) |

| Mobile |
| --- |
| ![Mobile](screenshots/mobile.png) |

## Deployment

The project is hosted on Vercel. The file `vercel.json` makes every address open the app, so refreshing a page like `/product/123` works.
For Netlify, the file `public/_redirects` does the same.

## Notes

- There is no server. Products and profile data are stored only in the browser of the person using the site.
- The contact form shows the message in the browser console only.

## Author

YOUR NAME
