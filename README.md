# Gioco Reale di Ur

[![Versione](https://img.shields.io/badge/versione-1.6-blue)](#versioni)
[![Licenza: AGPL v3](https://img.shields.io/badge/licenza-AGPL--3.0-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![GitHub Pages](https://img.shields.io/badge/demo-GitHub%20Pages-222?logo=github)](#pubblicazione-su-github-pages)
[![HTML5](https://img.shields.io/badge/HTML5-single%20file-E34F26?logo=html5&logoColor=white)](index.html)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES2020-F7DF1E?logo=javascript&logoColor=black)](index.html)
[![Three.js](https://img.shields.io/badge/Three.js-r128-000?logo=threedotjs&logoColor=white)](https://threejs.org/)
[![Lingua](https://img.shields.io/badge/lingua-italiano%20%7C%20inglese-green)](#)

Versione per browser del Gioco Reale di Ur, il gioco da tavolo diffuso in Mesopotamia dal III millennio a.C. e documentato dalle tavole della necropoli reale di Ur. Il progetto è una singola pagina HTML, senza fase di build e senza installazione.

## Caratteristiche

- **Due set di regole ricostruite**: Finkel (4 dadi tetraedrici) e Bell (3 dadi, con posta e banco). Varianti opzionali: regola del rimbalzo e uscita con tiro di quattro punti (Bell).
- **Pedine a testa**: 7 (regole moderne) oppure 5 (tavoletta analizzata da Finkel).
- **Avversario**: computer (euristica basata sulle probabilità di cattura) oppure due giocatori sullo stesso schermo.
- **Tavoliere** ispirato agli esemplari del British Museum, disegnato in SVG, con i simboli delle caselle.
- **Dadi tetraedrici in 3D** (Three.js), con i vertici marcati; i dadi diventano rossi quando tocca a Rosso. Se WebGL o Three.js non sono disponibili, la pagina usa dadi SVG 2D.
- **Animazioni** del movimento delle pedine casella per casella e del ritorno delle pedine catturate. Con «riduci movimento» attivo nel sistema operativo, le animazioni sono disattivate.
- **Audio** sintetizzato con Web Audio, senza file esterni: effetti sonori (attivi di default) e colonna sonora d'ispirazione mesopotamica (disattivata di default). La scelta è salvata nel browser.
- **Regole illustrate**: tutorial animato per Finkel (15 schermate) e Bell (17), con scenari verificati dal motore di gioco.
- **Storia**: sequenza a titoli cinematografici sulla storia del gioco, tratta dalla voce «Gioco reale di Ur» di Wikipedia, avviabile dal pulsante in alto.
- **Lingua**: interfaccia in italiano e inglese, con selettore IT/EN nella pagina. La scelta è salvata nel browser; al primo accesso si usa la lingua del browser.
- Interfaccia adattabile a schermi piccoli, con tema chiaro e scuro automatico, e navigazione da tastiera sulle pedine.

## Come si gioca

Ogni giocatore percorre quattordici caselle: quattro nella propria corsia, otto nella corsia centrale in comune, due nella corsia finale. Le rosette sono alle caselle 4, 8 e 14. Vince chi porta in salvo per primo tutte le proprie pedine.

Le regole complete, per ciascuna versione, sono nel pannello «Regole» della pagina e nel tutorial «Regole illustrate».

## Avvio

Apri `index.html` in un browser moderno. Non servono server né dipendenze da installare.

Al caricamento la pagina scarica da CDN, se raggiungibili:

- Three.js r128 da `cdnjs.cloudflare.com` (dadi 3D; senza, vengono usati i dadi 2D);
- i caratteri da Google Fonts (senza, vengono usati i caratteri di sistema).

Il gioco funziona anche senza questi due caricamenti.

## Pubblicazione su GitHub Pages

1. Copia `index.html` nella radice del repository.
2. In *Settings → Pages* scegli il branch (ad esempio `main`) e la cartella `/ (root)`.
3. La pagina sarà disponibile all'indirizzo `https://<utente>.github.io/<repository>/`.

## Struttura

Tutto il codice è in `index.html`, in tre parti:

| Parte | Contenuto |
|---|---|
| Motore | Logica pura, senza accesso al DOM: stato, lanci, generazione delle mosse, regole Finkel e Bell, scelta della CPU. |
| Interfaccia | Tavoliere SVG, pedine, dadi 3D/2D, animazioni, pannelli e impostazioni. |
| Contenuti | Tutorial «Regole illustrate», audio procedurale e storia. |

Il motore è stato verificato con simulazioni di partite complete e con scenari per le situazioni particolari (cattura, rosetta centrale occupata, uscita esatta, rimbalzo, posta di Bell).

## Fedeltà storica

Le regole originali sono sconosciute: tutte le versioni di gioco sono ricostruzioni. In particolare:

- le fonti riportano cinque o sette pedine; il numero è selezionabile;
- nella ricostruzione citata da Wikipedia chi salta una rosetta paga una posta e la pedina sulla rosetta non si cattura; qui valgono le regole moderne (nuovo lancio per Finkel, posta pagata dall'avversario per Bell);
- il percorso più lungo di Murray, le varianti a 16 caselle e quella allungata non sono incluse.

## Versioni

| Versione | Contenuto |
|---|---|
| 1.0 | Gioco con regole Finkel e Bell, tavoliere SVG, dadi 2D, giocatore contro computer o due giocatori. |
| 1.1 | Tavoliere restaurato sul modello degli esemplari del British Museum; dadi tetraedrici 3D. |
| 1.2 | Vertici dei dadi come piccole piramidi bianche o nere. |
| 1.3 | «Regole illustrate» per Finkel e Bell. |
| 1.4 | Animazione delle pedine, dadi rossi per Rosso, effetti sonori, colonna sonora, storia, impostazione di 5 o 7 pedine. |
| 1.5 | Layout compatto: tavoliere e comandi di lancio nella stessa schermata su display a partire da 1000 px di larghezza. |
| 1.6 | Interfaccia in italiano e inglese con selettore della lingua. |

## Fonti

- Voce «Gioco reale di Ur», Wikipedia.
- Regole ricostruite da Irving Finkel (British Museum) e da Robert C. Bell.

## Licenza

Copyright © 2026 Alessandro Valli.

Questo programma è software libero: puoi ridistribuirlo e modificarlo secondo i termini della GNU Affero General Public License, versione 3 o successiva, pubblicata dalla Free Software Foundation. In particolare, se fornisci una versione modificata come servizio in rete, devi renderne disponibile il codice sorgente agli utenti.

Il programma è distribuito senza alcuna garanzia. Il testo completo è in [LICENSE](LICENSE) e su <https://www.gnu.org/licenses/agpl-3.0.html>.

Three.js è distribuito con licenza MIT.
