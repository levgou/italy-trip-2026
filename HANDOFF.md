# Italy Trip — Conversation Handoff

> **Read this first.** You are picking up an existing Claude Code session on a different device. This file is self-contained — everything you need to continue work is below.

## Who / What / When

- **Trip:** Lev + 1 friend (2 guys), Italy road trip
- **Dates:** Sun May 31 → Sun Jun 7, 2026 (8 days)
- **Flight:** Arrive MXP 11am Sunday, depart MXP 8pm following Sunday
- **Route:** Milan → Lake Maggiore → Lake Como → Lake Garda → Trentino → Dolomites (2 nights) → Venice (1 night) → Milan
- **Total driving:** ~960 km
- **Budget:** Nice but not expensive — agriturismi, B&Bs, pensioni
- **Season note:** End of May = pre-peak. Pragser Wildsee road OPEN (closes Jul 10 only). Water still chilly — quick swims only.

## Repo & Live Links

- **Local path:** `/Users/levgourevitch/Documents/Documents - QG4ML4QJ1H/private/italy/`
- **GitHub:** https://github.com/levgou/italy-trip-2026
- **Live slides:** https://levgou.github.io/italy-trip-2026/
- **Owner:** github.com/levgou (use `gh auth switch -u levgou` before pushing — lev-loris has no write access)

## File Layout

| File | Purpose |
|------|---------|
| `HANDOFF.md` | This file. Self-contained handoff doc with full plan inlined |
| `italy_trip_plan.md` | Source-of-truth trip plan (also inlined below) |
| `index.html` | Reveal.js slide deck — 8 days, all places have real images |
| `browser_claude_prompt.md` | Prompt for browser Claude to add labeled pins to Google Maps (also inlined below) |
| `img/` | 70+ local jpg/webp — restaurants, hotels, gelato, scenic drives, heroes |
| `.github/workflows/pages.yml` | Auto-deploy to GitHub Pages on push |

## Design Decisions (carry forward)

- **Slide format:** Reveal.js, fonts = Libre Baskerville (headings) + Nunito (body). Background `#F0EBE3` (parchment). Italian tricolore accent. No dark slides.
- **Image strategy:** Real photos per place, NOT stock. Multi-image places use `thumb-row` (160px clickable thumbnails). Click any → full-size modal. Tap/Escape closes.
- **Hotel photos prioritized** so friend can book.
- **GMaps pin labels:** `🍝 Trattoria` `🍷 Osteria` `🦑 Bacaro` `🍽 Ristorante` `🏔 Rifugio` `🍺 Gasthaus` `🍦 Gelateria` `☕ Caffe` `🌾 Agriturismo` `🛏 B&B` `🐄 Maso` `🏨 Hotel` `🥾 Hike Start` `🛣 Scenic Drive` `👁 Viewpoint` `🏖 Beach/Swim` `🎯 Activity` `☂ Rain Backup` `🌙 Nightlife` `🏛 Sightseeing` `🅿 Parking`

## User Preferences

- Casual + fun tone. Russian gopnik banter OK in Cyrillic only (братан, давай, погнали). Technical content in English.
- One step at a time for multi-step changes. Don't batch.
- Don't run `Read` on images — burns tokens. Use `file` for dimensions.
- For image fetching: open Google Images search via `open` cmd, user saves to `img/`, then rename. Use `.sep-<name>` separator files to track which batch belongs to which place.
- "Show all images for a place" pattern: `img-card > thumb-row > <img>...<img>`. Each clickable → modal.
- No emojis in code/files unless requested. Emojis in chat OK.

## Image Fetch Workflow

```bash
# 1. Marker
touch .sep-<placename>

# 2. Open Google Images, large filter
open "https://www.google.com/search?q=<place+name>&tbm=isch&tbs=isz:l"

# 3. User saves to img/. Then:
find . -newer .sep-<placename> -name "*.jpg"

# 4. Rename
mv weird-name.jpg place-1.jpg

# 5. Update HTML to use new image
# 6. rm .sep-* when done
```

## Open Items / Possible Next Work

