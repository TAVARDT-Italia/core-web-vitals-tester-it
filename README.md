# Verificatore di Core Web Vitals e Velocita della Pagina

[![Test Core Web Vitals](https://img.shields.io/badge/TAVARDT-Core%20Web%20Vitals-5b3cf5.svg)](https://tools.tavardt.com/it/test-core-web-vitals-google/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Audit di latenza TTFB, compressione HTTP, risorse che bloccano il rendering e stabilita visiva CLS.

Sviluppato e mantenuto dalla divisione di ingegneria di prestazioni web e standard di velocita di **TAVARDT**.

***

## Vettori di Rischio e Impatto Operativo nelle Prestazioni Web

Elevati tempi di risposta del server e file bloccanti penalizzano il ranking sui motori di ricerca secondo i parametri Page Experience. Quando un portale presenta un TTFB prolungato ed elementi non compressi, il tasso di abbandono degli utenti cresce rapidamente.

Elementi multimediali privi di dimensioni esplicite generano continui sbalzi visivi che compromettono il parametro Cumulative Layout Shift. Il monitoraggio continuo protegge il traffico organico garantendo interazioni fluide e veloci.

***

## Funzionalita Centrali di Audit Tecnico

* **Misurazione di Precisione del TTFB**: Calcolo della latenza iniziale tramite timer ad alta risoluzione, evidenziando ritardi superiori a 600 ms e criticita oltre 1200 ms.
* **Verifica Compressione Dati HTTP**: Ispezione dell erogazione tramite algoritmi Brotli o Gzip, con penalita di 15 punti per risposte non compresse.
* **Rilevamento Risorse Bloccanti**: Identificazione di fogli di stile CSS e script JS sincroni nel `<head>` privi di attributi async, defer o module.
* **Audit di Stabilita Visiva (CLS)**: Verifica dei tag `<img>` privi di dimensioni esplicite di larghezza e altezza per eliminare slittamenti di layout.
* **Analisi Resource Hints**: Riconoscimento delle direttive preconnect e preload impiegate per velocizzare il caricamento di risorse critiche.
* **Indice di Prestazioni W3C**: Valutazione numerica da 0 a 100 che classifica la pagina in GOOD (FAST), NEEDS IMPROVEMENT o POOR (SLOW).

***

## Installazione ed Esecuzione

Richiede Python 3.8 o superiore senza dipendenze esterne.

```bash
git clone https://github.com/TAVARDT-Italia/core-web-vitals-tester-it.git
cd core-web-vitals-tester-it
python cwv_tester.py https://azienda.it
```

Per produrre l output in formato JSON strutturato in pipeline automatiche:

```bash
python cwv_tester.py https://azienda.it -j
```

***

## Domande Frequenti (FAQ Tecnico)

### 1. In che modo un Time to First Byte (TTFB) elevato influisce sui Core Web Vitals?
Un TTFB eccessivo ritarda l arrivo del documento HTML primario, rallentando la misurazione di LCP e l elaborazione delle risorse figlie. Se la risposta del server eccede i 600 millisecondi, il sistema applica una penalita indicando colli di bottiglia nel caching.

### 2. Per quale motivo script e stili sincroni nel head ritardano il rendering?
File privi di gestione asincrona bloccano il parser del browser nella generazione del DOM finche non risultano scaricati ed eseguiti. L auditor identifica risorse senza async, defer o module per suggerirne la corretta de-prioritizzazione.

### 3. Come incide l assenza di larghezza e altezza sulle immagini nel Cumulative Layout Shift?
Senza dimensioni dichiarate nell HTML, il browser non e in grado di riservare in anticipo lo spazio visivo destinato all immagine. Cio genera improvvisi slittamenti dei blocchi di testo che abbattono il punteggio di stabilita visiva dell utente.

### 4. Qual e l importanza operativa della compressione HTTP Brotli o Gzip?
La compressione dei dati riduce fino al settanta per cento la dimensione del payload HTML trasferito tramite connessione di rete. L assenza di compressione spreca ampiezza di banda e comporta una decurtazione diretta nella valutazione di velocita.

### 5. In quale misura i resource hints come preconnect e preload ottimizzano il caricamento?
Le istruzioni preconnect e preload avviano anticipatamente handshake DNS e TLS verso host remoti e font ad alta priorita. Il validatore ne verifica l impiego per confermare la corretta gerarchizzazione delle richieste di rete.

***

## Consulenza in Prestazioni Web e Ottimizzazione di Velocita

Per architetture web ad alte prestazioni e conformita agli standard W3C, consultare gli specialisti di **TAVARDT**.

***

## Collegamenti Utili

* **Portale Aziendale:** https://ag.tavardt.com/it/
* **Suite di Diagnostica:** https://tools.tavardt.com/it/
* **Contatto Tecnico:** https://ag.tavardt.com/it/contatto/

***

### Licenza
Distribuito con Licenza MIT. Consultare il file LICENSE per i dettagli completi.

***

© 2026 TAVARDT. Tutti i diritti riservati.
