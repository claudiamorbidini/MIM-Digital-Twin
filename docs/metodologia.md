# Metodologia — note sintetiche

I motori del Digital Twin combinano metodi statistici classici e machine learning. Ogni proiezione è accompagnata da **bande di incertezza**; il cruscotto mostra lo scenario centrale con l'intervallo.

## Motore A — Proiezione delle iscrizioni (metodo delle coorti)

Gli alunni dei prossimi anni **sono in larga parte già nati**. Il modello fa avanzare ogni coorte di età di anno in anno (*survival ratio*), applicando:

- tassi di passaggio tra gradi scolastici;
- ripetenze e abbandoni;
- saldi migratori per territorio.

Ne risulta una previsione robusta a breve-medio termine (fino a ~6 anni la coorte è osservata), che **segue popolazioni reali** invece di estrapolare un trend.

**Output:** alunni per grado, indirizzo e territorio, 2025–2035.

## Motore B — Uscite per pensionamento

Combina la struttura per **età e anzianità** del personale (NoiPA) con le **regole previdenziali** vigenti (INPS):

1. calcolo della maturazione dei requisiti per coorte;
2. ipotesi di **tasso di adesione** (differenziato per profilo/territorio);
3. stima delle cessazioni attese per anno.

**Output:** cessazioni attese per profilo, classe di concorso e territorio → base del **fabbisogno di reclutamento**.

## Motore C — Allocazione ottima

Problema di ottimizzazione con vincoli. Funzione obiettivo: **minimizzare la somma di esuberi e carenze** su tutti i territori e le classi di concorso.

Vincoli:
- tetto complessivo dei posti (legge di bilancio, intesa MEF);
- numerosità minime/massime delle classi (dimensionamento, D.I. 127/2023);
- salvaguardia scuole di piccole isole, montagna, aree interne;
- continuità didattica e diritti del personale di ruolo.

**Output:** proposta di distribuzione dei posti per provincia e classe di concorso.

## Equazione sintetica dell'organico

Per territorio *t* e anno *y*:

```
Posti(t,y) = Comuni(iscrizioni, alunni/classe)
           + Sostegno(alunni con disabilità)
           + Potenziamento
           + Italiano L2

Reclutamento(t,y) = Uscite(pensionamenti)
                  + ΔPosti netti
                  − rientri da mobilità
```

## Modello dimostrativo nel concept (`index.html`)

Il simulatore del Modulo 5 usa coefficienti che **replicano ordini di grandezza reali** (base a.s. 2024/25) ma è a scopo illustrativo:

- `studenti[y] = 7.073.587 × (1 + trend)^(y−2024)`
- `classi[y] = studenti[y] / (alunni per classe)`
- `posti_comuni[y] = classi[y] × (684.583 / 362.115)`
- `posti_sostegno[y] = studenti[y] × quota_disabilità × (205.253 / 331.124)`
- `ATA[y] = 196.495 × (0,55 + 0,45 × classi[y]/classi_base)`
- `reclutamento[y] = posti[y−1] × turnover + Δposti`

In produzione questi coefficienti sono stimati sui microdati ufficiali.
