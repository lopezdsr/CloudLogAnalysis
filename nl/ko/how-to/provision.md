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


# 로그 분석 서비스 프로비저닝
{: #provision}

{{site.data.keyword.Bluemix}} UI 또는 명령행에서 {{site.data.keyword.loganalysisshort}} 서비스를 프로비저닝할 수 있습니다.
{:shortdesc}


## UI에서의 프로비저닝
{: #ui}

{{site.data.keyword.Bluemix_notm}}에서 {{site.data.keyword.loganalysisshort}} 서비스의 인스턴스를 프로비저닝하려면 다음 단계를 완료하십시오. 

1. {{site.data.keyword.Bluemix_notm}} 계정에 로그인하십시오. 

    [http://bluemix.net![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")](http://bluemix.net "외부 링크 아이콘"){:new_window}에서 {{site.data.keyword.Bluemix_notm}} 대시보드를 찾을 수 있습니다.
    
	사용자 ID 및 비밀번호를 사용하여 로그인하면 {{site.data.keyword.Bluemix_notm}} UI가 열립니다. 

2. **카탈로그**를 클릭하십시오. {{site.data.keyword.Bluemix_notm}}에서 사용 가능한 서비스의 목록이 열립니다. 

3. **DevOps** 카테고리를 선택하여 표시된 서비스의 목록을 필터링하십시오. 

4. **로그 분석** 타일을 클릭하십시오. 

5. 서비스 플랜을 선택하십시오. 기본적으로 **라이트** 플랜이 설정됩니다. 

    서비스 플랜에 대한 자세한 정보는 [서비스 플랜](/docs/services/CloudLogAnalysis/log_analysis_ov.html#plans)을 참조하십시오.
	
6. 사용자가 로그인한 {{site.data.keyword.Bluemix_notm}} 영역의 {{site.data.keyword.loganalysisshort}} 서비스를 프로비저닝하려면 **작성**을 클릭하십시오. 
  
 

## CLI에서의 프로비저닝
{: #cli}

명령행을 통해 {{site.data.keyword.Bluemix_notm}}에서 {{site.data.keyword.loganalysisshort}} 서비스의 인스턴스를 프로비저닝하려면 다음 단계를 완료하십시오. 

1. Cloud Foundry(CF) CLI를 설치하십시오. CF CLI가 설치되면 다음 단계로 계속 진행하십시오. 

   자세한 정보는 [CF CLI 설치![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")](http://docs.cloudfoundry.org/cf-cli/install-go-cli.html "외부 링크 아이콘"){: new_window}을 설치하십시오. 
    
2. {{site.data.keyword.Bluemix_notm}} 지역, 조직 및 영역에 로그인하십시오.  

    예를 들어, 미국 남부 지역에 로그인하려면 다음 명령을 실행하십시오.

    ```
    cf login -a https://api.ng.bluemix.net
    ```
    {: codeblock}

    지시사항을 따르십시오. {{site.data.keyword.Bluemix_notm}} 신임 정보를 입력한 후 조직 및 영역을 선택하십시오. 
	
3. `cf create-service` 명령을 실행하여 인스턴스를 프로비저닝하십시오. 

    ```
	cf create-service service_name service_plan service_instance_name
	```
	{: codeblock}

    여기서,
	
	* service_name은 서비스 이름(즉, **ibmLogAnalysis**)입니다.
	* service_plan은 서비스 플랜 이름입니다. 플랜 목록의 경우 [서비스 플랜](/docs/services/CloudLogAnalysis/log_analysis_ov.html#plans)을 참조하십시오.
	* service_instance_name은 사용자가 작성한 새 서비스 인스턴스에 사용하려는 이름입니다.
	
	cf 명령에 대한 자세한 정보는 [cf create-service](/docs/cli/reference/cfcommands/index.html#cf_create-service)를 참조하십시오.

	예를 들어, 무료 사용제를 통해 {{site.data.keyword.loganalysisshort}} 서비스의 인스턴스를 작성하려면 다음 명령을 실행하십시오.
	
	```
	cf create-service ibmLogAnalysis lite my_logging_svc
	```
	{: codeblock}
	
4. 서비스가 작성되었는지 확인하십시오. 다음 명령을 실행하십시오.

    ```	
	cf services
	```
	{: codeblock}
	
	명령 실행의 출력은 다음과 같습니다.
	
	```
    Getting services in org MyOrg / space MySpace as xxx@yyy.com...
    OK
    
    name                           service                  plan                   bound apps              last operation
    my_logging_svc                ibmLogAnalysis               lite                                        create succeeded
	```
	{: screen}

	



