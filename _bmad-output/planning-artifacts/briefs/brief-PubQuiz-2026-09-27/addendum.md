# PubQuiz – utdypende innspill

Dette vedlegget bevarer innspill og utviklingen av ideen. Gjeldende krav og åpne valg står i [produktbeskrivelsen](brief.md). Historiske avsnitt nedenfor er bakgrunn, ikke parallelle krav.

## Gjeldende kommersiell status ved ferdigstilling

Dette avsnittet erstatter tidligere bastante formuleringer om priser og gratis pubrunde. Forretningsmodellen er tentativ og skal vurderes videre. Siste alternativer fra brukeren er full pakke med tre puber og tre quizer til 99 kroner, selvvalgt temaquiz til 30 kroner, og mulig mixed-quiz til 10 kroner når banken er solid. Ingen av prisene er endelig besluttet. Trequizpakken er fortsatt arbeidshypotesen for pubrunde; regelen for større kjøp er åpen.

Brukeren forstår at live-løsningen krever API-bruk og forventer at salgsinntekter dekker driften. Testkostnader og gratis koder til testpersoner aksepteres som prosjektkostnader. Dette er ikke en dokumentert kostnadskalkyle eller en fullmakt til å aktivere betalte tjenester nå. Tidligere nullbudsjett betyr ingen forhåndsavsatt sum, med investering mulig når behovet er begrunnet.

Brukerens ordlyd «Innleveringsfrist er dag» tolkes som i dag, 27. september 2026. Brukeren ber om commit når produktbeskrivelsen er ferdig; det er ikke bestilt utrulling eller implementering i denne samtalen.


## Dokumentregnskap ved ferdigstilling

- Produktbeskrivelsen inneholder gjeldende visjon, målgruppe, kjerneforløp, tentative pakker, MVP-grenser, kvalitet, suksessignaler og gjennomføringsrammer.
- Dette vedlegget bevarer konkrete eksempler, tekniske kandidater, leveringsdetaljer, kildeundersøkelser, senere muligheter og erfaringen fra bartobar.no for videre PRD- og arkitekturarbeid. Tidligere pris- og leveringsforslag er erstattet av gjeldende modell i brief.md og avsnittet ovenfor.
- Beslutningshistorikken ligger i .memlog.md. Tidligere åpne spørsmål som senere er avklart, samt samtalens arbeidsrekkefølge, er ikke gjeldende produktkrav. Rutinemessige verktøykall inngår ikke i leveransen.

## Historiske innspill og utdypinger


## Foreslått temavalg

Brukeren ser for seg en meny med skiftende temaforslag. Kunden kan eksempelvis få fire forslag og velge to, be om nye forslag, velge flere og avvelge tidligere valg. Eksempelet ender med fire valgte temaer og fem spørsmål per tema. Antall forslag per visning og grensen for valgte temaer er ikke endelig avklart.

## Innhold og levering

Et KI-API er foreslått for å lage spørsmålene. Brukerens tekniske skisse er å samle spørsmålene i en mappe og gi kunden en tilhørende kode. Lagringsformat og arkitektur avgjøres senere. Genererte spørsmål skal også legges i en felles bank for senere gjenbruk, blant annet i en blandet quiz med tilfeldig utvalg.

PDF og kode er foreslått som levering for pubrunder med og uten quiz. Alle med quizkoden skal kunne åpne quizen. Brukeren ønsker varig tilgang og fri deling av kjøpt quiz, uten eksklusivitet til enkeltspørsmålene. Fasit med spørsmål, svar og kilde vises ved slutten av hver quiz. Lagringsløsning for kodetilgang er ikke avklart. Hver deltaker blar selv.

## Rune-scenarioet: flaggskipet i MVP

Rune (26) besøker Oslo sammen med medstudentene Karsten og Tor fra Bergen. De vil utforske drikkesteder og ha sin egen quizkveld. På en pub oppdager Rune en plakat med QR-kode til pubquiz.no, skanner den og leser introduksjonen. QR-plakaten er en foreslått oppdagelseskanal; samarbeid med puber er ikke etablert i samtalen.

