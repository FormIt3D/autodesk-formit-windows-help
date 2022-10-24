---
description: >-
  Avviare un workflow BIM valutando le prestazioni degli elementi dall'inizio del processo di progettazione.
---

# Analisi solare + Analisi energetica

![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## Analisi energetica in FormIt

È possibile analizzare il modello di edificio per l'efficienza energetica nelle prime fasi del processo di progettazione.

[Visualizzazione dei progetti di Insight](https://gbs.autodesk.com/OneEnergy/Insight)

## Analisi energetica con Insight

Con un abbonamento a **FormIt Pro** tramite [AEC Collection](https://www.autodesk.com/collections/architecture-engineering-construction/overview), è possibile accedere ad Analisi energetica con **Insight:**

* Analizzare i modelli di progettazione nelle fasi iniziali con il motore di analisi di Green Building Studio
* Connettersi ad una vista della dashboard dei risultati dell'analisi per confrontare le opzioni per il progetto
* Regolare i widget del fattore di Analisi energetica, ad esempio rapporto finestra-muro, orientamento dell'edificio e altri
* Riepilogare l'impatto energetico dell'edificio con un singolo numero calcolato come costo per area finale
* Salvare i risultati di Analisi energetica per una revisione futura con clienti e altri soggetti coinvolti

## Novità di FormIt + Insight <a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Miglioramenti all'affidabilità di Insight** <a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) ora verifica la presenza di eventuali problemi comuni nel modello prima di avviare le esecuzioni di Insight e corregge gli errori comuni di Insight per un'esperienza più affidabile.
* FormIt 2021 migliora anche l'affidabilità della connessione FormIt + Insight, risolvendo molti errori noti e migliorando le percentuali di successo delle esecuzioni.

## Introduzione <a href="#insight-getting-started" id="insight-getting-started"></a>

### **Funzionamento** <a href="#how-it-works" id="how-it-works"></a>

* Analisi energetica di Insight carica i dati del modello di FormIt ed esegue diverse centinaia di analisi nel cloud per determinare i vari punteggi energetici.
* Analisi energetica utilizza Revit per analizzare il modello, quindi proprio come quando si inviano i dati di FormIt a Revit, sarà necessario [verificare che il modello di FormIt sia a tenuta ermetica e manifold](https://formit.autodesk.com/blog/post/repairing-solid-models).

### **Preparazione del modello di FormIt** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Insight utilizzerà qualsiasi geometria visibile nel disegno di FormIt.
  * Verificare che la struttura esterna dell'edificio che si desidera analizzare sia l'unica geometria visibile.
  * Posizionare la geometria di supporto, ad esempio il contesto, gli arredi e gli elementi della planimetria, su un [layer](../tool-library/layers.md) separato e disattivare il layer.
* Insight funziona meglio con un semplice modello di edificio solido.
  * Assicurarsi che la massa dell'edificio sia [solida e a tenuta ermetica](https://formit.autodesk.com/blog/post/repairing-solid-models).
  * Se il progetto dell'edificio contiene già aperture per finestre e porte, è consigliabile creare una nuova massa senza aperture specificamente per Analisi energetica e nascondere la versione più dettagliata utilizzando i layer.
* Alla massa dell'edificio semplice devono essere stati applicati [livelli](../tool-library/levels-and-area.md).
* Per il modello di FormIt deve essere stata impostata una [posizione](../tool-library/setting-location.md).

![](../.gitbook/assets/insight.png)

### **Avvio di Analisi energetica** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* Ricercare il pulsante Analisi energetica sulla barra degli strumenti.

![](../.gitbook/assets/generate\_insight.png)

* Fare clic su Genera informazioni approfondite per avviare il processo.
* In questo modo verranno caricati i dati del modello visibili e verranno eseguite diverse centinaia di simulazioni nel cloud.
* Al termine, nella parte superiore dello schermo verrà visualizzato un messaggio e il menu verrà aggiornato per indicare che è possibile visualizzare nuove informazioni approfondite.
  * Fare clic su Visualizza informazioni approfondite per visualizzare l'analisi nel browser Web.
  * Tutte le informazioni approfondite sono disponibili anche in [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight).

## Risoluzione dei problemi <a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **Errori comuni** <a href="#common-errors" id="common-errors"></a>

* Impossibile creare il progetto di Insight. Riprovare in un secondo momento.
  * Accedere alla [dashboard di Green Building Studio](https://gbs.autodesk.com/GBS/Project), quindi riavviare FormIt
    * Se non si riesce ad accedere o se viene visualizzata una pagina di accesso negato, potrebbe essere necessario [acquistare un abbonamento a Green Building Studio](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/ENU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html).
  * Verificare che il modello sia [solido e a tenuta ermetica](https://formit.autodesk.com/blog/post/repairing-solid-models).
  * Verificare la presenza di eventuali problemi relativi ai servizi di FormIt in [Autodesk Health Dashboard](https://health.autodesk.com/).
* Per verificare se le esecuzioni di Analisi energetica in Green Building Studio sono state corrette per questo progetto, consultare la [dashboard di Green Building Studio](https://gbs.autodesk.com/GBS/Project).
  * Il progetto più recente dovrebbe essere visualizzato nella parte superiore dell'elenco e dovrebbe visualizzare 248 esecuzioni.
  * Se visualizza 0 esecuzioni, [comunicarlo nel forum di FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142). Autodesk presterà l'assistenza necessaria per risolvere il problema.

### **Registri dettagliati** <a href="#detailed-logs" id="detailed-logs"></a>

* FormIt per il Web fornisce ulteriori dettagli quando Analisi energetica non riesce:
  * Accedere a [FormIt per il Web](https://formit.autodesk.com/app).
  * Aprire il modello che presenta problemi con Analisi energetica.
  * Esegui Analisi energetica.
  * Aprire Strumenti per sviluppatori (premere F12 in Google Chrome o Firefox).
  * Individuare la scheda Console.
  * Copiare o eseguire screenshot di eventuali errori e [segnalarli nei forum di FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142).

## Analisi solare

Con un abbonamento a **FormIt Pro** tramite [AEC Collection](https://www.autodesk.com/collections/architecture-engineering-construction/overview), è possibile visualizzare l'impatto del sole sull'edificio:

* Specificare le superfici pertinenti da analizzare per l'impatto solare
* Visualizzare i risultati in pochi secondi all'interno dell'area di disegno dell'app
* Posizionare il cursore del mouse su un punto di input per visualizzare i valori calcolati specifici dell'impatto solare
* Scegliere di visualizzare i risultati come studio mensile sulle vetrate o come studio di fattibilità annuale sui pannelli solari

Sono fornite ulteriori informazioni su [Analisi solare](../tool-library/solar-analysis.md) in FormIt Pro.
