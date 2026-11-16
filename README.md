# jellyfin-nocturnalV2-theme

**Nocturnal** — a dark, moonlit custom CSS theme for Jellyfin Web (10.10 / 10.11).
Deep navy surfaces, periwinkle accent, rounded pill tabs, Space Grotesk headings and
Inter body text. CSS only — no plugins, no JavaScript.

## What it styles

- **Home:** solid header with pill tabs, accent avatar ring, rounded posters that zoom
  inside their frame on hover, accent progress bars and badges
- **Side menu:** rounded items, accent highlight, user section pinned to the bottom
- **Libraries:** toolbar as chips, quiet A–Z jump bar, filter options as toggle chips
- **Movie & show pages:** backdrop band with the poster beside the title, "▶ Play"
  button, rating chips, seasons in one row, episode list, round cast photos
- **Player:** accent seek bar, readable fades, styled Up Next card
- **Login / server screens, search, dialogs, menus, user settings, admin dashboard**
- **Tablet, phone and TV** layouts, plus "reduce motion" support
- **Plugins** if installed: [Media Bar](https://github.com/IAmParadox27/jellyfin-plugin-media-bar)
  (the featured banner) and [Intro Skipper](https://github.com/intro-skipper/intro-skipper)

## Install

1. Open Jellyfin → **Dashboard → General → Custom CSS code**.
2. Paste:

   ```css
   @import url("https://cdn.jsdelivr.net/gh/OfficialHZ/jellyfin-nocturnalV2-theme@main/nocturnal.css");
   ```

3. Save, then hard-reload the browser with **Ctrl+F5**. In the desktop app, restart it
   and sign in once so it picks up the new CSS.

> jsDelivr caches `@main` for up to ~12 hours. To get an update immediately, use a
> version tag instead, e.g. `...jellyfin-nocturnalV2-theme@v0.2.0/nocturnal.css`.

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

Other useful knobs:

| Variable            | Default                          | What it does                                  |
|---------------------|----------------------------------|-----------------------------------------------|
| `--nc-login-bg`     | `none`                           | Login background, e.g. `url("/Branding/Splashscreen")` |
| `--nc-play-label`   | `"Play"`                         | Text on the detail-page Play button (`""` = icon only) |
| `--nc-poster-width` | `clamp(160px, 15vw, 260px)`      | Poster size beside the title on detail pages  |
| `--nc-hero-height`  | `62vh`                           | Height of the backdrop band on detail pages   |
| `--nc-hero-offset`  | `34vh`                           | Where the title block starts on detail pages  |
| `--nc-progress-h`   | `5px`                            | Thickness of progress bars                    |

> For the login background in the desktop app, use your server's full address,
> e.g. `url("http://your-server:8096/Branding/Splashscreen")`, and upload an image in
> **Dashboard → Branding → Splash screen**.

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
| `--nc-danger`      | `#F28B8B` | Sign out / Delete on hover            |

Radii: `--nc-radius` 14px (posters/cards), `--nc-radius-sm` 10px (tabs/menu items),
`--nc-radius-btn` 12px (buttons/inputs), `--nc-radius-lg` 18px (dialogs),
`--nc-radius-chip` 6px (rating chips), `--nc-radius-pill` (filter chips, search).
Fonts: `--nc-font-display` Space Grotesk, `--nc-font-body` Inter.

## Compatibility

- Jellyfin Web 10.10 / 10.11 in the browser, Jellyfin Media Player (desktop), the mobile
  apps, and LG webOS / Samsung Tizen TV apps.
- Native apps (Android TV, Fire TV, Roku, Swiftfin) don't use Custom CSS.
- The theme avoids `:has()`, flex `gap` and `backdrop-filter`, which the desktop app's
  engine ignores or draws badly.

## Roadmap

Things in the mockups that plain CSS can't do (they need JavaScript or a plugin):

- The big featured banner on the home screen — install the **Media Bar** plugin; the theme
  styles it to match
- Library tiles as large solid-coloured blocks ("My media")
- The A–Z jump bar *layout* on the tablet library view (Jellyfin's own picker is restyled)
- Library links (Movies / Shows / Anime / Music / Collections) as header tabs — Jellyfin's
  header tabs are per-page views (e.g. Home / Favorites)
- Search field inline in the desktop header (Jellyfin only has a search button)
- "NOCTURNAL" badge next to the logo
- Quality badges (4K / HD / HDR) and "N min left" labels on posters
- Collections row with stacked-poster thumbnails
- Season 1 / Season 2 segmented switch on the series page
- Dynamic button text ("Resume S2 · E4 from 28:40") — the Play button shows a fixed label
- "Current episode" highlight and Watched / Up next status column in episode rows
- Phone bottom navigation bar (Jellyfin Web 10.10/10.11 doesn't render one)

## Screenshots

Design mockups:

- [Home — desktop](mockup/Home%20—%20desktop.png)
- [Show detail — desktop](mockup/Show%20detail%20—%20desktop.png)
- [Home — tablet](mockup/Home%20—%20tablet.png)
- [Movies library — tablet](mockup/Movies%20library%20—%20tablet.png)
- [Home — phone](mockup/Home%20—%20phone.png)
- [Show detail — phone](mockup/Show%20detail%20—%20phone.png)

## Credits

Builds on lessons from [Nocturnal v1](https://github.com/OfficialHZ/jellyfin-nocturnal-theme)
(selectors verified on 10.11, the playback-transparency fix, the detail-page layout).
