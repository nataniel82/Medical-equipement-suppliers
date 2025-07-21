# Analisi e Previsione sui Fornitori di Servizi Sanitari USA

Questo progetto analizza un set di dati pubblico dei "Centers for Medicare & Medicaid Services" (CMS) per scoprire pattern nella distribuzione e nelle pratiche dei fornitori di servizi sanitari negli Stati Uniti. L'obiettivo finale è costruire un modello di machine learning in grado di prevedere se un fornitore accetterà o meno l'assegnazione ("assignment"), una domanda chiave per l'accessibilità dei pazienti alle cure.

![Mappa Dati Fornitori](https://storage.googleapis.com/dall-e-images/pYsufAN1RpaEGv7008npcjh8KHm1%2F342044bb-897f-4bfa-8f61-4494336df893.png)

## Motivazione

Lo scopo di questo progetto è applicare il processo di data science CRISP-DM per rispondere a domande concrete partendo da dati grezzi. Le domande di interesse erano:
1.  Dove si concentrano geograficamente i fornitori di servizi sanitari negli USA?
2.  Qual è la proporzione di fornitori che accettano l'assegnazione?
3.  È possibile costruire un modello predittivo affidabile per questa caratteristica?

Questo progetto dimostra un flusso di lavoro end-to-end: dall'esplorazione e pulizia dei dati, alla modellazione, fino alla valutazione e interpretazione dei risultati in uno scenario pratico.

## Installazione

Per eseguire questo progetto localmente, clona il repository e installa le dipendenze necessarie. È consigliabile creare un ambiente virtuale per evitare conflitti tra le librerie.

```bash
# Clona il repository
git clone https://github.com/nataniel82/Medical-equipement-suppliers.git

cd Medical-equipement-suppliers

# (Opzionale ma consigliato) Crea e attiva un ambiente virtuale
python -m venv venv
source venv/bin/activate  # Su Windows: venv\Scripts\activate

# Installa le dipendenze
pip install -r requirements.txt
```

## Contenuti del Repository

*   **`Medical_Supplier_Analysis.ipynb`**: Il notebook Jupyter contenente tutto il codice Python, l'analisi esplorativa dei dati (EDA), la pulizia dei dati, l'addestramento del modello e la valutazione.
*   **`README.md`**: Questo file, che fornisce una panoramica del progetto.
*   **`requirements.txt`**: Un file che elenca tutte le librerie Python necessarie per riprodurre l'ambiente di analisi.
*   **`blogpost.md`**: Una copia dell'articolo del blog che riassume i risultati in modo non tecnico, pubblicato al seguente indirizzo: https://medium.com/@gcapanna/will-your-next-medical-supplier-accept-your-insurance-the-data-might-have-the-answer-5696ecd5ceee


## Riepilogo dell'Analisi

L'analisi esplorativa ha rivelato che la maggior parte dei fornitori si concentra in stati ad alta densità di popolazione come California, Texas e Florida. Sorprendentemente, il numero di fornitori che accettano l'assegnazione è quasi identico a quelli che non la accettano (circa 48% vs 52%).

Per la fase di modellazione, è stato addestrato un `RandomForestClassifier` per prevedere la variabile `acceptsassignement`. Dopo un attento processo di pulizia e preparazione dei dati (gestione dei valori mancanti e one-hot encoding delle variabili categoriche), il modello ha raggiunto i seguenti risultati sul set di test:

*   **Accuratezza Generale:** ~74%
*   **Performance (F1-Score):** Un F1-score bilanciato sia per la classe `True` che `False`, indicando che il modello non è sbilanciato verso una singola previsione.

Infine, il modello è stato applicato a uno scenario ipotetico, prevedendo correttamente la probabile politica di un nuovo fornitore sulla base delle sue caratteristiche.

## Utilizzo

Per esplorare l'analisi, apri il file `Medical_Supplier_Analysis.ipynb` in un ambiente Jupyter (come Jupyter Lab o Visual Studio Code). Puoi eseguire le celle in sequenza per replicare l'intero processo, dai grafici iniziali fino alla previsione finale.

## Librerie Utilizzate

*   Pandas
*   NumPy
*   Scikit-learn
*   Matplotlib
*   Seaborn

## Riconoscimenti

I dati utilizzati in questo progetto sono stati forniti pubblicamente dai [Centers for Medicare & Medicaid Services (CMS)](https://data.cms.gov/provider-data/). Si ringrazia l'ente per la sua trasparenza e per aver reso disponibili queste preziose informazioni.
