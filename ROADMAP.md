# Briscoe Capital — Roadmap to a Fully Functional, Deployed Site

_Legend:_ **[You]** = Dylan provides a decision or asset · **[Me]** = I build it · **[Together]** = collaborative

---

## 1. Where the site stands today (honest audit)

### What's strong
- **Design & brand.** Premium, cohesive: real BC monogram, correct brand orange (#fc2f00), navy/cream system, Instrument Serif + Inter, real Texas photography, the pinned "Grounded in Texas" scroll, hero parallax. It clears the "beautiful, credible firm" bar.
- **Structure & copy.** Logical narrative (Hero → Credibility → Mission → Who We Work With → Criteria → Approach → Process → Story → Partners → CTA). Copy is now tight and scannable.
- **Fundamentals wired.** Mobile nav, scroll-reveal animations, smooth-scroll anchors, responsive layout, reduced-motion handling, favicons, Dylan's headshot (watermark removed).

### Functional gaps (nothing here actually "works" yet as a business tool)
- **No intake form.** 0 `<form>` elements. A seller/broker cannot submit a deal with structured info — only email a **personal Gmail** (`dylanbriscoe@gmail.com`).
- **Dead CTAs.** Both "Schedule a Call" buttons are `href="#"`. No scheduling link exists.
- **Personal email as the front door.** Weak trust signal for lenders/brokers; should be a branded address.
- **No confidentiality path.** Sellers care deeply about discretion; there's no NDA note or confidential-submission language.

### Positioning gaps (to actually convert the 3 audiences)
- **Sellers/owners:** need a low-friction, confidential "Submit Your Business" form + reassurance about what happens next.
- **Brokers:** need clear criteria (✓ done) **plus** a fast structured submission and a downloadable one-pager they can circulate.
- **Lenders / SBA credibility:** need entity legitimacy signals — branded domain + email, a named entity (LLC), physical presence, real bios, and ideally a short investment-thesis PDF. The look is there; the _proof_ artifacts are not.

### Technical/ops gaps
- No SEO or social metadata (OG/Twitter), no JSON-LD, no canonical, no `sitemap.xml`/`robots.txt`.
- No analytics — can't measure visits or conversions.
- Not deployed, **no domain, not under version control.** Single static `index.html` (which is good — cheap, fast, secure to host).

---

## 2. The sprint plan

### Sprint 0 — Decisions & assets _(unblocks everything)_ **[You]**
Cannot start the build meaningfully until these are chosen. Details in §3.
- Domain, branded email, scheduling tool, form-destination, deploy host, entity details, Bradley's photo/bios.

### Sprint 1 — Make it functional **[Me, with your inputs]**

**1a. Brand voice & copy — warm, owner-first, succession-minded** _(first pass DONE)_
- Reframed the emotional touchpoints (hero, credibility bar, mission, "for owners," approach, process, story, final CTA) to lead with the **seller's stakes** — their people, their name, their legacy — and to feel welcoming rather than transactional. Original wording; tone inspired by legacy-focused acquirers like Gloria Avenue Partners (studied for feel, not copied).
- Established four voice pillars now running through the site: **(1)** the sale is a beginning, not an end ("carry your business forward"); **(2)** an unhurried, **confidential** process with **seller agency at every step** ("you decide whether we move forward"); **(3)** operator-owners who are **present** ("we're the ones who show up"); **(4)** protection of **team, customers, and culture** ("we don't strip and flip").
- ✅ **"Our Promise to Owners"** section built (after Approach): a signed, four-point commitment — people, name, customers, long-term — closing with "— Dylan & Bradley Briscoe."
- _Remaining:_ an **FAQ** (confidentiality, timeline, what happens to my team) and **humanizing bios** for Dylan & Bradley (Sprint 2) — the biggest lever for authenticity, since legacy-minded sellers buy the _people_ first.

**1b. Deal intake & scheduling** — ✅ **BUILT (one input needed to go live)**
- ✅ **"Submit Your Business" confidential intake form** now lives in the contact section: name, email, phone, business name, industry, location, revenue, EBITDA/SDE, timeline, reason for selling, message, + confidential-consent checkbox. Required = name, email, business name, location, consent (rest optional, to stay low-friction).
- ✅ **Thank-you success state**, inline HTML5 validation, and honeypot spam protection all wired.
- ✅ **Confidentiality reassurances** on the form ("Every submission is strictly confidential" / "No pressure, no obligation").
- ✅ **`mailto:` fallback** + graceful error message if the send ever fails.
- ⏳ **YOUR ONE STEP TO GO LIVE:** get a free **Web3Forms access key** (30 sec at web3forms.com — enter the inbox you want deals sent to). I paste it into the form's `access_key` field and submissions start landing in your inbox. Until then the form validates but the send is inert.
- ⏳ **Scheduling:** "Schedule a call" currently opens a pre-filled email; give me a Calendly/cal.com link and I'll swap it in.
- ⏳ **Later:** point `mailto:` + Web3Forms at the **branded** email once it exists; optionally mirror submissions to Airtable/Sheets.

### Sprint 2 — Credibility & content **[Together]**
- **Bios** for Dylan & Bradley + confirmed titles; swap in Bradley's headshot (same watermark/crop treatment).
- **Investment one-pager (PDF)** — thesis, criteria, process, contact — downloadable for brokers/lenders. High-leverage SBA-credibility asset.
- **Entity + presence:** LLC name, formation state, service-area/address, optional phone.
- **Legal pages:** Privacy Policy + Terms (required once a form collects data) and a short Confidentiality statement.
- **Optional:** FAQ (confidentiality, timeline, what happens after you submit), advisor/partner logos if any.

### Sprint 3 — SEO, sharing & analytics **[Me]** — ✅ mostly DONE
- ✅ **Branded share image** (`images/og-image.jpg`, 1200×630) + full **Open Graph & Twitter** meta — links now preview properly on LinkedIn, iMessage, X, Slack.
- ✅ **JSON-LD** structured data (FinancialService: name, logo, area served = Austin/Dallas/Texas, founders, email).
- ✅ `sitemap.xml`, `robots.txt`, `favicon.ico`, canonical, theme-color, refined meta description.
- ✅ **Perf/a11y wins:** lazy-loading + explicit dimensions on images (no layout shift), `decoding=async`, semantic labels.
- ⏳ **Analytics — your pick:** Plausible/Fathom (privacy-friendly, ~$9/mo, recommended) or GA4 (free). Give me the word and I'll drop in the snippet + track form-submit and schedule-click as conversions.
- ⏳ **Domain swap:** all canonical/OG URLs currently assume `https://briscoecapital.com/` — I'll update if the real domain differs.
- ⏳ **Full Lighthouse run** happens post-deploy (needs the live URL); target ≥ 95 across the board.

### Sprint 4 — Deploy & launch **[Together]**
- Put the project under **git**; push to a repo.
- Deploy static site to **Vercel** (you already use it) or Cloudflare Pages — free tier, auto-SSL, global CDN.
- Connect **domain + DNS**, verify SSL, set up **email forwarding/inbox**.
- **End-to-end production test:** form deliverability, scheduling, all links, 404 page, mobile devices, Safari/Chrome/Firefox.
- Flip DNS → **launch.**

### Sprint 5 — Post-launch / ongoing **[Together, later]**
- **Deal-flow pipeline:** where submissions live (email + Airtable/Notion board) so nothing slips.
- Optional: insights/blog, LinkedIn company page linking back, broker outreach list, light retargeting.

---

## 3. Your homework (only you can provide these)

| # | Decision / Asset | Recommendation |
|---|------------------|----------------|
| 1 | **Domain** | Secure `briscoecapital.com` (or `.co`/`brisco ecapitalgroup.com`). I can check availability & options. |
| 2 | **Branded email** | `dylan@briscoecapital.com` via Google Workspace (~$6/mo). Biggest cheap credibility win. |
| 3 | **Scheduling link** | Free Calendly or cal.com; send me the URL. |
| 4 | **Form destination** | Which inbox receives deals + do you want a copy in a spreadsheet/Airtable? |
| 5 | **Form backend** | I recommend Formspree or Web3Forms (static-friendly). OK to proceed with one? |
| 6 | **Deploy host** | Vercel (you have it) or Cloudflare Pages. |
| 7 | **Entity details** | LLC legal name + formation state, service area/address, optional phone — for footer + legal. |
| 8 | **People** | Bradley's headshot; 2–3 sentence bios + titles for both of you. |
| 9 | **Confidentiality stance** | Simple "confidential submission" line, or a formal NDA option for sellers? |

---

## 4. Launch checklist (Sprint 4 gate)
- [ ] All CTAs point somewhere real (no `href="#"`)
- [ ] Test deal submission received in inbox (+ spreadsheet if enabled)
- [ ] Scheduling link opens live calendar
- [ ] Branded email live and forwarding
- [ ] OG share preview renders on LinkedIn/iMessage
- [ ] Analytics recording visits + conversions
- [ ] Lighthouse ≥ 95 across the board; passes on real mobile
- [ ] Privacy/Terms linked in footer
- [ ] 404 page; sitemap/robots present
- [ ] Cross-browser + cross-device pass

## 5. Recommended stack (keep it simple)
Static `index.html` → **Vercel/Cloudflare Pages** (host) · **Formspree/Web3Forms** (intake) · **Calendly** (scheduling) · **Google Workspace** (email) · **Plausible** (analytics). No server to maintain, near-zero cost, fast and secure — which itself reads as credible.

---

## Priorities if you do nothing else
1. **Domain + branded email** (credibility front door).
2. **Working confidential intake form** (the site's actual job).
3. **Deploy + SEO/share metadata** (so it exists and looks real when shared).
