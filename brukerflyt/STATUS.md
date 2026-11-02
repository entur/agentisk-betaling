# Brukerflyt for agentisk billettkjøp

Brukerflyten for agentisk billettkjøp, laget til samarbeidet med Vipps MobilePay. Agenten kjøper billett med menneskelig bekreftelse før betaling.

## Status 2. november 2026

- Salgs-MCP-en finnes som prototype i `entur/kix-salesmcp` (internt repo, team KI-eksperimentering). Den har fem verktøy, `get_offers`, `reserve_offers`, `pay_order`, `get_order` og `release_order`, og kjører i staging.
- Demoen er gjennomført i Claude, med bekreftelse før betaling. Betalingen er en Vipps-lenke som brukeren godkjenner i appen. Prototypen kjøper for én testkunde.
- Neste steg er samme flyt i ChatGPT, koblet til som egen MCP-server. Det krever ett endepunkt for både reisesøk og salg, og innlogging hos Entur, fordi ChatGPT ikke kan sende et fast token.
- Trekk fra Vipps-avtale og push-betaling er utsatt. Diagrammene viser flyten slik prototypen virker i dag.

## Filer

| Fil | Hva det er |
|---|---|
| `agentisk-billettkjop.html` | Oversikt med begge reisene i ett kjøp, og lenker til hvert use-case |
| `bergen.html` | Use-case 1: tog Oslo S til Bergen med vindusplass i kjøreretningen |
| `lillehammer.html` | Use-case 2: tog og buss Oslo S til Aulestad i Gausdal, honnørbillett |
| `skisser.html` | Skisser av Aulestad-kjøpet i Vipps' kjøpsassistent, ChatGPT og Enturs reiseagent, etter verktøyene i `entur/kix-salesmcp` |
| `skisser/*.png` | Én stripe per agent til deling i Slack. Lages på nytt fra `skisser.html?bilde` (se under) |
| `*.mmd` | Mermaid-kilden til hvert diagram. Sidene har samme kode innebygd |
| `chatgpt-flyt.png` | Oversiktsdiagrammet som bilde, til deling i Slack |

Sidene tegner diagrammene i nettleseren og trenger nett. Lokalt: `python3 -m http.server` i denne mappen.

Endres et diagram, må både `.mmd`-filen og den innebygde koden i HTML-siden oppdateres. Bildet lages på nytt med:

```
npx -y @mermaid-js/mermaid-cli@11.4.2 -i chatgpt-flyt.mmd -o chatgpt-flyt.png -s 2 -b white
```

Skissestripene tas som element-skjermbilder av `#vipps`, `#chatgpt` og `#reiseagent` på `skisser.html?bilde` i et vindu som er minst 2100 px bredt, med enhetsskala 2.

Diagrammene i `*.mmd` følger flytene i `entur/kix-salesmcp` under `docs/flows/`, med ChatGPT som agent i stedet for Claude.

## Neste steg

1. Koble reisesøk og salg til ChatGPT som én egen MCP-server, og kjør begge use-casene der.
2. Avklar innlogging hos Entur for ChatGPT med Team Selvbetjent.
3. Avklar med OpenAI om billetter kan selges i en publisert plugin, og om Vipps-lenken regnes som betaling utenfor ChatGPT.

## Avklart

- Tog og buss fra ulike operatører reserveres og betales i samme ordre.
- Vindus- eller midtgangsplass og kjøreretning kan ønskes ved reservasjon. Ønsket oppfylles hvis det finnes et ledig sete i samme klasse.
- Betalingen går gjennom Enturs Payments og Sales API, ikke gjennom en egen Vipps-MCP.
- Bekreftelsen som håndheves, er godkjenningen i Vipps-appen. Ja-et i chatten blir bedt om, men kan ikke kontrolleres av serveren.

## Åpne spørsmål

- To reiser i samme beskjed gir i dag to ordre og to godkjenninger i Vipps. Kan det bli én?
- Hvordan logger brukeren inn hos Entur fra ChatGPT, og gir innloggingen et bekreftet mobilnummer?
- Hvilken bussbillett selges mellom Lillehammer og Aulestad, og hva skjer med den hvis toget er forsinket?
- Trekk fra Vipps-avtale krever et mandatlag med tak. Hvem bygger det, og hos hvem skal taket ligge?

## Merk

Repoet er offentlig, og GitHub Pages publiserer `main` til entur.github.io/agentisk-betaling. Grenen `feat/brukerflyt-skisser` flettes inn først når skissene skal deles.
