# Gulf Coast Mow Service — Website

Reliable weekly lawn care subscription service serving Pearland, Manvel, and League City, TX.  
Built as a single `index.html` file, deployable directly to GitHub Pages with zero build tools.

---

## 🚀 Going Live Checklist

### 1. Stripe Payment Links
Open `index.html` and find these two lines near the top of the `<script>` block:

```js
const STRIPE_SMALL = 'https://buy.stripe.com/REPLACE_SMALL_PLAN';
const STRIPE_LARGE = 'https://buy.stripe.com/REPLACE_LARGE_PLAN';
```

Replace with your actual Stripe Payment Link URLs:
- **STRIPE_SMALL** → Your $45/week recurring plan link
- **STRIPE_LARGE** → Your $60/week recurring plan link

To create these in Stripe:
1. Go to [dashboard.stripe.com/payment-links](https://dashboard.stripe.com/payment-links)
2. Create a new Payment Link → Recurring → Weekly
3. Set price to $45 (or $60) → Copy the link

---

### 2. Referral Program Link
Find this line (appears twice — hero and referral page CTA):

```html
href="https://REPLACE_REFERRAL_SIGNUP_URL"
```

Replace with your Tolt affiliate signup URL.

To set up Tolt:
1. Sign up at [tolt.io](https://tolt.io) (~$29/month)
2. Connect your Stripe account
3. Set commission: $10/month per active referral (recurring)
4. Copy your affiliate signup page URL and paste it here

---

### 3. Contact Email
Find all instances of:

```
hello@gulfcoastmow.com
```

Replace with your real business email address. Appears in:
- Footer (both home and referral page)
- Custom quote mailto link in pricing section
- Custom quote modal mailto fallback

---

### 4. Business Name / Branding
If you change the business name, search for `Gulf Coast Mow` and update all instances.

---

## 📦 Deploying to GitHub Pages

1. Create a new GitHub repository (e.g. `gulfcoastmow`)
2. Upload `index.html` to the root of the repo
3. Go to **Settings → Pages**
4. Set source to `main` branch → `/ (root)`
5. Click Save — your site is live at:  
   `https://yourusername.github.io/gulfcoastmow`

### Custom Domain Setup
1. Buy your domain (e.g. `gulfcoastmow.com`) from Namecheap, GoDaddy, etc.
2. In GitHub → Settings → Pages → Custom domain → enter your domain
3. At your domain registrar, add these DNS records:

```
Type    Name    Value
A       @       185.199.108.153
A       @       185.199.109.153
A       @       185.199.110.153
A       @       185.199.111.153
CNAME   www     yourusername.github.io
```

4. Check "Enforce HTTPS" in GitHub Pages settings
5. DNS propagation takes 10–30 minutes

---

## 💳 Stripe Setup Notes

### How customer data flows into Stripe
When a customer completes the signup modal and clicks "Pay Securely via Stripe", the site passes:

- `prefilled_email` — pre-fills their email on the Stripe checkout page
- `client_reference_id` — a pipe-delimited string containing all signup info:

```
Format: YYYY-MM-DD|Full Name|Phone|Address|Plan
Example: 2025-08-01|John Smith|(832) 555-1234|123 Maple St Pearland TX|$45/wk
```

You can read this in your Stripe dashboard on every payment under **Payment details → Client reference ID**.

### Recommended Stripe settings for your Payment Links
In the Stripe Payment Link editor, enable:
- **Collect phone numbers** — backup in case they skip the modal
- **Collect billing address** — for your records
- **Collect shipping address** — use as service address backup

---

## 🔁 Referral Program — How It Works (Tolt + Stripe)

1. Customer signs up via Tolt → gets a unique referral link
2. Neighbor clicks link → 30-day cookie set
3. Neighbor subscribes via your Stripe Payment Link
4. Tolt detects the active Stripe subscription → credits referrer $10/month
5. On the 1st of each month, Tolt pays out via PayPal or ACH
6. If referral cancels → credit stops automatically next cycle
7. Referrer sees everything live in their Tolt dashboard

**Tolt commission setting:** Set as a flat $10/month recurring reward (not percentage).

---

## 📐 Pricing Tiers

| Plan | Yard Size | Weekly Rate | Monthly (approx) |
|------|-----------|-------------|------------------|
| Standard | Up to 10,000 sq ft | $45/week | ~$180/month |
| Large | 10,001 – 15,000 sq ft | $60/week | ~$240/month |
| Custom | Over 15,000 sq ft | Quote required | — |

---

## 🗂 File Structure

```
gulfcoastmow/
├── index.html      ← entire site (home + referral page)
└── README.md       ← this file
```

### When to split into multiple files
Consider splitting when you add:
- A blog or city-specific landing pages
- A backend form handler (Node/Python)
- Google Analytics or tag management scripts
- A separate admin or customer portal

---

## 🛠 Tech Stack

- **HTML/CSS/JS** — no frameworks, no build tools
- **Fonts** — Barlow Condensed + DM Sans via Google Fonts
- **Images** — Unsplash (free commercial license)
- **Payments** — Stripe Payment Links (no backend required)
- **Referrals** — Tolt.io (Stripe-native affiliate tracking)
- **Hosting** — GitHub Pages (free)

---

## 📍 Service Area

Currently serving:
- Pearland, TX
- Manvel, TX
- League City, TX

To add new cities, update the hero badge and testimonials section in `index.html`.

---

## 📞 Support & Business Info

| Item | Value |
|------|-------|
| Email | hello@gulfcoastmow.com |
| Service area | Pearland · Manvel · League City, TX |
| Plans | $45/wk (standard) · $60/wk (large) |
| Referral payout | $10/month per active referral, no cap |
| Guarantee | 7-day re-mow or refund |

---

*Last updated: 2025*
