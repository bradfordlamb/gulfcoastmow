# Yard Steady — Website

Weekly lawn mowing in Pearland, Manvel, and Friendswood, TX. A brand of BLamb Investments LLC.
Static site on GitHub Pages. `CNAME` is left as-is.

## Contact

The public number is **(832) 895-1693**.

- Call: `tel:+18328951693`
- Text: `sms:+18328951693`
- Schema `telephone`: `+1-832-895-1693`
- Email: blambinvestmentsllc@gmail.com

## Analytics

GA4 is installed in `index.html` with Measurement ID **G-SV2DYD9QR9**. The `track()` helper sends events through `gtag`, including `call_click` and `text_click`.

## Pages

| URL | What it is |
|-----|------------|
| `/` | Homepage |
| `/referral` and `/?page=referral` | Referral program (same page) |
| `/crew` | No crew page exists. This path redirects to the homepage so it does not 404. It is not listed in the sitemap. |

`referral/index.html` is a copy of `index.html` so GitHub Pages can serve `/referral`. Keep the two files the same.

## Signup

Signups post to Formspree (`https://formspree.io/f/xgavppqo`). Pricing on the page is unchanged: first mow $20, then $40/week (standard) or $55/week (large), plus tax. Stripe payment links in `index.html` are comments only and were not changed.