Gruppen velger kombinert runde med tre puber, godt ølutvalg og radius seks kilometer. Hvor radiusen måles fra, er ikke avklart. De velger knappen for én quiz per pub. Første quiz har blandede temaer. Den andre har andre verdenskrig, geografi, matematikk og Eurovision. Den tredje har matematikk, blandede spørsmål, idrettshelter og norske konger.

Rune betaler i eksemplet 99 kroner med Stripe eller Vipps. Betalingsløsning og pris er foreløpige forslag. Han mottar PDF og kode på e-post og deler koden med vennene, som åpner samme opplegg på nettsiden.

Velkomstsiden tilbyr Google Maps-rute til første destinasjon eller å gå videre dersom de allerede er fremme. Første quiz introduseres med 20 spørsmål og blandede temaer. Neste-knappen viser neste spørsmål. Etter quizen kommer alle spørsmål med svar og kilde. Deretter går gruppen videre til neste pub med kartveiledning, og forløpet gjentas. Neste-knappen påvirker bare egen telefon.

## Tekniske ønsker til senere vurdering

- Rask landingsside bygget i Astro, koblet til ulike API-er.
- Google Maps-integrasjon for å åpne pubrunden i kart og veksle mellom rute og quiz.
- Nettside i MVP; mulig nedlastbar app senere for bedre brukervennlighet.

Dette er brukerens løsningsforslag, ikke vedtatte arkitekturvalg.

## Avklart bruksmodell og betaling

Alle blar selv; Runes neste-knapp påvirker ikke de andres telefoner. Nettsiden skal i MVP fungere som en mer brukervennlig utgave av den leverte PDF-en. Brukeren mener egen blaing fremmer deltakelse fremfor passivitet. Synkronisering er utenfor MVP. En mulig senere quizmastermodus kan gi en Kahoot-lignende gjennomføring.

Betaling ønskes fra starten, mens ferdig quiz skal kunne deles videre med kode. Formålet er høy opplevd verdi og spredning gjennom anbefalinger. Brukeren uttrykker bekymring for misbruk fra gratisbrukere; dette er en utestet antakelse. Binding av quizer til brukerkontoer vurderes som en senere mulighet, men er ikke besluttet og må avstemmes med løftet om varig og delbar tilgang. Kjøpet betaler for å bygge quizen; koden åpner kun den ferdige leveransen og gir ikke ny generering.

## Senere funksjoner og brukssituasjoner

Registrering av deltakere og lag kan komme senere. Poengsystem er uavklart og uttrykkelig utenfor MVP. Brukeren ønsker både lokal og geografisk spredt deltakelse, uten produktbestemt grense for antall deltakere. MVP gir delt tilgang til samme innhold med individuell blaing.


## Presisering: levering uten konto

Brukeren foreslår omtrent 30 kroner per quiz som betaling knyttet til tokenbruk, og forventer at mange velger tre puber og tre quizer. Endelig pris og kostnadsgrunnlag er ikke fastsatt. Mobilopplevelsen og ferdig research skal gi en grunn til å betale fremfor å be en KI om quiz selv.

Kode og PDF leveres separat. Koden åpner bare PubQuiz sin egen leveranse i en mobiltilpasset fremviser; ingen opplasting eller import av vilkårlige KI-genererte PDF-er. Brukerens forslag er en statisk fremviser eller oversetter for eget format. Faktisk format avgjøres i arkitekturarbeidet. Rune kan dele koden og ruten med Siri som skal til Oslo uken etter.

Ingen innlogging eller personlig quizbibliotek i MVP. Kunden beholder PDF-en. Brukeren ønsker minst mulig manuell støtte ved mistet kode; automatisk gjenutsending av alle kjøpte koder til kjøpers e-post er en mulig løsning, ikke et besluttet MVP-krav. En slik løsning trenger kobling mellom kjøp, e-post og koder. Også en statisk fremviser må få innholdet fra et sted; fravær av konto betyr ikke nødvendigvis fravær av lagring.

