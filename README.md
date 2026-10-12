# offiRent — nieuwe website (concept)

Statische one-pager voor offirent.be: `index.html` + `media/`. Geen build-stap — open `index.html` of deploy de map (bv. Netlify drag & drop).

## Wat zit erin
- Full-screen hero-video (kantoor/werkomgeving), aparte staande versie voor mobiel, WebM + MP4, poster-afbeelding, pauzeknop, respecteert `prefers-reduced-motion`.
- offiRent-huisstijl: zwart + groen (#6DCD7C / #2F8A3D), lime #E6FFCC, peach #FFF1E6, zeshoek-motief, origineel logo.
- Formulekiezer ("Waar sta jij vandaag?"), bento-aanbod, sticky "inbegrepen"-sectie, privacy voor/na-slider, bezwaren-FAQ, team, Stwg3-community, locatie + kaart, aanvraagformulier.

## Chatbot
`netlify/functions/chat.mjs` (endpoint `/api/chat`) gebruikt Claude via de Netlify AI Gateway — geen eigen API-sleutel nodig, kosten lopen via Netlify-credits. Rate limit: 20 berichten/minuut per IP. Valt de AI weg, dan antwoordt de chat met vaste antwoorden uit `index.html` (zoek `const faq`). De feiten die de bot kent staan in `SYSTEM` in de functie — pas die aan als prijzen of diensten veranderen.

## Formulier
Aanvragen gaan naar Netlify Forms (formulier `aanvraag`). Stel in Netlify een e-mailnotificatie in naar info@offirent.be.

## Nog te doen vóór livegang
- Teamfoto's van Davy, Anja en Michel: op offirent.be bestaan die enkel als 46×56 px; nu zeshoek-monogrammen.
- "Je vaste aanspreekpunt: An Vaes" is een aanname — bevestigen.
- Prijzen van dagkantoor, vast kantoor en vergaderzaal toevoegen (nu enkel virtueel kantoor vanaf €80).
- Reviews (Google) verzamelen en tonen.
- Eigen video van het kantoor in Herk-de-Stad zou sterker zijn dan stockbeelden.

## Bronnen media
Hero-video gemonteerd uit Mixkit-clips (Mixkit Free License, commercieel gebruik toegestaan): 917, 4804, 4547, 4872.

Foto's in `media/img/` komen van offirent.be zelf.
