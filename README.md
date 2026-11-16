# jellyfin-nocturnalV2-theme

**Nocturnal** — a dark, moonlit custom CSS theme for Jellyfin Web (10.10 / 10.11).
Deep navy surfaces, periwinkle accent, rounded pill tabs, Space Grotesk headings and
Inter body text. CSS only — no plugins, no JavaScript.

## Install

1. Open Jellyfin → **Dashboard → General → Custom CSS code**.
2. Paste:

   ```css
   @import url("https://cdn.jsdelivr.net/gh/OfficialHZ/jellyfin-nocturnalV2-theme@main/nocturnal.css");
   ```

3. Save, then hard-reload the browser with **Ctrl+F5**.

> jsDelivr caches `@main` for a while. To get an update immediately, use a version tag
> instead, e.g. `...jellyfin-nocturnalV2-theme@v0.1.0/nocturnal.css`.

## Customize

Every colour, radius and font is a CSS variable. Override any of them in the same Custom CSS
box, **below** the `@import` line. For example, to switch the accent to mint:

```css
@import url("https://cdn.jsdelivr.net/gh/OfficialHZ/jellyfin-nocturnalV2-theme@main/nocturnal.css");

:root {
  --nc-accent: #7FD1C7;   /* other built-in options: #F2B872 (amber), #E58FB0 (rose) */
  --nc-radius: 10px;      /* squarer posters */
}
```

## Palette

| Token              | Value     | Used for                              |
|--------------------|-----------|---------------------------------------|
| `--nc-bg`          | `#0B0D14` | Page background                       |
| `--nc-header`      | `#0E1119` | Header, side drawer, phone bottom bar |
| `--nc-surface`     | `#121628` | Cards, panels, dialogs                |
| `--nc-surface-2`   | `#151927` | Inputs, secondary buttons             |
| `--nc-border`      | `#1F2540` | Borders                               |
| `--nc-border-soft` | `#1C2133` | Header / drawer divider               |
| `--nc-text`        | `#E8EAF2` | Main text                             |
| `--nc-text-2`      | `#C3C8D6` | Nav links, body copy                  |
| `--nc-muted`       | `#9AA1B5` | Secondary text                        |
| `--nc-accent`      | `#8B9CFF` | Accent (periwinkle)                   |
| `--nc-on-accent`   | `#0B0D14` | Text on accent                        |

Radii: `--nc-radius` 14px (posters/cards), `--nc-radius-sm` 10px (tabs/menu items),
`--nc-radius-btn` 12px (buttons/inputs), `--nc-radius-lg` 18px (dialogs),
`--nc-radius-chip` 6px (rating chips).
Fonts: `--nc-font-display` Space Grotesk, `--nc-font-body` Inter.

## Roadmap

Things in the mockups that plain CSS can't do (they'd need JavaScript or a plugin):

- The big featured "New on your server" banner on the home screen
- Library tiles as large solid-coloured blocks ("My media")
- The A–Z jump bar layout on the tablet library view (Jellyfin's own alpha picker is only recoloured)
- Library links (Movies / Shows / Anime / Music / Collections) as header tabs — Jellyfin's
  header tabs are per-page views (e.g. Home / Favorites)
- Search field inline in the desktop header (Jellyfin only has a search button)
- "NOCTURNAL" badge next to the logo
- Quality badges (4K / HD / HDR) and "N min left" labels on posters
- Collections row with stacked-poster thumbnails
- Season 1 / Season 2 segmented switch on the series page
- Text labels on detail-page buttons ("Resume S2 · E4 from 28:40", "Play from start")
- "Current episode" highlight and Watched / Up next status column in episode rows
- Phone bottom navigation bar (Jellyfin Web 10.10/10.11 doesn't render one)
- Library filter chips (Unwatched / 4K / Spanish audio …)

## Screenshots

Design mockups:

- [Home — desktop](mockup/Home%20—%20desktop.png)
- [Show detail — desktop](mockup/Show%20detail%20—%20desktop.png)
- [Home — tablet](mockup/Home%20—%20tablet.png)
- [Movies library — tablet](mockup/Movies%20library%20—%20tablet.png)
- [Home — phone](mockup/Home%20—%20phone.png)
- [Show detail — phone](mockup/Show%20detail%20—%20phone.png)
