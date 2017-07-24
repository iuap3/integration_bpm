# 流程的执行与控制服务

## 启动特定租户或子租户的流程

`POST runtime/process-instances
`
请求体（使用流程定义id启动）：

`{ 
   "processDefinitionId":"oneTaskProcess:1:158", 
   "businessKey":"myBusinessKey", 
   "variables": [ 
      { 
        "name":"myVar", 
        "value":"This is a variable", 
      }, 
      ... 
   ] 
}
`
请求体（使用流程定义key启动）：

`{ 
   "processDefinitionKey":"oneTaskProcess", 
   "businessKey":"myBusinessKey", 
   "tenantId": "tenant1", 
   "variables": [ 
      { 
        "name":"myVar", 
        "value":"This is a variable", 
      }, 
      ... 
   ] 
}`

启动流程实例 - 响应码

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>响应码</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>201</span> </p> </td> 
     <td> <p> <span>表示成功启动了流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示要么找到不到流程定义（基于id或key），要么传递了非法的变量。状态描述中包含了错误相关的额外信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{  "id":"7",  "url":"http://localhost:8182/runtime/process-instances/7",  "businessKey":"myBusinessKey",  "suspended":false,  "processDefinitionUrl":"http://localhost:8182/repository/process-definitions/processOne%3A1%3A4",  "activityId":"processTask",  "tenantId" : null }`

## 获取流程实例列表

`GET runtime/process-instances`

显示流程实例列表 - URL参数

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
     <td> <p> <span>id</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定id的流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定流程定义key的流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定流程定义id的流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>businessKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定businessKey的流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>involvedUser</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定用户参与过的流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>suspended</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>如果为&nbsp;true，只返回挂起的流程实例。如果为&nbsp;false，只返回未挂起（激活）的流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>superProcessInstanceId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定上级流程实例id的流程实例（对应call-activity）。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>subProcessInstanceId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定子流程id的流程实例（对方call-activity）。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>excludeSubprocesses</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>只返回非子流程的流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>includeProcessVariables</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>表示结果中包含流程变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>tenantId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定tenantId的流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>tenantIdLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定tenantId匹配的流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>withoutTenantId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>如果为&nbsp;true，只返回未设置tenantId的流程实例。如果为&nbsp;false，会忽略&nbsp;withoutTenantId&nbsp;参数。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>sort</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>排序字段，应该为id（默认），processDefinitionId，tenantId&nbsp;或&nbsp;processDefinitionKey三者之一。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>可以使用通用的</span><a href="http://www.mossle.com/docs/activiti/index.html%22 \l %22restPagingAndSort%22 \o %22%E5%88%86%E9%A1%B5%E4%B8%8E%E6%8E%92%E5%BA%8F"><span>分页和排序查询参数</span></a><span>。</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

显示流程实例列表 - 响应码 

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
     <td> <p> <span>表示请求成功，并返回了流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示传递了错误格式的参数。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
   "data":[ 
      { 
         "id":"7", 
         "url":"http://localhost:8182/runtime/process-instances/7", 
         "businessKey":"myBusinessKey", 
         "suspended":false, 
         "processDefinitionUrl":"http://localhost:8182/repository/process-definitions/processOne%3A1%3A4", 
         "activityId":"processTask", 
                 "tenantId" : null 
      }, 

      ... 
   ], 
   "total":2, 
   "start":0, 
   "sort":"id", 
   "order":"asc", 
   "size":2 
}
`
## 查询指定流程实例

`POST query/process-instances
`
请求体：

`{ 
  "processDefinitionKey":"oneTaskProcess", 
  "variables": 
  [ 
    { 
        "name" : "myVariable", 
        "value" : 1234, 
        "operation" : "equals", 
        "type" : "long" 
    }, 
    ... 
  ], 
  ... 
}
`
请求体可以包含用于4.3.2 获取流程实例列表中的查询参数。除此之外，查询条件中也可以使用通用的分页和排序查询参数。

查询流程实例 - 响应码

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
     <td> <p> <span>表示请求成功，并返回了流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示传递了错误格式的参数。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
   "data":[ 
      { 
         "id":"7", 
         "url":"http://localhost:8182/runtime/process-instances/7", 
         "businessKey":"myBusinessKey", 
         "suspended":false, 
         "processDefinitionUrl":"http://localhost:8182/repository/process-definitions/processOne%3A1%3A4", 
         "activityId":"processTask", 
                 "tenantId" : null 
      }, 

      ... 
   ], 
   "total":2, 
   "start":0, 
   "sort":"id", 
   "order":"asc", 
   "size":2 
}
`
## 激活或者挂起流程实例

`PUT runtime/process-instances/{processInstanceId}
`
Table 15.62. 激活或挂起流程实例 - URL参数

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
     <td> <p> <span>processInstanceId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望激活或挂起的流程实例id</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

请求响应体（挂起）：

`{ 
   "action":"suspend" 
}

