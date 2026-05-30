# Italy Trip — Complete Context for Next Claude

> **You're picking up this conversation from a different Claude session.** Read this whole file before responding. It contains everything you need to continue the work: trip state, decisions made (and why), things considered + rejected (and why), workflows used, pending tasks, user preferences. Self-contained — you do not need to read other files to be useful, though they exist if you want depth.

---

## TL;DR — Where things stand

- **Trip:** Lev + 1 friend, Italy road trip, **Sun May 31 → Sun Jun 7, 2026**, 8 days, ~960 km. Northern Italy lakes + Dolomites + Venice + Milan.
- **Status:** Plan is essentially complete and reviewed. Mobile guide site is trip-ready. Live URLs deployed.
- **Repo:** `levgou/italy-trip-2026` (PUBLIC) — https://github.com/levgou/italy-trip-2026
- **Live sites:**
  - Mobile guide (main trip tool): https://levgou.github.io/italy-trip-2026/guide.html
  - Desktop slide deck: https://levgou.github.io/italy-trip-2026/
- **Local path:** `/Users/levgourevitch/Documents/Documents - QG4ML4QJ1H/private/italy/`
- **GitHub auth note:** Two accounts exist locally (`lev-loris` and `levgou`). Repo is owned by `levgou`. Before pushing run: `gh auth switch -h github.com -u levgou`.

---

## Table of Contents

