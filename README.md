# Haven Health Clinic — Complete Website

A responsive, multi-section clinic website built with plain HTML, CSS and JavaScript. No Node.js, build tools, or frontend framework is required. It can be hosted as a static website on GitHub Pages.

## What's included

- Responsive home page with mobile navigation
- About, services, team, appointment, testimonials, FAQs and contact sections
- Appointment request form with browser-side validation
- Demo mode: appointment requests are saved only in the current browser's `localStorage`
- Optional Supabase integration for inserting appointment requests
- SQL schema with row-level security enabled and no public read policy
- Accessibility basics: skip link, semantic sections, form labels, status messages and reduced-motion support

## Run locally

Open `index.html` in a modern browser. For the closest match to deployment, use a simple static server or GitHub Pages. No compilation is required.

## Deploy on GitHub Pages

1. Create a GitHub repository (for example, `haven-health-clinic`).
2. Upload the complete contents of this folder, keeping the folder structure unchanged.
3. In the repository, open **Settings → Pages**.
4. Select **Deploy from a branch**, choose `main` and `/ (root)`, then save.
5. Open the Pages URL after deployment completes.

## Connect Supabase (optional)

The site works without Supabase. In demo mode it stores appointment requests in that browser only; it does not send them to a clinic.

To connect a Supabase project:

1. Create a Supabase project.
2. Open **SQL Editor** and run `supabase-schema.sql`.
3. In **Project Settings → API**, copy the Project URL and the anon/public key.
4. Add both values to `assets/js/config.js`:

```js
window.HAVEN_CONFIG = {
  SUPABASE_URL: "https://YOUR_PROJECT.supabase.co",
  SUPABASE_ANON_KEY: "YOUR_SUPABASE_ANON_PUBLIC_KEY"
};
```

5. Redeploy the site and submit a test request using dummy information.
6. Check the `appointments` table in Supabase.

**Never put a Supabase `service_role` key in browser code.** The included SQL enables row-level security and public inserts only. Before collecting real people's information, add suitable spam prevention/rate limiting, restrict who can access appointment data, define retention and deletion processes, and have the appropriate privacy notices and consent reviewed.

## Before publishing for a real clinic

This is a complete website template/demo, not a verified listing for an operating clinic. Replace all sample content:

- Clinic name, address, city, phone number and email
- Doctor names, titles, photographs and credentials
- Services, opening hours and appointment availability
- Testimonials (use only genuine feedback with permission)
- Hero and clinic images, map embed and social links
- Privacy notice, terms, consent text and emergency guidance

The current form only requests appointments. It is not a medical record, diagnostic service or emergency channel. Do not ask visitors to submit diagnoses, prescriptions, test reports or other sensitive medical information through this demo.

## Project structure

```text
haven-health-clinic/
├── index.html
├── README.md
├── supabase-schema.sql
└── assets/
    ├── css/
    │   └── styles.css
    ├── img/
    │   └── favicon.svg
    └── js/
        ├── app.js
        └── config.js
```
