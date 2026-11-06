# Boof Valley Pricing and Cost Laboratory

Mission 3 is a separate browser application for exploring the pricing of Boof Valley's All Star hoodie. It uses the Mission 2 mesh model, corrects the displayed branding to BOOF VALLEY, and retains the original tee research as historical background. It does not modify MKTG-project-3 or confirm the student's decision automatically.

## Run and deploy

Requires Node 22+ and npm. Run `npm install`, `npm test`, `npm run dev`, and `npm run build`. The production `dist/` uses relative Vite asset paths. Set GitHub Pages Source to GitHub Actions; the included workflow tests, builds, and deploys `main`.

## Student workflow

- Business overview shows the interactive hoodie, live price and quantity inputs, operating results, cost breakdown and startup cash. Drag the hoodie to rotate; scroll to zoom.
- Cost structure offers 21 suggested expenses with individual sliders, numeric inputs, optional expense toggles, reference markers, source links, assumptions, classification and frequency controls. Use Edit to change descriptions and cost allocation. Add and remove custom expenses; restore suggested amounts.
- Products and pricing allows extra hypothetical products, descriptions, prices, quantities, additional per-unit costs, features and add-ons. Existing unit-cost rows remain active: avoid entering their cost again as an additional unit cost. Bundle costs and quantities must both refer to the bundle. Subscription models are intentionally inactive for this physical apparel venture.
- Break-even analysis uses constant prices, unit costs and the current assumed sales mix. Shared overhead is counted once and allocated by revenue, units or equal shares for product reporting. Hover chart points for values. Choose an operating-cost category to inspect the underlying expenses.
- Financial scenarios offers lean, typical and expansion cost presets; price and sales quantities are preserved. The previous configuration is saved before switching. Custom scenario comparisons retain their saved horizon; preset rows use the currently selected horizon.
- Competitive position uses three observed hoodie alternatives. There is only one direct comparable; the direct sample median is not a market-wide estimate. The seven earlier tee offers are excluded from hoodie statistics.
- Pricing decision review evaluates financial and evidence risks using visible criteria. Changed model inputs make an evaluation outdated. Write at least 20 characters of justification. Major financial warnings require acknowledgment. After confirming, download both Pricing_Decision_Report.docx and Pricing_Decision_Data.json for Mission 4.

Browser edits save immediately to local storage. Export model creates a portable working JSON; Import restores it and clears prior evaluation/confirmation. Browser storage can be lost when switching devices or clearing data. Reports contain private modeled costs; customerFacing in the confirmed JSON intentionally contains only public product information.

## Cost evidence and assumptions

Checked 2026-11-06. Source links and qualifiers are bundled in src/data.js.

- Researched references: S&S public IND420XD $44.10–$50.60 catalog range; Shopify Basic $39/month month-to-month, standard card rate from 2.9% + $0.30. These are published references, not negotiated garment quotes or proof all card transactions qualify.
- Estimated costs: $6 decoration, $1.50 inbound freight, $1.25 packaging, five minutes packing labor valued at $18/hour, bookkeeping, content, insurance and domain renewal. Sticker Mule's $0.98 smaller mailer reference does not verify the $1.25 hoodie packaging allowance.
- Illustrative inputs: $5 outbound shipping subsidy, $2 returns reserve, $150 registration allowance. These need actual location, parcel and entity decisions.
- Startup cash includes samples, artwork setup, registration, equipment and the selected initial inventory. Inventory cash covers the primary product's blank, print and inbound freight. Operating profit includes those unit costs when sold, not an extra inventory expense. Equipment is depreciated over 36 months by default.
- No office, land purchase or full-time staff is assumed. Storage and nonfulfillment founder pay are optional disabled rows. Desired fit and quality need sample testing; volume is not a forecast.

## Calculation and risk definitions

Revenue = price × quantity. Variable costs include per-unit rows plus percentage-of-revenue rows. Unit contribution = price − variable cost per unit. Business profit = combined contribution − actual combined fixed costs. Break-even = fixed costs / weighted unit contribution, holding unit sales mix constant. Units round upward; sales revenue uses the exact intersection. Zero or negative weighted contribution has no finite break-even through extra sales. Monthly quantities and recurring costs scale together for annual reporting. One unit per order is assumed for payment flat fees.

The review labels unsustainable when weighted contribution ≤ 0; high when there is base loss, a noncontributing product, margin of safety below 20%, or a loss under a 20% lower-volume or 10% higher-variable-cost stress test; moderate for positive modeled tests with unresolved evidence/positioning gaps; lower only when no gaps remain. These are teaching thresholds, not probabilities of business failure.

## Confirmed export schema

Schema version 1.0. DOCX and JSON are generated from the same immutable confirmed snapshot. It includes venture and original website URLs, product/pricing data, all cost assumptions, source provenance and dates, annualized modeled costs, financial results, risk evaluation, saved scenarios, student justification, warning acknowledgments and confirmation time. customerFacing excludes costs, quantities, profit, justification and private risk data. Editing any model input clears confirmation. Imported working configurations always require new evaluation and confirmation.

## Verification

`npm test` independently checks single/multiple-product arithmetic, allocation, percent fees, horizon conversion, capital depreciation, startup cash, sales mix, no-volume cases, zero/negative contribution, stale reviews, justification, warning acknowledgment and import rejection. Browser QA uses `?test=1`, an isolated, visibly labeled session that does not write to the student's saved model. QA exports have a QA_TEST_ filename prefix and QA_TEST_ONLY record type. No QA snapshot is shipped as the student's decision.