1. [Your job (next-Claude instructions)](#your-job)
2. [User profile & tone](#user-profile)
3. [Trip facts](#trip-facts)
4. [The 8-day plan (full, inlined)](#the-plan)
5. [A/B decision history + reasoning](#ab-decisions)
6. [Considered + rejected](#considered-rejected)
7. [Bookings matrix](#bookings)
8. [Recommended A/B pairings](#pairings)
9. [File layout](#files)
10. [Image work state](#images)
11. [Workflow patterns](#workflows)
12. [Pending tasks](#pending)
13. [Open questions — all resolved](#resolved)
14. [Tech notes & gotchas](#tech)

---

<a name="your-job"></a>
## 1. Your job

You're continuing trip planning + iteration. The big picture is settled. Likely incoming tasks:
- Quick lookups ("which restaurant on Day X?") — pull from the plan below.
- New ideas to evaluate ("does X fit?") — use the geographic + scheduling logic.
- Mobile guide polish (image quality, content tweaks).
- **Pending: desktop slides Days 4-8 image cards** (see Pending Tasks).
- **Pending: ~13 low-res images** still need redo (see Image state).
- Possible: more places considered, A/B variants added.

Mode: be a smart sidekick. Don't fake certainty — the plan was built with verification (cable car hours checked, toll road reservation requirements confirmed, etc). Verify before claiming.

---

<a name="user-profile"></a>
## 2. User profile & tone

**Lev (Israel, software eng, makes the calls).**
- Casual + fun. Gopnik banter in Cyrillic OK (братан, давай, погнали). Sparingly. Always Cyrillic, never transliterated.
- Technical content stays in English.
- **Be terse.** Skip recap, skip restating context the user already has. One-line answers when one-line covers it.
- **Caveman mode active in current session** — drop articles/filler/pleasantries/hedging. Fragments OK. Code/commits/security stay normal. Pattern: `[thing] [action] [reason]. [next step].` E.g. NOT: "Sure! I'd be happy to..." YES: "Bug in X. Fix Y. Next:"
- **One step at a time** for multi-step work. Present each, wait for review, don't batch.
- **Never implement fixes when asked to "check" or "investigate".** Report first, wait for go-ahead.
- **"We don't skip"** — when offering to skip optional items, user generally says no, do them.

**Tools:**
- `pycharm` CLI to open files, not `open -a "PyCharm"`.
- `jq` for JSON. Avoid python one-liners except for pragmatic mechanical tasks.
- **Don't `Read` image files** — burns tokens. Use `file` or `sips -g pixelWidth`.
- For commands user runs themselves: show in fenced code block + `pbcopy` to clipboard.
- `opr <file>` reveals in Finder (fish alias — tmux send-keys, not Bash).
- Don't write em-dashes (—) in code; user prefers - in code files. (Body text OK.)
- No `from __future__ import annotations` (Python 3.13 already).
- Run `ruff check --fix .` after Python changes (irrelevant here but for context).

---

<a name="trip-facts"></a>
## 3. Trip facts

- **Who:** Lev + 1 friend (2 guys).
- **Dates:** Sun May 31 → Sun Jun 7, 2026. 8 days. Flight MXP land 11am Sun, depart MXP 20:00 next Sun.
- **Car:** Rental, pick up + drop off MXP.
- **Total driving:** ~960 km.
- **Budget vibe:** Agriturismi, B&Bs, pensioni. Nice but not fancy. Local trattorie not tourist traps.
- **Season:** Late May / early June = pre-peak. Water still chilly (16-18°C lakes, 12-14°C alpine = brave dip only). **Pragser/Braies road OPEN** at this date (restrictions only Jul 10 - Sep 10).
- **Route:** Milan → Lake Maggiore → Lake Como → Lake Garda → Trentino (Molveno) → Dolomites (Lago di Braies) → Venice → Milan.

---

<a name="the-plan"></a>
## 4. The 8-day plan (full)

Each day below has the A/B fork where applicable. "A/B = schedule toggle only." Activities, restaurants, hotels are all shown at once with plan-affinity badges. The mobile guide (guide.html) has the interactive version.

### Day 1 (Sun May 31) — MXP → Stresa, Lake Maggiore
- **Drive:** MXP → Stresa, 60 km, ~1h (autostrada to Arona, then SS33 lake shore last 20 km for first lake views).
- **A/B fork** = where's the long meal:
  - **Plan A — Lunch on Isola dei Pescatori** (seated 90-min on lake terrace, slower pace, lighter dinner).
  - **Plan B — Maximum islands + proper dinner Stresa** (quick panino lunch, both islands done properly, real dinner).
- **Sights:** Borromean Islands (Isola Bella = baroque palace + gardens, Isola dei Pescatori = fishing village).
- **Restaurants:** La Rampolina (top pick, osteria with lake+islands terrace), Trattoria Lo Stornello, Osteria degli Amici.
- **Gelato:** L'Angolo del Gelato (try caramello salato).
- **Sleep:** Agriturismo Nel Giardino di Dafne (~100-130 EUR, breakfast basket) OR Hotel La Palma (~120-150 EUR, 4-star lungolago).
- **Swim:** Spiaggia Lido di Stresa (pebbly, ~18-19°C).
- **Rain backup:** Borromeo Castle (Rocca di Angera, 30 min drive).

### Day 2 (Mon Jun 1) — Stresa → Lake Como
- **Drive:** Stresa → Sasso del Ferro (10 min) → Como, ~1.5h, 60 km. SS34 lake shore. Option: Laveno-Intra car ferry across Maggiore (~15 EUR, 20 min).
- **A/B fork** = pace:
  - **Plan A — Do it all, quick lunch:** Sasso del Ferro chairlift → quick slice lunch in Como → Brunate funicular + Faro Voltiano → Greenway hike. 3 lake angles. Tight timing.
  - **Plan B — Long lunch, skip Brunate:** Sasso del Ferro → seated 90-min lunch in Como → Greenway (longer/slower). Drops the most-skippable activity (Brunate = "Como from above"). Eats properly.
- **Activities:** Sasso del Ferro cable car, Brunate funicular + Faro Voltiano lighthouse, Greenway del Lago di Como (Colonno-Sala Comacina section), e-bike Menaggio-Sorico alt.
- **Restaurants:** Trattoria del Cacciatore (Brunate, lake-view hilltop), Osteria del Gallo (Slow Food 2025, Cortesella), Crotto del Sergente (Lora), Osteria il Governo (Lezzeno).
- **Local dish:** missultini (sun-dried lake fish).
- **Gelato:** Gelateria Guidi (best in Como).
- **Sleep:** Agriturismo Treterre (top pick, infinity pool, ~90-120) / B&B Vista Lago (9.2 rated, lake balcony every room) / Agriturismo Al-Marnich (Schignano, bio restaurant).
- **Rain backup:** Villa Carlotta (botanical garden + art museum, Tremezzina).

### Day 3 (Tue Jun 2) — Como → Sirmione (Lake Garda)
- **Drive:** Como → Sirmione, 100 km, ~2h via A4 (Bergamo/Brescia).
- **A/B fork** = afternoon (lunch in Sirmione for both):
  - **Plan A — Monte Baldo wow afternoon:** Quick Sirmione town → drive to Malcesine (~50 min east shore) → Monte Baldo rotating cable car to 1760m, ridge walk, Dolomites visible. Verified hours: first up 8:15, last up 18:00, last down 18:45 (June 2026).
  - **Plan B — Sirmione + thermal swim:** Full Sirmione → Grotte di Catullo Roman ruins at peninsula tip → Jamaica Beach (free wild swim with thermal bubbles from underwater springs) → optional Aquaria Spa (book ahead, ~50-70 EUR).
- **DROPPED: Isola del Garda** — was the original Day 3 anchor. Removed because too touristy, guided-tour format doesn't fit trip vibe, was the only mandatory advance booking.
- **Lunch (both plans):** La Speranzina (upscale, ~40-60), Trattoria La Rucola (Michelin-recognized, ~35-50), Trattoria Clementina (no-tourist authentic, ~25-35).
- **Dinner:** Osteria del Vecchio Fossato, Casa dei Pescatori (on the water near Castello).
- **Local dish:** bigoli con le sarde del Garda.
- **Sleep:** Agriturismo La Filanda (historic 1800s farmhouse, ~80-120) / B&B da Beatrice / Agriturismo Il Ghetto.
- **Nightlife:** Desenzano del Garda (15 min away) = THE Garda nightlife hub.

### Day 4 (Wed Jun 3) — Garda → Strada della Forra → Riva → Ponale → Molveno
- **Drive:** ~2.5h total, split: west Garda shore (~1h to Limone) → Strada della Forra detour → Riva (~45 min) → Molveno (~1h45). Order matters: Forra first (south), then Ponale (north), then inland.
- **A/B fork:**
  - **Plan A — Cliff terrace lunch, short Ponale:** Forra → Tremosine Terrazza del Brivido viewpoint → seated lunch on cliff terrace 350m above lake (Miramonti or La Forbisicla) → short Ponale hike (1.5h RT to first tunnels).
  - **Plan B — Hike priority, terrace = coffee:** Forra → Tremosine viewpoint quick spritz → medium Ponale hike (3h RT to Belvedere). Lunch = panino at Riva trailhead.
- **The big drive of the trip:** Strada della Forra (SP38) — 6 km gorge road, hairpins through tunnels carved in rock, James Bond (Quantum of Solace). Non-negotiable, in both plans.
- **Hike:** Sentiero del Ponale — old road carved into cliff face above Garda, tunnels through rock, views straight down to turquoise water. 6 km RT short (~2h, +200m) or 9.5km full to Pregasina (~3h, +450m).
- **Sights Molveno:** Lake Molveno (5 Vele award = best Italian beach), Fortini di Napoleone walk.
- **Restaurants Molveno:** Trattoria al Faggio, Ristorante All'Aquila Nera e Cima Tosa.
- **Local dish:** canederli (bread dumplings with speck/cheese).
- **Sleep Molveno (2 nights):** Agriturismo Ai Castioni (lake+Brenta view balcony) / B&B Il Nido (includes FREE Dolomiti Paganella Guest Card = free cable cars!) / B&B Le Coccole.
- **Nightlife Riva pre-Molveno drive:** Sailing Bar (ship-shaped, sunset aperitivo + DJ).

### Day 5 (Thu Jun 4) — Brenta Dolomites + Lago di Tovel (Molveno base)
- **Drive:** Molveno ↔ Tovel ~30 min each way. Chill day, no transfer.
- **A/B fork** = legs:
  - **Plan A — Big hike: Rifugio Croz dell'Altissimo.** Cabinovia from Molveno → Pradel (does first 800m vertical), then hike ~6 km RT, 3h, +400m, medium. Forest paths opening into Brenta. Eat lunch at rifugio (canederli, polenta, strudel). Tovel afternoon.
  - **Plan B — Pradel chill + lake day.** Cabinovia → Pradel → easy Sentiero di Sciury loop (2.5 km, 1h) + walk to Rifugio La Montanara (25 min from top) for light lunch with Brenta panorama. Tovel afternoon. Then back to Molveno lake beach + swim + canoa/pedalò.
- **Pairing-tip-with-Day-6 noted in mobile guide:** "Hard" = real hiking (Rifugio Croz 3h/+400m OR Day 6 Tre Cime walk at 2300m). "Easy" = cable car + flat strolls + lake. Don't stack two hard days. Best pairings: A5+A6 or B5+B6.
- **Tovel:** 4 km loop, ~1.5h flat. "The Red Lake," forest setting, very cold (1178m altitude).
- **Sleep:** Same as Day 4 (2nd Molveno night).

### Day 6 (Fri Jun 5) — Molveno → Lago di Braies + Dolomites
- **Drive:** Molveno → Pragser Wildsee, 130 km, ~2h. Through Val di Non → Val di Sole → Val Pusteria. Mountain roads. Fill up gas before leaving Molveno.
- **A/B fork:**
  - **Plan A — Braies + Val Pusteria villages.** Drive → walk Braies (3.5 km loop, ~1.5h, easy) → rowing boat 30 min → lunch near lake → explore Dobbiaco, Monguelfo, Villabassa villages → maso check-in → Gasthaus dinner.
  - **Plan B — Braies + Tre Cime detour.** Drive → Braies walk → quick lunch → drive to Lago di Misurina (~1h, 3 km easy loop, Tre Cime visible from shore) → toll road up to Rifugio Auronzo (BOOK AT pass.auronzo.info, 40 EUR/car) → 1h walk of Tre Cime panorama loop → drive back to Val Pusteria. +2h driving total.
- **Braies access (June 2026):** Road **OPEN**, no reservation. Restrictions only Jul 10 - Sep 10. Rowing boats at north end.
- **Tre Cime toll road (June 2026):** MANDATORY online reservation at pass.auronzo.info. 40 EUR/car, ticket valid 12h from chosen entry slot. Casello staffed 8:00-20:00. Shuttle line 444 alt (skip car).
- **Restaurants Val Pusteria:** Gasthaus in Dobbiaco or Monguelfo. Order speck, canederli, schlutzkrapfen (spinach-ricotta half-moons), kaiserschmarrn.
- **Sleep:** **Hanslerhof maso** (TOP PICK, 5.7 km from Braies, family farm at 1350m, insane breakfast w/ homemade speck) / Gallorosso curated maso in Dobbiaco / B&B Monguelfo/Villabassa.

### Day 7 (Sat Jun 6) — Val Pusteria → Venice
- **Drive:** ~210 km, ~3.5h south through Dolomite foothills via Belluno.
- **A/B fork:**
  - **Plan A — Push to Venice, long evening.** Tyrolean breakfast → drive → Lago di Santa Croce swim stop (1h) → Mestre by 13:30 → Venice afternoon + bacaro tour.
  - **Plan B — Cortina coffee stop.** Breakfast → Val Pusteria → Cortina d'Ampezzo (~1h, Corso Italia espresso + Basilica, 1h stop) → Venice via Belluno (~2.5h). Skip Santa Croce swim. Cortina = chic Olympic mountain town worth the detour.
- **Venice parking:** Pre-book Mestre lot at parclick.it (5-15 EUR/day) + 10-min train to Venezia Santa Lucia. Don't drive into Venice.
- **Bacaro tour Cannaregio** (3-4 stops = dinner): Cantina Do Spade (open since 1448), All'Arco, Alla Vedova (legendary polpette), Al Timon (canal-side), Taverna al Remer (HIDDEN GEM facing Grand Canal), Osteria Al Squero (Dorsoduro, overlooks gondola workshop).
- **Cicchetti to order:** baccalà mantecato su crostino (ICONIC), sarde in saor, polpette, frittura.
- **Gelato:** Gelateria Suso (near Rialto, eco), Da Nico (Zattere terrace, Gianduiotto — THE moment).
- **Sleep (1 night):** B&B in Cannaregio (RECOMMENDED, best value, near bacari, ~70-100) / B&B Dorsoduro / Mestre hotel (cheapest, less charm).
- **Nightlife:** Fondamenta della Misericordia (Cannaregio) = THE locals' canal-bar spot.

### Day 8 (Sun Jun 7) — Venice → Milan → ✈ MXP 20:00
- **Drive:** Venice → Milan, 270 km, ~3h (A4 autostrada, ~22 EUR toll).
- **A/B fork:**
  - **Plan A — Long Venice morning, no Verona, relaxed flight buffer.** Rialto fish market at dawn → last Venice wander → 11:00 leave Mestre → 14:00 lunch Milan (Trattoria Milanese dal 1933 / Antica Pesa) → 15:30 Duomo + Galleria → 16:30 Artico gelato → 17:00 MXP.
  - **Plan B — Short Verona coffee stop only (NOT a real visit).** 07:30 quick caffè → 08:30 leave Mestre → 10:00 Verona Piazza Bra + Arena exterior (~45 min coffee/gelato stop) → 10:45 **time check: behind schedule = leave NOW; ahead = quick Piazza delle Erbe peek** → 11:15 Verona → Milan → 13:00 lunch → 14:30 Duomo + Galleria → 15:30 Artico → 16:30 MXP. Flight non-negotiable.
- **The "old" Plan B with full Verona visit (Casa di Giulietta, full Piazza delle Erbe, etc) was deliberately TRIMMED** because three cities + flight in one day was too tight.
- **Last meal Milan:** Cotoletta alla milanese, risotto alla milanese (saffron), ossobuco. Order all three if possible.
- **Aperitivo if time:** Navigli canal bars (~8-10 EUR drink + free buffet — Milan ritual).

---

<a name="ab-decisions"></a>
## 5. A/B decision history + reasoning

Decisions made this trip planning, in order:

**1. Original single-track plan → A/B per day (sessions 1-2).**
Reason: each day has a real lever (long meal vs sightseeing pace, hike vs chill, etc). Two parallel timings give flexibility without cascading dependencies. Picker chooses A or B per day independently.

**2. A/B = schedule only, NOT activities/restaurants.**
Reason: tested briefly with A/B-scoped activity sections, user found it harder to compare. Switched to: schedule has A/B toggle, all activities visible at once with plan-affinity badges. Less interaction friction.

**3. Day 3 — Isola del Garda DROPPED entirely.**
Was the original Day 3 anchor (guided villa tour, 39-49 EUR/pp, closed Mondays = must book Tuesday).
Reason: too touristy, guided-tour format doesn't fit trip vibe. Bonus: removed the only mandatory advance booking, simplifying logistics.

**4. Day 3 new A/B — Monte Baldo (A) vs Sirmione thermal swim (B).**
Replaced the dropped Isola anchor. Two different vibes: active+wow (cable car to 1760m, Dolomite views) or chill+icon (Roman ruins + free thermal swim Jamaica Beach).

**5. Day 3 — Desenzano lunch alternative DROPPED.**
Earlier draft had Plan A = lunch Sirmione, Plan B = lunch Desenzano. Simplified: both plans lunch in Sirmione, A/B forks afternoon.

**6. Day 5 + Day 6 — pairing tip added.**
Don't stack two hard days. Best: A5+A6 (hike Brenta, chill Braies) or B5+B6 (chill, then Tre Cime). Spelled out: hard = real hiking, easy = cable car + flat strolls.

**7. Day 8 — Verona trimmed.**
Original Plan B had Verona Arena + Via Mazzini + Casa di Giulietta + Piazza Erbe + lunch in Verona. Too tight with 20:00 flight. Trimmed to: 45-min coffee/gelato + Arena exterior only, with explicit 10:45 time-check (behind=leave, ahead=quick piazza peek).

**8. Day 6 Plan B — Tre Cime kept after weighing alternatives.**
Considered swapping Tre Cime for Carezza (rainbow lake). Decided against: Tre Cime = peaks (different flavor from Day 6 Braies lake), Carezza would be a second lake same day = diminishing returns. Plus Carezza geographically wrong side.

**9. Days 4 ordering — flipped to Forra-first.**
Original: Ponale then Forra. Flipped to: Forra (south) first, then Ponale (north), then inland to Molveno. Geographically cleaner — no backtrack.

---

<a name="considered-rejected"></a>
## 6. Considered + rejected (with why)

These came up at various points and were evaluated against the plan. Park each, don't re-litigate unless new info.

**Carezza (Lago di Carezza / Karersee) — rainbow lake.**
- Where: Bolzano province, SS241 toward Val di Fassa.
- Why considered: stunning Insta-famous lake, emerald/rainbow water, Latemar peak reflection.
- Why rejected: only fits Day 6 (Molveno → Braies) as a +1h20 detour via Bolzano. But trip already has Braies (another iconic lake) same day = diminishing returns. AND would force dropping Tre Cime (opposite end of Dolomites). Tre Cime adds peak variety; Carezza would duplicate lake-energy.
- Verdict: skip this trip, save for a future Dolomites visit.

**Baia del Bogn — Lago d'Iseo hidden cove ("Lombardia's Thailand").**
- Where: Riva di Solto, Lago d'Iseo, between Como and Garda geographically.
- Why considered: cinematic limestone cliffs dropping into turquoise water, free wild swim spot, locals call it Thailand-of-Lombardia.
- Why rejected: only fits Day 3 (Como → Sirmione). Adds ~1h drive. Day 3 already packed (drive + Sirmione + Monte Baldo or thermal swim). And trip is already lake-heavy (Maggiore + Como + Garda + Molveno + Braies) — one more cove = diminishing returns. Bogn beats Jamaica Beach visually but Jamaica has thermal-bubble novelty + works with the rest of Sirmione.
- Verdict: skip unless user specifically wants to restructure Day 3 Plan B to swap Jamaica for Bogn.

**Cortina d'Ampezzo as Day 7 detour.**
- Why considered: chic Olympic Dolomites mountain town, on the geographic route Val Pusteria → Venice (via Belluno).
- Status: KEPT as Day 7 Plan B. ~1h detour cost. Honest read: Plan A (direct to Venice for more Venice time) is the stronger pick, but Plan B is valid if you want one more Dolomites town.

**Verona full visit on Day 8.**
- Status: TRIMMED (was full visit including Casa di Giulietta + Piazza Erbe + lunch). Now Plan B = coffee + Arena exterior only, ~45 min, time-gated. Flight non-negotiable.

**Full single-track plan (no A/B).**
- Original v1. Replaced by A/B because each day has a meaningful fork that doesn't cascade.

**Different city orderings.**
- Tried: starting with Venice. Tried: Dolomites first then lakes. Settled on lakes → Dolomites → Venice because it builds energy (low altitude → high → cultural finale). Plus flight in/out MXP makes Milan bookend natural.

---

<a name="bookings"></a>
## 7. Bookings matrix

| What | Required | Where | Cost | Day |
|------|----------|-------|------|-----|
| Venice parking (Mestre) | Yes | [parclick.it](https://parclick.it/parcheggio-venezia) | 5-15 EUR/day | 7 |
| Tre Cime toll road | **Yes if Day 6 Plan B** | [pass.auronzo.info](https://pass.auronzo.info) | 40 EUR/car (12h valid) | 6 |
| Borromean Islands ferry | No (walk-up) | navigazionelaghi.it | ~15-20 EUR/pp | 1 |
| Monte Baldo cable car | No (walk-up) | funiviedelbaldo.it | check site | 3 (Plan A) |
| Pragser Wildsee | **Not in June 2026** | n/a | n/a | 6 |
| Isola del Garda | **DROPPED FROM PLAN** | n/a | n/a | n/a |
| Aquaria Spa | If Plan B day 3 | aquaria.it | ~50-70 EUR | 3 (Plan B opt) |

---

<a name="pairings"></a>
## 8. Recommended A/B pairings

| Day | Plan A | Plan B |
|---|---|---|
| 1 | Lunch on Pescatori (long meal) | Dinner in Stresa (sightseeing first) |
| 2 | Do it all (quick lunch + Brunate + Greenway) | Long lunch in Como, skip Brunate |
| 3 | Monte Baldo cable car wow | Sirmione + thermal swim chill |
| 4 | Cliff terrace lunch (Tremosine), short Ponale | Quick lunch, medium Ponale hike |
| 5 | **Big hike Rifugio Croz** | **Pradel chill + lake day** |
| 6 | **Braies + Val Pusteria villages** | **Braies + Tre Cime di Lavaredo (with reservation)** |
| 7 | Direct to Venice (max Venice time) | Cortina coffee stop |
| 8 | No Verona, long Venice morning | Short Verona coffee stop only (45 min) |

**Pairing constraint (Days 5+6):** don't stack two hard days.
- ✅ A5+A6 (hike Brenta Thursday, chill Braies+villages Friday)
- ✅ B5+B6 (chill Pradel Thursday, push Tre Cime Friday)
- ❌ A5+B6 (two big-leg days back to back)
- ⚠️ B5+A6 (works but you skip both signature hikes)

---

<a name="files"></a>
## 9. File layout

```
/Users/levgourevitch/Documents/Documents - QG4ML4QJ1H/private/italy/
├── HANDOFF.md            # earlier cross-device doc (italy_trip_plan.md inlined)
├── CONTINUE.md           # THIS FILE — single source of truth for next session
├── FOR_FRIENDS.md        # mood-set brief to send to friends' Claudes
├── italy_trip_plan.md    # source-of-truth plain plan, all 8 days
├── index.html            # desktop Reveal.js slide deck (8 days)
├── guide.html            # mobile-first scroll page (8 days, A/B toggles, image modal)
├── browser_claude_prompt.md  # prompt to send to browser Claude for Google Maps pins
├── ab_plans_days_1-4.md  # archived first A/B draft (Day 3 since superseded — kept for history)
├── img/                  # ~100+ jpg/webp images, all locally hosted
├── .github/workflows/pages.yml  # auto-deploy on push to main
└── .git/                 # repo, remote = github.com/levgou/italy-trip-2026
```

**Live deploy:**
- Push to main → GitHub Actions auto-deploys to GitHub Pages.
- ~1 min from push to live.
- Site root = index.html (slides), /guide.html = mobile guide.

---

<a name="images"></a>
## 10. Image work state

**Total images: ~95 in img/.**

**Hero backgrounds (high-res, no watermarks):**
- hero-maggiore.jpg (2200x1238)
- hero-garda.jpg (2500x1875)
- hero-forra.jpg (1300x650)
- hero-brenta.jpg (1300x650)
- hero-braies.webp (2048x1365)
- hero-venice.jpg

**All major restaurants, hotels, sights, gelato, scenic shots have real photos** (not stock).

**Pattern in HTML:**
```html
<div class="thumb-row">
  <img src="img/place-1.jpg" alt="">
  <img src="img/place-2.jpg" alt="">
</div>
<div class="caption">...</div>
```
Each clickable → modal zoom (CSS `.modal` + JS event listener).

**Image extension policy:** always convert saves to .jpg via `sips -s format jpeg <src> --out target.jpg`. Keeps HTML refs stable when user saves arbitrary formats (.png, .webp, .jpeg).

**Still low-res (≤300px wide) — minor, mostly card thumbs that look fine at 140px display but ugly when zoomed:**
- econoleggio-2 (275px) — bike, minor
- angera-castle-2 (259px) — rain backup
- villa-carlotta-2 (201px) — rain backup
- il-nido-2 (194px) — hotel 2nd shot
- le-coccole-1 (274px) — hotel
- bb-beatrice-2 (275px) — hotel 2nd
- gallorosso-maso (300px) — generic curated farm-stay site
- della-pesa-1 (300px) — Milan trattoria
- suso-1 (200px) — Venice gelato
- al-remer-1 (275px) — Venice bacaro
- rifugio-croz-1 (275px) — Day 5 hike
- sciury-1 (259px) — Day 5 Plan B trail
- angolo-gelato-3 (201px) — Stresa gelato 3rd shot
- tre-cime-1 (268px) — Tre Cime (just drop it, tre-cime-2 is 2560px and great)

User-spec for redo loop:
- Tell user to **click image in Google results FIRST** (full panel opens), then save — gets full-res, not thumbnail.
- Open via `open "https://www.google.com/search?q=...&tbm=isch&tbs=isz:l"` (`&tbs=isz:l` = large images filter).
- User saves to ~/Downloads, types "n".
- CC grabs newest from Downloads, sips-converts to .jpg, replaces existing filename.

---

<a name="workflows"></a>
## 11. Workflow patterns used

**Image fetch loop (for new + redo):**
```bash
# 1. open Google Images, large filter
open "https://www.google.com/search?q=<place+name>&tbm=isch&tbs=isz:l"

# 2. user saves to Downloads, types "n" or "saved N"

# 3. grab newest N from Downloads
cd ~/Downloads && newest=$(ls -t | grep -iE '\.(jpg|jpeg|png|webp)$' | head -1)

# 4. convert to .jpg + replace target
sips -s format jpeg ~/Downloads/"$newest" --out "/Users/.../img/<target>.jpg" >/dev/null 2>&1
rm -f ~/Downloads/"$newest"

# 5. verify res, warn if low
w=$(sips -g pixelWidth "/Users/.../img/<target>.jpg" | awk '/pixelWidth/{print $2}')
echo "<target>.jpg ${w}px $([ "$w" -lt 800 ] && echo '⚠️ LOW')"
```

**Separator-file tracker (for batches when grabbing multiple images for one place):**
```bash
touch .sep-<placename>
# user saves stuff
find . -newer .sep-<placename> -name "*.jpg"
# rename each appropriately
rm -f .sep-*  # cleanup
```

**Git push with auth switch (repo is owned by levgou, not lev-loris):**
```bash
git push 2>&1 || (gh auth switch -h github.com -u levgou && git push)
```

**Bulk replace placeholders via small python script** (used once for wiring 36 placeholders → real images): see git history for `wire_images.py` (deleted after use). Pattern: dict of `placeholder_text → [img_files]`, build `<div class="thumb-row">` HTML, str.replace into guide.html.

**Resolution check across all images:**
```bash
cd img && for f in *.jpg *.jpeg *.png *.webp; do [ -f "$f" ] || continue
  w=$(sips -g pixelWidth "$f" 2>/dev/null | awk '/pixelWidth/{print $2}')
  h=$(sips -g pixelHeight "$f" 2>/dev/null | awk '/pixelHeight/{print $2}')
  if [ -n "$w" ] && [ "$w" -lt 800 ]; then echo "LOW $f ${w}x${h}"; fi
done
```

---

<a name="pending"></a>
## 12. Pending tasks (priority order)

1. **Desktop slides (index.html) Days 4-8 — add image cards.** Currently uses text place-cards for Days 4-8 (sights, restaurants). Mobile guide has all the images; just need to wire same images into slide HTML. Estimated ~40 image-card insertions. Same `.thumb-row` pattern works in slides too (CSS already defined). LOWER PRIORITY than mobile because mobile is the actual trip tool.

2. **Low-res image redo (~13 left).** See section 10 list. Use the fetch loop. Each takes ~30 seconds + user save.

3. **Maybe: 3 generic placeholders left** in mobile guide for B&B Monguelfo/Villabassa, B&B Dorsoduro, Mestre hotel. These are "pick from Booking.com" options without a specific place. Either stock B&B shot or leave placeholder.

4. **Possible future**: PDF version of trip plan for offline car use (low priority — phone works).

5. **Possible future**: more iterations on Days 1-2 mobile UI now that 3-8 use newer patterns — small style inconsistencies. (Cosmetic, not blocking.)

---

<a name="resolved"></a>
## 13. Open questions — all resolved

All 5 questions from earlier sessions are CLOSED. Details:

**Q1 — Monte Baldo cable car hours (Day 3 Plan A).** ✅ Resolved.
- Verified June 2026 at funiviedelbaldo.it: first up 8:15, last up 18:00, last down 18:45.
- Open Apr 4 - Nov 1. Every 30 min.
- Schedule (up 16:20, down 17:45) has buffer.

**Q2 — Tre Cime toll road (Day 6 Plan B).** ✅ Resolved.
- Verified at pass.auronzo.info: MANDATORY online reservation. 40 EUR/car, ticket valid 12h from chosen entry time.
- Road open May-Nov, 24h. Casello staffed 8:00-20:00.
- Shuttle line 444 alternative (May 31 - Oct 11) for no-car option.
- Early June = fewer crowds, bonus.

**Q3 — Day 5 + Day 6 pairing.** ✅ Resolved.
- Pairing tip box added to both days in mobile guide. Explicit "hard" definition (Rifugio Croz 3h/+400m, or Tre Cime walk at 2300m).
- Recommended: A5+A6 or B5+B6. Avoid A5+B6.

**Q4 — Cortina detour (Day 7).** ✅ Resolved (preference only).
- Recommended lean: Plan A (direct to Venice, max Venice time) > Plan B (Cortina). Cortina = chic, pretty, optional.
- No blocker, no booking.

**Q5 — Verona on Day 8 tight.** ✅ Resolved.
- Plan B trimmed: Verona = coffee/gelato + Arena exterior only (~45 min), explicit time-check at 10:45 (behind = leave, ahead = quick piazza peek).
- Plan A = no Verona, long Venice morning, big flight buffer. Recommended unless Verona explicitly wanted.

---

<a name="tech"></a>
## 14. Tech notes & gotchas

**Repo owner mismatch.** Local has two gh CLI accounts (`lev-loris` work + `levgou` personal). Repo is on `levgou`. Always switch before push:
```bash
gh auth switch -h github.com -u levgou
```
Pattern in commits: try push, fallback to switch:
```bash
git push 2>&1 || (gh auth switch -h github.com -u levgou && git push)
```

**Mobile guide CSS.** Two image-row classes:
- `.img-strip` — original mobile-first horizontal scroll (Days 1-2 hand-written)
- `.thumb-row` — added later (Days 3-8 wired by script)
Both have identical behavior: 140px square thumbs in flex row, horizontal scroll, single-child becomes 200px full-width. Modal listener matches both:
```js
e.target.closest('.img-strip img, .thumb-row img, .day-hero, .title-hero')
```

**Image extension drift.** Saves come as .jpg / .jpeg / .png / .webp. To keep HTML refs stable, always convert to .jpg with sips:
```bash
sips -s format jpeg ~/Downloads/<saved-file> --out img/<target>.jpg
```

**Date interpretation.** User mentioned "end of May" = May 31 2026 (Sunday). Trip Days 1-8 = May 31 Sun → Jun 7 Sun. Flight MXP 11am arrival, 20:00 departure same airport.

**Hebrew keyboard typos.** User sometimes accidentally types in Hebrew layout. "מ" = key position of "n" — interpret as "n" (yes/continue). Other Hebrew chars: ask if ambiguous.

**One memory rule.** Don't write em-dashes (`—`) in code files — user prefers `-` or `--`. This file body uses em-dashes (it's a doc, not code, so fine).

**caveman-mode** active in current session. User has a hook that enforces terse responses. Code, commits, security stay normal English. Apply when responding.

---

## What's NOT in here

- Day-by-day expanded restaurant menus (use `italy_trip_plan.md` if needed).
- Google Maps pin labels + icons (in `browser_claude_prompt.md`).
- Original A/B draft from desktop Claude (in `ab_plans_days_1-4.md` — historical).

---

*This file is the single source of truth for picking up. Update the "Pending tasks" + "Image work state" sections as work progresses. Date: 2026-05-30.*
