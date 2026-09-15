# Banche dati — Digital Twin degli Organici

Mappa delle fonti che alimentano il Digital Twin. Priorità ai **dati aperti**; gli archivi amministrativi interni sono usati in ambiente controllato e in forma pseudonimizzata (conformità GDPR).

## 1. Fonti aperte primarie

### Portale Unico dei Dati della Scuola — `dati.istruzione.it`
Cuore dei dati open del MIM. Licenza **IODL 2.0**; formati **CSV / JSON / RDF / XML**; **endpoint SPARQL**.

Dataset rilevanti:
- Anagrafe scuole e sedi (codici meccanografici, tipologie, geolocalizzazione)
- Studenti per grado, anno di corso, indirizzo di studio
- Docenti a tempo indeterminato per grado, tipo posto, genere, fascia d'età
- Docenti supplenti per tipo supplenza, contratto, fascia d'età
- ATA titolari e supplenti per profilo (collaboratori scolastici, assistenti amministrativi/tecnici)
- Edilizia scolastica; Sistema Nazionale di Valutazione (SNV)

### ISTAT — fondamento delle proiezioni di iscrizioni
- Previsioni della popolazione per età, sesso, regione
- Serie storiche delle nascite (natalità)
- Saldi migratori interni ed esteri
- Rilevazione sulle forze di lavoro (contesto socio-economico)
- Accesso: API, SDMX, `dati.istat.it`

### INPS — motore delle uscite per pensionamento
- Requisiti pensionistici vigenti (Fornero, Quota 103, APE sociale, pensione anticipata)
- Osservatorio pensioni e cessazioni del comparto scuola
- Base per la maturazione dei diritti per coorte

## 2. Fonti aperte di contesto e benchmark

| Fonte | Uso |
|-------|-----|
| **Eurostat / OCSE** (UOE, Education at a Glance) | Rapporto alunni/docente, spesa per studente, benchmark europei |
| **INVALSI** | Esiti di apprendimento e contesto (qualità, equità) |
| **ANPR / Ministero dell'Interno** | Popolazione residente per comune (bacini d'utenza, dimensionamento) |
| **dati.gov.it** | Catalogo nazionale open data (scoperta e armonizzazione metadati) |

## 3. Archivi amministrativi interni (accesso riservato)

Portano la **granularità individuale** necessaria alle simulazioni fini:

- **SIDI** — Sistema Informativo dell'Istruzione
- **Anagrafe Nazionale degli Studenti**
- Procedure di **organico di diritto/fatto**
- Procedure di **mobilità** (trasferimenti, passaggi di ruolo/profilo)
- **Reclutamento** — GaE, GPS, concorsi
- **NoiPA** (MEF) — anagrafica retributiva ed età del personale

## 4. Chiavi di integrazione (feature store)

- **Temporale:** anno scolastico (aggancio demografia e contesto macro)
- **Geografica:** comune → provincia → regione → macro-area
- **Organizzativa:** codice meccanografico dell'istituzione scolastica
- **Professionale:** profilo (docente/ATA), tipo posto, classe di concorso

Tutte le fonti vengono agganciate una volta sola nel feature store e riusate da tutti i moduli del Digital Twin.
