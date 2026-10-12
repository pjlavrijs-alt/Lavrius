# offiRent — nieuwe website (concept)

Statische one-pager voor offirent.be: `index.html` + `media/`. Geen build-stap — open `index.html` of deploy de map (bv. Netlify drag & drop).

## Wat zit erin
- Full-screen hero-video (kantoor/werkomgeving), aparte staande versie voor mobiel, WebM + MP4, poster-afbeelding, pauzeknop, respecteert `prefers-reduced-motion`.
- offiRent-huisstijl: zwart + groen (#6DCD7C / #2F8A3D), lime #E6FFCC, peach #FFF1E6, zeshoek-motief, origineel logo.
- Formulekiezer ("Waar sta jij vandaag?"), bento-aanbod, sticky "inbegrepen"-sectie, privacy voor/na-slider, bezwaren-FAQ, team, Stwg3-community, locatie + kaart, aanvraagformulier.

## Chatbot
`netlify/functions/chat.mjs` (endpoint `/api/chat`) gebruikt Claude via de Netlify AI Gateway — geen eigen API-sleutel nodig, kosten lopen via Netlify-credits. Rate limit: 20 berichten/minuut per IP. Valt de AI weg, dan antwoordt de chat met vaste antwoorden uit `index.html` (zoek `const faq`). De feiten die de bot kent staan in `SYSTEM` in de functie — pas die aan als prijzen of diensten veranderen.

## Aanvragen → info@offirent.be
Twee Netlify-formulieren:
- `aanvraag` — het contactformulier onderaan de pagina
- `chat-lead` — een chatgesprek waarin de bezoeker een telefoonnummer of e-mailadres achterlaat (volledig gesprek wordt meegestuurd)

**Verplicht in te stellen:** Netlify → project `offirent-concept` → Project configuration → Notifications → Emails and webhooks → *Form submission notifications* → Add notification → Email notification → Event: *New form submission*, Form: *Any form*, E-mail: `info@offirent.be`.

## Reviews
Sectie `#reviews` linkt naar het Google-bedrijfsprofiel. Score, aantal en citaten vul je in via `const GOOGLE` in `index.html` (alleen echte, letterlijke Google-reviews).

## Nog te doen vóór livegang
- Teamfoto's van Davy, Anja en Michel: op offirent.be bestaan die enkel als 46×56 px; nu zeshoek-monogrammen.
- "Je vaste aanspreekpunt: An Vaes" is een aanname — bevestigen.
- Google-score, aantal reviews en 2–4 citaten invullen in `const GOOGLE`.
- Eigen video van het kantoor in Herk-de-Stad zou sterker zijn dan stockbeelden.

## Bronnen media
Hero-video gemonteerd uit Mixkit-clips (Mixkit Free License, commercieel gebruik toegestaan): 917, 4804, 4547, 4872.

Foto's in `media/img/` komen van offirent.be zelf.
