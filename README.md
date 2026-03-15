# BidBash

BidBash is a static auction website built with HTML, CSS, JavaScript, and Bootstrap. It presents featured auction items, category-based auction listings, a bid details page, contact and about pages, and a simple client-side sign in / sign up flow using `localStorage`.

## Overview

The project is designed as a front-end auction experience with:

- a landing page with featured and current auctions
- a dedicated auctions page with current, previous, and upcoming sections
- a bid page that receives item details through URL query parameters
- an about page and contact page
- a basic sign in / sign up page with browser-side storage

## Features

- Responsive multi-page auction website
- Featured item carousel on the homepage
- Auction section switching on the auctions page
- Bid details page populated dynamically from selected item data
- Client-side sign up and sign in flow using `localStorage`
- Shared navigation and consistent visual styling across pages

## Tech Stack

- HTML5
- CSS3
- JavaScript
- Bootstrap 5
- Font Awesome

## Project Structure

```text
Bidbash/
├── index.html
├── Auctions.html
├── bid.html
├── AboutUs.html
├── Contact.html
├── SignIn.html
├── css files/
│   ├── style.css
│   ├── AboutUs.css
│   ├── ContactUs.css
│   ├── SignIn.css
│   └── Bid.css
├── js/
│   ├── script.js
│   └── signin.js
└── images/
```

## Main Pages

- `index.html`: Homepage with hero carousel, featured auctions, upcoming section, and footer
- `Auctions.html`: Full auction catalog with current, previous, and upcoming auction sections
- `bid.html`: Item bid page that reads item data from query parameters
- `AboutUs.html`: About page for the platform
- `Contact.html`: Contact and support page
- `SignIn.html`: Client-side sign in / sign up page

## How It Works

### Auction Navigation

The homepage and auctions page use buttons that call `redirectToBid(...)` from [`js/script.js`](C:\Users\garvi\OneDrive\Desktop\Bidbash\js\script.js). That function passes item name, price, image, and description into `bid.html` through the URL.

### Dynamic Bid Page

[`bid.html`](C:\Users\garvi\OneDrive\Desktop\Bidbash\bid.html) reads URL query parameters and fills in:

- item name
- item image
- starting bid
- description

### Section Switching

[`js/script.js`](C:\Users\garvi\OneDrive\Desktop\Bidbash\js\script.js) also controls switching between:

- current auctions
- previous auctions
- upcoming auctions

The selected section is stored in `localStorage` so the page can reopen with the same active tab.

### Sign In / Sign Up

[`SignIn.html`](C:\Users\garvi\OneDrive\Desktop\Bidbash\SignIn.html) stores user data in the browser using `localStorage`. This is suitable for demonstration purposes only and should not be used for production authentication.

## Run Locally

This is a static project, so no package installation is required.

### Option 1: Open directly

Open [`index.html`](C:\Users\garvi\OneDrive\Desktop\Bidbash\index.html) in a browser.

### Option 2: Use a local server

Using a local server is better for navigation and deployment testing.

If you have Python installed:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Deployment

This project can be deployed as a static site on Vercel, Netlify, GitHub Pages, or any static hosting provider.

### Vercel Notes

Use these settings:

- Framework Preset: `Other`
- Root Directory: project root
- Build Command: leave empty
- Output Directory: leave empty

Important:

- Upload the contents of the project folder, not a parent folder that contains `Bidbash/`
- Make sure `index.html` is at the deployment root

## Limitations

- Authentication is not secure and is only stored in browser `localStorage`
- Auction data is hardcoded in HTML
- No backend, database, or real payment / bidding system exists yet
- Some links in the footer such as `FAQ.html`, `terms.html`, and `privacy.html` are referenced but not currently present in the project

## Suggested Improvements

- Move auction data into JSON and render cards dynamically
- Add a backend for authentication and real auction management
- Replace `localStorage` auth with secure server-side authentication
- Add missing informational pages
- Improve accessibility and form validation
- Add a proper deployment configuration file such as `vercel.json` if needed

## Author

Built as the BidBash auction website project.