请求响应体（激活）：

{ 
   "action":"activate" 
}
`

激活或挂起流程实例 - 响应码

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
     <td> <p> <span>表示找到了流程实例并执行了对应操作。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示提供的操作不合法。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的流程实例</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>409</span> </p> </td> 
     <td> <p> <span>表示无法执行请求的流程实例操作，因为流程实例已经激活或挂起了。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 删除流程实例

`DELETE runtime/process-instances/{processInstanceId}`

删除流程实例 - URL参数

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
     <td> <p> <span>processInstanceId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望删除的流程实例id</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

删除流程实例 - 响应码 

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>响应码</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>204</span> </p> </td> 
     <td> <p> <span>表示找到了流程实例并已删除。响应内容为空。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的流程实例</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 创建（或更新）流程实例变量

`POST runtime/process-instances/{processInstanceId}/variables

PUT runtime/process-instances/{processInstanceId}/variables`

使用POST时，会创建所有传递的变量。如果流程实例中已经存在了其中一个变量，就会返回一个错误（409 - CONFLICT）。使用PUT时， 流程实例中不存在的变量会被创建，已存在的变量会被更新，不会有任何错误。

创建（或更新）流程实例变量 - URL参数

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
     <td> <p> <span>processInstanceId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>变量对应的流程实例id</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

请求体：

`[ 
   { 
      "name":"intProcVar" 
      "type":"integer" 
      "value":123 
   }, 

   ... 
]
`
请求体的数组中可以包含任意多个变量。注意此处忽略作用域，流程实例只能设置local作用域。

创建（或更新）流程实例变量 - 响应码

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>响应码</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>201</span> </p> </td> 
     <td> <p> <span>表示找到了流程实例，并创建了变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示请求体不完整，或包含非法值。状态描述包含对应错误的详细信息。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的流程实例</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>409</span> </p> </td> 
     <td> <p> <span>表示找到了流程实例，但是已经存在一个相同名称的变量（只在使用POST方法时抛出）。可以使用更新方法替代。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`[ 
   { 
      "name":"intProcVar", 
      "type":"integer", 
      "value":123, 
      "scope":"local" 
   }, 

   ... 

]
`
## 更新一个流程实例变量

`PUT runtime/process-instances/{processInstanceId}/variables/{variableName}
`
更新一个流程实例变量 - URL参数

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
     <td> <p> <span>processInstanceId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>变量对应的流程实例id</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>variableName</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望获得的变量名称</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

请求体：

` { 
    "name":"intProcVar" 
    "type":"integer" 
    "value":123 
 }
`
请求体的数组中可以包含任意多个变量。注意此处忽略作用域，流程实例只能设置local作用域。

更新一个流程实例变量 - 响应码

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
     <td> <p> <span>表示找到了流程实例和变量，并更新了变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的流程实例，或找不到给定名称的流程实例变量。状态描述包含对应错误的详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
      "name":"intProcVar", 
      "type":"integer", 
      "value":123, 
      "scope":"local" 
   }
`
当变量为二进制或序列化类型时，valueUrl给出了获得原始数据的URL。如果是普通变量，变量值就会直接包含在响应中。 注意只会返回local作用域的变量，因为流程实例变量没有global作用域。

## 检查指派信息

`POST runtime/ext/assigncheck
`
请求体：

`{ 
    " activityId ":"intProcVar" 
    " executionId ":"integer" 
    " processDefinitionId ":"processID"

" processDefinitionKey ":"processKey"

"taskId: "taskId" 
  }
`
检查指派信息 - 响应码

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
     <td> <p> <span>返回了指派信息</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的流程定义、流程活动下的指派信息。状态描述包含对应错误的详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{"assignInfo "：{

"taskId ": " "

"executionId ": " ",

"assignInfoItems ":

[{"activityId ": "activityId ",

"activityName ": " activityname",

"participants " :[{ "id ": " ", "code ": " ", "name ": " ", "type ": " " }]

}]

} 
   }
`
## 调整到流程实例内部的某个活动

`PUT runtime/process-instances /{processInstanceId}
`
请求体：

`{ 
    " action":"jumpToActivity" 
    " activityId":"activityId" 
    " jumpOrigin":"jumpOrigin"

  }
`
检查指派信息 - 响应码

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
     <td> <p> <span>返回了流程实例信息</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
   "id":"7", 
   "url":"http://localhost:8182/runtime/process-instances/7", 
   "businessKey":"myBusinessKey", 
   "suspended":false, 
   "processDefinitionUrl":"http://localhost:8182/repository/process-definitions/processOne%3A1%3A4", 
   "activityId":"processTask", 
   "tenantId": null 
}
`