## Automatisk research og områdevalg

Brukeren ønsker KI-assistert research i Google Maps og på nettet, fremfor et håndplukket pubregister. Kriterier som koselig, gastropub og stort lokale kan kombineres. Hvis ønskede egenskaper ikke finnes, foreslås nærmeste alternativer innen brukerens radius. Minstekravet omtales som alkoholutsalg; om dette konkret skal bety serveringssteder hvor gruppen kan sitte med quiz må presiseres. Ved færre enn ønsket antall steder er oppførselen åpen; en beklagelse med tilbud om bare quiz er foreslått.

Ingen GPS-tilgang i MVP. Startpunkt kan være adresse eller koordinater, eventuelt foreslåtte landemerker etter byvalg, som Oslo S og Nationaltheatret. Brukeren ønsker eksterne tjenester og minst mulig persondatabehandling. Besøkstidspunkt og håndtering av utdaterte åpningstider eller pubruter er ennå ikke avklart.


## Spørsmålsbank og tilgangskoder – avklart produktmodell

Alle spørsmål som eieren eller kundene genererer får hver sin ID i en felles spørsmålsbank. Hver tilgangskode knyttes til en ordnet liste med spørsmåls-ID-er, som brukes til å vise ett spørsmål om gangen. PDF-en viser ikke interne ID-er. Brukerens formulering om at PDF-en kun inneholder spørsmål må avstemmes med tidligere beskrivelse av pubrunde, fasit og kilder; det er ikke besluttet å fjerne disse.

Brukeren ønsker ingen lagring av kundens e-post i MVP; adressen brukes bare til å sende PDF og kode. Dette tolkes som ingen varig kundelagring, siden spørsmålsbank og kodekoblinger uttrykkelig skal lagres. Teknisk behandling under levering og leverandørenes lagring må avklares. Automatisk gjenutsending av koder etter e-postoppslag kan ikke forutsettes uten en varig kjøpskobling. Lagring av pubrute, rekkefølge per pub, fasit og kilder bak koden må detaljeres senere.

## Prishypotese og pubvalg

30 kroner per quiz er brukerens prisidé. Tre–fire quizer per kjøp er ønsket kjøpsmønster. Brukeren antar at høy kvalitet gir flere salg og at kjøp av kun én quiz kan være utprøving eller misnøye; dette er uttrykkelig spekulasjon, ikke kundeinnsikt.

Pubene skal være serveringssteder. Kunden kan kombinere preferanser for å avgrense researchen, inkludert kort gangavstand eller ønske om å gå litt mellom stoppene. Radius og gangavstand mellom stopp er forskjellige parametere. To ønskede forløp: automatisk valg av eksempelvis tre puber, eller en liste med forslag der kunden velger tre. Produktet skal både gi valgfrihet og mulighet til å slippe detaljvalg. Brukeren prioriterer bred appell i MVP.

Dato og starttid er akseptert som inndata fordi stengte eller nedlagte puber vil ødelegge opplevelsen. Hvordan åpningstidene skal kontrolleres mot forventet ankomst ved hvert stopp, er ikke avklart.


## PDF-leveranse og quizinnstillinger

For en pubrunde skal PDF-en inneholde et Google-kart samt destinasjoner med navn og åpningstider. Kartintegrasjon i eksport og vilkår for kartmateriale må undersøkes ved teknisk planlegging. Opplysningene er et øyeblikksbilde; åpningstider kan endres ved senere gjenbruk.

Brukeren aksepterer at begrensningen ved ingen lagret e-postkobling må fremgå av leveringsmodellen. E-posten kan be kunden ta vare på meldingen, PDF-en og tilgangskoden. At kunder normalt beholder e-post er brukerens uttrykkelige spekulasjon, ikke dokumentasjon på sikker levering eller gjenfinning.

