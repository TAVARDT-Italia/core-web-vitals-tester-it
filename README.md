# Test di Core Web Vitals e Prestazioni Web

[![Test Core Web Vitals](https://img.shields.io/badge/TAVARDT-Core%20Web%20Vitals-5b3cf5.svg)](https://tools.tavardt.com/it/test-core-web-vitals-google/)
[![Giurisdizione](https://img.shields.io/badge/Giurisdizione-Italia-00C853.svg)](https://ag.tavardt.com/it/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)

Verifica tecnica di latenza TTFB, compressione, elementi che bloccano il rendering e stabilita visuale.

Sviluppato e mantenuto dalla divisione di ingegneria di prestazione web di **[TAVARDT Italia](https://ag.tavardt.com/it/)**.

---

## Funzionalita di Verifica Core Web Vitals

* **Misurazione della Latenza e TTFB**: Valutazione del tempo di prima risposta del server e dei tempi di connessione iniziale.
* **Rilevamento Risorse che Bloccano il Rendering**: Analisi di script sincroni e fogli di stile nell'intestazione HTML.
* **Controllo della Stabilita Visiva (CLS)**: Ispezione degli attributi di dimensione e caricamento asincrono delle immagini.
* **Verifica della Compressione HTTP**: Controllo del supporto di codifica Brotli e Gzip nelle risposte HTTP.
* **Punteggio di Prestazione W3C**: Valutazione da 0 a 100 con passaggi tecnici di ottimizzazione.

---

## Installazione ed Esecuzione

Richiede Python 3.8 o superiore, operando esclusivamente con la libreria standard.

```bash
git clone https://github.com/TAVARDT-Italia/core-web-vitals-tester-it.git
cd core-web-vitals-tester-it
python cwv_tester.py https://azienda.it
```

Per generare il rapporto in formato strutturato JSON:

```bash
python cwv_tester.py https://azienda.it --json
```

---

## Diagnostica Completa sul Web

Per audit dettagliati di velocita di caricamento:

* **[Test di Core Web Vitals Ufficiale](https://tools.tavardt.com/it/test-core-web-vitals-google/)**
* **[Portale Aziendale TAVARDT Italia](https://ag.tavardt.com/it/)**

---

## Consulenza in Ottimizzazione delle Prestazioni Web

Per progetti di accelerazione e architettura web conformi a Standard W3C e Linee Guida di Prestazione Digitale, contattare il team di **[TAVARDT Italia](https://ag.tavardt.com/it/contatti/)**.
