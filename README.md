# Reverse Marketplace

Responsive marketplace MVP. Buyers publish a brief; sellers compete with priced offers.

## Run locally
Open `index.html` in a browser, or run a local static server from this folder:
`py -m http.server 4173`
Then visit http://localhost:4173.

## Current MVP functionality
- Buyer and seller demo registration/login (browser-local only)
- Create buyer requests with category, budget, deadline, description and optional image
- Browse/search/filter live requests
- Sellers submit price, delivery estimate and proposal
- Buyers compare offers and accept one
- In-app message records and buyer/seller dashboards
- Mark deals complete and record a 7% commission amount
- Responsive layout and realistic seed listings

## Important limitations
This build currently stores demo accounts and marketplace records in browser localStorage. It is not production authentication, is not shared between browsers/devices, and demo passwords are not securely stored. Do not use it for real customer accounts or sensitive data. Payments are not processed; completion records the commission only. Connect Supabase Auth, the schema in `supabase/schema.sql`, and a payment provider before public launch.

## Supabase setup
1. Create a dedicated Supabase project for Reverse Marketplace.
2. Run `supabase/schema.sql` in the Supabase SQL editor.
3. Replace the local demo auth/data layer with Supabase Auth and database calls.
4. Configure a private Storage bucket for request images and add storage policies.
5. Implement server-verified offer acceptance and transaction completion (never trust a browser-calculated commission).
6. Integrate Stripe Connect or another marketplace payment provider; collect the platform fee server-side.

Commission is configured to 7% in the schema. Adjust only after deciding the commercial terms and applicable tax/payment obligations.

[executed on device: pc (7e616b3d-018f-4da4-bed8-8a91e76dfa96)]