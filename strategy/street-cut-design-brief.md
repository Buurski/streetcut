# Street-Cut — prompt til Claude Design

This file has two things:
1. **The prompt** (next section) — paste this into Claude Design as-is. It's written loose on purpose so the design has room to breathe.
2. **The supporting brief** — palette, type, sections, motion, headline options. Reference material if Claude Design wants more, or if you want to tighten the prompt later.

---

## ✦ The prompt (paste this into Claude Design)

```
Design en landing page til Street-Cut — en kæde af frisørsaloner i København
og Odense. Den eksisterende side er www.street-cut.dk og fungerer, men ser
ud som en Webflow-skabelon. Vi vil bygge den om så den føles som et roligt,
velkureret magasin frem for en frisørkæde.

Brand-sandheden er: Street-Cut er det enkleste, mest tilgængelige sted at
få et godt klip i København. Klip fra 399 kr., fem saloner (Falkoner Allé,
to på Nørrebrogade, Rådhusstræde, Slotsgade i Odense), erfarne frisører,
bæredygtige produkter. Lav pris, høj smag. Vi vil signalere kuratering
og enkelhed — aldrig at det er billigt.

Vibe: skandinavisk redaktionel. Tænk Aesop, COS, Norse Projects, Skagen,
men varmere og mere menneskelig. Roligt, præcist, lidt magasinagtig. Ikke
trendy, ikke hypebeast, ikke korporativt, ikke "kæde". Sproget er dansk.

Palette: bone som primær baggrund (#EFE8DA), deep ink blue som primær
tekst og CTA (#142235). Sekundær bone-deep (#E5DCC7) til hover/sektioner.
Soft ink (#3E5878) til sekundær tekst. Én varm accent (#A37A4F) brugt
sparsomt — kun til ét element pr. sektion. Ingen sort, ingen gradienter,
ingen drop-shadows.

Typografi: en raffineret serif til overskrifter (fx GT Sectra, ABC Whyte
Inktrap, eller en god gratis variant som EB Garamond), tæt linjeafstand,
let negativ letter-spacing, aldrig versaler. En moderne grotesk til
brødtekst og UI (fx ABC Diatype, Söhne, eller Inter Tight / Manrope) i
kun to vægte, regular og medium. Eyebrows i tracket caps på 11-12px er
det eneste sted versaler er tilladt.

Fotografi: hero er ét stort editorial portræt — kunde midt-klipning,
godt sidelys, jordede toner som spiller mod den lyse bone-baggrund. Skal
kunne stå alene som et magasinforside-billede. Salonbilleder fra den
nuværende side bruges som dokumentation længere nede. Ingen stock,
ingen smilende model-fotos, ingen "team grid".

Layout: meget minimalistisk, men flydende — ikke et stift template-grid.
Generøs luft mellem sektioner (120-160px desktop). Hero er asymmetrisk:
typografi til venstre, portræt til højre, ca. 60/40. Max width 1320px.

Fire sektioner på siden, i denne rækkefølge:

1) HERO. Eyebrow "KØBENHAVN · ODENSE". Stor serif H1 (vælg én af de fire
   muligheder i brief'en — anbefalingen er "Lige din stil."). Sub i grotesk
   "Erfarne frisører. Fem saloner. Klip fra 399 kr." To CTA'er: "Book tid"
   (primær, ink baggrund, bone tekst) → street-cut.planway.com, og
   "Se priser" (sekundær, kun tekst med underline). Portræt-foto til højre.

2) PRISER-TEASER. Fem populære priser stillet op som store rækker —
   tjenestenavn til venstre i serif, pris til højre i grotesk, fin
   horisontal linje mellem hver. Klip 399 kr., Klip + vask 440 kr.,
   Vask + klip + føn 480 kr., Vask + klip + føn + styling 590 kr.,
   Luksusbehandling 700 kr. Afslut med stilfærdigt link "Se alle priser →".

3) SALONER-STRIP. Fem lokationer som horisontal strip eller 2-3 kolonne
   layout. Hver: lille thumbnail, adresse som overskrift, kort beskrivelse,
   "Book tid →"-link der peger på en specifik deeplink pr. salon (de
   ligger i references.md).

4) SERVICES-INTRO. Tre rolige kort: Herreklip, Dameklip, Børneklip. Hver
   med én kort linje på dansk og en pil. Ingen ikoner. Lige bredde, generøs
   padding, en tynd 0.5px border i ink-soft.

Animationer: små, raffinerede, "Figma-like" mikrointeraktioner. Aldrig
bouncy, aldrig scroll-jacking, aldrig spinning. Tilladt og anbefalet:
type fade-up med 80ms stagger pr. linje (cubic-bezier 0.22, 1, 0.36, 1,
600ms), hero-billede der reveal'er via horisontal clip-path wipe lige
efter type, magnetisk hover på primær Book tid-knap (~6px træk mod musen),
let parallax på hero-portræt (4-8px på Y når man scroller), cursor-hover
links med ink-blue underline der wipe'r ind fra venstre på 300ms, sektioner
der fade-up'er 16-24px når de kommer i viewport. Respektér prefers-reduced-motion.

Sticky nav øverst med bone-baggrund og 70% blur når man scroller, ellers
transparent. Footer minimalistisk — logo, adresser i én linje, social,
copyright.

Sproget er dansk og siden skal have lang="da". Book tid skal altid være
tilgængelig — det er den dominerende handling.

Lev efter to regler: (1) hvis du er i tvivl om en animation skal være der,
skal den ikke; (2) hvis du er i tvivl om en visuel detalje gør designet
mere eller mindre roligt, så vælg roligt.
```

