---
title: PubQuiz
status: complete
created: 2026-09-27
updated: 2026-09-27
---

# Produktbeskrivelse: PubQuiz

## Idé og verdi

PubQuiz på pubquiz.no skal gjøre det enkelt for små grupper å få en god quiz raskt, med en tilpasset pubrunde som mulig del av opplevelsen. Kunden velger temaer og vanskelighetsgrad, får ferdig innhold på mobilen og kan dele det med andre. En nedlastbar PDF gir kunden en kopi å beholde. Verdien ligger i gode spørsmål, pålitelig fasit, enkel gjennomføring og mindre planlegging.

Prosjektet starter som et skoleprosjekt, med ambisjon om offentlig lansering og videre utvikling. Initiativtakeren eier pubquiz.no. Norge er første marked; andre land skal ikke blokkeres, men pubrunder tilbys bare der informasjonsgrunnlaget er godt nok.

## Første kunde og behov

Første målgruppe er studenter mellom 20 og 30 år. Rune (26) besøker Oslo sammen med medstudentene Karsten og Tor fra Bergen. De vil oppdage gode puber og ha en egen quizkveld, uten å delta på et større arrangement. De mangler lokalkunnskap og vil bruke tiden sammen fremfor å planlegge alt selv.

Rune oppdager PubQuiz via en QR-plakat på en pub. Gruppen velger tre quizer og en passende pubrunde. Etter kjøpet deler Rune koden; alle åpner samme innhold og blar selv. Kartveiledning fører dem mellom stoppene. Den samme quizen kan senere deles med Siri, som skal til Oslo. Pubavtaler for QR-plakater er ikke etablert.

## Foreløpig tilbud og forretningsmodell

| Tilbud | Tentativ pris |
| --- | --- |
| Full pakke med tre puber og tre quizer | 99 kr |
| Én quiz med selvvalgte temaer fra temabanken | 30 kr |
| Mixed-quiz fra en tilstrekkelig stor spørsmålsbank | Mulig senere pris: 10 kr |

Prisene og modellen for pubrunder er ikke låst. Gjeldende arbeidshypotese er at pubrunde inngår i trequizpakken; én eller to quizer kjøpes uten pubrunde. Vilkår for større kjøp er åpne. En gratis prøvequiz består av 20 faste spørsmål: fem lette, fem middels, fem vanskelige og fem med stigende vanskelighet.

Første økonomiske mål er kostnadsdekning. Betalte kjøp skal finansiere drift, men lønnsomheten må måles. Eier aksepterer testkostnader og gratis testkoder som investering. Stor brukerbase, anbefalinger og domenets verdi er mulige fordeler, ikke dokumentert etterspørsel.

## MVP: kjøp, bruk og levering

MVP er en mobilvennlig nettside uten innlogging, GPS-tilgang, deltakerregistrering, lag eller poengsystem. Kunden velger fra en forhåndsdefinert temabank, uten friteksttemaer. Hvert tema gir fem spørsmål; fire temaer gir 20. Vanskelighetsvalg er lett, middels, vanskelig eller stigende. Mixed-quiz bruker banken; temabaserte kjøp skal få nye KI-genererte spørsmål som kontrolleres mot eksisterende innhold.

Ved pubrunde oppgir kunden startpunkt, dato, starttid og radius, med kombinerbare ønsker om eksempelvis ølutvalg, atmosfære og gangavstand. Kunden kan la tjenesten velge eller velge fra forslag. Egnede steder må finnes før betaling. Manglende datagrunnlag eller for få pålitelige puber skal gi tydelig beskjed, ikke en rute fylt med uegnede alternativer. Om kunden da får færre stopp eller tilbud om bare quiz må avklares. Kostnaden ved søk som ikke fører til kjøp må begrenses.

Hele ruten og alle kjøpte spørsmål, svar og kilder skal være kontrollert før oppstart. Deretter vises tilgangskoden og opplegget direkte på nettsiden. E-post med kode og senere PDF-klargjøring skal ikke holde igjen oppstarten. Alle med koden kan bruke og dele innholdet og laste ned PDF-en. Fasit med kilder vises etter hver quiz; ruten veksler mellom kartveiledning og quiz.

Ønsket klargjøringstid er omtrent ett minutt, med tydelig ventestatus. Eier vil varsles ved mer enn tre minutter. Tidsmålene er ikke verifisert. PDF-en for en pubrunde skal inneholde kart, destinasjoner og åpningstider i tillegg til quizinnhold; opplysningene kan bli utdaterte ved gjenbruk.

Spørsmål lagres med ID-er, og koden peker til kjøpets ordnede innhold. Koden gir ingen ny generering, og eksterne PDF-er kan ikke importeres. Kunden beholder PDF-en; varighet og drift av nettbasert tilgang må konkretiseres. E-post skal brukes til levering med minst mulig lagring; leverandørbehandling og nødvendige kjøpsdata må avklares. Ingen kontobasert gjenfinning loves; kunden skal bes om å bevare e-posten og filen.

## Kvalitet og tillit

Spørsmål og svar skal bygge på troverdige kilder; Wikipedia og Store norske leksikon er akseptable eksempler. Kontroll skal bekrefte at kilden besvarer akkurat det stilte spørsmålet. Tall skal være så presise som kildegrunnlaget tillater. Tvetydige spørsmål, omstridte fasitsvar og innhold som skaper dårlig stemning skal unngås gjennom redaksjonelle regler.

Gjentakelser skal minimeres, også ved omformuleringer. Bare feilaktige spørsmål sendes til retting; erstatningene kontrolleres mot resten. Uten brukerhistorikk kan tjenesten ikke vite alt kunden har sett i tidligere eller delte quizer. Banken må ha et godt startutvalg før lansering. Jevn kvalitet er et krav; hvis kravene ikke kan oppfylles, skal leveransen ikke presenteres som klar.

## Suksess, rammer og neste avklaringer

Viktigste suksessignaler er at brukerne vurderer spørsmålene som gode og anbefaler PubQuiz videre. Nettsiden skal kunne brukes uten veiledning. Feedback-knapper ved quizslutt og i e-posten, samt avgrenset analyse av brukstall, skal støtte forbedring. Målemetoder og terskler er ikke bestemt.

Én person bygger med Codex, eventuelt Claude senere. ChatGPT Plus finnes allerede; det er ikke satt av et eget startbudsjett. Investering vurderes ved behov. Oppgitt frist «er dag» er tolket som i dag, 27. september 2026, for denne leveransen. Ingen lanseringsdato er fastsatt.

Før implementering må PRD og arkitektur avklare priser/pakker, innholds- og pubkontroll, startbank, leveringsfeil, kostnadsgrenser, datalagring, konkrete kvalitetsmål og leverandørtilgang. Tekniske forslag og brukerens utdypinger finnes i [vedlegget](addendum.md).

Senere muligheter er quizmastermodus, kontoer og samlinger, nedlastbar app, fun facts, større grad av bankgjenbruk, Untappd-integrasjon og skjulte pubrunder med frivillige destinasjonsgåter. Disse er ikke lovet i MVP.
