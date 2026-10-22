# Orient Power BI TV Player

Static, browser-only Power BI TV slideshow frontend branded for **Orient Enterprise Gujarat Private Limited**. It contains no backend and does not store credentials or access tokens.

## Files

- `index.html` — app, dashboard playlist manager, playback settings, preview, and TV mode.
- `assets/orient-logo-reference.png` — temporary low-resolution crop from the supplied screenshot. Replace with Orient's approved original PNG/SVG before production.

## Before deployment

1. Create a new repository in Orient's client-owned GitHub organization, e.g. `orient-powerbi-tv-player`.
2. Upload `index.html`, `README.md`, and the `assets` folder to the repository root.
3. Replace `assets/orient-logo-reference.png` with the approved original logo, keeping the same filename or updating the `img#brandLogo` path in `index.html`.
4. In GitHub repository settings, enable **Pages** from the `main` branch and `/ (root)`.
5. Confirm with Orient IT whether the organization's GitHub plan supports restricting access to the published Pages site. A public repository/site must be treated as publicly accessible. If Pages access control is unavailable and the frontend itself must be restricted, use an IT-approved access-controlled hosting option instead; Power BI permissions do not make the static frontend private.
6. From Orient's Power BI tenant, collect each secure URL using `https://app.powerbi.com/reportEmbed?...reportId=...`. Do not use **Publish to web** links.
7. Open the published site, go to **Dashboards**, enter a dashboard name and secure URL, and add it. Configure 15-second rotation and other settings, then save.
8. Test on the actual TV/browser: Microsoft sign-in, report permissions/licensing, row-level security, cookies/session retention, fullscreen, rotation, and refresh behavior.

## Power BI URL requirements

The app accepts only HTTPS URLs whose host is `app.powerbi.com`, path is `/reportEmbed`, and query includes `reportId`. Use the secure embed URL copied from Orient's Power BI tenant. The URL alone does not grant permission.

## Security and storage notes

- No passwords, client secrets, refresh tokens, or access tokens are stored by this frontend.
- Playlist URLs and preferences are saved in `localStorage` in the current browser profile. They do not sync to other TVs and may be cleared by browser privacy settings.
- The app's configuration is not a security boundary. Access to reports is enforced by Microsoft Power BI for the signed-in user.
- Embedded Power BI may prompt for sign-in depending on the TV browser, session state, and third-party-cookie settings.
- This is a static frontend, not an unattended-authentication solution. It cannot guarantee that Microsoft sign-in will persist indefinitely.

## GitHub Pages deployment URL

After enabling Pages, use the URL shown in the repository's **Settings → Pages** screen. For a repository named `orient-powerbi-tv-player`, the URL is commonly:

`https://<orient-github-org>.github.io/orient-powerbi-tv-player/`

Replace the placeholders with the actual client organization and repository name.


## Preconfigured dashboards

The frontend includes four reportEmbed URLs from the supplied screenshot: Sales Performance, Sales Overview, Opportunity Analysis, and Opportunities Executive Overview. The first, third, and fourth report IDs were transcribed from a low-resolution screenshot and should be verified against the original Power BI links before production. These URLs do not grant access; each viewer still needs the appropriate Orient Power BI permissions and licensing. The app uses browser-local storage for settings and contains no credentials or access tokens.
