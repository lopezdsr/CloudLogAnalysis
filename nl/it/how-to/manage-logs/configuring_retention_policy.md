---

copyright:
  years: 2017
lastupdated: "2017-07-19"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Configurazione della politica di conservazione dei log
{: #configuring_retention_policy}

Utilizza il comando **cf logging option** per visualizzare e configurare la politica di conservazione che definisce il numero massimo di giorni in cui i log vengono conservati nella raccolta dei log. Per impostazione predefinita, i log vengono conservati per 30 giorni. Dopo la scadenza del periodo di conservazione, i log vengono eliminati automaticamente. Per impostazione predefinita, la politica di conservazione è disabilitata.
{:shortdesc}

Puoi disporre di diverse politiche di conservazione definite nell'account. Puoi avere una politica per l'account globale e politiche dello spazio individuali. La politica di conservazione che imposti al livello dell'account configura il numero massimo di giorni in cui puoi conservare i log. Se imposti una politica di conservazione dello spazio per un periodo di tempo più lungo del periodo al livello dell'account, la politica che viene applicata è l'ultima politica che hai configurato per tale spazio. 


## Disabilitazione della politica di conservazione dei log per uno spazio
{: #disable_retention_policy_space}

Completa la seguente procedura per disabilitare una politica di conservazione:

1. Accedi alla regione, organizzazione e spazio {{site.data.keyword.Bluemix_notm}} in cui desideri impostare una politica di conservazione dei log. 

    Ad esempio, per accedere alla regione Stati Uniti Sud, esegui questo comando:
	
	```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}
    
2. Imposta il periodo di conservazione su **-1** per disabilitarlo. Esegui il comando:

    ```
    cf logging option -r -1
    ```
    {: codeblock}
    
**Esempio**
    
Ad esempio, per disabilitare il periodo di conservazione per uno spazio con ID *d35da1e3-b345-475f-8502-cfgh436902a3*, esegui il seguente comando:

```
cf logging option -r -1
```
{: codeblock}

L'output è:

```
+--------------------------------------+-----------+
|               SPACEID                | RETENTION |
+--------------------------------------+-----------+
| d35da1e3-b345-475f-8502-cfgh436902a3 |        -1 |
+--------------------------------------+-----------+
```
{: screen} 



## Verifica della politica di conservazione dei log per uno spazio
{: #check_retention_policy_space}

Per ottenere il periodo di conservazione impostato per uno spazio {{site.data.keyword.Bluemix_notm}}, completa la seguente procedura:

1. Accedi alla regione, organizzazione e spazio {{site.data.keyword.Bluemix_notm}} in cui desideri impostare una politica di conservazione dei log. 

    Ad esempio, per accedere alla regione Stati Uniti Sud, esegui questo comando:
	
	```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}
    
2. Per ottenere il periodo di conservazione. Esegui il comando:

    ```
    cf logging option
    ```
    {: codeblock}

    L'output è:

    ```
    +--------------------------------------+-----------+
    |               SPACEID                | RETENTION |
    +--------------------------------------+-----------+
    | d35da1e3-b345-475f-8502-cfgh436902a3 |        30 |
    +--------------------------------------+-----------+
    ```
    {: screen}
    

## Verifica della politica di conservazione dei log per tutti gli spazi in un account
{: #check_retention_policy_account}

Per ottenere il periodo di conservazione impostato per ogni spazio {{site.data.keyword.Bluemix_notm}} in un account, completa la seguente procedura:

1. Accedi alla regione, organizzazione e spazio {{site.data.keyword.Bluemix_notm}} in cui desideri impostare una politica di conservazione dei log. 

    Ad esempio, per accedere alla regione Stati Uniti Sud, esegui questo comando:
	
	```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}
    
2. Per ottenere il periodo di conservazione di ogni spazio nell'account. Esegui il comando:

    ```
    cf logging option -a
    ```
    {: codeblock}

    L'output è:

    ```
    +--------------------------------------+-----------+
    |               SPACEID                | RETENTION |
    +--------------------------------------+-----------+
    | d35da1e3-b345-475f-8502-cfgh436902a3 |        30 |
    +--------------------------------------+-----------+
    | fdew45e3-b345-4365-8502-cfghrfthy5a3 |        30 |
    +--------------------------------------+-----------+
    ```
    {: screen}
    

## Configurazione di una politica di configurazione dei log al livello dell'account
{: #set_retention_policy_space}

Per visualizzare il periodo di conservazione per un account {{site.data.keyword.Bluemix_notm}}, completa la seguente procedura:

1. Accedi alla regione, organizzazione e spazio {{site.data.keyword.Bluemix_notm}} in cui desideri impostare una politica di conservazione dei log. 

    Ad esempio, per accedere alla regione Stati Uniti Sud, esegui questo comando:
	
	```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}
    
2. Per impostare il periodo di conservazione. Esegui il comando:

    ```
    cf logging option -r *Number_of_days* - a
    ```
    {: codeblock}
    
    dove *Number_of_days* è un numero intero che definisce il numero di giorni in cui desideri conservare i log. 
    
    
**Esempio**
    
Ad esempio, per conservare qualsiasi tipo di log nel tuo account soltanto per 15 giorni, esegui il seguente comando:

```
cf logging option -r 15 -a
```
{: codeblock}

L'output elenca una voce per ogni spazio nell'account, incluse le informazioni sul periodo di conservazione:

```
+--------------------------------------+-----------+
|               SPACEID                | RETENTION |
+--------------------------------------+-----------+
| d35da1e3-b345-475f-8502-cfgh436902a3 |        15 |
+--------------------------------------+-----------+
| fdew45e3-b345-4365-8502-cfghrfthy5a3 |        30 |
+--------------------------------------+-----------+
```
{: screen}

## Configurazione della politica di conservazione dei log per uno spazio
{: #set_retention_policy_account}

Per visualizzare il periodo di conservazione per uno spazio {{site.data.keyword.Bluemix_notm}}, completa la seguente procedura:

1. Accedi alla regione, organizzazione e spazio {{site.data.keyword.Bluemix_notm}} in cui desideri impostare una politica di conservazione dei log. 

    Ad esempio, per accedere alla regione Stati Uniti Sud, esegui questo comando:
	
	```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}
    
2. Per impostare il periodo di conservazione. Esegui il comando:

    ```
    cf logging option -r *Number_of_days*
    ```
    {: codeblock}
    
    dove *Number_of_days* è un numero intero che definisce il numero di giorni in cui desideri conservare i log.
    
    
**Esempio**
    
Ad esempio, per conservare i log disponibili in un spazio per un anno, esegui il seguente comando:

```
cf logging option -r 365
```
{: codeblock}

L'output è:

```
+--------------------------------------+-----------+
|               SPACEID                | RETENTION |
+--------------------------------------+-----------+
| d35da1e3-b345-475f-8502-cfgh436902a3 |       365 |
+--------------------------------------+-----------+
```
{: screen}


