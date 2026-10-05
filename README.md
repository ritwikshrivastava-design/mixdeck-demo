# Mixdeck — Amplitude demo site

A fictional music-creation app used to demo Amplitude's 2026 Enterprise capabilities live.
Everything in it is synthetic. Do not point it at a customer project.

## 1. Put it online (GitHub Pages — approved hosting)
1. Create a repository (e.g. `mixdeck-demo`) in your GitHub account or the team org.
2. Upload `index.html` to the root.
3. Settings → Pages → Deploy from branch → `main` / root. Wait about a minute.
4. Open `https://<user>.github.io/mixdeck-demo/?key=YOUR_MAIN_PROJECT_API_KEY`
   The key is remembered in the browser. To add the Portfolio project: `?sat=SATELLITE_KEY`.

You can also hard-code the keys in the `MIXDECK_CONFIG` block at the top of `index.html`.
Set `serverZone` to `"EU"` if the demo org is in the EU data centre.

## 2. What is instrumented
- Unified Script: Analytics + Session Replay (100% sample) + Web Experiment
- Guides & Surveys (engagement script)
- Autocapture: page views (incl. hash changes), clicks, forms, rage and dead clicks, web vitals
- Custom events: Screen Viewed, Track Played, Remix Started, Create Project Clicked, Track Added,
  Track Recorded, Collaborator Invited, Song Published, Mastering Preset Selected, Mastering Started,
  Mastering Completed, Paywall Viewed, Checkout Started, Checkout Abandoned, Trial Started (with revenue),
  Free Plan Kept, Promo Code Applied, SongStarter Opened, AI Prompt Submitted, AI Response Shown,
  AI Response Rated, AI Idea Opened In Studio, Signed In

## 3. Stable selectors for Guides & Surveys and Web Experiment
| Element | Selector |
|---|---|
| Hero CTA | `#hero-start-cta` |
| Add track | `#add-track-btn` |
| Invite collaborator | `#invite-btn` |
| Publish song | `#publish-btn` |
| Export WAV (paywall trigger) | `#export-btn` |
| Membership headline / subhead | `#membership-headline`, `#membership-subhead` |
| Trial CTA | `#trial-cta` |
| Price | `#member-price` |
| Promo "Apply" (does nothing on purpose — rage clicks) | `#promo-apply` |
| SongStarter input | `#prompt` |

## 4. Presenter tools
Open `#/control` (not in the nav): set keys, sign in as a persona, reset identity, and seed
30 days of synthetic history (600 creators ≈ 40K events). Seed **at least a day before** the call.

## 5. AI Feedback
`ai_feedback_sample.csv` holds 30 fictional reviews, tickets and survey answers. Upload it as a
file source in AI Feedback; map `text` as the feedback field.