---

## Supporting brief

Use this if Claude Design asks for more, or if you want to swap out parts of the prompt before pasting.

### Brand truth (one paragraph)

Street-Cut er ikke en luksussalon. De er den enkleste, mest tilgængelige vej til et godt klip i København og Odense. Klip fra 399 kr., erfarne frisører, fem saloner spredt på de centrale brokvarterer + Odense, bæredygtige produkter. Det er hverdagsfrisøren — men en hverdagsfrisør med smag. Det centrale paradoks vi designer ind i siden er **lav pris, høj smag** — premium-kvalitet i den visuelle ramme, folkelig pris i prisskiltet.

### Hvem skriver vi til

Københavnere og Odenseanere mellem 18 og 45 som vil have et hurtigt, godt klip uden snobberi. Forældre der booker børneklip. Folk der allerede kender Street-Cut og bare skal booke — det er den dominerende use case. **Book tid skal altid være synlig.**

### Hvordan det skal føles

| Skal føles som | Skal IKKE føles som |
|---|---|
| Et velkurateret magasin | Et Webflow-template |
| En rolig butik i Vesterbro | En kæde |
| En frisør som tager sig tid | En salon der haster dig igennem |
| Selvsikker uden at råbe | Trendy / hypebeast |
| Skandinavisk minimalisme | Klinisk eller koldt |

### Palette

| Token | Hex | Brug |
|---|---|---|
| bone | `#EFE8DA` | Primær baggrund |
| bone-deep | `#E5DCC7` | Sekundære flader, hover |
| ink | `#142235` | Primær tekst, primær CTA |
| ink-deep | `#0B1726` | Mørke kontrastsektioner |
| ink-soft | `#3E5878` | Sekundær tekst, fine detaljer |
| accent-warm | `#A37A4F` | Sparsomt — ét element pr. sektion |

### Typografi-rytme

- H1 hero: 96–128px desktop, serif, line-height 0.92–0.98, tracking -0.02em
- H2 sektioner: 40–56px, serif
- Brødtekst: 17px, grotesk, line-height 1.45
- Labels / eyebrows: 11–12px, grotesk, tracking 0.14em, ALL CAPS
- CTA primær: 14px medium, 14–16px padding, border-radius 0 eller max 2px

### Headline-muligheder (vælg én til hero'en)

