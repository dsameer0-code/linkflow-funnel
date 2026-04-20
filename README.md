# LinkFlow Pro — Complete Funnel Package
**Built by NextGen Web LLC / AI Growth Architect™**

## Funnel Architecture

```
/ (→ /sales)
├── /sales          Front-end offer   $97 OTO  [JVZOO FE PRODUCT]
├── /upsell         OTO1 Agency License $197   [JVZOO OTO1]
├── /downsell       OTO1 DS Accelerator $47    [JVZOO DS1]
├── /bonus          Value stack display
├── /thankyou       Post-purchase access page
└── /compliance     Earnings / Privacy / Terms / Refund / Affiliate
```

## Files
- `sales/index.html`       — Full-copy sales page, countdown timer, FAQ, pricing
- `upsell/index.html`      — OTO1 agency license with 15-min urgency timer
- `downsell/index.html`    — DS1 accelerator pack $47
- `bonus/index.html`       — 5-bonus value stack ($1,585)
- `thankyou/index.html`    — Post-purchase confirmation + access steps
- `compliance/index.html`  — Earnings disclaimer, privacy, ToS, refund, affiliate
- `vercel.json`            — Clean URL routing for Vercel deployment

---

## Step 1: Deploy to Vercel

```bash
npm i -g vercel
cd linkflow-funnel
vercel --prod
```

Or drag-drop into vercel.com dashboard. Clean URLs auto-configured via vercel.json.

---

## Step 2: Replace Stripe Payment Link Placeholders

Search-and-replace these strings across all HTML files:

| Placeholder | Replace With |
|---|---|
| `STRIPE_PAYMENT_LINK_FRONTEND` | Your Stripe payment link for $97 product |
| `STRIPE_PAYMENT_LINK_UPSELL` | Your Stripe payment link for $197 upsell |
| `STRIPE_PAYMENT_LINK_DOWNSELL` | Your Stripe payment link for $47 downsell |

### To create Stripe Payment Links:
1. Stripe Dashboard → Products → Create Product
2. Create 3 products: LinkFlow Pro ($97), Agency License ($197), Accelerator Pack ($47)
3. For each: Payment Links → Create link → one-time payment → no subscription
4. Set success URL to your Vercel domain: `https://your-domain.vercel.app/thankyou`
5. Copy each payment link and paste above

---

## Step 3: JVZoo Product Setup

### Front-End Product
1. JVZoo → Seller → Add Product
2. Product Name: LinkFlow Pro
3. Price: $97 one-time
4. Payment processor: Stripe (connect via JVZoo Stripe integration)
5. Thank you page: `https://your-domain.vercel.app/thankyou`
6. JVZoo IPN enabled: YES

### OTO1 — Agency License
1. Add as OTO to front-end product
2. Price: $197 one-time
3. Upsell page URL: `https://your-domain.vercel.app/upsell`
4. Downsell product: Accelerator Pack ($47)

### Downsell — Accelerator Pack
1. Price: $47
2. Page URL: `https://your-domain.vercel.app/downsell`

### Funnel Flow (JVZoo)
```
Purchase FE ($97) → Redirect to /upsell
  Accept OTO1 ($197) → Redirect to /thankyou
  Decline OTO1 → Redirect to /downsell
    Accept DS1 ($47) → Redirect to /thankyou
    Decline DS1 → Redirect to /thankyou
```

---

## Step 4: ProductDyno Collection Setup

1. ProductDyno → Collections → Create Collection: "LinkFlow Pro Members"
2. Create 3 products:
   - LinkFlow Pro (FE)
   - Agency License Add-On
   - Accelerator Pack Add-On
3. Add all bonuses as downloadable assets under "LinkFlow Pro"
4. Connect JVZoo IPN for automatic access delivery:
   - JVZoo → Product Settings → IPN URL: ProductDyno IPN endpoint
5. Access URL format: `https://members.productdyno.com/m/linkflow-pro`

---

## Step 5: Update Thank You Page

In `thankyou/index.html`, update:
- Dashboard URL: Replace `https://app.linkflow.io/login` with your actual member portal URL
- Support email: Replace `support@linkflow.io` with your actual support email

---

## Step 6: GoHighLevel Integration (Optional)

1. Add GHL webhook in `sales/index.html` form submission (if adding optin before buy)
2. Webhook URL: Your GHL account webhook endpoint
3. Tags to apply: `linkflow-pro-buyer`, `oto1-declined` (conditional)

---

## Compliance Notes

- Earnings disclaimer is linked from footer of all pages ✓
- Affiliate disclosure is included ✓
- Refund policy (30-day MBG) is documented ✓
- Privacy policy covers data collection ✓
- FTC compliant testimonials (individually achieved, not guaranteed) ✓

---

## Support
sdhawan1971@gmail.com | NextGen Web LLC | oncehub.com/PAGE-A2441E2BBC
