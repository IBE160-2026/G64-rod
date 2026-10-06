# Tilbakemelding på product brief

| | |
|---|---|
| **Gruppe** | G64 – G64-rod |
| **Product brief** | `_bmad-output/planning-artifacts/briefs/brief-PubQuiz-2026-09-27/brief.md` (commit `6122aca`), med `addendum.md` i samme mappe |
| **Tilbakemelding fra** | Faglærer i IBE160 (utarbeidet med KI-støtte) |
| **Dato** | 2026-10-06 |

## Samlet vurdering

- **Bør revideres før dere går videre.** Rett punktene markert «Endre» før dere lager PRD og arkitektur.

**Det som er bra:**

1. Rune-scenarioet gir en levende og konkret brukerhistorie: tre studenter fra Bergen i Oslo, QR-plakat, tre quizer, deling av koden med vennene og senere med Siri. Det er lett å se for seg skjermbildene, og prinsippet om at hver deltaker blar selv på egen telefon er en god forenkling.
2. Kvalitetskravene til innholdet er gjennomtenkte: fasit med kilder (Wikipedia og SNL), kontroll av at kilden faktisk besvarer spørsmålet, unngåelse av tvetydige og konfliktfylte spørsmål, og at en leveranse ikke skal presenteres som klar hvis kravene ikke er oppfylt. Erfaringen fra bartobar.no er nyttig for UX-arbeidet.

**De viktigste endringene:**

1. MVP-en er et kommersielt produkt, ikke en v1 for ett semester. Den inneholder betaling (Stripe/Vipps), KI-generering av nye spørsmål med kilde- og duplikatkontroll, KI-basert research av puber i Google Maps og på nettet, kartveiledning, PDF med kart og åpningstider, e-postlevering, tilgangskoder og tilbakemeldingsanalyse. Det er langt mer enn én person rekker gjennom hele BMAD-flyten med testing. Velg én kjerneflyt for emnet.
2. Briefen mangler testbare suksesskriterier. «Brukerne vurderer spørsmålene som gode» og «anbefaler PubQuiz videre» kan ikke måles i emnet, og briefen sier selv at målemetoder og terskler ikke er bestemt. Legg til funksjonelle kriterier, for eksempel «en bruker kan velge fire temaer og vanskelighetsgrad og får 20 spørsmål, fem per tema» og «alle med koden ser samme spørsmål i samme rekkefølge».
3. Lag en plan for hvordan sensor kan kjøre appen uten deres nøkler og betalte kontoer. Språkmodell, Google Maps, betaling og e-post krever alle nøkler og koster penger. Addendumet foreslår selv en lokal prototype med forhåndslagde testdata. Gjør det til v1.

## Vanskelighetsgrad og gjennomførbarhet

### Vurdert vanskelighetsgrad

- **Vanskelig**

**Sammenlignbart med:** 8) Foredragsnotater – sammendrag og quizgenerator (enkel) er utgangspunktet for quizdelen, men med betaling, flere eksterne tjenester, KI-basert stedssøk og strenge kvalitetskrav til KI-svarene blir helheten vanskelig.

**Begrunnelse:**

| Faktor | Nivå (lav / middels / høy) | Kommentar |
|---|---|---|
| Domenelogikk – hvor mange og hvor kompliserte regler og beregninger må stemme? | Middels | Temavalg, fem spørsmål per tema, vanskelighetsgrader inkludert «stigende», pakkeregler (tre quizer gir pubrunde) og regler for gjentakelser. Mange regler er fortsatt åpne. |
| Datamodell – antall entiteter og relasjoner mellom dem | Middels | Spørsmålsbank med ID-er, temaer, kilder, kjøp, tilgangskoder med ordnet spørsmålsliste, pubruter med stopp og tilbakemeldinger. |
| Brukere, roller og innlogging | Lav | Ingen innlogging i MVP. Tilgang styres med kode. |
| KI-funksjonalitet i appen, f.eks. kall til språkmodell, prompts i koden og håndtering av usikre svar | Høy | Generering av nye spørsmål, kildekontroll, duplikatkontroll på tvers av banken, parallelle KI-arbeidere og revisjonsagent. Svært krevende å gjøre pålitelig og å teste. |
| Integrasjoner og eksterne tjenester, f.eks. API-er, betaling og e-post | Høy | Språkmodell-API, Google Maps, betaling, e-post og eventuelt Untappd. |
| Sanntid, samtidighet eller flere brukere som påvirker hverandre | Lav | Ingen synkronisering mellom telefoner i MVP. |
| Filhåndtering, f.eks. opplasting, PDF-lesing og eksport | Middels | PDF-generering med quizinnhold, kart og åpningstider. |
| Sikkerhet og personvern | Middels | Betaling, e-postadresser og analyse av brukstall krever avklaring av personvern og lagring. |

**Hva vanskelighetsgraden betyr for dere:**

