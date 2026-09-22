# VakmanBot — landingspagina

Statische site (geen build-stap nodig): `index.html` + `privacy.html`.

## Live zetten via GitHub Pages

1. **Repository klaarzetten**
   - Maak (of gebruik) een repo, bijv. `vakmanbot-website`.
   - Zet `index.html`, `privacy.html` en `CNAME` in de **root** van de repo (niet in een submap).
   - Commit & push naar de `main`-branch.

2. **GitHub Pages inschakelen**
   - Ga naar je repo → **Settings** → **Pages**.
   - Bij "Build and deployment" → Source: **Deploy from a branch**.
   - Branch: `main`, map: `/ (root)`. Opslaan.
   - Na ~1 minuut is de site bereikbaar op `https://<jouw-gebruikersnaam>.github.io/<repo-naam>/`.

3. **Eigen domein koppelen (vakmanbot.nl)**
   - Het `CNAME`-bestand met `vakmanbot.nl` staat er al in — dat vertelt GitHub Pages welk domein erbij hoort.
   - Ga bij je domeinregistrar (waar je `vakmanbot.nl` hebt geregistreerd) naar de DNS-instellingen en voeg toe:
     - **Voor het kale domein (`vakmanbot.nl`)** — vier A-records naar GitHub Pages' IP-adressen:
       ```
       185.199.108.153
       185.199.109.153
       185.199.110.153
       185.199.111.153
       ```
     - **Voor `www.vakmanbot.nl`** (optioneel maar aan te raden) — een CNAME-record naar:
       ```
       <jouw-gebruikersnaam>.github.io
       ```
   - Terug in **Settings → Pages**: vul bij "Custom domain" `vakmanbot.nl` in en sla op. Vink **Enforce HTTPS** aan zodra die optie beschikbaar wordt (kan tot enkele uren duren na DNS-propagatie).

4. **Testen**
   - Wacht op DNS-propagatie (meestal binnen een paar uur, soms tot 24u).
   - Open `https://vakmanbot.nl` en controleer: WhatsApp-knoppen, de privacy-link in de footer, de Loom-video, en de interactieve prijs-estimator.

## Bestanden in dit pakket
- `index.html` — de homepage (voorheen `vakmanbot-landing.html`)
- `privacy.html` — de privacyverklaring, al gekoppeld via de footer-link op de homepage
- `CNAME` — nodig zodat GitHub Pages weet dat dit onder `vakmanbot.nl` moet draaien
