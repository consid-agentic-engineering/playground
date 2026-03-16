# Udbudsmateriale — Dataplatform til Roskilde Kommune

**Udstedt af:** Roskilde Kommune, Digitalisering & IT
**Dato:** Marts 2026
**Svarfrist:** 25. april 2026
**Kontakt:** udbud@roskilde.dk

*(English summary follows the Danish original — see section 8)*

---

## 1. Om Roskilde Kommune

Roskilde Kommune har ca. 92.000 borgere og beskæftiger ca. 5.800 medarbejdere fordelt på seks forvaltninger. IT og digitalisering varetages af en central afdeling med 24 medarbejdere.

---

## 2. Baggrund

Byrådet vedtog i 2024 en digitaliseringsstrategi med titlen *"Roskilde — en datadrevet kommune"*. Et centralt element i strategien er at samle kommunens data på tværs af fagsystemer, så ledere og politikere kan træffe beslutninger baseret på et fælles datagrundlag.

I dag er kommunens data spredt over syv primære fagsystemer med separate datavarehuse. Tværgående rapportering kræver manuel eksport og bearbejdning i Excel, hvilket er tidskrævende og fejlbehæftet.

**To tidligere projekter** med lignende ambitioner er ikke lykkedes:
- *Projekt DataBro (2020–2021):* Stoppet efter 14 måneder pga. scope creep og manglende ejerskab hos forvaltningerne.
- *Projekt Indsigt (2022–2023):* Leverede en BI-løsning til én forvaltning, men blev ikke rullet ud bredt. Leverandøren overskred budget med 40%.

Der er intern skepsis i organisationen. Denne gang ønsker vi en leverandør, der kan levere konkrete resultater i afgrænsede faser frem for at love et stort samlet løft.

---

## 3. Systemlandskab

| Fagsystem | Forvaltning | Leverandør | API |
|---|---|---|---|
| KMD Nexus | Social & Sundhed | KMD | REST (begrænset) |
| Acadre | Teknik & Miljø | Netcompany | SOAP |
| SD Løn | HR | Silkeborg Data | REST |
| SkoleIntra / Aula | Børn & Unge | UNI-C | REST |
| EG Sensum | Ældre & Handicap | EG | REST (delvis) |
| Opus Økonomi | Økonomi | KMD | REST |
| GIS-platform | Teknik & Miljø | Esri | REST |

Datakvaliteten varierer betydeligt på tværs af systemerne. Nogle systemer har ikke opdaterede data, og der er kendte inkonsekvenser i CPR-numre og adressedata.

---

## 4. Krav til løsningen

Vi søger en leverandør til at designe og implementere en dataplatform, der:

- Samler data fra ovenstående syv systemer i et centralt datalager
- Muliggør tværgående rapportering og analyse for ledere og politikere
- Leverer et selvbetjeningsværktøj, så fagkontorer selv kan trække rapporter uden IT-assistance
- Sikrer GDPR-compliance (herunder særligt følsomme personoplysninger i Social & Sundhed og Ældre & Handicap)
- Understøtter trinvis udrulning — vi ønsker at starte med ét eller to fagsystemer og udvide gradvist
- Dokumenterer datadefinitioner og transformationslogik, så kommunen ikke er afhængig af leverandøren for at forstå egne data

**Ikke i scope:**
- Udskiftning af fagsystemer
- Borgerrettede selvbetjeningsløsninger
- Realtidsintegration (batch er tilstrækkeligt i første fase)

---

## 5. Rammeaftale

Roskilde Kommune har en eksisterende rammeaftale med Consid. Dette udbud gennemføres inden for rammerne af denne aftale. Det betyder:
- Forenklet udbudsproces
- Forventet prismodel baseret på aftalte timepriser
- Kommunen forventer et fast-price tilbud på første fase

---

## 6. Evalueringskriterier

| Kriterium | Vægt |
|---|---|
| Løsningsdesign og arkitektur | 30% |
| Implementeringsplan (fasemodel, milepæle) | 25% |
| Pris (første fase, fast price) | 25% |
| Kompetencer og referencer fra tilsvarende projekter | 20% |

---

## 7. Krav til tilbuddet

Tilbuddet skal indeholde:

1. **Løsningsbeskrivelse** — arkitektur, teknologivalg, hosting
2. **Integrationsplan** — tilgang til de syv fagsystemer, herunder håndtering af SOAP og begrænsede API'er
3. **Faseplan** — hvilke systemer integreres hvornår, og hvad leveres i første fase
4. **Datakvalitetsstrategi** — hvordan håndteres kendte datakvalitetsproblemer
5. **Governance** — hvem ejer platformen på sigt, og hvordan sikres kommunens datakompetence
6. **Team og referencer** — nøgleroller og mindst to referencer fra offentlige kunder
7. **Økonomi** — fast pris på fase 1, estimat på samlede TCO over 3 år

---

## 8. English summary

Roskilde Municipality (92,000 citizens, ~5,800 employees) is seeking a vendor to design and implement a data platform consolidating data from seven case management systems. The project is part of a "data-driven municipality" strategy adopted in 2024.

**Key facts for vendors:**
- Two previous similar projects failed (scope creep, vendor overcommitment, budget overrun)
- Strong internal scepticism — the approach must demonstrate early, concrete results
- A framework agreement with Consid is already in place; this is effectively a direct award within that agreement
- The municipality expects a fixed-price offer for phase 1
- GDPR compliance is critical — the data includes sensitive personal data (social care, elderly care)
- The timeline is politically motivated: the mayor wants visible results before the 2027 local elections
- IT department capacity is limited: 24 staff, significant ongoing operational workload

The evaluation will prioritise a credible, phased delivery approach over an ambitious all-at-once vision. Vendors who overpromise will be viewed negatively given the failure history.

---

*Spørgsmål sendes til udbud@roskilde.dk senest den 31. marts 2026.*