- _Vanskelig:_ Et vanskelig prosjekt gir større mulighet for toppkarakter, men også større risiko. Definer en minimal versjon som sikkert kan bli ferdig, og legg resten i tydelige trinn etterpå. For dere bør den minimale versjonen være selve quizopplevelsen på mobil, bygget på en ferdig spørsmålsbank.

### Gjennomførbarhet med BMAD og Claude Code

Dere skal planlegge med BMAD (product brief → PRD → arkitektur → epics og stories) og implementere med Claude Code. Vurderingen under tar hensyn til at det må være tid til hele denne flyten, og til testing, retting og README til slutt.

| Spørsmål | Vurdering (OK / risiko / stor risiko) | Kommentar |
|---|---|---|
| **Tid og omfang** – kan v1 realistisk bli ferdig og stabil i løpet av semesteret, med tid til flere iterasjoner? | Stor risiko | Omfanget er stort for én person, og briefen lister selv mange avklaringer (priser, pubkontroll, startbank, kostnadsgrenser, datalagring, kvalitetsmål) som må gjøres før implementering. |
| **BMAD-flyten** – er briefen konkret nok til at PRD, arkitektur og stories kan lages uten store hull, og blir det overkommelig mange stories? | Risiko | Briefen følger ikke malens struktur (problem, løsning, brukere, suksesskriterier, scope inn/ut). Addendumet har mye detalj, men også mange historiske og motstridende forslag. Det gir uklare akseptansekriterier. |
| **Egnet for Claude Code** – bruker løsningen en vanlig, godt dokumentert teknologistakk som Claude Code håndterer godt, eller krever den nisjeteknologi, spesialmaskinvare eller mye manuell konfigurasjon? | Risiko | En mobilvennlig nettside (for eksempel Astro) er godt egnet. Integrasjonene mot betaling, kart og e-post krever mye manuell konfigurasjon av kontoer. Merk at emnet bruker Claude Code. Dokumenter det dersom dere også bruker Codex. |
| **Kontroll på KI-ens arbeid** – kan gruppen selv avgjøre om koden gjør det riktige? Krever domenet kunnskap gruppen ikke har, f.eks. avanserte beregninger eller fagregler, så er det vanskelig å kvalitetssikre. | Stor risiko | Å kontrollere at KI-genererte spørsmål er korrekte, kildebelagte og ikke duplikater, er svært vanskelig å automatisere. Selv addendumet viser et eksempel (Omaha-stranden) der fasiten var tvetydig. |
| **Testbarhet** – finnes det tydelige regler og forventede resultater som tester kan skrives mot? | Risiko | Kode, temavalg, antall spørsmål og rekkefølge er testbart. Kvaliteten på KI-genererte spørsmål og pubforslag er vanskelig å teste automatisk. |
| **Kjørbar for sensor** – kan appen kjøres lokalt etter README, uten gruppens nøkler, betalte kontoer eller egen infrastruktur? | Stor risiko | Uten en lokal modus med forhåndslagde data kan ikke sensor kjøre kjerneflyten. |
| **Avhengigheter og kostnader** – krever løsningen betalte API-er, f.eks. språkmodeller, og finnes det en plan for kostnad, testmodus eller mock-data? | Stor risiko | Språkmodell, kart, betaling og e-post koster penger. Briefen sier at startbudsjettet er null, og at ChatGPT Plus ikke dekker API-bruk. |

**Konklusjon om gjennomførbarhet:**

- **Lite realistisk uten vesentlige endringer.** Se forslagene under.

**Forslag til justering av omfang eller vanskelighetsgrad:**

1. Gjør v1 til en lokal quizapp: en ferdig kuratert spørsmålsbank med temaer, vanskelighetsgrader og kilder; temavalg og vanskelighetsvalg; generering av tilgangskode; mobilvennlig visning med ett spørsmål om gangen; og fasit med kilder etter quizen. Betaling simuleres («kjøp»-knapp uten ekte betaling).
2. Legg KI-generering av nye spørsmål inn som et avgrenset trinn 2 med mock-modus, der genererte spørsmål alltid går til en kontrollkø i stedet for direkte til kunden. Flytt pubrunde, kart, ekte betaling, e-post, PDF med kart og analyse til visjonen.

## Hvorfor product brief er viktig for mappen

Product brief er utgangspunktet for PRD, arkitektur, stories og til slutt koden. Del 1 av mappen vurderes blant annet på om sensor kan følge en sporbar vei fra plan til ferdig app. Den vurderes også på om appen gjør det dere har beskrevet, om den er testet, om den er godt designet, og om den kan kjøres etter README. Et uklart, for stort eller for lite brief gjør alt dette vanskeligere senere. Det er mye enklere å rette nå enn sent i semesteret.

## 1. Gjennomgang av briefens deler