Fire vanskelighetsvalg: lett, middels, vanskelig og stigende vanskelighet. Hvert tema har fem spørsmål. Om stigende vanskelighet gjelder innen hvert tema eller over hele quizen er åpent.

Fun facts vurderes for en senere versjon, med mulig ja/nei-preferanse for en innledning før spørsmål og eventuelt en utfyllende opplysning ved svaret. Brukerens illustrasjon er D-dagen, Normandies fem landgangsstrender og Omaha som foreslått svar på hvor amerikanerne gikk i land. Eksemplet er ikke godkjent quizinnhold: amerikanerne gikk i land på både Utah og Omaha, så spørsmålet må avgrenses for å få én fasit. Tapstall og øvrige detaljer må kildeverifiseres før bruk.


## Nye spørsmål, mixed-quiz og jevn kvalitet

Mixed-quiz skal hente fra eksisterende bank. Brukerens bekymring for kvalitet ved helt tilfeldig KI-generering av temaer og spørsmål er uttrykkelig en antakelse; bankbasert sammenstilling er det valgte produktgrepet. Banken må ha et godt startutvalg før MVP lanseres. Antall spørsmål og fordeling mellom temaer er ikke bestemt.

Ved temabasert kjøp ønsker brukeren nye KI-genererte spørsmål som ikke allerede finnes i banken. Temainndelte biblioteker foreslås for å avgrense sammenligningsmengden. Oppdeling er et løsningsforslag; spørsmål kan overlappe på tvers av temaer. Et krav i KI-instruksen alene er ikke dokumentasjon på duplikatfrihet. Kontrollmetode, håndtering av omformuleringer og kvalitet ved smale temaer må avklares senere.

Brukeren ønsker at Rune skal kunne kjøpe mange quizer uten fall i kvalitet, omtalt som at kvaliteten skal være lineær. Dette tolkes som jevn kvalitet, ikke et målbart løfte om ubegrenset kapasitet. Kriterier og terskler for kvalitet er ennå ikke bestemt.

Troverdige kilder i fasiten er et sentralt krav. Wikipedia og snl.no er uttrykkelig akseptable kilder for brukeren. Kilden må støtte den konkrete påstanden og fasiten, ikke bare handle om samme tema.

Ved gjentatte spørsmål foreslår brukeren at kunden sender e-post og får en gratis quiz eller kode manuelt, med noe ventetid. Dette er en foreslått støtteordning, ikke et løfte med fastsatt responstid. Det krever ikke i seg selv konto eller forhåndslagret kundehistorikk. Uten historikk vet tjenesten ikke hvilke spørsmål kunden tidligere har sett gjennom egne kjøp eller delte koder. Ingen gjentakelser i samme quiz eller kjøp er en mulig avgrenset garanti som fortsatt må bekreftes.


## Temastyring og senere gjenbruk

Brukeren ønsker en stor, forhåndsdefinert temabank fremfor friteksttemaer, for å beskytte kvaliteten. Eksempler er geografi, historie, underholdning og litteratur. KI oppleves som lite tilfeldig; parametere for årstall, antall og datoer foreslås som mulige variasjonsgrep. Dette er utforskende ideer, ikke en bestemt genereringsalgoritme.

På lengre sikt ønsker brukeren å kunne redusere nygenereringen når spørsmålsbanken blir stor, eventuelt med nye spørsmål bare på eksplisitt bestilling. Dette er fremtidig retning og erstatter ikke ennå MVP-valget om nygenerering ved temabasert kjøp. Kontoer, personlige samlinger og deling via profiler kan vurderes ved senere brukeretterspørsel, men er utenfor MVP. Brukeren aksepterer at risiko for gjentakelser ikke nødvendigvis kan fjernes og at reaksjoner varierer mellom kunder.

## Leveringstid og alternativ PDF-levering

