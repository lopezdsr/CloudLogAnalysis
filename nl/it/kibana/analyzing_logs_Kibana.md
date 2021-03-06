---

copyright:
  years: 2017

lastupdated: "2017-07-19"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}

# Analisi log avanzata con Kibana
{:#analyzing_logs_Kibana}

In {{site.data.keyword.Bluemix}}, puoi utilizzare Kibana 5.1, una piattaforma di analisi e visualizzazione open source, per monitorare, ricercare, analizzare e visualizzare i tuoi dati in una varietà di grafici, ad esempio, diagrammi e tabelle. Utilizza Kibana per eseguire attività di analisi avanzate.
{:shortdesc}

Kibana è un'interfaccia basata su browser in cui puoi analizzare i dati interattivamente e personalizzare i dashboard che potrai quindi utilizzare per analizzare i dati di log ed eseguire attività di gestione avanzate. Per ulteriori informazioni, vedi la [Kibana User Guide ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno")](https://www.elastic.co/guide/en/kibana/5.1/index.html "Icona link esterno"){: new_window}.

I dati visualizzati da una pagina Kibana sono vincolati da una ricerca. La serie di dati predefinita è definita dal modello di indice preconfigurato. Per filtrare le informazioni, puoi aggiungere nuove query di ricerca e applicare i filtri alla serie di dati predefinita. Puoi quindi salvare la ricerca per riutilizzi futuri. 

Kibana include diverse pagine che puoi utilizzare per analizzare i tuoi log:

| Pagina Kibana | Descrizione |
|-------------|-------------|
| Rileva | Utilizza questa pagina per definire le ricerche e per analizzare i tuoi log interattivamente tramite una tabella e un istogramma. |
| Visualizza | Utilizza questa pagina per creare visualizzazioni come grafici e tabelle che puoi utilizzare per analizzare i tuoi dati di log e confrontare i risultati.  |
| Dashboard | Utilizza questa pagina per analizzare i tuoi log tramite le raccolte di ricerche e visualizzazioni salvate.  |
{: caption="Tabella 1. Pagine Kibana" caption-side="top"}

**Nota:** puoi analizzare solo 1 giorno completo alla volta tramite la pagina Visualizza o Dashboard, anche se se puoi andare indietro di 3 giorni. I dati di log sono conservati per 3 giorni per impostazione predefinita. 

| Pagina Kibana | Informazioni periodo di tempo |
|-------------|-------------------------|
| Rileva | Analizza i dati per un massimo di 3 giorni. |
| Visualizza | Analizza i dati per un periodo di 24 ore. <br> Puoi filtrare i dati di log per un periodo personalizzato che passi le 24 ore.  |
| Dashboard | Analizza i dati per un periodo di 24 ore. <br> Puoi filtrare i dati di log per un periodo personalizzato che passi le 24 ore. <br> Il selezionatore di tempo che imposti, viene applicato a tutte le visualizzazioni incluse nel dashboard. |
{: caption="Tabella 2. Informazioni periodo di tempo" caption-side="top"}

Ad esempio, questo è un modo di utilizzare Kibana per visualizzare le informazioni su un contenitore o un'applicazione CF nel tuo spazio tramite pagine differenti:

## Passa al dashboard Kibana
{: #launch_Kibana}

Puoi avviare Kibana in uno dei seguenti modi:

* Dal dashboard del servizio {{site.data.keyword.loganalysisshort}}

    Puoi avviare Kibana in modo che i dati che visualizzi aggreghino i log dai servizi in uno spazio {{site.data.keyword.Bluemix_notm}} fornito.
	
	Per ulteriori informazioni, vedi [Passaggio a Kibana dal dashboard del servizio Analisi di log](/docs/services/CloudLogAnalysis/kibana/launch.html#launch_Kibana_from_log_analysis).

* Da {{site.data.keyword.Bluemix_notm}}

    Puoi eseguire l'avvio ai tuoi specifici log dell'applicazione CF nel contesto di tale specifica applicazione. Per ulteriori informazioni, vedi [Passaggio a Kibana dal dashboard di una applicazione CF](/docs/services/CloudLogAnalysis/kibana/launch.html#launch_Kibana_from_cf_app).
    
    Puoi eseguire l'avvio ai tuoi specifici log del contenitore Docker in Kibana nel contesto di tale specifico contenitore. Questa funzione si applica solo ai contenitori distribuiti nell'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}. Per ulteriori informazioni, vedi [Passaggio a Kibana dal dashboard di un contenitore](/docs/services/CloudLogAnalysis/kibana/launch.html#launch_Kibana_for_containers).
    
    Per le applicazioni CF, la query che viene utilizzata per filtrare i dati disponibili per l'analisi in Kibana richiama le voci di log per l'applicazione Cloud Foundry. Le informazioni di log visualizzate da Kibana per impostazione predefinita sono tutte correlate a un'unica applicazione Cloud Foundry e a tutte le sue istanze. 
    
    Per i contenitori, la query che viene utilizzata per filtrare i dati disponibili per l'analisi in Kibana richiama le voci di log per tutte le istanze del contenitore. Le informazioni di log visualizzate da Kibana per impostazione predefinita sono tutte correlate a un solo contenitore o a un gruppo di contenitori e a tutte le relative istanze. 
    
    

* Da un link diretto del browser

    Potresti voler avviare Kibana in modo che i dati che visualizzi aggreghino i log dai servizi all'interno di uno spazio {{site.data.keyword.Bluemix_notm}} fornito.
    
    La query che viene utilizzata per filtrare i dati visualizzati nel dashboard richiama le voci di log per uno spazio nell'organizzazione
{{site.data.keyword.Bluemix_notm}}. Le informazioni di log visualizzate da Kibana includono i record per
tutte le risorse che vengono distribuite all'interno dello spazio dell'organizzazione {{site.data.keyword.Bluemix_notm}} a cui sei connesso. 
    
    Per ulteriori informazioni, vedi [Passaggio al dashboard Kibana da un browser web](/docs/services/CloudLogAnalysis/kibana/launch.html#launch_Kibana_from_browser).
    
    

## Analizza i dati interattivamente
{: #analyze_discover}

Nella pagina Rileva, puoi definire nuove query di ricerca e applicare i filtri alle query. I dati di log sono visualizzati tramite una tabella e un istogramma. Puoi utilizzare queste visualizzazioni per analizzare i dati interattivamente. Per maggiori informazioni, vedi [Analisi dei log interattiva in Kibana](analize_logs_interactively.html#analize_logs_interactively).

Puoi configurare i filtri dai campi di log, ad esempio, message_type e instance_ID e impostare un periodo di tempo. Puoi abilitare o disabilitare dinamicamente questi filtri. La tabella e l'istogramma visualizzeranno le voci di log che soddisfano la query e i criteri di filtro da te abilitati. Per maggiori informazioni, vedi [Filtro dei log in Kibana](/docs/services/CloudLogAnalysis/kibana/filter_logs.html#filter_logs).

## Analizza i dati attraverso una visualizzazione
{: #analyze_visualize}
    
Nella pagina Visualizza, puoi definire nuove visualizzazioni e query di ricerca. Puoi anche aprire le visualizzazioni salvate o salvarne una.

Per analizzare i dati, puoi creare visualizzazioni basate su una ricerca esistente o una nuova ricerca. Kibana include diversi tipi di visualizzazioni, come tabella, tendenze e istogramma, che puoi utilizzare per analizzare le informazioni. Ogni visualizzazione ha un obiettivo diverso. Alcune visualizzazioni sono organizzate in righe che forniscono i risultati di una o più query. Altre visualizzazioni mostrano documenti o informazioni personalizzate. I dati in una visualizzazione possono essere corretti o modificati se viene aggiornata una query di ricerca. Puoi incorporare la tua visualizzazione in una pagina web o condividerla. 

Per maggiori informazioni, vedi [Analisi dei log utilizzando le visualizzazioni](/docs/services/CloudLogAnalysis/kibana/kibana_visualizations.html#kibana_visualizations).

## Analizza i dati in un dashboard
{: #analyze_dashboard}

Nella pagina Dashboard, puoi personalizzare, salvare e condividere più visualizzazioni e ricerche contemporaneamente. 

Puoi aggiungere, rimuovere e riorganizzare le visualizzazioni nel dashboard. Per maggiori informazioni, vedi [Analisi dei log in Kibana tramite un dashboard](/docs/services/CloudLogAnalysis/kibana/analize_logs_dashboard.html#analize_logs_dashboard).
    
Dopo aver personalizzato un dashboard Kibana, puoi analizzare i dati tramite le relative visualizzazioni e salvarli per un utilizzo successivo. Per maggiori informazioni, vedi [Salvataggio di un dashboard Kibana ](/docs/services/CloudLogAnalysis/kibana/analize_logs_dashboard.html#save).

In Kibana, esiste inoltre una pagina **Gestione** che puoi utilizzare per configurare Kibana e per salvare, eliminare, esportare e importare ricerche, visualizzazioni e dashboard.


