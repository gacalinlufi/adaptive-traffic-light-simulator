SEMAFORI INTELLIGENTI — FASE 4 (AI SPERIMENTALE)

AVVIO
1. Estrai la cartella ZIP.
2. Apri index.html con Chrome o Edge.
3. Non serve installare software né collegarsi a un servizio esterno.

MODALITÀ
- Tempi fissi: verde di 12 secondi.
- Adattivo: regola predefinita che allunga il verde in funzione della coda della direzione.
- AI — Q-learning: agente di apprendimento per rinforzo che sceglie direzione e durata del verde (6, 10, 14, 18 o 22 secondi).

COME IMPARA
Il sistema discretizza le code nelle due direzioni in quattro livelli (0, 1-3, 4-7, 8 o più auto) e considera anche quale direzione è stata servita per ultima. Per ogni stato prova una delle 10 combinazioni direzione/durata. Accumula un premio negativo proporzionale alle code e un premio positivo per le auto che escono, quindi aggiorna i valori Q per orientare le decisioni successive.

L'agente usa epsilon-greedy: all'inizio esplora il 25% circa delle decisioni; la percentuale cala fino al 5%. Nelle prime prove può quindi comportarsi peggio delle altre modalità. L'apprendimento richiede molte decisioni e non garantisce di trovare la strategia ottimale.

CONFRONTO PIÙ EQUO
Ogni volta che premi Azzera, la sequenza di arrivi riparte dallo stesso seme pseudo-casuale. Con intensità e velocità identiche puoi confrontare più facilmente le modalità. Le decisioni AI e il modello appreso rimangono invece memorizzati tra gli azzeramenti.

Il modello viene salvato in localStorage se il browser consente la memorizzazione per il file locale. Se questa funzionalità è bloccata, l'apprendimento resta disponibile fino a quando la pagina rimane aperta. Il pulsante “Azzera apprendimento AI” riparte con una tabella Q vuota.

NOTA
È un prototipo educativo di Q-learning tabellare, non una rete neurale né un sistema pronto per controllare semafori reali. La simulazione semplifica il comportamento del traffico: i risultati sono indicativi e vanno confrontati su molte prove.
