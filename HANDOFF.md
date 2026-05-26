# Italy Trip — Conversation Handoff

> Read this first. You are picking up an existing Claude Code session on a different device. Full state below.

## Who / What / When

- **Trip:** Lev + 1 friend (2 guys), Italy road trip
- **Dates:** Sun May 31 → Sun Jun 7, 2026 (8 days)
- **Flight:** Arrive MXP 11am Sunday, depart MXP 8pm following Sunday
- **Route:** Milan → Lake Maggiore → Lake Como → Lake Garda → Trentino → Dolomites (2 nights) → Venice (1 night) → Milan
- **Total driving:** ~960 km
- **Budget vibe:** Not expensive — agriturismi, B&Bs, pensioni. Nice but affordable.
- **Season note:** End of May = pre-peak. Pragser Wildsee road OPEN (closes Jul 10 only). Water still chilly — quick swims only.

## Repo

- **Local path:** `/Users/levgourevitch/Documents/Documents - QG4ML4QJ1H/private/italy/`
- **GitHub:** https://github.com/levgou/italy-trip-2026
- **Live slides:** https://levgou.github.io/italy-trip-2026/
- **Owner:** github.com/levgou

## Files

| File | Purpose |
|------|---------|
| `italy_trip_plan.md` | Full 9-day plan text — drives, restaurants, hotels, hikes, gelato, nightlife, swim spots, rain backups per day |
| `index.html` | Reveal.js slide deck — 8 days, all places have real images |
| `browser_claude_prompt.md` | Prompt for browser Claude to add labeled pins to Google Maps list |
| `img/` | 70+ local jpg/webp — restaurants, hotels, gelato, scenic drives, heroes |
| `.github/workflows/pages.yml` | Auto-deploy to GitHub Pages on push |

## Design Decisions Already Made

- **Slide deck format:** Reveal.js, fonts = Libre Baskerville (headings) + Nunito (body). Background `#F0EBE3` (parchment). Italian tricolore accent. No dark slides.
- **Image strategy:** Real photos per place, not stock. Multi-image places use `thumb-row` (160px clickable thumbnails). Click any → full-size modal. Tap/Escape closes.
- **Hotel photos prioritized** so friend can book.
- **Labels for Google Maps pins:** `🍝 Trattoria`, `🍷 Osteria`, `🦑 Bacaro`, `🍽 Ristorante`, `🏔 Rifugio`, `🍺 Gasthaus`, `🍦 Gelateria`, `☕ Caffe`, `🌾 Agriturismo`, `🛏 B&B`, `🐄 Maso`, `🏨 Hotel`, `🥾 Hike Start`, `🛣 Scenic Drive`, `👁 Viewpoint`, `🏖 Beach/Swim`, `🎯 Activity`, `☂ Rain Backup`, `🌙 Nightlife`, `🏛 Sightseeing`, `🅿 Parking`

## Day-by-Day Summary

- **Day 1 (Sun)** MXP → Stresa, Borromean Islands. Sleep Stresa.
- **Day 2 (Mon)** Stresa → Como via Sasso del Ferro. Brunate + Greenway. Sleep Como.
- **Day 3 (Tue)** Como → Sirmione. Isola del Garda tour (BOOK AHEAD, closed Mon). Sleep Garda.
- **Day 4 (Wed)** Garda → Riva → Molveno via **Strada della Forra**. Hike #1: **Sentiero del Ponale**. Sleep Molveno.
- **Day 5 (Thu)** Brenta Dolomites. Hike #2: **Rifugio Croz dell'Altissimo** from Pradel cabinovia. Tovel afternoon. Sleep Molveno (2nd night).
- **Day 6 (Fri)** Molveno → Lago di Braies. Walk lake, rowing boat. Val Pusteria villages. Sleep Hanslerhof.
- **Day 7 (Sat)** Val Pusteria → Venice via Lago di Santa Croce. Bacaro tour Cannaregio. Sleep Venice (B&B Cannaregio).
- **Day 8 (Sun)** Venice → Milan (opt. Verona stop). Last meal: cotoletta + ossobuco + risotto. MXP 8pm flight.