1. **Lige din stil.** — eksisterende slogan. Kort, stærk, allerede kendt. Sikrest.
2. **Klippet, som du vil have det.** — varm, samtaleagtig. Matcher det folkelige DNA.
3. **Københavns enkleste klip.** — repositionerer på "enkleste". Premium, selvsikker.
4. **Et godt klip. Tæt på.** — mest poetisk. Læner sig op af nærhed og hverdag.

Anbefaling: gå med (1) i hero. Lad (3) eller (4) optræde som en stille statement længere nede på siden (fx mellem Saloner-strip og Services-intro som et stort centreret citat).

### Sektioner — detaljer

**Hero**. Asymmetrisk 60/40 split. Venstre: eyebrow `KØBENHAVN · ODENSE`, H1, sub `Erfarne frisører. Fem saloner. Klip fra 399 kr.`, to CTA'er stillet ved siden af hinanden. Højre: ét portræt-foto, fuldhøjt, beskåret som magasinforside.

**Priser-teaser**. Ikke en fuld prisliste. Fem rækker, tjeneste til venstre i serif, pris til højre i grotesk, fin horisontal linje (0.5px ink-soft) mellem hver. Afsluttes med `Se alle priser →` link.

**Saloner-strip**. Horisontal scroll eller 2-3 kolonne grid med fem lokationer. Hver: thumbnail (250x300px), adresse som overskrift i serif, beskrivelse i 14px grotesk, `Book tid →` der peger på den specifikke planway-deeplink.

**Services-intro**. Tre rolige kort i lige bredde: Herreklip, Dameklip, Børneklip. Hver med kort dansk linje + pil. Ingen ikoner. Tynd 0.5px border, generøs padding (40px), bone-deep hover.

### Motion-principper

Den vigtigste regel: **animationer skal man ikke lægge mærke til. De skal bare føles rigtige.**

Tilladt og anbefalet:
- Type reveal: H1 fade-up + stagger pr. linje, 80ms forsinkelse, cubic-bezier(0.22, 1, 0.36, 1), 600ms
- Image reveal: hero-foto kommer ind via horisontal clip-path wipe fra venstre til højre, 900ms, lige efter type
- Magnetic CTA: primær Book tid-knap har let magnetisk hover (~6px træk mod musen)
- Parallax-portræt: hero-billedet bevæger sig 4-8px på Y når man scroller
- Cursor hover: links får en ink-blue underline der wipe'r ind fra venstre, 300ms
- Sektioner: subtle fade-up (16-24px translate, 600ms) når 30% af sektionen er i viewport
- Sticky nav: bone-baggrund med 70% blur når man scroller forbi første viewport-højde

Forbudt: bouncy/spring, scroll-jacking, auto-play, spinning, drop-shadows på interaktioner, 3D-tilt, confetti.

### Tilgængelighed

- Kontrast bone + ink = 14.6:1 (AAA på body og headlines)
- Synlig focus ring i ink-soft, 2px outline, 4px offset
- Respektér `prefers-reduced-motion`
- Touch targets min. 44px
- `lang="da"` på html-tag

### Praktiske referencer

- Eksisterende site (det vi bygger om): https://www.street-cut.dk/
- Eksisterende priser: https://www.street-cut.dk/priser
- Booking-deeplinks pr. salon: se `references.md` i samme mappe
- Billedmateriale: se `assets/photos/` (hero, saloner, atmosfære, produkter)
- Logo: se `assets/logos/` (primær, alternativ, hvid)
- Inspirerende sites: aesop.com, cos.com, norseprojects.com, skagen.com

### Leverancer fra Claude Design

1. En enkelt landing page med de fire sektioner (Hero, Priser-teaser, Saloner-strip, Services-intro)
2. Desktop-first, men også mobile breakpoint
3. Faktiske animationer implementeret som beskrevet (ikke kun statisk)
4. Dansk copy gennemført
5. Brug de eksisterende fotos fra `assets/` — eller foreslå nye hvis et bestemt billede mangler

---

*Sidst opdateret: 19. maj 2026*
