# Digital Twin degli Organici — Ministero dell'Istruzione e del Merito

**Concept esecutivo** di un Digital Twin della rete scolastica per la **pianificazione del fabbisogno di docenti e personale ATA**.

> Predisposto per la **Direzione generale per l'innovazione digitale, la semplificazione e la statistica** (Dott. D'Amico).

---

## Obiettivo

Simulare il fabbisogno di docenti e personale ATA in funzione di **iscrizioni, pensionamenti, mobilità e nuovi indirizzi di studio**, ottimizzando la distribuzione delle risorse per territorio, grado e classe di concorso.

Il Digital Twin trasforma la programmazione annuale dell'organico da esercizio *reattivo* a decisione *anticipata, misurabile e ottimizzata*.

## Contenuto del repository

| File | Descrizione |
|------|-------------|
| [`index.html`](index.html) | Dashboard interattiva (file unico, self-contained). Emblema e simulatore sono incorporati: si apre in qualsiasi browser. |
| [`docs/fonti-dati.md`](docs/fonti-dati.md) | Note di metodo: banche dati aperte e archivi amministrativi che alimentano il modello. |
| [`docs/metodologia.md`](docs/metodologia.md) | Note di metodo: motori di proiezione (iscrizioni, pensionamenti, allocazione). |

## Come consultare il concept

La dashboard è [`index.html`](index.html): file unico, emblema e loghi incorporati. Chi ha accesso al repository:

1. Apre [`index.html`](index.html) su GitHub → *Download raw file* → doppio clic sul file scaricato.
2. Oppure clona il repository e apre `index.html` nel browser.

Le note di metodo sono in [`docs/`](docs/).

## Struttura del documento (7 moduli)

1. **Sintesi esecutiva** — visione, sfida demografica, valore per il Ministero.
2. **Le leve del fabbisogno** — iscrizioni, pensionamenti, mobilità, nuovi indirizzi, sostegno, italiano L2.
3. **Banche dati aperte** — fonti open + archivi interni, feature store.
4. **Architettura** — dai dati alla decisione in quattro livelli.
5. **Simulatore organici** — cruscotto interattivo con proiezione 2025–2035.
6. **Ottimizzazione & allocazione** — distribuzione ottima dei posti.
7. **Governance & roadmap** — implementazione, privacy/GDPR, benefici.

## Dati di riferimento (a.s. 2024/2025, fonte MIM — Organico di Fatto)

- **7.073.587** studenti scuola statale in **362.115** classi (di cui **331.124** con disabilità)
- **889.836** posti docente = **684.583** comuni + **205.253** sostegno
- **196.495** posti ATA (+ ~7.936 DSGA); **7.461** istituzioni scolastiche
- Trend: **−134.000** studenti nel 2025/26; fino a **−1,5 mln** alunni e **−130.000** cattedre entro il 2035

## Nota

Le cifre puntuali usate nelle simulazioni hanno **finalità illustrativa** e non sostituiscono le procedure ufficiali di determinazione degli organici. In produzione i motori sono calibrati sui microdati ufficiali e restituiscono bande di incertezza.

---

*Concept v1.0 — luglio 2026*
