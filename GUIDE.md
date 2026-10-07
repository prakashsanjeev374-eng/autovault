# AutoVault

A responsive customer storefront and owner inventory interface. Single HTML frontend with Supabase Postgres and Auth backend. GitHub Pages hosts the website. No build tools are needed to open the site.

## Customer interface

- Blue AutoVault design based on the supplied reference, location picker, search, vehicle selection, category tiles, offers and a persistent enquiry cart.
- Broad starting catalog of 47 brands and 649 current/discontinued model entries. Year selector runs from 1980 to 2026. This is not a complete list of every India vehicle, a production-year mapping, or a part-fitment database.
- Search by name, part number, brand or model. Selecting a brand/model filters listings. Use Reset and Clear filters to see everything again.
- View part details, add to cart, change quantity, remove, and copy an enquiry draft.
- No payments, checkout, shipments or messages are sent. Sample listings cannot be bought.

## Owner interface

Click Account or Manage inventory. Sign in with the owner email and the password you chose securely. Add parts, edit them or delete them. Fields include name, part number, category, brand/model, INR price, quantity, condition, image URL, offer flag and donor/fitment notes. Brand/model are free-form and new inventory names are added to the customer selector automatically.

Use original part photos. Enter an HTTPS image URL. When no photo is supplied, reference artwork is clearly identified as an illustration. Add provenance, donor year/variant, condition and inspection information in the notes. Confirm safety-critical parts professionally.

Customer browsers read the shared database on load and every 30 seconds while the page is visible. Returning to a tab reloads inventory. Saving in admin refreshes that admin view immediately. Customers do not need a redeploy or a manual catalog update.

Inventory changes and website design changes are different. The owner panel edits inventory, not page code or CSS. Website design/code can be edited in the GitHub repository, triggering a Pages deployment.

## Backend and security

- Supabase project: AutoVault, in the owner's AutoVault Free organization.
- schema.sql contains the exact inventory table and server-side Row Level Security rules.
- Public users can read inventory. Only the confirmed owner UUID can insert, update or delete it.
- index.html includes only the public anon key, never an admin password, database password or service-role secret.
- Owner sessions are stored in sessionStorage for this tab and expire server-side. Sign out on shared laptops.
- Photos are URLs in this release. Direct photo upload, other sellers, customer accounts, payments, orders, delivery tracking and returns are future work.

## Free-plan limits

Supabase Free is $0 with 500 MB database and 1 GB file storage. Projects can pause after one week of inactivity. Quotas apply. No card or paid upgrade was added. These limits mean this is an early working inventory app, not a promised unlimited production marketplace.

## Source catalog

Current and discontinued names: CarWale brand pages, checked 7 October 2026.
Classic closed-brand names: Autocar India, India at 75: Car brands we have said goodbye to.
See catalog-sources.json for exact observed source URLs. Reference images were provided by the project owner.

## Project files

index.html is the customer website and admin UI, including CSS, JavaScript, embedded reference artwork and catalog. schema.sql is the backend schema and access policies. catalog-sources.json is the source list. README.md is this guide. There are no passwords in the project archive.