## Bookings Required

| What | Where | When |
|------|-------|------|
| Isola del Garda tour | isoladelgarda.com | Day 3 Tue, ~39-49 EUR/pp, closed Mon |
| Venice parking Mestre | parclick.it | Day 7, 5-15 EUR/day |
| Borromean Islands ferry | navigazionelaghi.it | Day 1, walk-up OK every 30 min |

## Top Hotel Picks (for friend to book)

- **Day 1 Stresa:** Agriturismo Nel Giardino di Dafne (~100-130 EUR) OR Hotel La Palma (~120-150 EUR)
- **Day 2 Como:** Agriturismo Treterre (~90-120 EUR) — TOP PICK, infinity pool
- **Day 3 Garda:** Agriturismo La Filanda (~80-120 EUR) — historic 1800s farmhouse
- **Day 4-5 Molveno (2 nights):** Agriturismo Ai Castioni OR B&B Il Nido (free cable car passes!)
- **Day 6 Braies:** **Hanslerhof** maso — TOP PICK, 5.7 km from lake, insane breakfast
- **Day 7 Venice:** B&B in Cannaregio (~70-100 EUR)

## Open Items / Possible Next Work

- More restaurant images for Days 3-8 (only Days 1-2 fully photo'd)
- More scenic shots: Strada della Forra, Sentiero del Ponale, Venice bacari, Milan trattorias, cotoletta
- Add Day 8 Milan-specific images
- Compact PDF version of trip plan for offline use in car
- Verify Pages deploy succeeded

## User Preferences (carry forward)

- Casual + fun tone. Russian banter OK in Cyrillic only (gopnik slang: братан, давай, погнали). Technical content in English.
- One step at a time for multi-step changes. Don't batch.
- Don't run `Read` on images — burns tokens. Use `file` for dimensions.
- For image fetching: open Google Images search via `open` command, user saves to img/, then rename. Use `.sep-<name>` separator files to track which batch belongs to which place.
- "Show all images for a place" pattern: `img-card > thumb-row > <img>...<img>`. Each clickable → modal.
- No emojis in code/files unless requested. Emojis in chat OK.

## How To Pick Up

You can verify state with:
```bash
cd "/Users/levgourevitch/Documents/Documents - QG4ML4QJ1H/private/italy"
git log --oneline | head
ls img/ | wc -l
open index.html  # preview slides
```

If user asks to keep adding images, the workflow is:
1. `touch .sep-<placename>` (separator marker)
2. `open "https://www.google.com/search?q=<place>&tbm=isch&tbs=isz:l"` (open Google Images, large filter)
3. Wait for user to save image(s) to `img/` folder
4. `find . -newer .sep-<placename> -name "*.jpg"` to see what landed
5. Rename to clean filename (e.g. `mv weird-name.jpg place-1.jpg`)
6. Update HTML to use new image
7. Remove `.sep-*` files at end

---

## Export-Back Instructions (read when user wants to migrate back)

When the user says they want to take this conversation BACK to another Claude session, do this:

1. **Re-read this HANDOFF.md.** Use it as base.
2. **Append a section** called `## Updates During This Session` summarizing:
   - What got done (new images, slide changes, plan tweaks, commits)
   - Any new decisions made
   - Any new files added or removed
   - Current state of any open items
3. **Commit the updated HANDOFF.md** to the repo.
4. **Tell the user:** "Updated HANDOFF.md committed. Pull repo on other device, paste contents of HANDOFF.md into the new Claude session, and continue."
5. If new conversation is on Claude.ai (web/mobile) without filesystem access, also output the full HANDOFF.md contents in a code block in chat so user can copy directly.

Keep this HANDOFF.md as the **single source of truth** for cross-device handoffs. Update it before every migration.
