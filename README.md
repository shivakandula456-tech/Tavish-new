# TAVISH & CO.

A complete static e-commerce website for an Indian jewellery brand. Built with plain HTML5, CSS3 and vanilla JavaScript — no framework, build step, backend, API, database or npm dependency.

The storefront and administration pages share browser `localStorage` on the same origin. The initial catalogue is bundled for functional testing; customer orders, newsletter entries, audit history, cart, wishlist and admin session start empty.

## Pages

**Storefront:** home, shop, product detail, cart/checkout, wishlist, search, about, contact, FAQs, shipping & delivery, returns & refunds, privacy policy, terms & conditions.

**Administration:** `/admin/` with login, dashboard, products, product editor, categories, media library, orders, order detail, newsletter, settings/backup and audit log.

## Features

- 24 initial catalogue products with four product images each.
- 94 stock/reference images distributed as editorial/style-inspiration imagery and available in the Admin Media Library.
- Cart and wishlist persisted in `localStorage`.
- Cash-on-delivery checkout with validation and WhatsApp hand-off to +91 99213 18679.
- Floating WhatsApp Enquiry control across the public website.
- Product-specific WhatsApp enquiries containing product name and SKU.
- Shop filtering, URL-synced categories/flags, sorting and search.
- Admin product CRUD, image picker, publish checklist, category management, order status tracking, newsletter list, settings, JSON backup/restore, catalogue import and audit log.
- No seeded/fake orders, fake customers, fake newsletter subscribers or fake audit history.
- SEO: page titles/descriptions/canonicals, Open Graph, JSON-LD, sitemap and robots.
- Accessibility: skip links, keyboard focus, ARIA labels/states and reduced-motion support.
- Responsive layouts from 360px phones through 4K desktop displays.

## Static data limitation

The Admin and storefront synchronize only within the same browser/origin because the project intentionally has no backend or database. A product edited in Admin is immediately available to the storefront in that browser. A real centralized catalogue shared by every customer's device requires a server-side data store or CMS and is outside this static architecture.

## Running locally

Serve the folder with any static file server, for example:

```bash
python -m http.server 8080
```

Then open `http://localhost:8080`.

## Administration

- URL: `/admin/login.html`
- Initial local credentials: username `admin`, password `tavish123`

The login is compared entirely in the browser and is not server-side authentication. It should not be used to protect sensitive customer data.

Settings provides:

- Download full JSON backup
- Restore backup
- Import catalogue JSON
- Clear local orders
- Clear audit log
- Factory reset local store

Factory reset restores the initial catalogue/categories/settings and clears orders, newsletter entries, audit history, cart, wishlist and the local admin session. It does not recreate fake orders.

## Imagery

The 24 initial catalogue entries use temporary reference product photography. The 94 stock/reference images are used for visual styling, editorial sections and product-page style inspiration; they are not represented as actual TAVISH & CO. product photography. Replace them with final brand photography before commercial launch.

Image provenance is documented in:

`assets/images/stock_reference/SOURCES.md`

## Hero and logo source

During development, the supplied TAVISH & CO. logo and hero-page video are sourced from:

`C:\Users\Welcome\OneDrive\Desktop\New folder (3)`

This Windows path is development-only and is never referenced by the deployed website. Public copies are stored under the project's `assets/images/brand/`, `assets/images/hero/` and `assets/video/` paths.

## Deployment

The project can be deployed as static files to GitHub Pages, Netlify or Vercel static hosting. No build command or install step is required.

Before commercial launch, replace the placeholder canonical domain `https://tavishandco.example` in the page metadata, sitemap, robots file and SEO settings.

For a real multi-device commercial catalogue, centralized orders and secure authentication, add a proper backend/CMS later rather than treating `localStorage` as a server database.


### V6 transparent homepage header correction
- Homepage navigation header and its inner wrappers are explicitly transparent at the top of the page, with no backdrop blur.
- The ivory sticky state activates after 120px of scrolling rather than immediately after 8px, preventing a tiny scroll/restored scroll position from making the hero header appear opaque.
- Announcement bar and navigation links/actions remain unchanged.


## Admin redesign V7
- Admin styling refreshed to a practical premium system: ivory workspace, charcoal sidebar, restrained champagne-gold accents, clearer forms and compact mobile spacing.
- Product editor supports uploading 1–4 product images directly from the device. Images are resized and compressed in the browser before being stored as data URLs in localStorage.
- At least one image is required to save a product; no more than four product images may be attached. The first image is the primary image; image order can be changed in the editor.
- Important static-site limitation: uploaded images and product changes are stored only in the current browser's localStorage. They do not upload files to GitHub Pages or sync to other devices. For public deployment, upload the final optimized image files into the site assets and use their relative paths, or later add centralized storage. Browser localStorage is quota-limited; keep uploads optimized and export a backup regularly.
