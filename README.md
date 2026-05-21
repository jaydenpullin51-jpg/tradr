# Tradr — Tinder Parody for Blue-Collar Businesses

Single-file Tinder-style swipe app for Santino's marketing video.

## Run it

Double-click `index.html` to open in Chrome. No build step, no install.

For cleanest screen-recording: open in Chrome, hit `Cmd+Shift+M` for device toolbar, pick iPhone 14 Pro. Or just record the centered 390×844 phone frame on the desktop view.

## Deck

8 cards, fixed order:

1. HVAC — Cold Front HVAC, Phoenix
2. Plumbing — Hank's Plumbing, Charlotte
3. Electrical — Daugherty Electric, Indianapolis
4. Landscaping — Greenline Landscaping, Tampa
5. Pressure Washing — Rojas Pressure Pros, Tulsa
6. Concrete — Big Mike's Concrete, Nashville *(no hero image — uses colored placeholder)*
7. General Contracting — Sutter & Sons GC, Boise
8. **Subcontract** — luxe black + gold "holy grail" card (no image)

## Hero images

Drop into `images/`, matching these filenames:

- `images/hvac.png`
- `images/plumbing.png`
- `images/electrical.png`
- `images/landscaping.png`
- `images/pressure-washing.png`
- `images/concrete.png` *(currently missing — placeholder fallback)*
- `images/general-contracting.png`

Swap or add `.jpg` versions if needed — edit the `hero:` path in the `BUSINESSES` array at the top of the `<script>` tag in `index.html`.

## Final reveal image

The climax of the video. Drop the reveal at:

- `images/subcontract-reveal.png` (preferred)
- `images/subcontract-reveal.jpg` (auto-fallback)

If missing, the overlay shows `[ subcontract-reveal.png goes here ]` so the flow still works for testing. The `<img>` tag is wrapped in a clearly-marked comment block in `index.html` (search "FINAL REVEAL IMAGE").

## How the flow works

- Swipe / drag cards left (Nope) or right (Like). Buttons trigger the same animation.
- Right-swipe on a normal card → "It's a match!" modal flashes → dismiss with "Keep Swiping".
- Reach card 8 (Subcontract) — luxe black + gold, slow pulse glow.
  - **Right-swipe / Like** → full-screen reveal image (the climax). Click anywhere to continue → end screen.
  - **Left-swipe / Nope** → "Wrong answer." modal → "Try again" puts Subcontract back on top.
- End screen: "Out of profiles in your area" with a Restart button.

## Editing the deck

Open `index.html`, find the `BUSINESSES` array near the top of the `<script>` tag. Each entry has `name`, `age`, `city`, `hero`, `bio`, `tags`, and `details`. Order in the array = order in the deck.