- More restaurant images for Days 3-8 (only Days 1-2 fully photo'd)
- More scenic shots: Strada della Forra, Sentiero del Ponale, Venice bacari, Milan trattorias, cotoletta
- Day 8 Milan-specific images
- Compact PDF version of trip plan for offline use in car
- Verify Pages deploy succeeded

## Quick Verify State

```bash
cd "/Users/levgourevitch/Documents/Documents - QG4ML4QJ1H/private/italy"
git log --oneline | head
ls img/ | wc -l
open index.html  # preview slides
```

---

## EXPORT-BACK INSTRUCTIONS (read when migrating back to another Claude)

When user wants to take this conversation BACK to another Claude session:

1. **Re-read this entire HANDOFF.md.**
2. **Replace the section below `## SESSION UPDATES`** (or add if missing) summarizing:
   - What got done (new images, slide changes, plan tweaks, commits)
   - Any new decisions made
   - New files added/removed
   - Current state of open items
3. **Also update the inlined `italy_trip_plan.md` content below** if the plan itself changed. Keep inlined version in sync with the actual file.
4. **Commit HANDOFF.md** to repo.
5. **Tell user:** "Updated HANDOFF.md committed + pushed. On other device, pull repo OR copy HANDOFF.md contents from GitHub raw view, paste into new Claude session as first message."
6. If new Claude is web/mobile (no filesystem), paste full HANDOFF.md inline in chat. It has everything self-contained.

HANDOFF.md is the **single source of truth** for cross-device handoffs. Update before every migration.

---

## SESSION UPDATES

(Append updates here when migrating. Latest at top.)

- 2026-05-14: Initial handoff doc created. State at this point: 5 commits on main, 81 img files, Pages deployed, all Days 1-8 slides built with hero images + sleep images.

---

# INLINED: italy_trip_plan.md

> This is the full trip plan. Source of truth. If editing in a session without filesystem access, mirror changes back to the standalone `italy_trip_plan.md` file when migration is done.

# Italy Road Trip - 9 Days (Sun May 31 - Sun Jun 8, 2026)

**Who:** Lev + friend (2 guys)
**Route:** Milan (MXP) -> Lake Maggiore -> Lake Como -> Lake Garda -> Trentino -> Dolomites (2 nights) -> Venice (1 night) -> Milan
**Total driving:** ~960 km over the week
**Rental car:** Pick up & drop off at MXP
**Budget:** Nice but not expensive - agriturismos, B&Bs, pensioni
**Season:** Late May / early June - pre-peak, good prices, Pragser road OPEN (closes Jul 10 only)

---

## Booking Alerts (Do These First!)

| What | Where to Book | Cost | Notes |
|------|--------------|------|-------|
| Isola del Garda tour | [isoladelgarda.com](https://www.isoladelgarda.com/en/guided-tours) | 39-49 EUR/pp | Closed Mondays! Book for Tue Jun 2 |
| Venice parking | [parclick.it](https://parclick.it/parcheggio-venezia) | 5-15 EUR/day (Mestre) | Pre-book to guarantee spot |
| Borromean Islands ferry | [navigazionelaghi.it](https://www.navigazionelaghi.it/en/tickets-and-timetables-lake-maggiore/) | Check site | Every 30 min, 9:00-18:00 |
| ~~Pragser Wildsee parking~~ | ~~prags.bz~~ | -- | **NOT NEEDED** - end of May, road is open! |

---

## Day 1 (Sunday May 31) - Arrive MXP -> Lake Maggiore

### Driving
- **MXP -> Stresa:** 60 km, ~1h
- **When:** Right after landing (arrive 11am, car pickup, on the road by ~12:30)
- **Scenic route:** Take autostrada to Arona, then **SS33 along the lake shore** for the last 20 km to Stresa - first lake views of the trip

### What to Do (~5h of free time)
| Time | Activity | Duration |
|------|----------|----------|
| 13:30-14:30 | Arrive Stresa, drop bags, quick lunch | 1h |
| 15:00-18:00 | **Borromean Islands** by ferry (Isola Bella + Isola dei Pescatori) | 3h |
| 18:00-19:30 | **Lungolago Stresa** evening passeggiata | 1h |
| 20:00 | Dinner | - |

- **Borromean Islands** - ferry from Stresa piazzale lido, every 30 min
  - Isola Bella - baroque palace + terraced gardens (the showstopper, ~1.5h)
  - Isola dei Pescatori - tiny fishing village, wander + grab a snack (~1h)
  - Skip Isola Madre if short on time

### Where to Eat

**Lunch options on arrival:**
- **Quick on the lungolago** in Stresa - any bar/cafe for a panino + caffe
- **Stop in Arona** (on the way, 20 min before Stresa) - nice lakeside town, grab a pizza al taglio or sit at a trattoria by the water
- **Isola dei Pescatori** - if you head to the islands first, eat lunch THERE. The whole island is basically a fish restaurant village. Pick any spot on the water

**Dinner - Stresa:**
| Name | Vibe | What to Get | Address |
|------|------|------------|---------|
| La Rampolina | Osteria/bottega, terrace WITH lake + Borromean Islands view. Locals go here | Piemontese tradition, lake fish | Stresa |
| Trattoria Lo Stornello | Simple family spot in centro storico, no fuss | Pesce persico, risotto, stufato | Via Cavour 35 |
| Osteria degli Amici | Homey, menu changes daily with season | Zuppe, spezzatini, paste fresche | Via Bolongaro 31 |

**Must-try:** pesce di lago (persico, lavarello, trota), risotto, polenta

### Gelato & Coffee
- **L'Angolo del Gelato** - centro Stresa, generous portions, try caramello salato
- **Coffee:** any bar on the lungolago for a proper Italian espresso + cornetto. Nothing fancy needed - it's all good here

### Nightlife
- Stresa is quiet at night - enjoy the **lungolago passeggiata** with a drink
- Aperitivo on the hotel terrace watching the sunset over the islands is the move

### Quick Swim
- **Spiaggia Lido di Stresa** - right in town, pebbly beach. Water will be ~18-19C end of May - refreshing but short dip territory

### Rain Backup
- **Isola Bella palace + gardens** work even in light rain (palace is indoor). Skip the ferry in heavy storms though
- Drive to **Borromeo Castle in Angera** (30 min) - medieval castle with doll museum, lake views from the tower

### Where to Sleep (Stresa / Verbania area)
| Name | Type | Price Range | Why |
|------|------|-------------|-----|
| Agriturismo Nel Giardino di Dafne | Agriturismo | ~100-130 EUR | Breakfast basket at 8am: local milk, yogurt, fresh pastries. Quiet garden |
| Hotel La Palma | 4-star hotel | ~120-150 EUR | Lungolago, rooftop terrace panorama at sunset, good value for 4-star |
| B&B on the hills above Stresa | Various on Booking | ~70-100 EUR | Panoramic views at half the lakefront price |

---

## Day 2 (Monday) - Lake Maggiore -> Lake Como

### Driving
- **Stresa -> Sasso del Ferro:** 10 min
- **Sasso del Ferro -> Como:** 60 km, ~1.5h
- **When:** Drive after Sasso del Ferro, arrive Como for lunch
- **Scenic route:** **SS34 along the lake shore** to Verbania, option to take the **Laveno-Intra car ferry** across Lake Maggiore (~20 min crossing, ~15 EUR) instead of driving around

### What to Do (~7h of free time)
| Time | Activity | Duration |
|------|----------|----------|
| 09:00-10:30 | **Sasso del Ferro** - cable car up, panoramic peak | 1.5h |
| 10:30-12:00 | Drive to Como (scenic route) | 1.5h |
| 12:00-13:00 | Lunch in Como | 1h |
| 13:30-15:30 | **Brunate** - funicular up + walk to Faro Voltiano lighthouse | 2h |
| 16:00-18:00 | **Greenway del Lago di Como** - Colonno to Sala Comacina section | 2h |
| 20:00 | Dinner | - |

**Alternative to Greenway:** **E-bike ride** along the lake - rent from [Econoleggio Como Lake](https://www.econoleggiocomolake.it/noleggio-bici/), Menaggio-Sorico route is gorgeous

### Scenic Walk Option: Chestnut Trail (Sentiero dei Castagni)
- **Stresa -> Belgirate** along ancient mule tracks through woods and hamlets
- 5 km, ~2.5h, easy
- Do this INSTEAD of Sasso del Ferro if you want a proper morning walk before leaving Maggiore

### Where to Eat

**Lunch - Brunate or Como:**
| Name | Vibe | What to Get | Where |
|------|------|------------|-------|
| Trattoria del Cacciatore | Traditional, killer lake view from hilltop | Game, local dishes | Brunate (10 min from funicular) |

**Dinner - Como:**
| Name | Vibe | What to Get | Where |
|------|------|------------|-------|
| Osteria del Gallo | **NEW in Slow Food 2025!** Feels like an old village inn | Traditional osteria fare | Cortesella, Como |
| Crotto del Sergente | One of the few "real" restaurants, locals know it | Authentic local cuisine | Lora, Como |
| Osteria il Governo | Historical osteria, garden with lake view, km0 | Traditional lake cuisine | Lezzeno (if driving along lake) |

**Must-try:** **missultini** (sun-dried lake fish - iconic Como dish), risotto con pesce persico, busecca

### Gelato & Coffee
- **Gelateria Guidi** - Via Domenico Fontana (between Piazza Cavour and Piazza Volta). THE gelato spot in Como - you'll be speechless
- **Gelab** - Via Cinque Giornate, near the Duomo. Small shop, lab visible, excellent quality
- **Coffee:** grab a cornetto + espresso at any bar near the funicular before heading up to Brunate

### Nightlife
- **Como lungolago** - evening aperitivo with lake views
- Como is chill at night - walk along the water, grab a drink at a bar on Piazza Cavour

### Quick Swim
- **Lido di Lenno** or **beaches near Colonno** (if doing Greenway) - small pebbly spots, crystal water
- Como town has some spots along the eastern shore near Mandello/Abbadia Lariana

### Rain Backup
- **Villa Carlotta** in Tremezzina - stunning botanical garden + art museum, partially covered. Worth it even in drizzle
- Stay longer in Como old town - Duomo (free), Basilica di Sant'Abbondio, covered shopping streets

### Where to Sleep (Como area)
| Name | Type | Price Range | Why |
|------|------|-------------|-----|
| Agriturismo Treterre | Agriturismo | ~90-120 EUR | Infinity pool, rustic chic, panoramic Como views |
| B&B Vista Lago | B&B | ~80-110 EUR | Rated 9.2, lake + mountain view balcony every room, free parking |
| Agriturismo Al-Marnich | Agriturismo | ~80-100 EUR | Schignano, bio restaurant on-site, rustic rooms |

---

## Day 3 (Tuesday) - Como -> Lake Garda

### Driving
- **Como -> Sirmione:** 100 km, ~2h
- **When:** Morning drive, arrive Sirmione by ~11am
- **Scenic route:** Mostly A4 autostrada - save scenic energy for Strada della Forra tomorrow

### What to Do (~7h of free time)
| Time | Activity | Duration |
|------|----------|----------|
| 08:30-10:30 | Drive Como -> Sirmione | 2h |
| 11:00-13:00 | Walk **Sirmione old town** + Castello Scaligero + Grotte di Catullo | 2h |
| 13:00-14:00 | Lunch in Sirmione | 1h |
| 14:30-17:00 | **Isola del Garda** guided tour (boat + villa + gardens + wine) | 2.5h |
| 17:30-19:00 | Chill at accommodation, lakeside walk | 1.5h |
| 20:00 | Dinner | - |

**Isola del Garda:**
- Closed Mondays, **Tuesday is perfect**
- Boat from Sirmione ~30 min each way
- Tour: neo-Gothic villa, gardens, wine tasting + olive oil DOP
- ~39-49 EUR/pp, [isoladelgarda.com](https://www.isoladelgarda.com/en/guided-tours)

### Where to Eat

**Lunch - Sirmione:**
| Name | Vibe | What to Get | Where |
|------|------|------------|-------|
| Trattoria Clementina | Authentic trattoria with courtyard, zero tourist BS | Local lake fish | Piazza Rovizzi |
| Osteria del Vecchio Fossato | Hidden in the old walls, intimate & quiet | Tagliatelle with trout, aole sale | Via Antiche Mura 16 |

**Dinner - Garda area:**
| Name | Vibe | What to Get | Where |
|------|------|------------|-------|
| Casa dei Pescatori | On the water, near Castello Scaligero | Lake fish, organic/seasonal | Sirmione |
| Trattoria Da Renato | Family place, good prices | Fish + meat | Via Gramsci 61, Desenzano |

**Must-try:** **bigoli con le sarde del Garda** (THE Garda dish), persico fritto

### Gelato & Coffee
- Sirmione centro storico is PACKED with gelaterie - walk and pick one that looks good, they're all competitive
- For a proper caffe, find a bar in the old town with a view of the castle

### Nightlife
- **Desenzano del Garda** is THE nightlife hub on Garda - bars, live music, clubs until 2am
- **Sirmione** is more chill - evening passeggiata + aperitivo by the castle
- If you sleep near Desenzano, walk the waterfront bars

### Quick Swim
- **Lido delle Bionde** (Sirmione) - famous spot with thermal spring water mixing into the lake! Warmer than other spots
- **Jamaica Beach** (Sirmione) - flat rocks going into the water, popular with locals
- **Spiaggia Desenzanino** (Desenzano) - free beach, nice sand

### Rain Backup
- **Terme di Sirmione** - if it rains, lean into it: thermal spa day. Indoor pools, treatments
- **Museo del Castello Scaligero** - the castle in Sirmione is interesting inside too

### Where to Sleep (Lake Garda area)
| Name | Type | Price Range | Why |
|------|------|-------------|-----|
| Agriturismo La Filanda | Agriturismo | ~80-120 EUR | Historic 1800s farmhouse on Garda shores, pool |
| B&B da Beatrice | B&B | ~70-90 EUR | Garden + pool, quiet, 2km from Sirmione center |
| Agriturismo Il Ghetto | Agriturismo | ~70-100 EUR | Countryside 1.2km from lake, rustic vibe |

---

## Day 4 (Wednesday) - Lake Garda North -> Molveno

### Driving
- **Garda south -> Riva del Garda (north):** 60 km, ~1.5h via western shore
- **Riva del Garda -> Molveno:** 40 km, ~1h
- **Total driving:** ~2.5h, broken up by the hike
- **When:** Morning drive along west shore, hike midday, Molveno afternoon
- **SCENIC ROUTE: Strada della Forra** - western shore via Limone -> Tremosine. 6 km of INSANE hairpins through a gorge carved in rock. Most spectacular road in Europe. James Bond (Quantum of Solace). **DO NOT MISS.**

### DAY HIKE #1: Sentiero del Ponale
| | |
|-|-|
| **Start** | Riva del Garda waterfront |
| **Distance** | 6 km round trip (to Ponale Alto Belvedere) |
| **Time** | ~2-2.5h |
| **Elevation** | +200m |
| **Difficulty** | Easy-moderate, wide path |
| **What** | Old road carved into CLIFF FACE above Lake Garda. Tunnels through rock, views straight down to turquoise water. One of the most famous walks in Italy |
| **Lunch** | Stop at **Ponale Alto Belvedere** restaurant at turnaround for drinks + food with a view |

### What to Do (~8h of free time)
| Time | Activity | Duration |
|------|----------|----------|
| 08:30-10:00 | Drive south Garda -> Riva via **Strada della Forra** | 1.5h |
| 10:00-12:30 | **Sentiero del Ponale** hike + drink at Ponale Alto | 2.5h |
| 12:30-13:30 | Lunch in Riva del Garda | 1h |
| 14:00-15:00 | Drive Riva -> Molveno | 1h |
| 15:30-17:00 | **Lago di Molveno** - beach, swim, chill (5 Vele award beach!) | 1.5h |
| 17:30-19:00 | Walk: Fortini di Napoleone or half the lake loop | 1.5h |
| 20:00 | Dinner | - |

### Where to Eat

**Lunch:** Riva del Garda - any lakefront spot, it's a proper town (not a tourist trap)
OR eat at Ponale Alto Belvedere during the hike

**Dinner - Molveno:**
| Name | Vibe | What to Get | Where |
|------|------|------------|-------|
| Trattoria al Faggio | Top-rated, traditional mountain food | Canederli, polenta, spezzatino di capriolo | Molveno |
| All'Aquila Nera e Cima Tosa | Centro, excellent quality/price | Trentino specialties | Molveno centro |

**Must-try:** **canederli** (bread dumplings with speck/cheese), polenta con capriolo (deer stew), funghi porcini

### Gelato & Coffee
- Molveno is a small town - grab gelato at any bar on the lakefront strip
- **Peccati di Gola** in Riva del Garda (before you leave) - since 1998, artisanal gelato, crepes, granita with fresh fruit

### Nightlife
- **Riva del Garda** (before driving to Molveno): **Sailing Bar** - shaped like a ship, sunset aperitivo + live music + DJ sets on summer evenings
- Molveno itself is mountain-quiet at night - grab a beer at a local bar, enjoy the stars and the lake

### Quick Swim
- **Spiaggia Lago di Molveno** - 5 Vele award (best beach in Italy!). Crystal water, Brenta backdrop. Water ~16-18C end of May - quick dip, towel, done
- If you did Ponale: no real swim spot there, but Riva has a beach

### Rain Backup
- **Climbing Stadium Arco** (near Riva, 30 min from Molveno) - indoor climbing wall, good for a rainy afternoon
- Or: skip Ponale hike, drive directly to Molveno, visit **Castello di Stenico** (medieval castle, 20 min from Molveno) + indoor pool/spa at **Andalo Life Park** (next town over - ice rink, pool, wellness center)

### Where to Sleep (Molveno area)
| Name | Type | Price Range | Why |
|------|------|-------------|-----|
| Agriturismo Ai Castioni | Agriturismo | ~90-120 EUR | Lake + Brenta Dolomites view from balcony, peaceful |
| B&B Il Nido | B&B | ~70-90 EUR | Breakfast, parking, **Dolomiti Paganella Guest Card** included (free cable cars!) |
| B&B Le Coccole | B&B | ~80-100 EUR | Overlooking Lake Molveno, "corner of paradise" |

---

## Day 5 (Thursday) - Brenta Dolomites Hike + Lago di Tovel

### Driving
- **Molveno -> Lago di Tovel:** 30 km, ~30 min (afternoon side trip)
- **When:** Hike in the morning, Tovel in the afternoon. No rush today!
- This is the RELAXED Dolomite day - tomorrow is the big drive

### DAY HIKE #2: Rifugio Croz dell'Altissimo (Brenta Dolomites)
| | |
|-|-|
| **Start** | Pradel (take cabinovia from Molveno center) |
| **Distance** | ~6 km round trip from Pradel |
| **Time** | ~3h round trip |
| **Elevation** | +400m from cable car station |
| **Difficulty** | Medium |
| **What** | Forest paths opening into the heart of the Brenta Dolomites. Dramatic rock walls towering above. Rifugio at 1430m serves canederli + strudel with Dolomite panorama |
| **Tip** | Cable car does the heavy lifting (first 800m!). Eat lunch at the rifugio. Bring a layer - it's cooler up there |

### What to Do (~9h of free time - the chill day)
| Time | Activity | Duration |
|------|----------|----------|
| 08:00-08:30 | Cabinovia up to Pradel | 30 min |
| 08:30-12:00 | **Hike to Rifugio Croz dell'Altissimo** + lunch at rifugio | 3.5h |
| 12:00-12:30 | Cabinovia down | 30 min |
| 13:00-14:00 | Chill / rest at Molveno lake | 1h |
| 14:30-15:00 | Drive to **Lago di Tovel** | 30 min |
| 15:00-17:00 | Walk around Tovel (4 km loop, flat, ~1.5h) + relax by the lake | 2h |
| 17:00-17:30 | Drive back to Molveno | 30 min |
| 18:00-20:00 | Free time, beach, evening walk | 2h |
| 20:00 | Dinner | - |

### Where to Eat

**Lunch:** At **Rifugio Croz dell'Altissimo** - canederli, polenta, strudel. THE proper mountain lunch.

**Dinner:** Same options as Day 4 (Molveno), or try whatever you didn't have last night

### Gelato & Coffee
- Same as Day 4 - Molveno lakefront bars

### Quick Swim
- **Lago di Tovel** - beautiful but COLD (mountain lake at 1178m). Brave dip only
- **Lago di Molveno** - better bet, slightly warmer, do it after the hike to cool off

### Rain Backup
- **Andalo Life Park** - indoor pool, spa, wellness. 10 min from Molveno
- Or: skip the hike, do a scenic drive day instead - cruise through Val di Non, visit **Castel Thun** (medieval castle with frescoed rooms, 30 min from Molveno)

### Where to Sleep: Same place as Day 4 (2nd night in Molveno)

---

## Day 6 (Friday) - Molveno -> Pragser Wildsee (Dolomites)

### Driving
- **Molveno -> Pragser Wildsee:** 130 km, ~2h
- **When:** Morning drive, arrive Braies by ~11am
- **Scenic route:** Through **Val di Non -> Val di Sole -> Val Pusteria**. All mountain roads, every turn is a Dolomite postcard. Fill up gas before leaving Molveno!

### Driving Tips for Dolomites
- Use **engine braking** on descents - save brake pads
- Watch for cyclists and motorcyclists - everywhere
- Fill up gas BEFORE mountain roads - stations sparse
- End of May = road to Braies is **OPEN** (restrictions only Jul 10 - Sep 10)

### What to Do (~7h of free time)
| Time | Activity | Duration |
|------|----------|----------|
| 08:30-10:30 | Scenic drive Molveno -> Val Pusteria | 2h |
| 11:00-12:30 | **Pragser Wildsee / Lago di Braies** - walk the loop (3.5 km, 1.5h) | 1.5h |
| 12:30-13:00 | Rent a rowing boat on the lake | 30 min |
| 13:00-14:00 | Lunch near the lake | 1h |
| 14:30-17:00 | Explore **Val Pusteria villages** - Dobbiaco, Monguelfo, Villabassa | 2.5h |
| 17:00-18:00 | Drive to accommodation, settle in | 1h |
| 19:00 | Dinner | - |

**Braies lake walk details:**
- 3.5 km loop, ~1.5h, easy
- West shore flat and wide, east shore has rock steps
- Turquoise water + Dolomite backdrop - THE postcard
- Rowing boats usually available for rent at the north end

### Where to Eat

**Lunch:** At the lake or a Gasthaus in Braies/Ferrara area

**Dinner - Val Pusteria:**
| Name | Vibe | What to Get | Where |
|------|------|------------|-------|
| Gasthaus in Dobbiaco | South Tyrolean inn, hearty portions | Speck, canederli, schlutzkrapfen, kaiserschmarrn | Dobbiaco |
| Gasthaus in Monguelfo | Traditional Tyrolean | Same good stuff | Monguelfo |

**Must-try:** **speck** (smoked ham - you're in South Tyrol!), **schlutzkrapfen** (spinach-ricotta half-moons), **kaiserschmarrn** (shredded pancake + plum compote), strudel di mele

### Gelato & Coffee
- South Tyrol does strudel > gelato. Get a slice of warm apfelstrudel with vanilla sauce at any Gasthaus/Cafe
- For proper gelato: try any gelateria in Dobbiaco or Brunico main street
- Coffee is solid everywhere - Austrian influence means good pastries + coffee culture here

### Nightlife
- Val Pusteria is mountain quiet - it's beers at the Gasthaus kind of vibe
- **Brunico** (30 min) has more going on if you want a livelier evening - pedestrian zone with bars

### Quick Swim
- **Lago di Braies** - stunning but ICE COLD (mountain lake at 1496m, water ~12-14C end of May). Feet in = yes. Full swim = you're insane (but do it for the story)
- **Lago di Dobbiaco** - slightly more accessible, still cold

### Rain Backup
- **MMM Messner Mountain Museum** in Brunico (Castel di Brunico) - Reinhold Messner's museum about mountain peoples and cultures. Indoor, fascinating even for non-climbers
- Or: use the rain day to just enjoy the maso - long breakfast with homemade speck, read a book, chill. You've been going hard for 5 days

### Where to Sleep (Val Pusteria / Braies)
| Name | Type | Price Range | Why |
|------|------|-------------|-----|
| Hanslerhof | Maso/Agriturismo | ~80-110 EUR | **5.7 km from Braies!** Family farm at 1350m. Insane breakfast: homemade speck, eggs, milk, strudel, syrups. The real Tyrolean deal |
| Gallorosso maso in Dobbiaco | Agriturismo | ~70-100 EUR | [gallorosso.it](https://www.gallorosso.it) - curated South Tyrol farm stays |
| B&B in Monguelfo/Villabassa | B&B | ~60-90 EUR | 15-20 min from Braies, typical Tyrolean style |

---

## Day 7 (Saturday) - Dolomites -> Venice

### Driving
- **Val Pusteria -> Lago di Santa Croce:** 120 km, ~2h
- **Santa Croce -> Venice (Mestre):** 90 km, ~1.5h
- **Total driving:** ~3.5h
- **When:** Leave after Hanslerhof breakfast (don't rush it - that breakfast is worth it), Santa Croce swim ~11am, Venice by early afternoon
- **Scenic route:** South through **Dolomite foothills via Belluno** - alpine peaks transition to rolling hills to Veneto plain

### What to Do
| Time | Activity | Duration |
|------|----------|----------|
| 08:00-09:00 | Epic Tyrolean breakfast at the maso | 1h |
| 09:00-11:00 | Drive Val Pusteria -> Lago di Santa Croce | 2h |
| 11:00-12:00 | **Lago di Santa Croce** - swim stop, stretch legs | 1h |
| 12:00-13:30 | Drive to Venice, park car | 1.5h |
| 14:00-15:00 | Lunch in Venice | 1h |
| 15:00-19:00 | Wander: Dorsoduro, San Marco, Rialto, get lost | 4h |
| 19:30-22:00 | **Bacaro tour** through Cannaregio | 2.5h |

**Parking strategy:**
- **Best value:** Park in **Mestre** (5-15 EUR/day) + train to Venezia Santa Lucia (10 min, ~2 EUR)
- **Convenience:** Tronchetto (25-30 EUR/day) - walk/vaporetto to centro
- Pre-book on [parclick.it](https://parclick.it/parcheggio-venezia)

### Where to Eat

**Bacaro Tour (THIS IS THE WAY) - hop between 3-4:**
| Name | Vibe | What to Get | Where |
|------|------|------------|-------|
| Cantina Do Spade | Open since **1448**. | Classic cicchetti | Near Rialto Market |
| All'Arco | Family-run, tiny, seasonal cicchetti | Whatever's fresh today | Near Ponte di Rialto |
| Alla Vedova | LEGENDARY polpette (meatballs) | Polpette + ombre di vino | Cannaregio |
| Al Timon | Lively, outdoor seating on canal | Cicchetti + local wines | Cannaregio |

**Hidden gems:**
| Name | Vibe | What to Get | Where |
|------|------|------------|-------|
| Taverna al Remer | Hidden campiello FACING Grand Canal, anonymous alley entrance | Full menu + cicchetti | Cannaregio |
| Vino Vero | "Bacaro of natural wines" | Natural wine + cicchetti | Cannaregio |
| Osteria Al Squero | Overlooks historic gondola workshop | Aperitivo | Dorsoduro |
| Codroma | Osteria with kitchen, off tourist circuit | Proper dishes + cicchetti | Near Zattere, Dorsoduro |

**Must-try:** **baccala mantecato** su crostino (creamed cod - ICONIC), **sarde in saor** (sweet & sour sardines), polpette, frittura

### Gelato & Coffee
- **Gelateria Suso** - near Rialto. Natural ingredients, no artificial colors, eco-conscious. One of the best in Venice
- **Da Nico** - Dorsoduro, on Zattere waterfront. 80+ years. Famous for **Gianduiotto** (chocolate-hazelnut frozen block). 25+ flavors. Sit on the terrace facing Giudecca canal
- **Alaska Gelateria** - 30+ years, creative: zafferano, cardamomo, zenzero, curcuma. For the adventurous
- **Coffee:** Venice has a unique torrefazione in Cannaregio active since the 1930s - the only specialty coffee shop in the city. Otherwise, any bar for a classic espresso al banco (standing at the counter = cheaper!)

### Nightlife
- **Fondamenta della Misericordia** (Cannaregio) - THE spot. Multiple bars along this canal, locals hang out here, lively late into the night
- **Ai Ormesini** area - continuation of Misericordia, same vibe
- Venice nightlife = bacaro hopping + canal-side drinks. No clubs, but you won't miss them

### Rain Backup
- Venice in the rain is STILL amazing - arguably more atmospheric. Just bring a jacket
- **Peggy Guggenheim Collection** (Dorsoduro) - world-class modern art, indoor
- **Teatro La Fenice** - guided tour of one of the world's most beautiful opera houses
- Extended bacaro tour - more time inside cozy wine bars = not a bad thing

### Where to Sleep (Venice - 1 night)
| Name | Type | Price Range | Why |
|------|------|-------------|-----|
| B&B in Cannaregio | B&B | ~70-100 EUR | Best value in Venice. Near Alla Vedova, Al Timon, Fondamenta della Misericordia. Walk out your door = real Venice |
| B&B in Dorsoduro | B&B | ~80-120 EUR | Artsy, near galleries + Zattere waterfront |
| Mestre (mainland) | Hotel/B&B | ~50-70 EUR | Cheapest, 10 min train. Less charm but saves ~40 EUR/night |

**Recommendation:** Cannaregio B&B - you're in the heart of bacaro territory

---

## Day 8 (Sunday Jun 7) - Venice Morning -> Milan

### Driving
- **Venice -> Milan:** 270 km, ~3h (A4 autostrada)
- **Tolls:** ~22.40 EUR
- **When:** Leave Venice ~10am, arrive Milan ~1pm
- **Optional stop:** **Verona** (directly on route) - 1h walk: Arena, Piazza delle Erbe, espresso

### What to Do
| Time | Activity | Duration |
|------|----------|----------|
| 07:30-09:30 | Morning walk in Venice - Rialto fish market (early!), cornetto + caffe, last wander | 2h |
| 10:00-10:30 | Get car, leave Venice | 30 min |
| 10:30-13:00 | Drive to Milan (optional Verona stop ~1h) | 2.5-3h |
| 13:00-14:00 | Lunch in Milan | 1h |
| 14:00-16:30 | Walk: Duomo, Galleria Vittorio Emanuele, Navigli | 2.5h |
| 17:00 | Drive to MXP, return car | - |
| 20:00 | Flight | - |

### Where to Eat

**Lunch - Milan (last Italian meal, make it count):**
| Name | Vibe | What to Get | Where |
|------|------|------------|-------|
| Trattoria Milanese dal 1933 | Institution near Duomo, timeless | Risotto alla milanese + ossobuco, cotoletta | Near Piazza del Duomo |
| Antica Trattoria della Pesa | Since 1880. Milanese generations eat here | Risotto, ossobuco, cotoletta in burro chiarificato | Milano |
| Madonnina | Daily menu, mastered the holy trinity | Cotoletta, ossobuco, risotto | Milano |

**Must-try:** **cotoletta alla milanese** (in clarified butter), **risotto alla milanese** (saffron), **ossobuco**

### Gelato & Coffee
- **Artico** - top-rated in Milan, pistacchio salato is legendary
- **Pavé Gelati & Granite** - near center, gelato + granite + pastries
- **Coffee:** Milan takes espresso seriously. **Orsonero Caffe** for specialty (cold brew, aeropress) or **Loste Cafe** (Risorgimento area) for amazing pastries + specialty coffee

### What to Do in Milan (~3h)
| Time | Activity | Duration |
|------|----------|----------|
| 13:00-14:00 | Lunch at a trattoria | 1h |
| 14:00-14:30 | **Duomo** - even just the piazza is impressive | 30 min |
| 14:30-15:00 | **Galleria Vittorio Emanuele II** - walk through, grab an espresso | 30 min |
| 15:00-16:00 | Walk to **Navigli** - canals, street art, aperitivo vibes | 1h |
| 16:00-16:30 | Gelato at Artico or Pavé | 30 min |
| 17:00 | Head to MXP | - |

### Aperitivo in Milan
- **Navigli canal bars** - aperitivo Milanese style: you buy a drink (~8-10 EUR) and get access to a buffet of snacks. The whole waterfront is lined with bars competing for your business
- This is THE Milan ritual - spritz + free food + canal vibes

---

## Driving Summary

| Day | Route | Km | Drive Time | When to Drive | Scenic Highlight |
|-----|-------|----|-----------|---------------|------------------|
| 1 (Sun) | MXP -> Stresa | 60 | 1h | After landing ~12:30 | SS33 lake shore |
| 2 (Mon) | Stresa -> Como | 60 | 1.5h | Morning 10:30 | SS34 + Laveno ferry option |
| 3 (Tue) | Como -> Sirmione | 100 | 2h | Morning 08:30 | A4 (efficient) |
| 4 (Wed) | Garda S -> Riva -> Molveno | 100 | 2.5h | Morning + afternoon | **Strada della Forra** (MUST DO) |
| 5 (Thu) | Molveno -> Tovel -> Molveno | 60 | 1h | Afternoon only | Val di Non |
| 6 (Fri) | Molveno -> Braies | 130 | 2h | Morning 08:30 | **Val Pusteria mountain roads** |
| 7 (Sat) | Val Pusteria -> Venice | 210 | 3.5h | Morning 09:00 | Dolomite foothills -> plains |
| 8 (Sun) | Venice -> Milan | 270 | 3h | Morning 10:00 | Optional Verona stop |
| **Total** | | **990 km** | **~16.5h** | | |

### Must-Drive Scenic Routes
1. **Strada della Forra** (Day 4) - 6 km gorge, hairpins through carved rock, James Bond. THE drive.
2. **Val Pusteria mountain roads** (Day 6) - Val di Non -> Val di Sole -> Val Pusteria. Dolomite postcards.
3. **SS34 Lake Maggiore** (Day 2) - Stresa to Verbania hugging the lake.
4. **Dolomite foothills to Belluno** (Day 7) - Alpine peaks melting into rolling Veneto hills.

---

## Day Hikes

### Hike 1: Sentiero del Ponale (Day 4, Lake Garda)
| | |
|-|-|
| **Start** | Riva del Garda waterfront |
| **Distance** | 6 km round trip |
| **Time** | ~2-2.5h |
| **Elevation** | +200m |
| **Difficulty** | Easy-moderate |
| **What** | Old road carved into CLIFF FACE above Lake Garda. Tunnels through rock, views straight down to turquoise water. One of Italy's most famous walks |
| **Lunch** | Ponale Alto Belvedere restaurant at the turnaround |

### Hike 2: Rifugio Croz dell'Altissimo (Day 5, Brenta Dolomites)
| | |
|-|-|
| **Start** | Pradel (cabinovia from Molveno center) |
| **Distance** | ~6 km round trip from Pradel |
| **Time** | ~3h |
| **Elevation** | +400m from cable car |
| **Difficulty** | Medium |
| **What** | Forest into the heart of Brenta Dolomites. Rock walls towering above. Rifugio at 1430m with canederli + strudel |
| **Tip** | Cable car does first 800m. Eat lunch at rifugio |

### Bonus: Lago di Tovel loop (Day 5, afternoon)
- 4 km, ~1.5h, flat. "The Red Lake" in peaceful forest setting.

---

## Biking Opportunities

| Where | What | Rental | Cost |
|-------|------|--------|------|
| Lake Como (Day 2) | Menaggio-Sorico lakeside | [Econoleggio](https://www.econoleggiocomolake.it/noleggio-bici/) | ~25-35 EUR |
| Lake Garda (Day 4) | Limone-Riva suspended bike path | [Bike Center Limone](https://www.bikecenterlimone.it/it) | ~20-35 EUR |
| Molveno (Day 5) | Cabinovia + Pradel trails | Ask locally | ~15-20 EUR |

---

## Cost Estimates (per person, for 2 people)

| Item | Total | Per Person |
|------|-------|------------|
| Autostrada tolls | ~80-100 EUR | ~40-50 |
| Gas (~990 km) | ~120 EUR | ~60 |
| Isola del Garda tour | ~80-100 EUR | ~40-50 |
| Venice parking (1 day Mestre) | ~10-15 EUR | ~5-8 |
| Borromean Islands ferry | ~30-40 EUR | ~15-20 |
| Cable cars (Sasso del Ferro, Molveno x2) | ~40-50 EUR | ~20-25 |
| **Total extras** | **~360-405 EUR** | **~180-200** |

| Accommodation (7 nights) | Per Night | Total |
|---------------------------|-----------|-------|
| Agriturismos/B&Bs average | ~80-100 EUR/room | ~560-700 EUR (~280-350/pp) |

---

## Prompt for Browser Claude (Add to Google Maps List)

Copy-paste this to your browser Claude to add all pins to "Italy" list:

```
Add these restaurants and points of interest to my Google Maps saved list "Italy". Search for each and save:

STRESA: La Rampolina Stresa, Trattoria Lo Stornello Via Cavour 35 Stresa, Osteria degli Amici Via Bolongaro 31 Stresa

COMO: Trattoria del Cacciatore Brunate, Osteria del Gallo Como, Crotto del Sergente Lora Como, Osteria il Governo Lezzeno

SIRMIONE: Trattoria Clementina Piazza Rovizzi Sirmione, Osteria del Vecchio Fossato Via Antiche Mura 16 Sirmione, Casa dei Pescatori Sirmione

MOLVENO: Trattoria al Faggio Molveno, Ristorante All'Aquila Nera e Cima Tosa Molveno

RIVA DEL GARDA: Ponale Alto Belvedere Riva del Garda (restaurant on the Ponale trail)

VENICE: Cantina Do Spade Venice, All'Arco Venice, Alla Vedova Venice, Al Timon Venice, Taverna al Remer Venice, Osteria Al Squero Venice, Codroma Venice

MILAN: Trattoria Milanese dal 1933 Milan, Antica Trattoria della Pesa Milan

SCENIC: Strada della Forra Tremosine sul Garda, Sentiero del Ponale Riva del Garda, Faro Voltiano Brunate, Rifugio Croz dell'Altissimo Molveno

GELATO: Gelateria Guidi Como, Gelab Via Cinque Giornate Como, Gelateria Suso Venice, Da Nico Zattere Venice, Artico Gelateria Milan, Pave Gelati Milan, Peccati di Gola Riva del Garda

COFFEE: Orsonero Caffe Milan, Loste Cafe Milan

SWIM: Lido delle Bionde Sirmione, Jamaica Beach Sirmione, Spiaggia Lago di Molveno

RAIN BACKUP: Villa Carlotta Tremezzina, Terme di Sirmione, MMM Messner Mountain Museum Brunico, Climbing Stadium Arco, Castello di Stenico
```

---

## Sources

### Food
- [Gambero Rosso - Stresa](https://www.gamberorosso.it/ristoranti/dove-mangiare-stresa-ristoranti/)
- [Scatti di Gusto - Lago Maggiore](https://www.scattidigusto.it/lago-maggiore-migliori-trattorie)
- [Slow Food 2025 - Como](https://comozero.it/attualita/le-sublimi-osterie-e-i-magnifici-ristoranti-di-como-nella-guida-slow-food-2025-con-due-stupende-sorprese/)
- [Gambero Rosso - Lago di Garda](https://www.gamberorosso.it/ristoranti/dove-mangiare-pasqua-lago-garda/)
- [Guida Michelin - Garda fish](https://guide.michelin.com/it/it/best-of/ristoranti-di-pesce-sul-lago-di-garda)
- [Gambero Rosso - Bacari Venezia](https://www.gamberorosso.it/ristoranti/bacari-di-venezia-guida-ai-migliori-dove-mangiare/)
- [Venezia fuori dai circuiti turistici](https://www.dimoredepoca.it/it/news/614-venezia-fuori-dai-circuiti-turistici-10-ristoranti-e-bacari-da-non-perdere)
- [Milano Citta Stato - Trattorie 2025](https://www.milanocittastato.it/featured/le-10-trattorie-piu-buone-di-milano-annata-2025/)

### Activities
- [Sentiero del Ponale](https://www.gardatrentino.it/en/activity/ponale-path-from-riva-del-garda-_8214)
- [Brenta Dolomites from Molveno](https://www.trentino.com/en/leisure-activities/mountains-and-hiking/hiking-in-summer/from-molveno-to-the-brenta-dolomites/)
- [Isola del Garda](https://www.isoladelgarda.com/en/guided-tours)
- [Borromean Islands](https://www.navigazionelaghi.it/en/tickets-and-timetables-lake-maggiore/)
- [Strada della Forra](https://viaggidialegio.it/idee-di-viaggio/la-strada-della-forra-il-percorso-panoramico-piu-bello-del-mondo/)
- [Limone bike path](https://soloviaggiumili.it/pista-ciclabile-sul-lago-di-garda-unesperienza-unica-a-limone/)
- [Venice parking](https://www.idealista.it/news/vacanze/mete-turistiche/2025/10/02/274996-dove-parcheggiare-l-auto-a-venezia-spendendo-poco-e-visitarla-senza-pensieri)

### Accommodation
- [Gallorosso - South Tyrol farms](https://www.gallorosso.it/it/meta-di-vacanze/alto-adige/dolomiti/alta-val-pusteria)
- [Hanslerhof Braies](https://www.hanslerhof-dolomiti.com/agriturismo-val-pusteria-braies.php)
- [Agriturismo Treterre Como](https://lombardiasecrets.com/rustico/agriturismo-treterre-lago-di-como/)
- [Agriturismo Ai Castioni Molveno](https://agriturismomolveno.com/en/)

---

# INLINED: browser_claude_prompt.md

> Prompt for browser Claude to add pins to Google Maps. Reproduce contents to user if they ask to update the maps list.

# Prompt for Browser Claude - Add All Places to Google Maps

Copy everything below the line and paste to Claude in the browser:

---

I have a Google Maps saved list called "Italy" (the one with the Italian hand emoji). I need you to add all the places below to this list. Some may already be saved - if so, just make sure they have the correct label and note/comment applied. Don't duplicate existing pins.

For each place:
1. Search for it on Google Maps
2. Save it to the "Italy" list
3. Apply the **label** exactly as shown (e.g. "Trattoria", "Osteria", etc.)
4. Add the **note/comment** if one is provided - this includes tips like what to order, booking info, etc.

## Label Legend (use these exact labels with icons)

Put the icon BEFORE the label text on each saved place.

- `🍝 Trattoria` - traditional Italian restaurant, family-run
- `🍷 Osteria` - wine bar / simple eatery, local vibe
- `🦑 Bacaro` - Venetian wine bar with cicchetti (small bites)
- `🍽 Ristorante` - restaurant (more formal than trattoria)
- `🏔 Rifugio` - mountain hut restaurant
- `🍺 Gasthaus` - South Tyrolean inn
- `🍦 Gelateria` - gelato shop
- `☕ Caffe` - coffee shop / specialty cafe
- `🌾 Agriturismo` - farm stay accommodation
- `🛏 B&B` - bed and breakfast
- `🐄 Maso` - South Tyrolean farm stay
- `🏨 Hotel` - hotel
- `🥾 Hike Start` - trailhead or hike starting point
- `🛣 Scenic Drive` - scenic road or viewpoint
- `👁 Viewpoint` - panoramic viewpoint
- `🏖 Beach/Swim` - swimming spot or beach
- `🎯 Activity` - cable car, bike rental, boat tour, etc.
- `☂ Rain Backup` - indoor activity for rainy days
- `🌙 Nightlife` - bar, aperitivo spot, nightlife
- `🏛 Sightseeing` - monument, castle, historical site
- `🅿 Parking` - parking spot

---

## DAY 1 - STRESA (Lake Maggiore)

### Food
- **La Rampolina, Stresa** | Label: `🍷 Osteria` | Note: "Terrace with lake + Borromean Islands view. Locals' favorite. Order lake fish + piemontese dishes"
- **Trattoria Lo Stornello, Via Cavour 35, Stresa** | Label: `🍝 Trattoria` | Note: "Simple family spot. Order pesce persico, risotto, stufato"
- **Osteria degli Amici, Via Bolongaro 31, Stresa** | Label: `🍷 Osteria` | Note: "Menu changes daily with season. Zuppe, spezzatini, paste fresche"

### Gelato
- **L'Angolo del Gelato, Stresa** | Label: `🍦 Gelateria` | Note: "Try caramello salato. Generous portions"

### Sleep
- **Agriturismo Nel Giardino di Dafne, Stresa** | Label: `🌾 Agriturismo` | Note: "Breakfast basket at 8am: local milk, yogurt, fresh pastries. ~100-130 EUR"
- **Hotel La Palma, Stresa** | Label: `🏨 Hotel` | Note: "4-star on lungolago. Rooftop terrace sunset panorama. ~120-150 EUR"

### Activities
- **Isola Bella, Lake Maggiore** | Label: `🏛 Sightseeing` | Note: "Baroque palace + terraced gardens. ~1.5h visit. Ferry from Stresa every 30 min"
- **Isola dei Pescatori, Lake Maggiore** | Label: `🏛 Sightseeing` | Note: "Tiny fishing village. Can eat lunch here - the whole island is a restaurant village"
- **Spiaggia Lido di Stresa** | Label: `🏖 Beach/Swim` | Note: "Pebbly beach in town. Water ~18-19C end of May - quick dip"

### Rain Backup
- **Rocca di Angera (Borromeo Castle), Angera** | Label: `☂ Rain Backup` | Note: "Medieval castle, 30 min from Stresa. Doll museum + lake views from tower"

---

## DAY 2 - COMO (Lake Como)

### Food
- **Trattoria del Cacciatore, Brunate** | Label: `🍝 Trattoria` | Note: "Killer lake view from Brunate hilltop. Order game + local dishes. 10 min from funicular"
- **Osteria del Gallo, Cortesella, Como** | Label: `🍷 Osteria` | Note: "NEW in Slow Food 2025! Feels like an old village inn. Traditional osteria fare"
- **Crotto del Sergente, Lora, Como** | Label: `🍷 Osteria` | Note: "One of the few 'real' restaurants in Como. Locals know it"
- **Osteria il Governo, Lezzeno** | Label: `🍷 Osteria` | Note: "Historical osteria, garden with lake view, km0 products. Order missultini (sun-dried lake fish)"

### Gelato & Coffee
- **Gelateria Guidi, Via Domenico Fontana, Como** | Label: `🍦 Gelateria` | Note: "THE gelato in Como. Between Piazza Cavour and Piazza Volta"
- **Gelab, Via Cinque Giornate, Como** | Label: `🍦 Gelateria` | Note: "Small shop near Duomo, lab visible. Excellent quality"

### Sleep
- **Agriturismo Treterre, Lake Como** | Label: `🌾 Agriturismo` | Note: "Infinity pool, rustic chic, panoramic Como views. ~90-120 EUR"
- **B&B Vista Lago, Como** | Label: `🛏 B&B` | Note: "Rated 9.2. Lake + mountain view balcony every room. Free parking. ~80-110 EUR"
- **Agriturismo Al-Marnich, Schignano, Como** | Label: `🌾 Agriturismo` | Note: "Bio restaurant on-site. Rustic rooms. ~80-100 EUR"

### Activities
- **Sasso del Ferro, Laveno** | Label: `👁 Viewpoint` | Note: "Cable car up to panoramic peak over Lake Maggiore. ~1.5h visit"
- **Faro Voltiano, Brunate** | Label: `👁 Viewpoint` | Note: "Lighthouse at top of Brunate. 30 min easy walk from funicular station. Insane views"
- **Greenway del Lago di Como** | Label: `🥾 Hike Start` | Note: "10 km scenic path on western shore. Do Colonno-Sala Comacina section (3-5 km, 1-2h)"
- **Sentiero dei Castagni, Stresa** | Label: `🥾 Hike Start` | Note: "Chestnut Trail, Stresa to Belgirate. 5 km, 2.5h, easy. Ancient mule tracks through woods"
- **Econoleggio Como Lake** | Label: `🎯 Activity` | Note: "E-bike rental. Menaggio-Sorico lakeside route is gorgeous"

### Swim
- **Lido di Lenno, Lake Como** | Label: `🏖 Beach/Swim` | Note: "Small pebbly spot, crystal water. On the Greenway route"

### Rain Backup
- **Villa Carlotta, Tremezzina** | Label: `☂ Rain Backup` | Note: "Stunning botanical garden + art museum. Partially covered - worth it even in drizzle"

---

## DAY 3 - SIRMIONE (Lake Garda)

### Food
- **Trattoria Clementina, Piazza Rovizzi, Sirmione** | Label: `🍝 Trattoria` | Note: "Authentic with courtyard. Zero tourist BS. Order local lake fish"
- **Osteria del Vecchio Fossato, Via Antiche Mura 16, Sirmione** | Label: `🍷 Osteria` | Note: "Hidden in old walls, intimate & quiet. Order tagliatelle with trout, aole sale"
- **Casa dei Pescatori, Sirmione** | Label: `🍽 Ristorante` | Note: "On the water near Castello Scaligero. Lake fish, organic/seasonal"
- **Trattoria Da Renato, Via Gramsci 61, Desenzano** | Label: `🍝 Trattoria` | Note: "Family place, good prices. Fish + meat"

### Sleep
- **Agriturismo La Filanda, Lake Garda** | Label: `🌾 Agriturismo` | Note: "Historic 1800s farmhouse on Garda shores. Pool. ~80-120 EUR"
- **B&B da Beatrice, Sirmione** | Label: `🛏 B&B` | Note: "Garden + pool, quiet residential zone. 2km from Sirmione center. ~70-90 EUR"
- **Agriturismo Il Ghetto, Lake Garda** | Label: `🌾 Agriturismo` | Note: "Countryside 1.2km from lake. Rustic vibe. ~70-100 EUR"

### Activities
- **Isola del Garda** | Label: `🎯 Activity` | Note: "BOOK AHEAD at isoladelgarda.com! 39-49 EUR/pp. Closed Mondays. Guided tour: villa + gardens + wine tasting + olive oil DOP. ~2.5h"
- **Castello Scaligero, Sirmione** | Label: `🏛 Sightseeing` | Note: "Medieval castle at entrance to old town. Quick visit"
- **Grotte di Catullo, Sirmione** | Label: `🏛 Sightseeing` | Note: "Roman villa ruins at the tip of the peninsula. Lake views"

### Swim
- **Lido delle Bionde, Sirmione** | Label: `🏖 Beach/Swim` | Note: "Famous! Thermal spring water mixes into the lake - warmer than other spots"
- **Jamaica Beach, Sirmione** | Label: `🏖 Beach/Swim` | Note: "Flat rocks into water. Popular with locals"

### Nightlife
- **Desenzano del Garda waterfront** | Label: `🌙 Nightlife` | Note: "THE nightlife hub on Garda. Bars, live music, clubs until 2am"

### Rain Backup
- **Terme di Sirmione** | Label: `☂ Rain Backup` | Note: "Thermal spa. Indoor pools, treatments. Perfect rainy day plan"

---

## DAY 4 - RIVA DEL GARDA + MOLVENO

### Food
- **Ponale Alto Belvedere, Riva del Garda** | Label: `🍽 Ristorante` | Note: "Restaurant ON the Ponale trail at the turnaround point. Drinks + food with insane lake view"
- **Trattoria al Faggio, Molveno** | Label: `🍝 Trattoria` | Note: "Top-rated in Molveno. Order canederli, polenta, spezzatino di capriolo (deer stew)"
- **Ristorante All'Aquila Nera e Cima Tosa, Molveno** | Label: `🍽 Ristorante` | Note: "Centro Molveno. Excellent quality/price. Trentino specialties"

### Gelato
- **Peccati di Gola, Riva del Garda** | Label: `🍦 Gelateria` | Note: "Since 1998. Artisanal gelato, crepes, granita with fresh fruit"

### Sleep
- **Agriturismo Ai Castioni, Molveno** | Label: `🌾 Agriturismo` | Note: "Lake + Brenta Dolomites view from balcony. Peaceful. ~90-120 EUR"
- **B&B Il Nido, Molveno** | Label: `🛏 B&B` | Note: "Breakfast + parking + Dolomiti Paganella Guest Card (FREE cable cars!). ~70-90 EUR"
- **B&B Le Coccole, Molveno** | Label: `🛏 B&B` | Note: "Overlooking Lake Molveno. 'Corner of paradise'. ~80-100 EUR"

### Hikes & Scenic
- **Sentiero del Ponale, Riva del Garda** | Label: `🥾 Hike Start` | Note: "DAY HIKE #1. Old road carved into cliff face above Lake Garda. 6 km RT, 2-2.5h, +200m. Tunnels through rock. One of Italy's most famous walks"
- **Strada della Forra, Tremosine sul Garda** | Label: `🛣 Scenic Drive` | Note: "DO NOT MISS. 6 km gorge, insane hairpins through carved rock. Most spectacular road in Europe. James Bond (Quantum of Solace)"
- **Fortini di Napoleone, Molveno** | Label: `🥾 Hike Start` | Note: "Easy historical walk from Molveno centro. ~1h"

### Swim
- **Spiaggia Lago di Molveno** | Label: `🏖 Beach/Swim` | Note: "5 Vele award (best beach in Italy!). Crystal water, Brenta Dolomites backdrop. Water ~16-18C end May"

### Nightlife
- **Sailing Bar, Riva del Garda** | Label: `🌙 Nightlife` | Note: "Shaped like a ship. Sunset aperitivo + live music + DJ sets"

### Activity
- **Bike Center Limone, Via IV Novembre 29, Limone sul Garda** | Label: `🎯 Activity` | Note: "Bike rental for Limone-Riva suspended bike path. 2.5 km, insane views. E-bike ~25-35 EUR"

### Rain Backup
- **Climbing Stadium, Arco** | Label: `☂ Rain Backup` | Note: "Indoor climbing wall near Riva. Good rainy afternoon activity. 30 min from Molveno"
- **Castello di Stenico** | Label: `☂ Rain Backup` | Note: "Medieval castle, 20 min from Molveno. Indoor museum"

---

## DAY 5 - MOLVENO (Brenta Dolomites + Tovel)

### Hikes
- **Rifugio Croz dell'Altissimo, Molveno** | Label: `🏔 Rifugio` | Note: "DAY HIKE #2. Take cabinovia from Molveno to Pradel, then hike ~6 km RT, 3h, +400m. Forest into Brenta Dolomites. EAT LUNCH HERE: canederli, polenta, strudel. Bring a layer"
- **Lago di Tovel** | Label: `🥾 Hike Start` | Note: "'The Red Lake'. 4 km loop, 1.5h, flat. Beautiful forest setting. 30 min drive from Molveno"

### Rain Backup
- **Andalo Life Park, Andalo** | Label: `☂ Rain Backup` | Note: "Indoor pool, spa, wellness, ice rink. 10 min from Molveno"
- **Castel Thun, Vigo di Ton** | Label: `☂ Rain Backup` | Note: "Medieval castle with frescoed rooms. 30 min from Molveno"

---

## DAY 6 - VAL PUSTERIA / BRAIES (Dolomites)

### Food
- **(Find a well-rated Gasthaus in Dobbiaco)** | Label: `🍺 Gasthaus` | Note: "South Tyrolean inn. Order speck, canederli, schlutzkrapfen (spinach-ricotta half-moons), kaiserschmarrn"

### Sleep
- **Hanslerhof, Braies** | Label: `🐄 Maso` | Note: "TOP PICK. 5.7 km from Lago di Braies! Family farm at 1350m. INSANE breakfast: homemade speck, eggs, milk, strudel, syrups, yogurt. ~80-110 EUR"

### Activities
- **Lago di Braies (Pragser Wildsee)** | Label: `🥾 Hike Start` | Note: "Walk the loop: 3.5 km, 1.5h, easy. West shore flat, east shore has rock steps. Turquoise water + Dolomite backdrop. Rent rowing boat at north end. Road OPEN end of May (closed Jul 10 - Sep 10 only)"
- **Lago di Dobbiaco** | Label: `🏖 Beach/Swim` | Note: "More accessible than Braies for a dip. Still cold!"

### Scenic Drive
- **Val Pusteria (Val di Non -> Val di Sole -> Val Pusteria road)** | Label: `🛣 Scenic Drive` | Note: "Mountain roads the whole way from Molveno. Every turn is a Dolomite postcard. Fill up gas before leaving!"

### Rain Backup
- **MMM Messner Mountain Museum, Brunico** | Label: `☂ Rain Backup` | Note: "Reinhold Messner's museum in Castel di Brunico. Mountain peoples + cultures. Indoor, fascinating"

### Nightlife
- **Brunico pedestrian zone** | Label: `🌙 Nightlife` | Note: "If you want a livelier evening than the quiet Gasthaus vibe. Bars + shops. 30 min from Braies"

---

## DAY 7 - VENICE

### Bacari (Venetian wine bars)
- **Cantina Do Spade, Venice** | Label: `🦑 Bacaro` | Note: "Open since 1448. Classic cicchetti. Near Rialto Market"
- **All'Arco, Venice** | Label: `🦑 Bacaro` | Note: "Family-run, tiny. Seasonal fresh cicchetti. Near Ponte di Rialto"
- **Alla Vedova, Venice** | Label: `🦑 Bacaro` | Note: "LEGENDARY polpette (meatballs). Must order. Cannaregio"
- **Al Timon, Venice** | Label: `🦑 Bacaro` | Note: "Lively, outdoor seating on canal. By Ponte delle Guglie, Cannaregio"
- **Taverna al Remer, Venice** | Label: `🦑 Bacaro` | Note: "HIDDEN GEM. Secret campiello FACING Grand Canal. Enter through anonymous alley from Strada Nuova. Cannaregio"
- **Vino Vero, Venice** | Label: `🦑 Bacaro` | Note: "'Bacaro of natural wines'. Cannaregio"
- **Osteria Al Squero, Venice** | Label: `🦑 Bacaro` | Note: "Overlooks historic gondola workshop. Perfect aperitivo spot. Dorsoduro"
- **Codroma, Venice** | Label: `🍷 Osteria` | Note: "Not a pure bacaro - osteria with proper kitchen. Off tourist circuit. Near Zattere, Dorsoduro"
- **Adriatico Venezia, Venice** | Label: `🦑 Bacaro` | Note: "Hidden 'malvasia' near Basilica dei Frari. Refined wine experience. Dorsoduro"

### Gelato & Coffee
- **Gelateria Suso, Venice** | Label: `🍦 Gelateria` | Note: "Near Rialto. Natural ingredients, eco-conscious. One of the best"
- **Da Nico, Zattere, Venice** | Label: `🍦 Gelateria` | Note: "80+ years! Famous for GIANDUIOTTO (chocolate-hazelnut frozen block). Terrace facing Giudecca canal. THE gelato moment"
- **Alaska Gelateria, Venice** | Label: `🍦 Gelateria` | Note: "30+ years. Creative: zafferano, cardamomo, zenzero. For the adventurous"

### Sleep
- **B&B in Cannaregio, Venice** | Label: `🛏 B&B` | Note: "RECOMMENDED ZONE. Best value in Venice. Near Alla Vedova, Al Timon, Fondamenta della Misericordia. ~70-100 EUR"

### Nightlife
- **Fondamenta della Misericordia, Venice** | Label: `🌙 Nightlife` | Note: "THE spot for Venice nightlife. Multiple bars along this canal. Locals hang out here, lively late. Cannaregio"

### Sightseeing
- **Rialto Fish Market, Venice** | Label: `🏛 Sightseeing` | Note: "Go EARLY morning to see it in action. Grab cornetto + caffe nearby"

### Parking
- **Parcheggio Mestre (near train station)** | Label: `🅿 Parking` | Note: "5-15 EUR/day. Train to Venezia Santa Lucia 10 min, ~2 EUR. Pre-book on parclick.it"

### Rain Backup
- **Peggy Guggenheim Collection, Venice** | Label: `☂ Rain Backup` | Note: "World-class modern art. Dorsoduro. Indoor"
- **Teatro La Fenice, Venice** | Label: `☂ Rain Backup` | Note: "Guided tour of one of the world's most beautiful opera houses"

---

## DAY 8 - MILAN

### Food
- **Trattoria Milanese dal 1933, Milan** | Label: `🍝 Trattoria` | Note: "Institution near Duomo. Order risotto alla milanese + ossobuco + cotoletta. Tight tables, timeless"
- **Antica Trattoria della Pesa, Milan** | Label: `🍝 Trattoria` | Note: "Since 1880. Milanese generations eat here. Cotoletta in clarified butter. Risotto, ossobuco"
- **Madonnina, Milan** | Label: `🍝 Trattoria` | Note: "Daily-updated menu. Mastered the holy trinity: cotoletta, ossobuco, risotto"

### Gelato & Coffee
- **Artico Gelateria, Milan** | Label: `🍦 Gelateria` | Note: "Top-rated in Milan. Pistacchio salato is legendary. 3 Coni Gambero Rosso"
- **Pave Gelati & Granite, Milan** | Label: `🍦 Gelateria` | Note: "Gelato + granite + pastries. Near center"
- **Orsonero Caffe, Milan** | Label: `☕ Caffe` | Note: "Specialty coffee pioneer. Cold brew, aeropress, pour-over"
- **Loste Cafe, Milan** | Label: `☕ Caffe` | Note: "Amazing pastries (pain au chocolat, cinnamon roll) + specialty coffee"

### Nightlife
- **Navigli, Milan** | Label: `🌙 Nightlife` | Note: "Aperitivo Milanese: buy a drink (~8-10 EUR), get buffet of snacks. The whole canal is lined with competing bars. THE Milan ritual"

### Sightseeing
- **Duomo di Milano** | Label: `🏛 Sightseeing` | Note: "Even just the piazza is impressive. Quick visit"
- **Galleria Vittorio Emanuele II, Milan** | Label: `🏛 Sightseeing` | Note: "Walk through, grab an espresso. Beautiful architecture"

---

## SCENIC ROUTES (mark as lines/directions if possible)

- **SS33 Arona -> Stresa** | Label: `🛣 Scenic Drive` | Note: "Day 1. Lake shore road. First views of Lago Maggiore"
- **SS34 Stresa -> Verbania** | Label: `🛣 Scenic Drive` | Note: "Day 2. Hugging the lake shore"
- **Laveno-Intra car ferry** | Label: `🎯 Activity` | Note: "Day 2 option. Ferry across Lake Maggiore. ~20 min, ~15 EUR. Cool experience"
- **Val di Non -> Val di Sole -> Val Pusteria** | Label: `🛣 Scenic Drive` | Note: "Day 6. All mountain roads through Dolomites. Every turn is a postcard. Fill up gas first!"

---

IMPORTANT: If any of these places are already saved in the list, don't add duplicates. Instead, just update/add the label and note if they're missing. Work through the list systematically, one day at a time.
