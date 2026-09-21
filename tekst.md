<!--
  REDIGERINGSFIL for pre-readen til Vipps MobilePay.
  Kilde: 2026-09-18-agentisk-betaling-vipps-preread.html

  Skriv fritt i teksten under. Når du er ferdig, si fra, så fletter jeg
  endringene inn i HTML-en. Å redigere her endrer ikke HTML-en av seg selv.

  Ankerlinjene <!-- @seksjon.NN . element --> forteller hvor hver tekstbit
  hører hjemme i HTML-en. La dem stå, og la teksten bli stående under
  sitt eget anker. Ett anker er ett element i HTML-en, så hold blokken
  samlet som ett avsnitt. Linjeskift inne i en blokk forsvinner.

  Vil du fjerne noe, stryk teksten og skriv SLETT på linjen. Vil du legge
  til et nytt avsnitt, skriv det der det hører hjemme og marker det NYTT.
  Da tar jeg det som et nytt element når jeg fletter.

  Formatering som blir med tilbake til HTML-en:
    **fet**              fet skrift
    *kursiv*             kursiv
    `kode`               kodeutheving, for eksempel `FLEXIBLE`
    {{kilde:Navn>URL}}   kildehenvisning i hevet skrift
    {{lenke:Tekst>URL}}  vanlig lenke

  To vedlegg nederst: navigasjonslenkene øverst på siden, og teksten inne
  i figurene. Figurtekst er plassert manuelt i en tegning, så der må nye
  formuleringer være omtrent like lange som de gamle.
-->

# Pre-read til Vipps MobilePay, all tekst


---

<!-- ===== seksjon: <section id="head"> ===== -->

<!-- @head.01 . title -->
Agentisk betaling, forarbeid til et møte med Vipps MobilePay

<!-- @head.02 . h1 -->
# Agentisk betaling

<!-- @head.03 . p -->
Entur er salgs- og distribusjonsinfrastrukturen for norsk kollektivtransport. Dette er et notat utarbeidet i forkant av møte med Vipps om ett konkret mål: et gjennomført agentkjøp av en norsk kollektivbillett før jul. Under følger våre betraktninger av hvor feltet står, hva vi tror et agentmandat kan kreve av en betalingsavtale, og spørsmålene vi trenger svar på for å komme dit.

<!-- @head.09 . divider -->
MER DETALJER ↓


---

<!-- ===== seksjon: <section id="hensikt"> ===== -->

<!-- @hensikt.01 . h2 -->
## Hensikten med møtet

<!-- @hensikt.02 . p -->
Å enes om et samarbeid om å tilrettelegge for agentisk kjøp over Enturs og Vipps' infrastruktur.

<!-- @hensikt.03 . div.k -->
HENSIKT

<!-- @hensikt.04 . div.v -->
Legge til rette for at en AI-agent kan kjøpe kollektivbilletter i Norge på infrastrukturen Entur og Vipps allerede har mellom seg, innenfor en ramme den reisende har godkjent selv.

<!-- @hensikt.05 . div.k -->
ØNSKET RESULTAT

<!-- @hensikt.06 . div.v -->
Et gjennomført kjøp via en tredjepartsagent før jul, med ekte billett og ekte betaling.

<!-- @hensikt.07 . div.k -->
FORESLÅTT CASE

<!-- @hensikt.08 . div.v -->
To reiser som demonstrerer hvor en agent kan brillere. **Billett med setereservasjon til Bergen:** et produkt med beholdning, der reservasjonen må holdes mens betalingen går. **Togbillett til Lillehammer med overgang til lokal buss:** to operatører, to tariffeiere, ett kjøp og én belastning.

<!-- @hensikt.09 . div.k -->
TEKNISK HYPOTESE

<!-- @hensikt.10 . div.v -->
En betalings-MCP. Salgs- og betalingssteget eksponeres som verktøy en agent kan kalle, med mandatkontrollen foran betalingen og ikke inne i agenten. Søkelaget finnes allerede som MCP-server hos Entur. Kjøpssiden er det vi trenger å gå opp.


---

<!-- ===== seksjon: <section id="sammendrag"> ===== -->

<!-- @sammendrag.01 . h2 -->
## Sammendrag

<!-- @sammendrag.02 . p -->
Agentisk betaling vil si at en AI-agent gjennomfører kjøp på vegne av et menneske, innenfor rammer mennesket har satt på forhånd. Feltet har gått fra pilot til faktisk tjeneste i det europeiske markedet, men foreløpig i lavt volum. Det forskyver hvem som eier kunderelasjonen, og det treffer alle som selger noe på nett, også kollektivbilletter. Kunnskapsgrunnlaget under er sammenstilt av Entur våren og sommeren 2026, og deles her fordi neste steg krever at vi og Vipps har et omforent verdensbilde.