Omtrent ett minutt oppleves som akseptabel ventetid. Brukeren legger vekt på at kunden vet hva som skjer og hvor lenge det ventes. Ved belastning og eksempelvis 15 minutters venting håper brukeren kundene vil vente; dette er ikke et akseptert leveringsmål eller validert kundetoleranse. Eier ønsker varsel dersom klargjøring tar mer enn tre minutter, slik at årsaken kan undersøkes. Varslingskanal og hva tidsmålingen omfatter må bestemmes senere.

Brukeren vurderer å sende bare kode på e-post og tilby «last ned som PDF» på nettsiden når filen er klar. Det vurderes også å generere spørsmål gradvis mens kunden gjennomfører pubrunden. Ingen av disse endringene er endelig valgt. Dette skaper et åpent spørsmål om kjøpet må være komplett før bruk, hva som skjer dersom senere innhold feiler, og når kilder/fasit og PDF kan leveres. At kunden kan vente på senere spørsmål er foreløpig en hypotese.


## Besluttet leveringsløfte og forslag til parallell generering

Brukeren godkjenner komplett pubrute og alle spørsmål, svar og kilder, kontrollert før oppstart. PDF-en kan komme litt senere som nedlasting for alle med koden. Brukeren fremhever at enkel, rask quizproduksjon er et grunnprinsipp, og at delbar PDF øker verdien for kjøperen.

For å redusere produksjonstid foreslår brukeren parallelle KI-arbeidere: én per quiz (tre oppgaver med 20 spørsmål) eller én per tema (tolv oppgaver med fem spørsmål). En felles revisjonsagent foreslås for å kontrollere hele kjøpet og oppdage gjentakelser på tvers av quizer og temaer. Dette er kandidater til teknisk utprøving, ikke vedtatt arkitektur eller en dokumentert tidsbesparelse. Leveringsmålet på omtrent ett minutt må måles med research, kildekontroll, duplikatkontroll og eventuelle reparasjoner inkludert.


## Kildebaserte svar, tilgjengeliggjøring og suksess

Brukeren ønsker formuleringen «kontroller at svarene kommer fra kildene», fremfor bare at kildene støtter svarene. Dette presiserer at faktagrunnlaget skal hentes fra kildene og at referansene ikke bare tilføyes etterpå. Kontroll må fortsatt avklare at faktagrunnlaget besvarer det konkrete spørsmålet, med riktige forbehold, tidsrom og avgrensninger. Det kreves ikke ordrett gjengivelse av kildetekst.

Når hele leveransen er kontrollert, skal kode og opplegg være tilgjengelig direkte på nettsiden for Rune og vennene, uten at e-post eller PDF blokkerer oppstart. Dette endrer ikke beslutningen om komplett kontrollert innhold før oppstart. E-post med kode og senere PDF-nedlasting inngår fortsatt.

Revisjon skal returnere bare feilaktige spørsmål til retting, ikke hele quizen. Nye erstatninger må også kontrolleres mot det øvrige innholdet. Regelmessig variasjon av regler og genereringsparametere foreslås som en senere strategi ved gjentakelser eller lite kreative spørsmål, ikke som en fastlagt algoritme.

Brukeren prioriterer gode spørsmål og anbefalinger videre som de viktigste suksessignalene. Forventningen om at dette automatisk gir inntekter er en antakelse. Bruk uten hjelp betyr at nettsidens kjøps- og gjennomføringsflyt skal være selvforklarende; det handler ikke om å kunne besvare alle quizspørsmål uten hjelp. Vanskelighetsvalg skal gjøre det mulig å tilpasse utfordringen.

En quiz med 15 spørsmål, fordelt på fem lette, fem middels og fem vanskelige, foreslås for å prøve nivåene. Det er ikke avklart om dette er et eget format eller en konkretisering av stigende vanskelighet, og hvordan det passer med fem spørsmål per valgt tema. Ingen tidligere antallsregel er endret på grunnlag av dette forslaget.


## Redaksjonelle grenser og presisjon