| Del av brief | Status | Kommentar |
|---|---|---|
| Executive Summary – er det klart hva appen er, og hvilket problem den løser? | Juster | «Idé og verdi» forklarer produktet godt, men mest som forretningsidé. Si også hva som skal leveres i emnet. |
| The Problem – er problemet konkret, med reelle situasjoner og brukere? | Juster | Problemet ligger implisitt i Rune-scenarioet (mangler lokalkunnskap, vil slippe planlegging). Skriv det ut som en egen del. |
| The Solution – beskriver løsningen brukeropplevelsen, ikke bare teknologi? | OK | MVP-avsnittet og Rune-scenarioet beskriver opplevelsen fra temavalg til fasit og kartveiledning. |
| What Makes This Different – er vurderingen ærlig og realistisk? | Juster | Mangler som egen del. Addendumet nevner at mobilopplevelse og ferdig research skal gi grunn til å betale fremfor å spørre en KI selv. Løft dette inn, og vær ærlig om konkurransen. |
| Who This Serves – er primærbrukerne tydelige, og vet vi hva de trenger? | OK | Studenter 20–30 år på besøk i en ny by, med Rune som tydelig persona. |
| Success Criteria – kan kriteriene faktisk sjekkes eller testes? | Endre | Bare forretnings- og opplevelsessignaler uten målemetode. Legg til funksjonelle, testbare kriterier. |
| Scope – er det klart hva som er med i første versjon, og hva som ikke er det? | Endre | Det er klart hva som ikke er med (innlogging, GPS, lag, poeng), men det som er med, er for stort. Lag en tydelig «In for v1»-liste for emnet og en «Explicitly out»-liste. |
| Vision – henger visjonen sammen med resten uten å blåse opp omfanget? | OK | Quizmastermodus, kontoer, app og Untappd ligger utenfor MVP. Pubrunde og betaling bør flyttes hit. |

## 2. Utgangspunkt for del 1 av mappen

Punktene følger kriteriene i sensorveiledningen for del 1. Vektene i parentes viser hvor mye hvert kriterium teller i del 1.

| Kriterium i del 1 | Hva briefen bør legge til rette for | Status | Kommentar |
|---|---|---|---|
| **1. Prosess og KI-styring** (30 %) | Brief som er presis nok til at PRD og stories kan bygges direkte på den, slik at krav kan spores fra brief til kode. | Endre | Med mange åpne valg og et stort addendum blir sporbarheten svak. En kort, avgrenset brief gir PRD og stories som kan følges til kode. |
| **2. Funksjonalitet og omfang** (20 %) | Realistisk omfang for gruppen og semesteret: en tydelig kjerneflyt som kan bli ferdig og stabil, og nok innhold til å vise reell funksjonalitet. | Endre | Velg quizopplevelsen som kjerneflyt og gjør den ferdig og stabil. |
| **3. Kvalitetssikring og testing** (15 %) | Suksesskriterier og funksjoner som er konkrete nok til å bli testtilfeller. | Endre | Ingen testbare kriterier ennå. Pakkeregler, temavalg og kodeoppslag kan bli gode testtilfeller. |
| **4. Design og brukeropplevelse** (10 %) | Tydelige brukere og brukssituasjoner som designet kan bygges rundt, gjerne med de viktigste skjermbildene eller flytene skissert. | OK | Mobilbruk på pub, én hånd og ett spørsmål om gangen gir et godt utgangspunkt for design. |
| **5. Kodekvalitet og arkitektur** (10 %) | Teknologivalg som er begrunnet og ikke mer komplekse enn appen trenger. | Juster | Parallelle KI-arbeidere og revisjonsagent er avansert arkitektur. Hold v1 til nettside, database og spørsmålsbank. |
| **6. README og kjørbarhet** (10 %) | Løsning som andre kan kjøre lokalt uten betalte kontoer, og uten tilgang til gruppens egne tjenester og nøkler. | Endre | Krever i dag flere betalte tjenester. Lokal modus med forhåndslagde data må være standard. |
| **7. Ryddighet i repoet** (5 %) | En plan for hvor hemmeligheter, testdata og dokumentasjon skal ligge. | Juster | Dere har dokumentert utviklingsmiljøet, det er bra. Planlegg `.env.example` for alle nøkler og en egen mappe for spørsmålsbanken som testdata. |

## 3. Neste steg for gruppen

1. Skriv om briefen etter malens struktur, med en tydelig v1 for emnet: lokal quizapp med ferdig spørsmålsbank, temavalg, tilgangskode og fasit med kilder.
2. Legg til funksjonelle, testbare suksesskriterier, og bygg en liten startbank (for eksempel 100–200 kontrollerte spørsmål) som testdata.
3. Flytt pubrunde, betaling, e-post og KI-research til visjonen, og planlegg eventuell KI-generering som et senere trinn med mock-modus.

Oppdater product brief i repoet når dere har gjort endringene, slik at historikken viser hvordan planen utviklet seg. Det er en del av prosessen sensor ser etter.
