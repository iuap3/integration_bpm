# 流程定义

## 获取指定流程定义

`GET repository/process-definitions/{processDefinitionId}
`
获得一个流程定义 - URL参数

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>参数</span> </p> </th> 
     <th> <p> <span>是否必须</span> </p> </th> 
     <th> <p> <span>值</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>processDefinitionId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望获取的流程定义的id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获得一个流程定义 - 响应码

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>响应码</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>200</span> </p> </td> 
     <td> <p> <span>表示找到了流程定义，并返回了结果。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的流程定义。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{  "id" : "oneTaskProcess:1:4",  "url" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4",  "version" : 1,  "key" : "oneTaskProcess",  "category" : "Examples",  "suspended" : false,  "name" : "The One Task Process",  "description" : "This is a process for testing purposes",  "deploymentId" : "2",  "deploymentUrl" : "http://localhost:8081/repository/deployments/2",  "graphicalNotationDefined" : true,  "resource" : "http://localhost:8182/repository/deployments/2/resources/testProcess.xml",  "diagramResource" : "http://localhost:8182/repository/deployments/2/resources/testProcess.png",  "startFormDefined" : false }`

● graphicalNotationDefined：表示流程定义包含图形信息。

● resource：包含实际部署的BPMN 2.0 xml。

● diagramResource：包含流程的图形内容，如果没有图形就返回null。

## 获取流程定义列表

`GET repository/process-definitions`

流程定义列表 - URL参数

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>参数</span> </p> </th> 
     <th> <p> <span>是否必须</span> </p> </th> 
     <th> <p> <span>值</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>version</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>integer</span> </p> </td> 
     <td> <p> <span>只返回给定版本的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>name</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回给定名称的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>nameLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与给定名称匹配的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>key</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回给定key的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>keyLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与给定key匹配的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>resourceName</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回给定资源名称的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>resourceNameLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与给定资源名称匹配的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>category</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回给定分类的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>categoryLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与给定分类匹配的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>categoryNotEquals</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回非给定分类的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>deploymentId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回包含在与给定id一致的部署中的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>startableByUser</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回给定用户可以启动的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>latest</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>只返回最新的流程定义版本。只能与'key'或'keyLike'参数一起使用，如果使用了其他参数会返回400的响应。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>suspended</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>如果为true，只返回挂起的流程定义。如果为false，只返回活动的（未挂起）的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>sort</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>'name'（默认），'id'，'key'，'category'，'deploymentId'和'version'</span> </p> </td> 
     <td> <p> <span>排序的属性，可以与'order'一起使用。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>也可以使用通用的</span><a href="http://www.mossle.com/docs/activiti/index.html%22 \l %22restPagingAndSort%22 \o %22%E5%88%86%E9%A1%B5%E4%B8%8E%E6%8E%92%E5%BA%8F"><span>分页与排序查询参数</span></a><span>。</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

流程定义列表 - 响应码 

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>响应码</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>200</span> </p> </td> 
     <td> <p> <span>表示请求成功，流程定义已返回。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示传递的参数格式错误，或'latest'与'key'，'keyLike'之外的其他参数一起使用了。状态信息包含更多信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{

"data": [

{

"id" : "oneTaskProcess:1:4",

"url" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4",

"version" : 1,

"key" : "oneTaskProcess",

"category" : "Examples",

"suspended" : false,

"name" : "The One Task Process",

"description" : "This is a process for testing purposes",

"deploymentId" : "2",

"deploymentUrl" : "http://localhost:8081/repository/deployments/2",

"graphicalNotationDefined" : true,

"resource" : "http://localhost:8182/repository/deployments/2/resources/testProcess.xml",

"diagramResource" : "http://localhost:8182/repository/deployments/2/resources/testProcess.png",

"startFormDefined" : false

}

],

"total": 1,

"start": 0,

"sort": "name",

"order": "asc",

"size": 1

}`

● graphicalNotationDefined：表示流程定义包含图形信息（BPMN DI）。

● resource：包含实际部署的BPMN 2.0 xml。

● diagramResource：包含流程的图形内容，如果没有图形就返回null。

## 暂停流程定义

`PUT repository/process-definitions/{processDefinitionId}`

请求JSON体：
`{ 
  "action" : "suspend", 
  "includeProcessInstances" : "false", 
  "date" : "2013-04-15T00:42:12Z" 
}`

暂停流程定义 - 请求的JSON参数 

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>参数</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
    <tr></tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>action</span> </p> </td> 
     <td> <p> <span>执行的动作。activate&nbsp;或&nbsp;suspend。</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>includeProcessInstances</span> </p> </td> 
     <td> <p> <span>是否把流程定义下正在运行的流程时也暂停或激活。如果忽略，就不改变流程实例的状态。</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>date</span> </p> </td> 
     <td> <p> <span>执行暂停或激活的日期（ISO-8601格式）。如果忽略，会立即执行暂停或激活。</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

暂停流程定义 - 响应码 

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>响应码</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>200</span> </p> </td> 
     <td> <p> <span>表示暂停流程成功。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的流程定义。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>409</span> </p> </td> 
     <td> <p> <span>表示请求的流程定义已经暂停了。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 激活流程定义

`PUT repository/process-definitions/{processDefinitionId}`

请求JSON体：

`{  "action" : "activate",  "includeProcessInstances" : "true",  "date" : "2013-04-15T00:42:12Z" }`

激活流程定义 - 响应码

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>响应码</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>200</span> </p> </td> 
     <td> <p> <span>表示激活流程成功。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的流程定义</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>409</span> </p> </td> 
     <td> <p> <span>表示请求的流程定义已经激活了。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

