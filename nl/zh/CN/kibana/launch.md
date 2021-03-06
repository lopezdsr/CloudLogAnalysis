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


# 导航至 Kibana 仪表板
{: #launch}

可以通过 {{site.data.keyword.loganalysisshort}} 服务、通过 {{site.data.keyword.Bluemix}} UI 或直接通过 Web 浏览器启动 Kibana。
{:shortdesc}

对于在 {{site.data.keyword.Bluemix_notm}} 管理的云基础架构中部署的 CF 应用程序和 Docker 容器，可以通过 {{site.data.keyword.Bluemix_notm}} 启动 Kibana 以在从中启动 Kibana 的资源的上下文中查看和分析数据。例如，可以在特定 CF 应用程序的上下文中，使用 Kibana 显示该 CF 应用程序的日志。
    
对于任何云资源（例如在 Kubernetes 基础架构中部署的 Docker 容器），可以通过直接浏览器链接或 {{site.data.keyword.loganalysisshort}} 服务仪表板来启动 Kibana 以查看从提供的 {{site.data.keyword.Bluemix_notm}} 空间内各服务中聚集的日志数据。用于过滤仪表板中所显示数据的查询会检索 {{site.data.keyword.Bluemix_notm}} 组织中空间的日志条目。Kibana 显示的日志信息包括在您登录到的 {{site.data.keyword.Bluemix_notm}} 组织空间内部署的所有资源的记录。 

下表列出用于启动 Kibana 的某些云资源和受支持导航方法：

<table>
<caption>表 1. 资源和受支持导航方法的列表。</caption>
  <tr>
    <th>资源</th>
	<th>通过 {{site.data.keyword.loganalysisshort}} 服务仪表板导航至 Kibana 仪表板</th>
    <th>通过 Bluemix 仪表板导航至 Kibana 仪表板</th>
    <th>通过 Web 浏览器导航至 Kibana 仪表板</th>
  </tr>
  <tr>
    <td>CF 应用程序</td>
	<td>是</td>
    <td>是</td>
    <td>是</td>
  </tr>  
  <tr>
    <td>在 Kubernetes 集群中部署的容器</td>
	<td>是</td>
    <td>否</td>
    <td>是</td>
  </tr>  
  <tr>
    <td>在 {{site.data.keyword.Bluemix_notm}} 管理的云基础架构中部署的容器</td>
	<td>是</td>
    <td>是</td>
    <td>是</td>
  </tr>  
</table>

有关 Kibana 的更多信息，请参阅 [Kibana User Guide ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")](https://www.elastic.co/guide/en/kibana/5.1/index.html "外部链接图标"){: new_window}。
    

##  通过 Log Analysis 服务的仪表板导航至 Kibana
{: #launch_Kibana_from_log_analysis}

用于过滤 Kibana 中所显示数据的查询会检索 {{site.data.keyword.Bluemix_notm}} 组织中该空间的日志条目。 
	
Kibana 显示的日志信息包括在您登录到的 {{site.data.keyword.Bluemix_notm}} 组织空间内部署的所有资源的记录。

要通过 {{site.data.keyword.loganalysisshort}} 服务的仪表板启动 Kibana，请完成以下步骤：

1. 登录到 {{site.data.keyword.Bluemix_notm}}，然后在 {{site.data.keyword.Bluemix_notm}} 仪表板中单击 {{site.data.keyword.loganalysisshort}} 服务。 
    
2. 在 {{site.data.keyword.Bluemix_notm}} UI 中选择**受管**选项卡。

3. 单击**启动**。这将打开 Kibana 仪表板。

缺省情况下，**发现**页面会装入所选的缺省索引模式，并将时间过滤器设置为最近 15 分钟。 

如果“发现”页面未显示任何日志条目，请调整时间选取器。有关更多信息，请参阅[设置时间过滤器](filter_logs.html#set_time_filter)。

	
	
##  通过 Web 浏览器导航至 Kibana
{: #launch_Kibana_from_browser}

用于过滤 Kibana 中所显示数据的查询会检索 {{site.data.keyword.Bluemix_notm}} 组织中该空间的日志条目。 
	
Kibana 显示的日志信息包括在您登录到的 {{site.data.keyword.Bluemix_notm}} 组织空间内部署的所有资源的记录。

要通过浏览器启动 Kibana，请完成以下步骤：

1. 打开 Web 浏览器并启动 Kibana。然后，登录到 Kibana 用户界面。
    
    例如，下表列出了在美国南部区域中启动 Kibana 所必须使用的 URL：
      
    <table>
          <caption>表 1. 每个区域用于启动 Kibana 的 URL</caption>
           <tr>
            <th>区域</th>
            <th>URL</th>
          </tr>
          <tr>
            <td>美国南部</td>
            <td>https://logging.ng.bluemix.net/ </td>
          </tr>
    </table>
	
	这将打开 Kibana 中的“发现”页面。
	
2. 为要查看并分析其中日志数据的 {{site.data.keyword.Bluemix_notm}} 空间选择索引模式。

    1. 单击 **default-index**。
	
	2. 为该空间选择索引模式。索引模式的格式如下：
	
	    ```
	    [logstash-Space_ID-]YYYY.MM.DD 
	    ```
        {screen}
	
	    其中，*Space_ID* 是要查看并分析其中日志数据的 {{site.data.keyword.Bluemix_notm}} 空间的 GUID。 
	
如果“发现”页面未显示任何日志条目，请调整时间选取器。有关更多信息，请参阅[设置时间过滤器](/docs/services/CloudLogAnalysis/kibana/filter_logs.html#set_time_filter)。


	
##  通过 CF 应用程序的仪表板导航至 Kibana
{: #launch_Kibana_from_cf_app}

用于过滤 Kibana 中所显示数据的查询会检索从中启动 Kibana 的 {{site.data.keyword.Bluemix_notm}} CF 应用程序的日志条目。

要在 Kibana 中查看 Cloud Foundry 应用程序的日志，请完成以下步骤：

1. 登录到 {{site.data.keyword.Bluemix_notm}}，然后在 {{site.data.keyword.Bluemix_notm}} 仪表板中单击该应用程序名称或容器。 
    
2. 在 {{site.data.keyword.Bluemix_notm}} UI 中打开“日志”选项卡。

    对于 CF 应用程序，单击导航栏中的**日志**。这将打开“日志”选项卡。  

3. 单击**高级视图**。这将打开 Kibana 仪表板。

    缺省情况下，**发现**页面会装入所选的缺省索引模式，并将时间过滤器设置为最近 30 秒。搜索查询会设置为与 CF 应用程序的所有条目相匹配。

    如果“发现”页面未显示任何日志条目，请调整时间选取器。有关更多信息，请参阅[设置时间过滤器](/docs/services/CloudLogAnalysis/kibana/filter_logs.html#set_time_filter)。


##  通过容器的仪表板导航至 Kibana
{: #launch_Kibana_for_containers}

此方法仅适用于在 {{site.data.keyword.Bluemix_notm}} 管理的云基础架构中部署的容器。

用于过滤 Kibana 中所显示数据的查询会检索从中启动 Kibana 的容器的日志条目。

要在 Kibana 中查看 Docker 容器的日志，请完成以下步骤：

1. 登录到 {{site.data.keyword.Bluemix_notm}}，然后在 {{site.data.keyword.Bluemix_notm}} 仪表板中单击该容器。 
    
2. 在 {{site.data.keyword.Bluemix_notm}} UI 中打开“日志”选项卡。

    对于在 {{site.data.keyword.IBM_notm}} 管理的云基础架构中部署的容器，选择导航栏中的**监视和日志**，然后单击**日志记录**选项卡。 
    
    这将打开“日志”选项卡。  

3. 单击**高级视图**。这将打开 Kibana 仪表板。

    缺省情况下，**发现**页面会装入所选的缺省索引模式，并将时间过滤器设置为最近 30 秒。搜索查询会设置为与 Docker 容器的所有条目相匹配。

    如果“发现”页面未显示任何日志条目，请调整时间选取器。有关更多信息，请参阅[设置时间过滤器](/docs/services/CloudLogAnalysis/kibana/filter_logs.html#set_time_filter)。

	