Brukeren ønsker så nøyaktige tall som mulig og å unngå kontroversielle spørsmål eller temaer som skaper dårlig stemning. Eksemplene er spørsmål om hvem som har rett til Sør-Kinahavet og Israel/Palestina. Forhåndsdefinerte temaer er et tiltak for å styre innholdet. Brukeren foreslår en sjekkliste for revisjonsagenten; konkrete kategorier og grenser må utformes og bekreftes. Dette betyr ikke at alle historiske eller politiske fakta automatisk er utelukket. Kildeusikkerhet skal ikke skjules bak eksakte tall; ved uenighet bør spørsmålet omformuleres eller byttes ut. Disse prinsippene må også gjelde generering og utvalg fra banken, ikke bare sluttkontroll.

## Økonomisk ambisjon og antakelser

Kostnadsdekning er viktigere enn høy inntjening i starten. Brukeren mener stor brukerbase og et kjent navn vil gi gode inntektsmuligheter, og oppfatter pubquiz.no som en mulig fordel fremfor alternative domenenavn. Rask konkurranse, sammenheng mellom pris og opplevd kvalitet, og risiko ved for høy eller lav pris er brukerens hypoteser. Ingen markedsanalyse eller dokumentert betalingsvilje er etablert. 30 kroner per quiz er fortsatt en prisidé som må vurderes mot faktisk leveransekostnad.

## Gratis prøvequiz – erstatter tidligere 15-spørsmålsforslag

En gratis prøvequiz skal ha 20 faste spørsmål: fem lette, fem middels, fem vanskelige og fem i en egen bolk med stigende vanskelighetsgrad. Dette er forhåndslaget innhold uten ny generering per besøk. Forslaget erstatter den tidligere åpne ideen om en 15-spørsmålsquiz for å prøve nivåer. Betalte quizers regel om fem spørsmål per valgt tema er ikke endret. Den konkrete vanskelighetskurven i stigende-bolken er ikke bestemt.


## Geografisk rekkevidde og kvalitet på pubforslag

Norge er hovedmarked og MVP-fokus, men brukeren ønsker ingen hard landbegrensning. Ambisjonen er å kunne tilby pubrunder internasjonalt der kart- og nettkilder gir godt nok grunnlag. Brukeren er klar over at informasjonens dekning og aktualitet varierer mellom land. Kartdekning alene skal ikke regnes som bevis på at en pålitelig pubrunde kan leveres.

Manglende puber skal meldes tydelig til kunden. Tjenesten skal ikke fylle en rute med irrelevante spisesteder eller feil- og spøkeregistrerte private steder. Brukerens eksempel er en privat kjeller registrert som pub for moro skyld. Det etterspørres sikringer mot dette; konkrete datakilder, kontrollregler og terskler er ennå ikke valgt. Tidligere forslag om nærmeste alternativer må derfor forstås som verifiserte egnede steder, ikke enhver kartoppføring.

## Tilbakemeldinger og analyse

En feedback-knapp skal legges ved slutten av quizen og i e-posten som leverer kjøpet. Brukeren ønsker et system for å ta imot tilbakemeldinger og analysere tall som grunnlag for forbedring. Dette er et nytt funksjonskrav til MVP. Det er ikke valgt et analyseverktøy eller bestemt hvilke hendelser, tilbakemeldingsfelt eller personopplysninger som skal lagres. Løsningen må avstemmes med tidligere ønske om ingen varig lagring av kundens e-post og ingen konto. Et offentlig nettsted og frivillig feedback er ikke i seg selv samtykke til å samle vilkårlig brukerhistorikk.


## Betaling etter egnethetskontroll og erfaring fra bartobar.no

Brukeren bekrefter at muligheten for å levere pubrunden skal kontrolleres før betaling, og at kvalitetsnivået skal holdes jevnt eller leveransen avstås. Kunden skal vite hva kjøpet omfatter. Samtidig er kopiering av synlige pubanbefalinger før betaling en bekymring; forhåndsvisningens detaljer er ikke bestemt.