<!-- @sammendrag.03 . li -->
- **Vipps MobilePay har pekt ut UCP.** Utviklerdokumentasjonen for agentisk handel støtter Universal Commerce Protocol, med en egen betalingshandler for lommebok og kort.{{kilde:Vipps>https://developer.vippsmobilepay.com/docs/APIs/agentic-commerce/}} For oss er det et tydelig signal om hvilket checkout-spor norsk agentisk handel går i. Mandatformatet, altså hvordan brukerens ramme uttrykkes og håndheves, er derimot fortsatt åpent, og det er der vi tror samarbeidet ligger.

<!-- @sammendrag.04 . li -->
- **Halve mekanismen finnes allerede mellom oss.** Entur bruker Vipps betalingsavtaler i dag, og ad-hoc-trekk mot en godkjent avtale er i drift. Mennesket godkjenner én gang, agenten belaster uten ny autentisering. Det som mangler er rammen: `FLEXIBLE` er den eneste avtaletypen som tillater ad-hoc-trekk, og den bærer verken beløp, intervall eller maksgrense. **Det er det tekniske spørsmålet vi vil løse sammen.**

<!-- @sammendrag.05 . li -->
- **Reisemarkedet er allerede i agentene.** Bolt selger ride-hailing i ChatGPT i Norge, Flix ligger der med søk, Omio selger norske togreiser gjennom partnere. Ingen norsk kollektivaktør er der ennå. Travelport har lagt MCP oppå salgs- og servicelaget sitt i drift hos over 400 europeiske byråer, som er samme grep vi ser for oss med vårt eget salgs-API.

<!-- @sammendrag.06 . li -->
- **Det viktigste er at rollene endrer seg.** Beslutningen og kassen flytter inn i agentflaten. Både selgeren og betalingsleverandøren risikerer å havne bak et grensesnitt noen andre eier. Det gjelder Entur og Vipps på hver vår måte.

<!-- @sammendrag.07 . li -->
- **Det vi foreslår.** Ett møte om de tre flatene der løsningen avhenger av betalingsleddet: et signert mandat Vipps kan verifisere selv, step-up til Vipps når en forespørsel overskrider taket, og en tilbaketrekking som forplanter seg begge veier. Målet er et gjennomført kjøp via en tredjepartsagent før jul. Spørsmålene står til slutt i første del.


---

<!-- ===== seksjon: <section id="entur"> ===== -->

<!-- @entur.01 . h2 -->
## Hvorfor vi ønsker å samarbeide med Vipps

<!-- @entur.02 . p -->
Entur er salgs- og distribusjonsinfrastrukturen for norsk kollektivtransport, og bruker Vipps i dag. Vi er ikke betalingsleverandør og skal ikke bli det. Når en agent skal kjøpe en billett på vegne av en reisende, oppstår det likevel et lag mellom brukerens godkjenning og selve trekket som ingen av oss dekker i dag. Det er det laget vi vil snakke om.

<!-- @entur.03 . tag -->
DET SOM FINNES

<!-- @entur.04 . h3 -->
### Halve mekanismen er i produksjon

<!-- @entur.05 . p -->
Kunden godkjenner en betalingsavtale én gang i Vipps, og trekk kan deretter gjennomføres uten ny autentisering. Det er nøyaktig formen et agentkjøp trenger: sterk kundeautentisering ved oppsett, deretter trekk initiert av brukerstedet.

<!-- @entur.06 . p -->
Mandatmodellen har hjemmel i finansavtaleloven § 4-3,{{kilde:Lovdata>https://lovdata.no/dokument/NL/lov/2020-12-18-146/KAPITTEL_4-3}} så dette ligger inne i dagens PSD2-regime, ikke foran det.

<!-- @entur.07 . tag -->
DET SOM MANGLER

<!-- @entur.08 . h3 -->
### Rammen agenten skal holde seg innenfor

<!-- @entur.09 . p -->
Et agentmandat trenger fire ting en betalingsavtale i dag ikke bærer samlet: tak per trekk og per periode, formålsbinding altså hvilke produkter og operatører som er tillatt, et kort utløp, og en tilbaketrekking som virker umiddelbart fra begge sider.

<!-- @entur.10 . p -->
Avtaletypen som tillater ad-hoc-trekk er den eneste som ikke bærer noen av delene. Mekanikken under er derfor på plass. Rammen over er ikke.

<!-- @entur.11 . tag -->
GRENSEN VÅR

<!-- @entur.12 . h3 -->
### Det vi ikke skal bygge

<!-- @entur.13 . p -->
Entur skal ikke bli betalingsleverandør, ikke oppgjørsrail og ikke autentiseringstjeneste. Sterk kundeautentisering skal bli liggende hos Vipps, og BankID-signaturen skal bli der den er i dag.

<!-- @entur.14 . p -->
Den grensen er viktig for oss juridisk, og vi antar den er like viktig for dere.{{kilde:Norton Rose>https://www.nortonrosefulbright.com/en/knowledge/publications/cedd39c6/psd3-and-psr-from-provisional-agreement-to-2026-readiness}} Vi vil bygge et mandatlag over betalingen, ikke en parallell betalingsvei ved siden av den.


---

<!-- ===== seksjon: <section id="mandat"> ===== -->

<!-- @mandat.01 . h2 -->
## Mandatmekanismen og det som mangler

<!-- @mandat.02 . tag -->
VIPPS OG UCP

<!-- @mandat.03 . p -->
Vipps har publisert en agentisk betalingshandler bygget på UCP, sist oppdatert 25. august og merket «under development».{{kilde:Vipps>https://developer.vippsmobilepay.com/docs/APIs/agentic-commerce/}} Dokumentasjonen omtaler ikke mandater, samtykkemodell, gjentakende trekk eller beløpstak, og skjemaene ligger på `ucp.vipps.no`. Vi leser den som bevisst avgrenset til engangskjøp i denne omgang, men vi vet det ikke.

<!-- @mandat.04 . p -->
Derfor står dette spørsmålet øverst: **skal betalingshandleren bære mandat, gjentakende trekk og beløpstak, eller er den ment for engangskjøp i en agentflyt?** Svaret avgjør om rammen bygges i betalingsleddet, hos brukerstedet, eller som noe vi definerer sammen.

<!-- @mandat.05 . p -->
Mekanikken er allerede i bruk mellom oss: Entur registrerer en betalingsavtale, kunden godkjenner den i Vipps, avtalen blir aktiv, og trekk kan gjøres uten ny autentisering. Mennesket godkjenner én gang. Det som mangler er grensen agenten skal holde seg innenfor.

<!-- @mandat.06 . tag -->
KJERNEN · TAK OG AD-HOC UTELUKKER HVERANDRE

<!-- @mandat.07 . p -->
Vipps tilbyr tre avtaletyper, og Entur bruker alle tre. **`VARIABLE`** bærer en maksgrense brukeren godkjenner, men krever et fast intervall og tillater ikke trekk utenom kadensen. **`FLEXIBLE`** er den eneste som tillater ad-hoc-trekk, altså vilkårlig beløp når som helst, som er nøyaktig det en reiseagent trenger. Og `FLEXIBLE` sender kun valuta: ingen beløp, intet intervall, ingen maksgrense.

<!-- @mandat.08 . p -->
**Avtaletypen som lar agenten kjøpe fritt, er den som ikke bærer noe tak.** Slik det står i dag må mandatlaget være kilden til grensen og ikke en speiling av en grense lenger nede: telle forbruket, reservere mot taket før trekket sendes, og bekrefte eller frigi reservasjonen når svaret foreligger. Trekket krysser en systemgrense, så det finnes ingen felles transaksjon å bokføre i, og utfallet «vet ikke» må håndteres eksplisitt.

<!-- @mandat.09 . p -->
Det er en løsbar oppgave, men den blir vesentlig enklere og mer robust hvis grensen kan uttrykkes i selve avtalen. Det er derfor vi spør før vi bygger.

<!-- @mandat.25 . p -->
Mandatet fjerner ikke autentisering, det flytter den: til oppsettet, og til de sjeldne tilfellene der banken krever den på nytt.

<!-- @mandat.26 . tag -->
TAKET

<!-- @mandat.27 . h3 -->
### Hvor skal grensen ligge

<!-- @mandat.28 . p -->
En `FLEXIBLE`-avtale har ingen beløpsgrense, så rammen må defineres, telles og håndheves før hvert trekk. Rekkefølgen er reserver, send trekk, bekreft eller frigi. Teller man først etter at trekket er sendt, lekker taket når agenten kjøper to ting samtidig.

<!-- @mandat.29 . p -->
Spørsmålet til dere er om denne tellingen hører hjemme hos brukerstedet, eller om en avtaletype kan bære et tak som Vipps håndhever. Begge deler er mulige svar. Vi vil bare unngå å bygge to tellere som er uenige.

<!-- @mandat.30 . tag -->
TILBAKETREKKING

<!-- @mandat.31 . h3 -->
### Stopp må virke begge veier

<!-- @mandat.32 . p -->
I dag stopper kunden en avtale i Vipps-appen, og vi speiler status når webhooken kommer. For et agentmandat trenger vi i tillegg det motsatte: at en stopp initiert fra Enturs side tar effekt umiddelbart, og at kunden kan trekke mandatet fra våre egne flater uten å gå veien om agenten.

<!-- @mandat.33 . p -->
Anbefalt tid til full spredning for legitimasjon som kan utløse betaling er under 15 minutter. Det er en felles oppgave, ikke en vi kan løse alene på vår side.


---

<!-- ===== seksjon: <section id="neste"> ===== -->

<!-- @neste.01 . h2 -->
## Seks spørsmål vi bør besvare

<!-- @neste.02 . p -->
Sortert etter hvor mye svaret flytter. De to første avgjør om rammen bygges i betalingsleddet eller hos brukerstedet, og dermed hvor stort dette løftet blir for oss.

<!-- @neste.03 . li -->
- **Skal UCP-betalingshandleren bære mandat, gjentakende trekk og beløpstak?** Dokumentasjonen er publisert, men omtaler det ikke. Svaret avgjør om betalingsavtalene vi bruker i dag kan kobles på UCP-sporet, eller om vi ender med to parallelle mekanismer, og hvordan et UCP-mandat i det hele tatt oversettes til `FIXED`, `VARIABLE` og `FLEXIBLE`.

<!-- @neste.04 . li -->
- **Kan en `FLEXIBLE`-avtale bære et tak?** Hvis ja, blir mandatlaget vesentlig enklere og grensen håndheves ett sted. Hvis nei, må taket telles og håndheves hos oss før hvert trekk, og vi vil gjerne vite det før vi bygger det.

<!-- @neste.05 . li -->
- **Finnes det et mandatformat dere planlegger å verifisere mot?** Vi ser for oss et signert, kortlevd mandat som betalingsleddet kan kontrollere selv framfor å stole på en oppføring hos oss. Er dette noe dere allerede arbeider med, eller er formatet åpent?

<!-- @neste.06 . li -->
- **Kommer en stopp-operasjon mot en aktiv avtale?** I dag stopper kunden avtalen i Vipps-appen, og vi får vite det etterpå. For et agentmandat trenger vi at en stopp virker i begge retninger, og raskt.

<!-- @neste.07 . li -->
- **Får vi agentflagget videre?** Europeiske utstedere sender allerede identifikatorer som avslører at en transaksjon er agentisk. Kommer det signalet videre til brukerstedet i webhooks og oppgjørsdata, eller stopper det hos dere?

<!-- @neste.08 . li -->
- **Hvordan tenker dere om prising av agenttransaksjoner?** Ingen av nettverkene har publisert noe. På kollektivbillettens beløpsnivå kan et fast ledd være forskjellen på om agentkjøp gir mening i det hele tatt, og det er verdt å ta tidlig.

<!-- @neste.09 . tag -->
HVA VI ØNSKER OSS FRA MØTET

<!-- @neste.10 . p -->
Om dere er interessert: en forpliktelse til å få dette til, og enighet om neste steg. Vi vil vite hvor grensen mellom betalingsavtalen og et mandatlag bør gå, slik at vi bygger det som faktisk mangler og ikke noe dere allerede har på veikartet. Deretter vil vi prøve det i praksis: ett kjøp, én agent, før jul.

<!-- @neste.11 . p -->
Norge har to ting få markeder har: BankID som et signeringsrail myndighetene allerede stoler på, og en nøytral nasjonal infrastruktur for kollektivtransport. Skal en agent kunne kjøpe en norsk kollektivbillett på en måte som holder juridisk, må begge deler spille sammen med betalingsleddet. **Det får ikke Entur til alene og vi tror det beste første steget er med Vipps.**

<!-- @neste.12 . boks-tittel -->
Mer detaljert gjennomgang

<!-- @neste.13 . boks-undertekst -->
Salgsflyt, grensesnitt mot betalingsleddet og landskapet slik vi ser det.

<!-- @neste.14 . boks-vis -->
Vis underlaget ↓

<!-- @neste.15 . boks-skjul -->
Skjul underlaget ↑


---

<!-- ===== seksjon: <section id="poc"> ===== -->

<!-- @poc.01 . h2 -->
## Hvordan kan dette se ut?

<!-- @poc.02 . p -->
Først det konkrete: hvordan et agentkjøp ville gått gjennom Enturs salgsflyt, og hvordan grensesnittet mot betalingsleddet kan se ut. Deretter landskapet vi har kartlagt, som bakgrunn for vurderingene i første del.

<!-- @poc.03 . div.k -->
01

<!-- @poc.04 . div.v -->
Entur er brukersted for betalingen og formidler av salget. Et agentlag legger seg oppå betalingsinfrastrukturen som allerede finnes, og rører aldri kundens midler.

<!-- @poc.05 . div.k -->
02

<!-- @poc.06 . div.v -->
Betalingsavtalen bærer godkjenningen og revisjonssporet, men ikke taket. Avtaletypen som tillater ad-hoc-trekk har ingen beløpsgrense.

<!-- @poc.07 . div.k -->
03

<!-- @poc.08 . div.v -->
Salgsflyten er en tilstandsmaskin med tre tidsvinduer, og mandatbetalingen kobler seg på i femte steg. Det er der rammen må håndheves.


---

<!-- ===== seksjon: <section id="salgsflyt"> ===== -->

<!-- @salgsflyt.01 . h2 -->
## Salgsflyten i Entur Sales API

<!-- @salgsflyt.02 . p -->
Sales API er åtte tjenester som dekker hele salget. Ryggraden agenten følger, er en kjede med tre faste tidsvinduer. Det uthevede steget er der mandatbetalingen kobler seg på.

<!-- @salgsflyt.03 . div.n -->
01

<!-- @salgsflyt.04 . div.t -->
Reisesøk

<!-- @salgsflyt.05 . div.d -->
Journey Planner gir trip pattern

<!-- @salgsflyt.06 . div.n -->
02

<!-- @salgsflyt.07 . div.t -->
Søk tilbud

<!-- @salgsflyt.08 . div.d -->
offers/v3/search → offerId. Gyldig 30 min

<!-- @salgsflyt.09 . div.n -->
03

<!-- @salgsflyt.10 . div.t -->
Opprett ordre

<!-- @salgsflyt.11 . div.d -->
Nullstilles etter 20 min

<!-- @salgsflyt.12 . div.n -->
04

<!-- @salgsflyt.13 . div.t -->
Reserver tilbud

<!-- @salgsflyt.14 . div.d -->
offerId → ordrelinjer

<!-- @salgsflyt.15 . div.n -->
05

<!-- @salgsflyt.16 . div.t -->
Betal (mandat)

<!-- @salgsflyt.17 . div.d -->
paymentAgreementId → authorize/capture. Lås 3 min

<!-- @salgsflyt.18 . div.n -->
06

<!-- @salgsflyt.19 . div.t -->
Distribuer billett

<!-- @salgsflyt.20 . div.d -->
NOD + Kafka-event, asynkront

<!-- @salgsflyt.21 . p -->
Tre tidsvinduer: tilbud 30 min, ordre-reset 20 min, betalingslås 3 min. Dette er en tilstandsmaskin, ikke en fri agentsekvens.


---

<!-- ===== seksjon: <section id="arkitektur"> ===== -->

<!-- @arkitektur.01 . h2 -->
## Grensesnittet mot betalingsleverandøren

<!-- @arkitektur.02 . p -->
Entur har allerede en MCP-server for søk, men ikke for salg.{{kilde:Entur MCP>https://github.com/entur/opentripplanner-mcp}} Skissen under viser hvordan et agentkjøp ville vært satt opp. Prinsippet er at språkmodellen eier dialog og intensjon, mens en deterministisk tjeneste eier penger og tilstand. Av lagene i en slik løsning er tre avhengige av betalingsleverandøren, og det er de tre vi vil diskutere.

<!-- @arkitektur.22 . p -->
purchase-verktøyet rutes gjennom mandat-tjenesten, ikke direkte til Payment API. Det er den viktigste kontrollen, både teknisk og juridisk.

<!-- @arkitektur.23 . h3 -->
### Tre flater vi deler med dere

<!-- @arkitektur.24 . p -->
Mønsteret er entydig på tvers av referansearkitekturene som er publisert: håndhevingen sitter ikke i agenten og ikke i agentrammeverket, den sitter hos den som utsteder beviset, og ved autorisasjonspunktet nedstrøms. Det meste av et slikt mandatlag er vårt eget ansvar. Tre av flatene er det ikke, fordi de bare fungerer hvis betalingsleddet er med på dem.

<!-- @arkitektur.25 . div.t -->
Mandatet som signert, kortlevd bevis

<!-- @arkitektur.26 . div.d -->
Et signert dokument framfor en rad i en tabell: tak per trekk og per periode, valuta, kort utløp, tillatte formål altså produkttyper og operatører, agentidentitet, kundeidentitet, referanse til autentiseringshendelsen som opprettet mandatet, og hash av forrige versjon. **Hvorfor det angår dere:** et signert mandat kan Vipps verifisere selv. En databaserad kan dere bare stole på. **Hvorfor kortlevd:** en fagfellevurdert analyse av AP2 dokumenterer gjenbruk av tidligere autoriserte betalingsforespørsler og løsrivelse fra opprinnelig kontekst.{{kilde:arXiv>https://arxiv.org/pdf/2602.06345}} **Spørsmålet:** finnes det et format dere allerede planlegger å verifisere mot, eller er dette åpent?

<!-- @arkitektur.27 . div.t -->
Step-up til Vipps ved terskel

<!-- @arkitektur.28 . div.d -->
Når en forespørsel overskrider mandatet, bør svaret ikke være en feilkode, men en godkjenningsforespørsel til kunden. **Hvorfor:** uten det settes taket for høyt av produkthensyn, fordi et lavt tak bare gir sinte kunder. Med det kan taket settes lavt, fordi en overskridelse blir en dialog. MCP-spesifikasjonen gir nå protokollhjemmel for scope-akkumulering ved step-up.{{kilde:MCP>https://blog.modelcontextprotocol.io/posts/2026-07-28-release-candidate/}} **Hvorfor Vipps:** det er allerede flaten for sterk kundeautentisering og der BankID-signaturen skjer. En parallell godkjenningsflate ville splittet samtykkebeviset over to systemer, og det vil vi unngå.

<!-- @arkitektur.29 . div.t -->
Tilbaketrekking med definert spredningstid

<!-- @arkitektur.30 . div.d -->
To operasjoner, skilt fra hverandre. **Pause** stopper nye trekk under et mandat umiddelbart. **Tilbaketrekking** ugyldiggjør agentidentiteten og forplanter seg nedstrøms, med mål under 15 minutter. **Hvorfor det angår dere:** uten en stopp-operasjon mot avtalen er det eneste virkemidlet vi har å blokkere kundens avtale, altså å ramme kunden i stedet for agenten. Kunden bør kunne trekke sitt eget mandat fra begge sider, og begge sider bør vite om det med det samme.

<!-- @arkitektur.31 . tag -->
DET LAGET BEVISST IKKE GJØR

<!-- @arkitektur.32 . h3 -->
### Tre avgrensninger

<!-- @arkitektur.33 . p -->
**Bygger ikke betalingslag.** Entur er ikke betalingsforetak og skal ikke bli det. Mandatlaget rører aldri kundens midler, og trekket går fortsatt gjennom betalingsleverandøren.

<!-- @arkitektur.34 . p -->
**Autentiserer ikke.** Sterk kundeautentisering blir liggende hos Vipps. Bygger vi noe som i praksis autentiserer på deres vegne, havner vi i et utkontrakteringsregime ingen av oss er tjent med.{{kilde:Norton Rose>https://www.nortonrosefulbright.com/en/knowledge/publications/cedd39c6/psd3-and-psr-from-provisional-agreement-to-2026-readiness}}

<!-- @arkitektur.35 . p -->
**Låser ikke mandatformatet.** Flatene over kan uttrykkes i UCP, AP2 eller et format dere allerede jobber mot. Vi har ingen preferanse ut over at det skal være ett format, ikke to.

<!-- @arkitektur.36 . tag -->
TRUSSELBILDET LAGET MÅ TÅLE

<!-- @arkitektur.37 . h3 -->
### Anta at agenten tar feil, ikke at den er hacket

<!-- @arkitektur.38 . p -->
Prompt-injeksjon mot betalende agenter er ute av laboratoriet, med ferdige transaksjonsspesifikasjoner gjemt i nettinnhold.{{kilde:SecurityWeek>https://www.securityweek.com/prompt-injection-attacks-trick-ai-agents-into-making-crypto-payments/}} OWASPs 2026-liste bruker minneforgiftning i en reiseagent som eksempel: angriper planter falske priser i agentens minne, agenten lagrer det som sannhet og godkjenner bestillinger forbi betalingskontrollene.{{kilde:OWASP 2026>https://www.giskard.ai/knowledge/owasp-top-10-for-agentic-application-2026}}

<!-- @arkitektur.39 . p -->
Men de fleste tapene kommer fra feil, ikke angrep. Agenter som lykkes rundt 60 prosent av tiden på ett forsøk faller til rundt 25 prosent over åtte påfølgende kjøringer. Og antimønsteret er dokumentert i begge de kjente overforbrukstilfellene: **taket eksisterte, men ble håndhevet av samme system som brukte pengene.**{{kilde:Cloudflare>https://blog.cloudflare.com/wallets/}}


---

<!-- ===== seksjon: <section id="felt"> ===== -->

<!-- @felt.01 . h2 -->
## Hva skjer nå

<!-- @felt.02 . p -->
Fem ting vi har merket oss fra det siste halvåret. Den første er utgangspunktet for dette initiativet til kontakt med Vipps.

<!-- @felt.03 . tag -->
UTGANGSPUNKTET

<!-- @felt.04 . h3 -->
### Vipps har pekt ut UCP

<!-- @felt.05 . p -->
Vipps har publisert utviklerdokumentasjon for agentisk handel med en egen betalingshandler for lommebok og kort, bygget på Universal Commerce Protocol. Sist oppdatert 25. august, merket «under development».{{kilde:Vipps>https://developer.vippsmobilepay.com/docs/APIs/agentic-commerce/}} Skjemaene ligger på `ucp.vipps.no`.

<!-- @felt.06 . p -->
Dokumentasjonen omtaler ikke mandater, samtykkemodell, gjentakende trekk eller beløpstak. Det kan bety at det kommer senere, eller at rammen er ment å ligge hos brukerstedet. Hvilken av delene det er, er det vi gjerne vil vite.

<!-- @felt.07 . tag -->
PROTOKOLLER

<!-- @felt.08 . h3 -->
### Fem protokoller i tre lag, med voksne eiere

<!-- @felt.09 . p -->
AP2 er donert til FIDO Alliance, som samtidig opprettet to arbeidsgrupper der Mastercard og Visa leder betalingssiden.{{kilde:FIDO>https://fidoalliance.org/fido-alliance-to-develop-standards-for-trusted-ai-agent-interactions/}} x402 gikk operativt under Linux Foundation 14. juli med 40 medlemmer.{{kilde:Linux F.>https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications}} MCP og A2A ligger i Agentic AI Foundation. UCP kom til som femte protokoll og dekker oppdagelse og checkout.

<!-- @felt.10 . p -->
Ingen av de store satser på én protokoll. Stripe og Visa sitter på øverste medlemsnivå i x402 samtidig som de driver hvert sitt konkurrerende spor.

<!-- @felt.11 . tag -->
KORTNETTVERK

<!-- @felt.12 . h3 -->
### Europa har produksjonssatte agentbetalinger

<!-- @felt.13 . p -->
Visa gjorde opp de første brukerstedsbetalingene i Europa 2. juli, med Payment Passkeys som SKA-mekanisme og Nordea, OP og S-Payment blant de nordiske bankene i programmet.{{kilde:Visa UK>https://www.visa.co.uk/about-visa/newsroom/press-releases.3457328.html}} Nordea kjørte Finlands første live agenttransaksjon 5. juni med Mastercard Agent Pay.{{kilde:Nordea>https://www.nordea.com/en/news/first-ever-finnish-ai-agent-payment-mastercard-and-nordea-completes-live-agentic-transaction}}

<!-- @felt.14 . p -->
Visa oppgir at alle transaksjonene ble sikret med Payment Passkeys, og knytter det eksplisitt til kravene om sterk kundeautentisering i Europa. Nordea-meldingen nevner derimot verken PSD2, sterk kundeautentisering eller mandatramme. Felles for begge er at mennesket bekrefter til slutt. **Mandatbasert autentisering én gang, med etterfølgende autonome trekk, har ingen vist fram i EØS.**

<!-- @felt.15 . tag -->
SIKKERHET

<!-- @felt.16 . h3 -->
### Fra hypotese til observerte angrep

<!-- @felt.17 . p -->
Zscaler har identifisert kampanjer med indirekte prompt-injeksjon rettet mot agenter med betalingsevne, med ferdige transaksjonsspesifikasjoner gjemt i nettinnhold.{{kilde:SecurityWeek>https://www.securityweek.com/prompt-injection-attacks-trick-ai-agents-into-making-crypto-payments/}} Akamai melder at handel nå er den mest angrepne bransjen, drevet av overgangen til agentisk handel.{{kilde:Akamai>https://www.akamai.com/newsroom/press-release/akamai-research-commerce-becomes-the-epicenter-for-ai-bot-attacks-and-agentic-fraud-in-2026}}

<!-- @felt.18 . p -->
Escrow som eget mellomledd har derimot ikke modnet. Det som har modnet er verifisering, agentforsikring med revisjonskoblet premie, og forbrukstak i lommeboken.

<!-- @felt.19 . tag -->
DISTRIBUSJON

<!-- @felt.20 . h3 -->
### MCP oppå salgslaget er i drift

<!-- @felt.21 . p -->
Travelport la MCP direkte oppå Trip Services, plattformen som håndterer bestillinger, ombookinger og refusjoner, og koblet det 1. juli til over 400 europeiske reisebyråer gjennom Travelsoft.{{kilde:TDN>https://traveldistributionnews.com/travelport-and-travelsoft-bet-on-mcp-now-comes-the-real-test-across-400-agencies/}}

<!-- @felt.22 . p -->
Det er ikke en assistentflate mot forbruker. Det er agentinfrastruktur i distribusjonsleddet, og det er samme grep Entur ser for seg med sitt eget salgs-API. Kilden er bransjemedier, ikke primærkilde.


---

<!-- ===== seksjon: <section id="protokoller"> ===== -->

<!-- @protokoller.01 . h2 -->
## De fem protokollene, på tre lag

<!-- @protokoller.02 . p -->
De fem er ikke konkurrenter på samme lag. Ett lag handler om **oppdagelse og checkout** (hvordan agenten finner og bestiller), ett om **autorisasjon** (hvem som får betale, og hvordan samtykke bevises), ett er **oppgjørsrails** (hvordan pengene flyttes). En selger forholder seg til ett fra hvert lag, ikke ett av fem.

<!-- @protokoller.03 . tab -->
UCP

<!-- @protokoller.04 . tab -->
ACP

<!-- @protokoller.05 . tab -->
AP2

<!-- @protokoller.06 . tab -->
x402

<!-- @protokoller.07 . tab -->
MPP

<!-- @protokoller.08 . lagmerke -->
Oppdagelse + checkout

<!-- @protokoller.09 . h3 -->
### UCP, Universal Commerce Protocol

<!-- @protokoller.10 . dt -->
HVEM

<!-- @protokoller.11 . dd -->
Google og Shopify, med Etsy, Wayfair, Target og Walmart tidlig ute, og over 20 støttespillere blant dem Adyen, American Express, Mastercard, Stripe, Visa og Zalando.{{kilde:Google>https://developers.googleblog.com/under-the-hood-universal-commerce-protocol-ucp/}} Siste versjon er fra 8. april 2026. Den er merket som utkast, med Apache 2.0-lisens, og det kom ingen ny versjon i juni, juli eller august.

<!-- @protokoller.12 . dt -->
PRIMITIV

<!-- @protokoller.13 . dd -->
Fire stadier: produktoppdagelse, kapabilitetsforhandling, checkout og etterkjøpsoverlevering. Betalingsmetoder hentes gjennom et **payment handler**-konsept som oppdages fra selgerens `/.well-known/ucp`-profil. AP2, A2A og MCP er innebygd som støttede standarder.

<!-- @protokoller.14 . dt -->
RAIL

<!-- @protokoller.15 . dd -->
Rail-agnostisk gjennom handleren. Koblet inn i Google Search AI Mode og Gemini, og det er UCP som bærer Googles agentiske hotellbooking i test.

<!-- @protokoller.16 . dt -->
FOR ENTUR

<!-- @protokoller.17 . dd -->
**Dette er sporet Vipps har valgt.**{{kilde:Vipps>https://developer.vippsmobilepay.com/docs/APIs/agentic-commerce/}} Det åpne spørsmålet er hvordan et UCP-mandat oversettes til våre avtaletyper `FIXED`, `VARIABLE` og `FLEXIBLE`. Ingen offentlig kilde svarer på det, og det er derfor det står øverst på spørsmålslisten vår.

<!-- @protokoller.18 . lagmerke -->
Autorisasjon + checkout

<!-- @protokoller.19 . h3 -->
### ACP, Agentic Commerce Protocol

<!-- @protokoller.20 . dt -->
HVEM

<!-- @protokoller.21 . dd -->
OpenAI og Stripe. **Ikke lenger live som kjøpsflate:** Instant Checkout, flyten ACP ble bygget for, ble lagt ned i mars 2026.{{kilde:CNBC>https://www.cnbc.com/2026/03/24/openai-revamps-shopping-experience-in-chatgpt-after-instant-checkout.html}} Protokollen lever videre som oppdagelse, med kjøpet tilbake hos selgeren.

<!-- @protokoller.22 . dt -->
STATUS

<!-- @protokoller.23 . dd -->
Siste spesifikasjon 17. april 2026, fortsatt beta, fortsatt forvaltet av OpenAI og Stripe som «founding maintainers». Nøytral stiftelse er omtalt som et mål, ikke som en beslutning.

<!-- @protokoller.24 . dt -->
PRIMITIV

<!-- @protokoller.25 . dd -->
Shared Payment Token (SPT). Agenten setter sammen handlekurv fra en vare-feed, brukeren velger betaling inne i agentflaten, og en scoped token postes til selgerens checkout. Agenten ser aldri rå kortdata.

<!-- @protokoller.26 . dt -->
HVORFOR DEN DØDE

<!-- @protokoller.27 . dd -->
Sekundærkilder oppgir at bare rundt 30 Shopify-forhandlere hadde kommet gjennom påkoblingen, og at Walmart målte konvertering inne i ChatGPT rundt tre ganger dårligere enn klikk ut til eget nettsted.{{kilde:S: EnterpriseDNA>https://enterprisedna.co/resources/news/openai-agentic-commerce-protocol-walmart-sparky/}} Ingen av tallene er bekreftet av Walmart eller OpenAI direkte, og de bør behandles deretter.

<!-- @protokoller.28 . dt -->
FOR ENTUR

<!-- @protokoller.29 . dd -->
At kjøpet flyttet tilbake til selgerens flate er gunstig for oss. Det er den modellen som passer et nasjonalt billettsystem med egne kjøpsvilkår og eget mandatlag.

<!-- @protokoller.30 . lagmerke -->
Autorisasjon / tillitsrammeverk

<!-- @protokoller.31 . h3 -->
### AP2, Agent Payments Protocol

<!-- @protokoller.32 . dt -->
HVEM

<!-- @protokoller.33 . dd -->
Startet hos Google med Coinbase og 60+ organisasjoner. **Donert til FIDO Alliance 28. april 2026**, samme organ som eier passkeys.{{kilde:Google>https://blog.google/products-and-platforms/platforms/google-pay/agent-payments-protocol-fido-alliance/}} Videre standardisering skjer i FIDOs arbeidsgrupper, ikke i Googles repo.

<!-- @protokoller.34 . dt -->
STATUS

<!-- @protokoller.35 . dd -->
Siste versjon v0.2.0, 28. april 2026. Nyheten der er **Human Not Present**: agenten kan gjennomføre kjøp autonomt på et forhåndsautorisert mandat. Det er formaliseringen av «gi agenten kortet innenfor rammer».

<!-- @protokoller.36 . dt -->
PRIMITIV

<!-- @protokoller.37 . dd -->
To signerte mandater: **Intent Mandate** (hva agenten kan kjøpe når ingen godkjenner hvert kjøp) og **Cart Mandate** (endelig kurv med brukerens signatur, menneske til stede). Selve betalingen er utfallet, ikke et tredje mandat.

<!-- @protokoller.38 . dt -->
RAIL

<!-- @protokoller.39 . dd -->
Rail-agnostisk. Pares med x402 for stablecoin-oppgjør; Google leverer identitet, policy og etterlevelse.

<!-- @protokoller.40 . dt -->
FOR ENTUR

<!-- @protokoller.41 . dd -->
Portabel, signert autorisasjon med revisjonsspor. Mandatmodellen kartlegger renest mot EØS-kravet om bevisbart samtykke, og at FIDO nå eier både passkeys og mandatformatet gjør «SKA én gang ved oppsett, deretter mandatbaserte trekk» til en linje som kan bli standardisert i stedet for hjemmesnekret.

<!-- @protokoller.42 . lagmerke -->
Oppgjørsrail

<!-- @protokoller.43 . h3 -->
### x402

<!-- @protokoller.44 . dt -->
HVEM

<!-- @protokoller.45 . dd -->
Startet hos Coinbase.{{kilde:Coinbase>https://www.coinbase.com/developer-platform/discover/launches/x402}} **x402 Foundation gikk operativt under Linux Foundation 14. juli 2026** med 40 medlemmer, og overføringen fra Coinbase er fullført.{{kilde:Linux F.>https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications}} På øverste medlemsnivå ligger blant andre Adyen, AWS, American Express, Cloudflare, Mastercard, Stripe og Visa.

<!-- @protokoller.46 . dt -->
PRIMITIV

<!-- @protokoller.47 . dd -->
Gjenoppliver HTTP-statuskode {{mono:402 Payment Required}} til en maskinlesbar utfordring-respons for umiddelbart stablecoin-oppgjør over HTTP.

<!-- @protokoller.48 . dt -->
RAIL

<!-- @protokoller.49 . dd -->
Stablecoins over HTTP. Håndterer pengeflytting, ikke autorisasjon.

<!-- @protokoller.50 . dt -->
BEST FOR

<!-- @protokoller.51 . dd -->
Betal-per-kall til API-er og data, og agent-til-agent. I EØS trekker dette inn MiCA/e-penge-spørsmål på toppen av PSD2.

<!-- @protokoller.52 . dt -->
VOLUM · MED FORBEHOLD

<!-- @protokoller.53 . dd -->
Over 100 millioner kumulative transaksjoner på Base gjennom første kvartal 2026.{{kilde:Chainalysis>https://www.chainalysis.com/blog/x402-agentic-payments-adoption/}} Men **daglig transaksjonsvolum falt over 92 prosent** fra toppen i desember 2025 til februar 2026, og faktisk handelsvolum anslås til rundt 28 000 dollar per dag, og omtrent halvparten av aktiviteten er klassifisert som spillpreget.{{kilde:S: Presenc>https://presenc.ai/research/x402-protocol-adoption-tracker-2026}} Tallene er sekundærkilder, ikke reviderte, og bør ikke brukes som beslutningsgrunnlag uten ny verifisering.

<!-- @protokoller.54 . lagmerke -->
Oppgjør + metering

<!-- @protokoller.55 . h3 -->
### MPP, Machine Payments Protocol

<!-- @protokoller.56 . dt -->
HVEM

<!-- @protokoller.57 . dd -->
Stripe og Tempo. Lansert 18. mars 2026, 50+ tjenester i første uke.{{kilde:Stripe>https://stripe.com/blog/machine-payments-protocol}}

<!-- @protokoller.58 . dt -->
PRIMITIV

<!-- @protokoller.59 . dd -->
{{mono:402}} pluss en **sessions**-primitiv: autoriser et tak på forhånd, og strøm deretter mikrobetalinger per token / per sekund / per kall uten en kjede-transaksjon for hver interaksjon.

<!-- @protokoller.60 . dt -->
RAIL

<!-- @protokoller.61 . dd -->
Stablecoins på Tempo L1 (sub-millidollar avgifter), utvidet til kort/wallets/Lightning.

<!-- @protokoller.62 . dt -->
BEST FOR

<!-- @protokoller.63 . dd -->
Strømmende, målt forbruk. Løser 30-årsproblemet med mikrobetalinger ved å fjerne det menneskelige beslutningspunktet.

<!-- @protokoller.64 . p -->
Kilde per fane lenket inline. Sammenlikning på tvers: <a class="src" href="https://www.crossmint.com/learn/agentic-payments-protocols-compared" target="_blank" rel="noopener">Crossmint, protocols compared</a>.

<!-- @protokoller.65 . tag -->
SJETTE BRIKKE · IKKE EN BETALINGSPROTOKOLL

<!-- @protokoller.66 . h3 -->
### MCP fikk godkjenningsprimitiver, ikke betaling

<!-- @protokoller.67 . p -->
Spesifikasjonen fra 28. juli 2026 er den viktigste oppdateringen siden fjern-MCP kom.{{kilde:MCP>https://blog.modelcontextprotocol.io/posts/2026-07-28-release-candidate/}} Den inneholder fortsatt ingen betalingsprimitiv. Betaling ligger utenpå, som en sperre foran verktøykallet.

<!-- @protokoller.68 . p -->
To ting derfra treffer et mandatlag direkte. **Step-up-scope er nå eksplisitt i spesifikasjonen**, altså hjemmel for mønsteret «agenten har lavt scope og må eskalere for å betale». Og et verktøy kan be om en bekreftelse midt i et kall, som er den tekniske kroken for et «godkjenn dette kjøpet»-steg. **Sampling er deprekert**, så enhver skisse som antok modellkall tilbake til verten må endres.

<!-- @protokoller.69 . tag -->
TILLITSLAGET

<!-- @protokoller.70 . h3 -->
### To rammeverk, nå i samme rom

<!-- @protokoller.71 . p -->
Mastercards Verifiable Intent og Visas Trusted Agent Protocol svarer på hvert sitt spørsmål. Visa spør hvor agenten kommer fra og om den er ekte. Mastercard spør hva agenten prøver å gjøre og om brukeren faktisk sa det.

<!-- @protokoller.72 . p -->
Begge er nå grunnlagsbidrag inn i FIDOs betalingsgruppe, som Mastercard og Visa leder sammen. At de smelter sammen der er sannsynlig, men ikke annonsert. Konsekvensen for oss er uansett at **verifisering av agentidentitet ikke lenger er et ledig rom**.


---

<!-- ===== seksjon: <section id="aktorer"> ===== -->

<!-- @aktorer.01 . h2 -->
## Aktørene

<!-- @aktorer.02 . p -->
Verdikjeden består av kjente og nye aktører. Forskjellen ligger i hva hver av dem prøver å eie når kjeden settes opp på nytt.

<!-- @aktorer.03 . tag -->
INFRASTRUKTUR → TILLIT

<!-- @aktorer.04 . h3 -->
### Kortnettverk

<!-- @aktorer.05 . p -->
Visa og Mastercard går fra å flytte penger til å verifisere agenter og selgere. Konkurranseflaten blir agentregisteret og spørsmålet om en gitt agent faktisk får handle et sted.

<!-- @aktorer.06 . tag -->
NY DISTRIBUSJON

<!-- @aktorer.07 . h3 -->
### Modell-labbene

<!-- @aktorer.08 . p -->
OpenAI, Google og Anthropic eier agentflaten der kjøpet skjer. Det er det nye butikkvinduet, og den som eier flaten, eier kunderelasjonen.

<!-- @aktorer.09 . tag -->
RAILS + TOKEN

<!-- @aktorer.10 . h3 -->
### Betalingsleverandører

<!-- @aktorer.11 . p -->
Stripe, Adyen og Vipps leverer scoped tokens og mandat-primitiver. Stripes Shared Payment Token og Vipps recurring er allerede byggeklosser for agentkjøp.

<!-- @aktorer.12 . tag -->
NYTT MELLOMLAG

<!-- @aktorer.13 . h3 -->
### Verifisering tatt, escrow ikke

<!-- @aktorer.14 . p -->
Kategorien har delt seg i tre. **Verifisering** er tatt av Visa, Mastercard, Prove og Cloudflare. **Agentforsikring** har modnet, med Armilla som Lloyd's coverholder og AIUC som kobler revisjonsscore til premie.{{kilde:FinTech Global>https://fintech.global/2026/01/23/armilla-ai-raises-25m-to-expand-ai-liability-coverage/}} **Escrow**, altså å holde penger til leveranse er bekreftet, er derimot fortsatt akademisk.

<!-- @aktorer.15 . p -->
Det som fortsatt er hjemløst er mandatforvaltning med beløpstak og formålsbinding. Der har ingen leverandør tatt kategorinavnet.

<!-- @aktorer.16 . tag -->
STANDARDORGANER

<!-- @aktorer.17 . h3 -->
### Stiftelsene tok over

<!-- @aktorer.18 . p -->
FIDO Alliance eier autorisasjonslaget etter donasjonene av AP2 og Verifiable Intent, med to arbeidsgrupper der Mastercard og Visa leder betalingssiden.{{kilde:FIDO>https://fidoalliance.org/fido-alliance-to-develop-standards-for-trusted-ai-agent-interactions/}} Linux Foundation eier x402 og, gjennom Agentic AI Foundation, MCP og A2A. EMVCo har en arbeidsgruppe, men ingen publisert spesifikasjon.

<!-- @aktorer.19 . p -->
Et negativt funn: **ISO 20022, Berlin Group og European Payments Council er tause**. Det europeiske kontobetalingssporet, der Entur og Vipps faktisk lever, har ingen agentstandard i arbeid.

<!-- @aktorer.20 . tag -->
KANTLAGET

<!-- @aktorer.21 . h3 -->
### Infrastrukturen blir identitetsutsteder

<!-- @aktorer.22 . p -->
Cloudflare gikk fra betalingsport 1. juli til lommebøker med tak, tillatelseslister og overstyringsforespørsel 4. august.{{kilde:Cloudflare>https://blog.cloudflare.com/wallets/}} Samtidig flytter agentverifisering inn i kantlaget gjennom signerte forespørsler.

<!-- @aktorer.23 . p -->
For en selger står valget for hver enkelt bot ikke lenger mellom å slippe gjennom eller blokkere. Det tredje alternativet er å ta betalt. Det forutsetter at agenten lar seg identifisere, og den identifiseringen finnes ikke i dag for kollektivtransport.

<!-- @aktorer.24 . tag -->
RAMMEVERK

<!-- @aktorer.25 . h3 -->
### Regulatorer

<!-- @aktorer.26 . p -->
Finanstilsynet, EBA og EU rammer inn feltet. PSD2 og SCA binder fortsatt, og ingen europeisk tilsynsmyndighet har gitt bindende veiledning om AI-agenter som betaler.{{kilde:EBA>https://www.eba.europa.eu/single-rule-book-qa/qna/view/publicId/2019_4792}}

<!-- @aktorer.27 . p -->
PSD3 og PSR er ferdigforhandlet. Publisering i EU-tidende var ventet mot slutten av andre kvartal 2026, og reglene gjelder 18 måneder etter ikrafttredelse, altså tidligst rundt årsskiftet 2027/2028.{{kilde:Norton Rose>https://www.nortonrosefulbright.com/en/knowledge/publications/cedd39c6/psd3-and-psr-from-provisional-agreement-to-2026-readiness}} Man trenger ikke vente på dem for å bygge, men to ting derfra bør arkitekturen ta høyde for nå: **delegert SKA er utkontraktering** med DORA-krav, og **kommisjonærunntaket strammes**. I Norge har ingen myndighet uttalt seg. Det rommet er tomt, ikke lukket.

<!-- @aktorer.28 . tag -->
MANDAT-ANKER

<!-- @aktorer.29 . h3 -->
### Nasjonal eID

<!-- @aktorer.30 . p -->
BankID signerer mandatet og leverer SCA ved oppsett. Det er Norges naturlige fortrinn: et regulator-betrodd signeringsrail som markeder uten nasjonal eID mangler.


---

<!-- ===== seksjon: <section id="roller-ledig"> ===== -->

<!-- @roller-ledig.01 . h2 -->
## Hvilke roller er mulige og ledige i Norge

<!-- @roller-ledig.02 . p -->
Midtlaget er ikke ett rom, det er ni roller med ulik eier. Tabellen viser hva som må fylles for at en agent skal kunne kjøpe en kollektivbillett, hvem som fyller det internasjonalt, og hva som står åpent i Norge.

<!-- @roller-ledig.03 . table -->
| Rolle | Hva den gjør | Hvem fyller den i dag | Ledig i Norge |
|---|---|---|---|
| **Agentregister** | Registrerer agenter, utsteder og roterer nøkler, publiserer oppslag | Visa Agentic Registry, Mastercard Agent Pay, ERC-8004 | Ja, for kollektivtransport |
| **Agentverifisering** | Binder agenten til en ansvarlig juridisk person, verifiserer ved transaksjon | Prove, Skyfire, Visa Trusted Agent Protocol | Nei internasjonalt, ja i Norge. Ingen norsk aktør, og koblingen til BankID er ikke tatt |
| **Tillitsanker** | Utsteder rotidentiteten andre stoler på | Cloudflare, kortnettverkene, i EU potensielt EUDI-lommeboken | Ja, og gapet er formelt beskrevet{{kilde:CSA>https://labs.cloudsecurityalliance.org/research/csa-research-note-enisa-eu-digital-wallet-ai-agent-identity/}} |
| **Mandatmyndighet** | Registrerer, håndhever og trekker tilbake fullmakter med tak og formålsbinding | Ingen entydig. Mandatformater finnes, tjenesten finnes ikke | Ja, klart ledig. Ingen leverandør har tatt kategorinavnet |
| **Agent-egnethet** | Måler om et salgspunkt er navigerbart og trygt for agenter | Visa Agent Score | Ja, for norske kollektivselskaper |
| **Escrow** | Holder penger til leveranse er bekreftet | Ingen moden aktør | Ja, men lav modenhet. Ikke et sted å bygge nå |
| **Agentforsikring** | Tegner ansvar for agentfeil, kobler revisjonsscore til premie | Armilla, AIUC | Ja, men naturlig at internasjonale forsikringsaktører tar den |
| **Kill switch** | Stopper en aktiv fullmakt umiddelbart, uavhengig av agenten | Nettverkslaget dekket internasjonalt, kortnettverk og utstederbanker | Ja. For en aktiv billettfullmakt dekkes den av ingen |
| **Agent-of-record** | Den som juridisk står ansvarlig for agentens handlinger overfor kunden | Ikke etablert som rolle noe sted | Ja, og det er det viktigste uavklarte punktet i hele bildet |

<!-- @roller-ledig.04 . p -->
«Know Your Agent» og «agent registry» har festet seg som bransjebegreper. «Tillitsanker», «mandatmyndighet» og «agent-of-record» har ikke. Vi bruker dem her som analytiske kategorier for å få oversikt, ikke som etablert terminologi.


---

<!-- ===== seksjon: <section id="roller"> ===== -->

<!-- @roller.01 . h2 -->
## Hvordan rollene endrer seg

<!-- @roller.02 . p -->
Den viktigste endringen er hvor beslutningen tas. Beslutningen og kassen flytter ut av selgerens nettside og inn i agentflaten, grensesnittet der agenten handler. Det deler den klassiske «kunden» i to og skyver hver aktør én plass.

<!-- @roller.30 . p -->
Kunden deles i et menneske som setter rammer og en agent som handler. Beslutningen flytter til agentflaten. Et nytt mandat- og tillitslag åpner seg i midten.

<!-- @roller.31 . div.h-now -->
I dag

<!-- @roller.32 . div.h -->
Med agenter

<!-- @roller.33 . div.role -->
KUNDEN

<!-- @roller.34 . div.c-then -->
Ett menneske som både velger, autentiserer og betaler, klikk for klikk.

<!-- @roller.35 . div.c -->
Deles i to. **Mennesket** setter intensjon og et mandat med tak. **Agenten** utfører kjøpene. Autentisering flytter fra hver transaksjon til oppsettet.

<!-- @roller.36 . div.role -->
SELGEREN

<!-- @roller.37 . div.c-then -->
Eier butikkvinduet, kassen og kunderelasjonen. Nettsiden er der beslutningen tas.

<!-- @roller.38 . div.c -->
Blir en **feed pluss leveranse**. Mister kassen som beslutningspunkt. Risikerer å bli en utbyttbar leverandør bak en agent noen andre eier.

<!-- @roller.39 . div.role -->
DISTRIBUSJONEN

<!-- @roller.40 . div.c-then -->
Søkemotorer og apper sender trafikk til selgerens nettside.

<!-- @roller.41 . div.c -->
Agentflaten (modell-laben) blir det **nye butikkvinduet**. Den som eier flaten, eier etterspørselen og kunderelasjonen.

<!-- @roller.42 . div.role -->
NETTVERK OG BANK

<!-- @roller.43 . div.c-then -->
Flytter penger og utfører sterk kundeautentisering per kjøp.

<!-- @roller.44 . div.c -->
Reposisjonerer mot **tillitsregister**: hvem er agenten, er den verifisert. SCA flytter til mandat-oppsett og delegert autentisering.

<!-- @roller.45 . div.role -->
MELLOMLAGET

<!-- @roller.46 . div.c-then -->
Finnes knapt. PSP-en dekker det meste.

<!-- @roller.47 . div.c -->
Et **nytt, ueid lag** åpner seg: mandatforvaltning, agent-verifisering, escrow, og EØS-korrekt autorisasjon. Her klynger uavhengige aktører seg nå.


---

<!-- ===== seksjon: <section id="reise"> ===== -->

<!-- @reise.01 . h2 -->
## Reise og mobilitet

<!-- @reise.02 . p -->
Mønsteret i resten av reisebransjen gir noen indikasjoner: søket har flyttet seg inn i assistenten, kjøpet er stort sett hjemme hos selgeren, og det som skjer på salgssiden skjer i distribusjonsleddet.

<!-- @reise.03 . tag -->
DET NÆRMESTE VÅRT EGET GREP

<!-- @reise.04 . h3 -->
### Travelport la MCP oppå salgslaget

<!-- @reise.05 . p -->
Travelport har lagt et MCP-lag direkte oppå Trip Services, plattformen som håndterer bestillinger, ombookinger og refusjoner, slik at samtalebaserte forespørsler kan oversettes til bekreftede bestillinger med levende tilgjengelighet. 1. juli ble det koblet til over 400 europeiske reisebyråer.{{kilde:TDN>https://traveldistributionnews.com/travelport-and-travelsoft-bet-on-mcp-now-comes-the-real-test-across-400-agencies/}}

<!-- @reise.06 . p -->
Dette er ikke en assistentflate mot forbruker. Det er agentinfrastruktur i B2B-distribusjonen, uten forbruker i den andre enden, og det er den første målbare testen på om slikt betaler seg.

<!-- @reise.07 . tag -->
FØRSTE ENDE-TIL-ENDE-KJØP

<!-- @reise.08 . h3 -->
### Fly, i produksjon, betalt med lommebok

<!-- @reise.09 . p -->
Sabre, PayPal og Mindtrip lanserte 6. mai flybooking der søk, valg og betaling skjer inne i samtalen.{{kilde:Skift>https://skift.com/2026/05/06/sabre-mindtrip-paypal-launch-agentic-ai-travel-booking/}}

<!-- @reise.10 . p -->
Merk betalingsleddet: PayPal, ikke kort med scoped mandat og ikke stablecoin. Det er en tredje vei ved siden av tokenisert kort og stablecoin, **eksisterende lommebok med eksisterende brukerrelasjon**. Den krever ingen ny mandatinfrastruktur, og den er derfor den enkleste konkurrenten til et Entur-mandatlag.

<!-- @reise.11 . tag -->
UCP I REISE

<!-- @reise.12 . h3 -->
### Google tester agentisk hotellbooking

<!-- @reise.13 . p -->
7. august bekreftet Google en begrenset test i USA, inne i AI Mode, der reisende kan beskrive hva de vil ha og fullføre bookingen hos partneren de velger.{{kilde:Skift>https://skift.com/2026/08/07/google-confirms-hotel-agentic-booking-is-now-in-testing/}} Booking Holdings, Expedia, Marriott, Wyndham og IHG er blant partnerne.

<!-- @reise.14 . p -->
Det som gjør det mulig oppgis å være UCP. UCP fungerer altså som transaksjonslag for reise, ikke bare for varehandel.

<!-- @reise.15 . tag -->
I NORGE, ALLEREDE

<!-- @reise.16 . h3 -->
### Bolt og Flix selger norske reiser i ChatGPT

<!-- @reise.17 . p -->
Bolt lanserte ride-hailing i ChatGPT 29. juli.{{kilde:Bolt>https://bolt.eu/en/blog/chat-gpt-integration/}} Norge er blant markedene. Betalingen skjer fortsatt i Bolt-appen, med direktebetaling gjennom assistenten planlagt senere i år, opplyst i pressedekningen.{{kilde:TechCabal>https://techcabal.com/2026/07/30/bolt-integrates-with-chatgpt/}} Flix la søk og sammenlikning av forbindelser inn i ChatGPT i juni, med kjøpet på egne sider.{{kilde:busplaner>https://www.busplaner.de/de/news/flix-setzt-bei-reiseplanung-auf-kuenstliche-intelligenz-268074.html}} Omio selger norske togreiser gjennom sine partnere.

<!-- @reise.18 . p -->
Ingen nordisk kollektivaktør har annonsert noe tilsvarende. Verken Vy, Ruter, SJ, DSB, AtB, Skyss eller Kolumbus har noe ute. Rommet er tomt.

<!-- @reise.19 . tag -->
MØNSTERET I EUROPEISK JERNBANE

<!-- @reise.20 . h3 -->
### Assistenter innover, ikke API-er utover

<!-- @reise.21 . p -->
DB, SBB og SNCF bygger assistenter for egne kunder, og åpne data-API-er uten salg. Trainline har ChatGPT-app for rutesøk, med bookingen hjemme.

<!-- @reise.22 . p -->
Enturs særtrekk er at begge halvdelene ligger i samme hus: Journey Planner, salgsinfrastrukturen og betalingsavtalene. Søkelaget ligger allerede ute som eget repo.{{kilde:Entur MCP>https://github.com/entur/opentripplanner-mcp}} Det er nettopp den kombinasjonen bransjen etterlyser, et nøytralt lag som kan gjennomføre selve kjøpet, og vi har den for norsk kollektivtransport uten å måtte bygge den.

<!-- @reise.23 . tag -->
NYTT PROBLEM · KAPASITET

<!-- @reise.24 . h3 -->
### Volum og latens er et salgsspørsmål

<!-- @reise.25 . p -->
Amadeus og Sabre peker på opptil 200 000 søk per solgt billett i et agentisk regime, og svarer med forhåndsberegning i stedet for live prising.{{kilde:OAG>https://www.oag.com/blog/airline-ai-interface}} I hotellbransjens definisjon av agentklar inngår p95-latens under 800 ms.{{kilde:Gimmonix>https://gimmonix.com/news/only-11-percent-agent-ready-2026}}

<!-- @reise.26 . p -->
Det er lett å se agenter som et autorisasjons- og oppgjørsproblem. Det er like mye et kapasitets- og kostnadsproblem, og det gjelder både søkeleddet og betalingsleddet.


---

## Vedlegg A. Navigasjonslenkene øverst på siden

<!-- Korte knappetekster i toppmenyen. Må være korte. -->

<!-- @head.04 . nav -->
Hensikt

<!-- @head.05 . nav -->
Sammendrag

<!-- @head.06 . nav -->
Samarbeidet

<!-- @head.07 . nav -->
Mandat og tak

<!-- @head.08 . nav -->
Spørsmål til Vipps

<!-- @head.10 . nav -->
Salgsflyt

<!-- @head.11 . nav -->
Grensesnittet

<!-- @head.12 . nav -->
Hva skjer

<!-- @head.13 . nav -->
Protokoller

<!-- @head.14 . nav -->
Aktørene

<!-- @head.15 . nav -->
Ledige roller

<!-- @head.16 . nav -->
Rolleendringen

<!-- @head.17 . nav -->
Reise


---

## Vedlegg B. Tekst inne i figurene

<!-- Hver linje er en tekstlinje i en tegning, plassert manuelt.
     Nye formuleringer bør være omtrent like lange. -->


**Figur i seksjon mandat**

<!-- @mandat.10 . figurtekst -->
MENNESKE · ÉN GANG

<!-- @mandat.11 . figurtekst -->
Oppsett av mandat

<!-- @mandat.12 . figurtekst -->
Godkjenn Vipps-avtale med

<!-- @mandat.13 . figurtekst -->
BankID. Tak settes i mandatet.

<!-- @mandat.14 . figurtekst -->
SCA oppfylt her

<!-- @mandat.15 . figurtekst -->
AGENT · MANGE GANGER

<!-- @mandat.16 . figurtekst -->
Kjøp innenfor tak

<!-- @mandat.17 . figurtekst -->
Reserver tilbud, belast på

<!-- @mandat.18 . figurtekst -->
paymentAgreementId.

<!-- @mandat.19 . figurtekst -->
MIT, ingen ny SCA

<!-- @mandat.20 . figurtekst -->
UNNTAK · STEP-UP

<!-- @mandat.21 . figurtekst -->
Frisk autentisering

<!-- @mandat.22 . figurtekst -->
SOFT_DECLINE eller over tak:

<!-- @mandat.23 . figurtekst -->
bruker sendes til terminal.

<!-- @mandat.24 . figurtekst -->
SCA på nytt


**Figur i seksjon arkitektur**

<!-- @arkitektur.03 . figurtekst -->
Bruker (chat)

<!-- @arkitektur.04 . figurtekst -->
LLM-agent

<!-- @arkitektur.05 . figurtekst -->
intensjon, dialog · guardrails: MAX_LOOPS, budsjett

<!-- @arkitektur.06 . figurtekst -->
DISCOVERY MCP · finnes hos Entur

<!-- @arkitektur.07 . figurtekst -->
Søk og oppdagelse

<!-- @arkitektur.08 . figurtekst -->
trip · departures · geocode (read-only)

<!-- @arkitektur.09 . figurtekst -->
SALES/MANDAT MCP · vårt bidrag

<!-- @arkitektur.10 . figurtekst -->
Mandatbundet kjøp

<!-- @arkitektur.11 . figurtekst -->
search · quote · purchase · get_ticket

<!-- @arkitektur.12 . figurtekst -->
PORTVOKTER

<!-- @arkitektur.13 . figurtekst -->
Mandat-tjeneste

<!-- @arkitektur.14 . figurtekst -->
scope + tak-sjekk

<!-- @arkitektur.15 . figurtekst -->
ENTUR

<!-- @arkitektur.16 . figurtekst -->
Sales API

<!-- @arkitektur.17 . figurtekst -->
offers·order·payment

<!-- @arkitektur.18 . figurtekst -->
ENTUR

<!-- @arkitektur.19 . figurtekst -->
Journey Planner · Geocoder

<!-- @arkitektur.20 . figurtekst -->
GraphQL / REST

<!-- @arkitektur.21 . figurtekst -->
Fulfillment-lytter · Kafka billettdistribusjon (asynkron)


**Figur i seksjon roller**

<!-- @roller.03 . figurtekst -->
I DAG

<!-- @roller.04 . figurtekst -->
Forbruker

<!-- @roller.05 . figurtekst -->
velger + betaler

<!-- @roller.06 . figurtekst -->
Nettbutikk

<!-- @roller.07 . figurtekst -->
kasse + relasjon

<!-- @roller.08 . figurtekst -->
PSP

<!-- @roller.09 . figurtekst -->
prosesserer

<!-- @roller.10 . figurtekst -->
Kortnettverk

<!-- @roller.11 . figurtekst -->
flytter penger

<!-- @roller.12 . figurtekst -->
Bank

<!-- @roller.13 . figurtekst -->
SCA + midler

<!-- @roller.14 . figurtekst -->
MED AGENTER

<!-- @roller.15 . figurtekst -->
Menneske

<!-- @roller.16 . figurtekst -->
setter mandat

<!-- @roller.17 . figurtekst -->
+ agent utfører

<!-- @roller.18 . figurtekst -->
Agentflate

<!-- @roller.19 . figurtekst -->
ny beslutningstakt

<!-- @roller.20 . figurtekst -->
modell-lab

<!-- @roller.21 . figurtekst -->
Mandat- og

<!-- @roller.22 . figurtekst -->
tillitslag

<!-- @roller.23 . figurtekst -->
nytt, ueid

<!-- @roller.24 . figurtekst -->
Selger

<!-- @roller.25 . figurtekst -->
feed + levering

<!-- @roller.26 . figurtekst -->
mister kassen

<!-- @roller.27 . figurtekst -->
Nettverk

<!-- @roller.28 . figurtekst -->
+ bank

<!-- @roller.29 . figurtekst -->
tillitsregister
