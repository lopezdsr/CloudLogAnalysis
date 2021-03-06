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

# 配置日誌保留原則
{: #configuring_retention_policy}

使用指令 **cf logging option** 來檢視及配置保留原則，而此保留原則定義將日誌保留在「日誌收集」中的天數上限。依預設，日誌會保留 30 天。保留期間到期之後，會自動刪除日誌。依預設，會停用保留原則。
{:shortdesc}

您可以在帳戶中定義不同的保留原則。您可以有廣域帳戶原則及個別空間原則。您在帳戶層次設定的保留原則，可設定您可以保留日誌的天數上限。如果您為空間保留原則設定的時段大於帳戶層次期間，則套用的原則是您為該空間所配置的最後一個原則。 


## 停用空間的日誌保留原則
{: #disable_retention_policy_space}

請完成下列步驟，以停用保留原則：

1. 登入您要設定日誌保留原則的 {{site.data.keyword.Bluemix_notm}} 地區、組織及空間。 

    例如，若要登入「美國南部」地區，請執行下列指令：
	
	```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}
    
2. 將保留期間設為 **-1**，以停用保留期間。執行下列指令：

    ```
    cf logging option -r -1
    ```
    {: codeblock}
    
**範例**
    
例如，若要停用 ID 為 *d35da1e3-b345-475f-8502-cfgh436902a3* 的空間的保留期間，請執行下列指令：

```
cf logging option -r -1
```
{: codeblock}

輸出如下：

```
+--------------------------------------+-----------+
|               SPACEID                | RETENTION |
+--------------------------------------+-----------+
| d35da1e3-b345-475f-8502-cfgh436902a3 |        -1 |
+--------------------------------------+-----------+
```
{: screen} 



## 檢查空間的日誌保留原則
{: #check_retention_policy_space}

若要取得為 {{site.data.keyword.Bluemix_notm}} 空間所設定的保留期間，請完成下列步驟：

1. 登入您要設定日誌保留原則的 {{site.data.keyword.Bluemix_notm}} 地區、組織及空間。 

    例如，若要登入「美國南部」地區，請執行下列指令：
	
	```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}
    
2. 取得保留期間。執行下列指令：

    ```
    cf logging option
    ```
    {: codeblock}

    輸出如下：

    ```
    +--------------------------------------+-----------+
    |               SPACEID                | RETENTION |
    +--------------------------------------+-----------+
    | d35da1e3-b345-475f-8502-cfgh436902a3 |        30 |
    +--------------------------------------+-----------+
    ```
    {: screen}
    

## 檢查帳戶中所有空間的日誌保留原則
{: #check_retention_policy_account}

若要取得為帳戶中每一個 {{site.data.keyword.Bluemix_notm}} 空間所設定的保留期間，請完成下列步驟：

1. 登入您要設定日誌保留原則的 {{site.data.keyword.Bluemix_notm}} 地區、組織及空間。 

    例如，若要登入「美國南部」地區，請執行下列指令：
	
	```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}
    
2. 取得帳戶中每一個空間的保留期間。執行下列指令：

    ```
    cf logging option -a
    ```
    {: codeblock}

    輸出如下：

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
    

## 設定帳戶層次日誌保留原則
{: #set_retention_policy_space}

若要查看 {{site.data.keyword.Bluemix_notm}} 帳戶的保留期間，請完成下列步驟：

1. 登入您要設定日誌保留原則的 {{site.data.keyword.Bluemix_notm}} 地區、組織及空間。 

    例如，若要登入「美國南部」地區，請執行下列指令：
	
	```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}
    
2. 設定保留期間。執行下列指令：

    ```
    cf logging option -r *Number_of_days* - a
    ```
    {: codeblock}
    
    其中 *Number_of_days* 是整數，用來定義您要保留日誌的天數。 
    
    
**範例**
    
例如，若要將帳戶中的任何日誌類型僅保留 15 天，請執行下列指令：

```
cf logging option -r 15 -a
```
{: codeblock}

輸出會針對帳戶中的每一個空間列出一個項目，包括保留期間的相關資訊：

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

## 設定空間的日誌保留原則
{: #set_retention_policy_account}

若要查看 {{site.data.keyword.Bluemix_notm}} 空間的保留期間，請完成下列步驟：

1. 登入您要設定日誌保留原則的 {{site.data.keyword.Bluemix_notm}} 地區、組織及空間。 

    例如，若要登入「美國南部」地區，請執行下列指令：
	
	```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}
    
2. 設定保留期間。執行下列指令：

    ```
    cf logging option -r *Number_of_days*
    ```
    {: codeblock}
    
    其中 *Number_of_days* 是整數，用來定義您要保留日誌的天數。
    
    
**範例**
    
例如，若要將空間中可用的日誌保留一年，請執行下列指令：

```
cf logging option -r 365
```
{: codeblock}

輸出如下：

```
+--------------------------------------+-----------+
|               SPACEID                | RETENTION |
+--------------------------------------+-----------+
| d35da1e3-b345-475f-8502-cfgh436902a3 |       365 |
+--------------------------------------+-----------+
```
{: screen}


