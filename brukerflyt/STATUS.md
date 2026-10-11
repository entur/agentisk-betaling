# Brukerflyt for agentisk billettkjøp

Førsteutkast til brukerflyten for demoen med Vipps MobilePay. Agenten kjøper billett i ChatGPT, med menneskelig bekreftelse før betaling.

## Filer

| Fil | Hva det er |
|---|---|
| `agentisk-billettkjop.html` | Oversikt med begge reisene i ett kjøp, og lenker til hvert use-case |
| `bergen.html` | Use-case 1: tog Oslo S til Bergen med vindusplass i kjøreretningen |
| `lillehammer.html` | Use-case 2: tog og buss Oslo S til Aulestad i Gausdal, honnørbillett |
| `*.mmd` | Mermaid-kilden til hvert diagram. Sidene har samme kode innebygd |
| `chatgpt-flyt.png` | Oversiktsdiagrammet som bilde, til deling i Slack |

Sidene tegner diagrammene i nettleseren og trenger nett. Lokalt: `python3 -m http.server` i denne mappen.

Endres et diagram, må både `.mmd`-filen og den innebygde koden i HTML-siden oppdateres. Bildet lages på nytt med:

```
npx -y @mermaid-js/mermaid-cli@11.4.2 -i chatgpt-flyt.mmd -o chatgpt-flyt.png -s 2 -b white
```

## Neste steg

1. Lag flyten der kjøpet starter i Vipps' handleassistent, til deling fredag 9. oktober.
2. Del diagrammet over salgs-MCP og reisesøk-MCP i den felles Slack-kanalen.
3. Skriv ut use-caset fra reisesiden, slik at Vipps kan svare fra betalingssiden.
4. Gå gjennom flytene i møtet mandag 12. oktober kl. 13.

## Åpne spørsmål

- Kan tog og buss fra ulike operatører selges og betales i samme ordre?
- Kan brukeren be om vindusplass i kjøreretningen gjennom salgsflyten, og er setereservasjonen et eget tilleggsprodukt?
- Hvilken bussbillett selges mellom Lillehammer og Aulestad, og hva skjer med den hvis toget er forsinket?
- Holder bekreftelse i chatten når beløpet trekkes fra en eksisterende Vipps-avtale?
- Er telefonnummer nok til å identifisere brukeren når kjøpet starter i ChatGPT?
- Skal betalingen gå gjennom Sales API eller gjennom en egen Vipps-MCP?

## Merk

Grenen er ikke flettet inn i `main`. Repoet er offentlig, og GitHub Pages publiserer `main` til entur.github.io/agentisk-betaling. Flett inn først når sidene skal deles.