Brukeren har tidligere laget bartobar.no og brukertestet en modell der pubene først ble avslørt ved startpunktet gjennom gåter/hint. Feil gjetning førte folk til feil sted; brukeren beskriver dette som en bommert. Dette er konkret brukeroppgitt erfaring og bør tas med i videre UX-arbeid.

Nytt forslag: tre spørsmål for å gjette neste destinasjon som spenningsmoment i pubrunden. Dette er en idé til vurdering, ikke et bekreftet MVP-krav. En mulig utforming er frivillige hint med visning av korrekt sted og kart før man går, uavhengig av svaret; dette er assistentens forslag og krever brukerens tilslutning. Ingen GPS-basert sjekk av ankomst er besluttet; eksisterende MVP-avgrensning uten GPS gjelder fortsatt.

## Untappd som mulig datakilde

Brukeren foreslår integrasjon og preferanse for Untappd Verified Venues. Ingen tilkoblet Untappd-integrasjon eller autentisert API-tilgang er tilgjengelig i denne samtalen. Offentlige dokumenter viser en generell API og et eget Business-API. Faktisk tilgang for PubQuiz, kostnader, tillatt bruk og tilgjengelige søke-/stedsdata må undersøkes før dette blir en avhengighet.

Untappd beskriver Verified Venue som en side for et sted som har et forretningsforhold til Untappd, med mulighet for blant annet menyer og arrangementer. Statusen er derfor et mulig tilleggssignal, ikke alene en garanti for kvalitet, riktig åpningstid eller egnethet.

Kilder undersøkt i samtalen:
- https://help.untappd.com/hc/en-us/articles/360034387071-What-is-a-Verified-Venue
- https://untappd.com/api/docs
- https://docs.business.untappd.com/


## Endret betalingsmodell: pubrunde inkludert i quizproduktet

Brukeren velger å gjøre pubrunden til en gratis tilleggsfunksjon til quizene, fremfor et separat betalt produkt. Begrunnelsen er at kunder ellers kan kopiere pubforslagene til eget kart og avbryte før betaling, mens researchen allerede har kostet penger. Kunden betaler dermed for quizinnholdet; pubrunden har ingen egen pris. Dette erstatter den opprinnelige ideen om salg av pubrunde alene.

Skjult pubrunde og destinasjonsgåter flyttes til senere. Nøyaktig tilgang til gratis rutesøk før kjøp er ikke avklart. At ruten inkluderes gratis fjerner ikke kostnaden ved søk som aldri fører til kjøp; kostnadsrammer og eventuell begrensning eller gjenbruk av søk må behandles i videre planlegging. Det er ikke vedtatt å åpne ubegrenset gratis research som en frittstående tjeneste.


## Pakketerskel og gjennomføringsrammer

Brukeren endrer tilbudet til at kjøp av tre quizer gir en inkludert pubrunde. Pubrunder med bare én eller to puber ønskes ikke som produkt. Én og to quizer kan fortsatt kjøpes uten pubrunde. Om tilbudet gjelder nøyaktig tre eller minst tre quizer, samt antall stopp ved større kjøp, må avklares. Tidligere generell formulering om gratis pubrunde til ethvert quizkjøp erstattes.

Brukeren bygger alene, med Codex og muligens Claude senere. ChatGPT Plus finnes allerede. Startbudsjettet er null; investering er mulig dersom brukeren ser grunn til det. Dette er ikke en generell godkjenning til å pådra kostnader. Innleveringsdato eller annen tidsfrist er ikke oppgitt.

Utviklingsverktøy og drift må budsjetteres separat: eksisterende ChatGPT-abonnement innebærer ikke at nettsidens automatiske KI-generering, research og øvrige eksterne tjenester er gratis. En lokal prototype med forhåndslagde testdata kan brukes til å prøve kjerneflyten før kostnader til reelle integrasjoner besluttes. Dette er et forslag til gjennomføring, ikke en endring av det ønskede sluttproduktet.
