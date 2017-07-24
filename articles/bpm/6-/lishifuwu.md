# 流程与任务历史服务

## 获得历史流程实例

`GET history/historic-process-instances/{processInstanceId}
`

获得历史流程实例 - 响应码

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
     <td> <p> <span>表示找到了历史流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到历史流程实例。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
  "data": [ 
    { 
      "id" : "5", 
      "businessKey" : "myKey", 
      "processDefinitionId" : "oneTaskProcess%3A1%3A4", 
      "processDefinitionUrl" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4", 
      "startTime" : "2013-04-17T10:17:43.902+0000", 
      "endTime" : "2013-04-18T14:06:32.715+0000", 
      "durationInMillis" : 86400056, 
      "startUserId" : "kermit", 
      "startActivityId" : "startEvent", 
      "endActivityId" : "endEvent", 
      "deleteReason" : null, 
      "superProcessInstanceId" : "3", 
      "url" : "http://localhost:8182/history/historic-process-instances/5", 
      "variables": null, 
          "tenantId":null 
    } 
  ], 
  "total": 1, 
  "start": 0, 
  "sort": "name", 
  "order": "asc", 
  "size": 1 
}
`
## 历史流程实例列表

`GET history/historic-process-instances
`
历史流程实例列表 - URL参数

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>参数</span> </p> </th> 
     <th> <p> <span>是否必填</span> </p> </th> 
     <th> <p> <span>数据</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>processInstanceId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史流程实例id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史流程实例的流程定义key。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史流程实例的流程定义id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>businessKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史流程实例的businessKey。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>involvedUser</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史流程实例的参与者。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>finished</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>表示历史流程实例是否结束了。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>superProcessInstanceId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史流程实例的上级流程实例id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>excludeSubprocesses</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>只返回非子流程的历史流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>finishedAfter</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回指定时间之后结束的历史流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>finishedBefore</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回指定时间之前结束的历史流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>startedAfter</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回指定时间之后开始的历史流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>startedBefore</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回指定时间之前开始的历史流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>startedBy</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回由指定用户启动的历史流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>includeProcessVariables</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>表示是否应该返回历史流程实例变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>tenantId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定tenantId的实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>tenantIdLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定tenantId匹配的实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>withoutTenantId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>如果为&nbsp;</span><span>true</span><span>，只返回未设置tenantId的实例。如果为&nbsp;</span><span>false</span><span>，会忽略&nbsp;</span><span>withoutTenantId</span><span>&nbsp;参数。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>可以使用通用的&nbsp;</span><a href="http://www.mossle.com/docs/activiti/index.html%22 \l %22restPagingAndSort%22 \o %22%E5%88%86%E9%A1%B5%E4%B8%8E%E6%8E%92%E5%BA%8F"><span>分页和排序查询参数</span></a><span>。</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

历史流程实例列表 - 响应码 

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
     <td> <p> <span>表示成功返回了历史流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示传递了错误格式的参数。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
  "data": [ 
    { 
      "id" : "5", 
      "businessKey" : "myKey", 
      "processDefinitionId" : "oneTaskProcess%3A1%3A4", 
      "processDefinitionUrl" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4", 
      "startTime" : "2013-04-17T10:17:43.902+0000", 
      "endTime" : "2013-04-18T14:06:32.715+0000", 
      "durationInMillis" : 86400056, 
      "startUserId" : "kermit", 
      "startActivityId" : "startEvent", 
      "endActivityId" : "endEvent", 
      "deleteReason" : null, 
      "superProcessInstanceId" : "3", 
      "url" : "http://localhost:8182/history/historic-process-instances/5", 
      "variables": [ 
        { 
          "name": "test", 
          "variableScope": "local", 
          "value": "myTest" 
        } 
      ], 
          "tenantId":null 
    } 
  ], 
  "total": 1, 
  "start": 0, 
  "sort": "name", 
  "order": "asc", 
  "size": 1 
}`

## 查询历史流程实例

`POST query/historic-process-instances
`
请求体：

{ 
  "processDefinitionId" : "oneTaskProcess%3A1%3A4", 
  ... 

  "variables" : [ 
    { 
      "name" : "myVariable", 
      "value" : 1234, 
      "operation" : "equals", 
      "type" : "long" 
    } 
  ] 
}

查询历史流程实例 - 响应码

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
     <td> <p> <span>表示请求成功，并返回结果。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示传递了错误格式的参数。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
  "data": [ 
    { 
      "id" : "5", 
      "businessKey" : "myKey", 
      "processDefinitionId" : "oneTaskProcess%3A1%3A4", 
      "processDefinitionUrl" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4", 
      "startTime" : "2013-04-17T10:17:43.902+0000", 
      "endTime" : "2013-04-18T14:06:32.715+0000", 
      "durationInMillis" : 86400056, 
      "startUserId" : "kermit", 
      "startActivityId" : "startEvent", 
      "endActivityId" : "endEvent", 
      "deleteReason" : null, 
      "superProcessInstanceId" : "3", 
      "url" : "http://localhost:8182/history/historic-process-instances/5", 
      "variables": [ 
        { 
          "name": "test", 
          "variableScope": "local", 
          "value": "myTest" 
        } 
      ], 
          "tenantId":null 
    } 
  ], 
  "total": 1, 
  "start": 0, 
  "sort": "name", 
  "order": "asc", 
  "size": 1 
}`

## 删除历史流程实例

`DELETE history/historic-process-instances/{processInstanceId}
`
响应码

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
     <td> <p> <span>表示成功删除了历史流程实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到历史流程实例。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 获得一个历史流程实例的所有评论

`GET history/historic-process-instances/{processInstanceId}/comments`

获得流程实例的所有评论 - URL参数

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>参数</span> </p> </th> 
     <th> <p> <span>必填</span> </p> </th> 
     <th> <p> <span>值</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>processInstanceId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>获取评论对应的流程实例id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

[ 
  { 
    "id" : "123", 
    "processInstanceUrl" : "http://localhost:8081/activiti-rest/service/history/historic-process-instances/100/comments/123", 
    "message" : "This is a comment on the task.", 
    "author" : "kermit", 
    "time" : "2014-07-13T13:13:52.232+08:00", 
    "processInstanceId" : "100" 
  }, 
  { 
    "id" : "456", 
    "processInstanceUrl" : "http://localhost:8081/activiti-rest/service/history/historic-process-instances/100/comments/456", 
    "message" : "This is another comment.", 
    "author" : "gonzo", 
    "time" : "2014-07-14T15:16:52.232+08:00", 
    "processInstanceId" : "100" 
  } 
]

获得流程实例的所有评论 - 响应码

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
     <td> <p> <span>表示找到了流程实例，并返回了评论。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的流程实例。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 获得单独历史任务实例

`GET history/historic-task-instances/{taskId}
`
获得单独历史任务实例 - 响应码

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
     <td> <p> <span>表示找到了历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到历史任务实例。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
  "id" : "5", 
  "processDefinitionId" : "oneTaskProcess%3A1%3A4", 
  "processDefinitionUrl" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4", 
  "processInstanceId" : "3", 
  "processInstanceUrl" : "http://localhost:8182/history/historic-process-instances/3", 
  "executionId" : "4", 
  "name" : "My task name", 
  "description" : "My task description", 
  "deleteReason" : null, 
  "owner" : "kermit", 
  "assignee" : "fozzie", 
  "startTime" : "2013-04-17T10:17:43.902+0000", 
  "endTime" : "2013-04-18T14:06:32.715+0000", 
  "durationInMillis" : 86400056, 
  "workTimeInMillis" : 234890, 
  "claimTime" : "2013-04-18T11:01:54.715+0000", 
  "taskDefinitionKey" : "taskKey", 
  "formKey" : null, 
  "priority" : 50, 
  "dueDate" : "2013-04-20T12:11:13.134+0000", 
  "parentTaskId" : null, 
  "url" : "http://localhost:8182/history/historic-task-instances/5", 
  "variables": null, 
  "tenantId":null 
}
`
## 获取历史任务实例

`GET history/historic-task-instances
`
获取历史任务实例 - URL参数

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>参数</span> </p> </th> 
     <th> <p> <span>是否必填</span> </p> </th> 
     <th> <p> <span>数据</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processInstanceId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的流程实例id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的流程定义key。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionKeyLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的流程定义key与指定值匹配。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的流程定义id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionName</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的流程定义名称。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionNameLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的流程定义名称与指定值匹配。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processBusinessKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的流程实例businessKey。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processBusinessKeyLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的流程实例业务key与指定值匹配。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>executionId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的分支id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskDefinitionKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>流程的任务部分的流程定义key。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskName</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的任务名称。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskNameLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>对任务名称使用'like'查询历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskDescription</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的任务描述。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskDescriptionLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>对任务描述使用'like'查询历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskDefinitionKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例对应的流程定义的任务定义key。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskDeleteReason</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的删除任务原因。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskDeleteReasonLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>对删除任务原因使用'like'查询历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskAssignee</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的负责人。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskAssigneeLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>对负责人使用'like'查询历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskOwner</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的原拥有者。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskOwnerLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>对原拥有者使用'like'查询历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskInvolvedUser</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的参与者。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskPriority</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的优先级。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>finished</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>表示是否历史任务实例已经结束了。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processFinished</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>表示历史任务实例的流程实例是否已经结束了。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>parentTaskId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>历史任务实例的可能的上级任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>dueDate</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回指定持续时间的历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>dueDateAfter</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回指定持续时间之后的历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>dueDateBefore</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回指定持续时间之前的历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>withoutDueDate</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>只返回没有设置持续时间的历史任务实例。当设置为false时会忽略这个参数。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskCompletedOn</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回在指定时间完成的历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskCompletedAfter</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回在指定时间之后完成的历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskCompletedBefore</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回在指定时间之前完成的历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskCreatedOn</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回指定创建时间的历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskCreatedBefore</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回在指定时间前创建的历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskCreatedAfter</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回在指定时间后创建的历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>includeTaskLocalVariables</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>表示是否应该返回历史任务实例局部变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>includeProcessVariables</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>表示是否应该返回历史任务实例全局变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>tenantId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定tenantId的历史任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>tenantIdLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定tenantId匹配的历史任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>withoutTenantId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>如果为&nbsp;true，只返回未设置tenantId的历史任务。如果为&nbsp;false，会忽略&nbsp;withoutTenantId&nbsp;参数。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>可以使用通用的&nbsp;</span><a href="http://www.mossle.com/docs/activiti/index.html%22 \l %22restPagingAndSort%22 \o %22%E5%88%86%E9%A1%B5%E4%B8%8E%E6%8E%92%E5%BA%8F"><span>分页和排序查询参数</span></a><span>。</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获取历史任务实例 - 响应码 

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
     <td> <p> <span>表示可以查询的历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示传递了错误格式的参数。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
  "data": [ 
    { 
      "id" : "5", 
      "processDefinitionId" : "oneTaskProcess%3A1%3A4", 
      "processDefinitionUrl" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4", 
      "processInstanceId" : "3", 
      "processInstanceUrl" : "http://localhost:8182/history/historic-process-instances/3", 
      "executionId" : "4", 
      "name" : "My task name", 
      "description" : "My task description", 
      "deleteReason" : null, 
      "owner" : "kermit", 
      "assignee" : "fozzie", 
      "startTime" : "2013-04-17T10:17:43.902+0000", 
      "endTime" : "2013-04-18T14:06:32.715+0000", 
      "durationInMillis" : 86400056, 
      "workTimeInMillis" : 234890, 
      "claimTime" : "2013-04-18T11:01:54.715+0000", 
      "taskDefinitionKey" : "taskKey", 
      "formKey" : null, 
      "priority" : 50, 
      "dueDate" : "2013-04-20T12:11:13.134+0000", 
      "parentTaskId" : null, 
      "url" : "http://localhost:8182/history/historic-task-instances/5", 
      "taskVariables": [ 
        { 
          "name": "test", 
          "variableScope": "local", 
          "value": "myTest" 
        } 
      ], 
      "processVariables": [ 
        { 
          "name": "processTest", 
          "variableScope": "global", 
          "value": "myProcessTest" 
        } 
      ], 
          "tenantId":null 
    } 
  ], 
  "total": 1, 
  "start": 0, 
  "sort": "name", 
  "order": "asc", 
  "size": 1 
}`

## 查询历史任务实例

`POST query/historic-task-instances
`
查询历史任务实例 - 请求体：

`{ 
  "processDefinitionId" : "oneTaskProcess%3A1%3A4", 
  ... 

  "variables" : [ 
    { 
      "name" : "myVariable", 
      "value" : 1234, 
      "operation" : "equals", 
      "type" : "long" 
    } 
  ] 
}
`
所有支持的JSON参数字段和获得历史任务实例集合完全一样，但是传递的是JSON参数，而不是URL参数，这样可以支持更高级的参数，同时避免请求uri过长。除此之外，查询支持基于流程变量查询。 taskVariables和processVariables属性是一个json数组，包含此处描述的格式。

查询历史任务实例 - 响应码

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
     <td> <p> <span>表示请求成功，并返回任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示传递了错误格式的参数。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
  "data": [ 
    { 
      "id" : "5", 
      "processDefinitionId" : "oneTaskProcess%3A1%3A4", 
      "processDefinitionUrl" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4", 
      "processInstanceId" : "3", 
      "processInstanceUrl" : "http://localhost:8182/history/historic-process-instances/3", 
      "executionId" : "4", 
      "name" : "My task name", 
      "description" : "My task description", 
      "deleteReason" : null, 
      "owner" : "kermit", 
      "assignee" : "fozzie", 
      "startTime" : "2013-04-17T10:17:43.902+0000", 
      "endTime" : "2013-04-18T14:06:32.715+0000", 
      "durationInMillis" : 86400056, 
      "workTimeInMillis" : 234890, 
      "claimTime" : "2013-04-18T11:01:54.715+0000", 
      "taskDefinitionKey" : "taskKey", 
      "formKey" : null, 
      "priority" : 50, 
      "dueDate" : "2013-04-20T12:11:13.134+0000", 
      "parentTaskId" : null, 
      "url" : "http://localhost:8182/history/historic-task-instances/5", 
      "taskVariables": [ 
        { 
          "name": "test", 
          "variableScope": "local", 
          "value": "myTest" 
        } 
      ], 
      "processVariables": [ 
        { 
          "name": "processTest", 
          "variableScope": "global", 
          "value": "myProcessTest" 
        } 
      ] 
    } 
  ], 
  "total": 1, 
  "start": 0, 
  "sort": "name", 
  "order": "asc", 
  "size": 1 
}
`

## 删除历史任务实例

`DELETE history/historic-task-instances/{taskId}`

响应码

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
     <td> <p> <span>表似乎删除了历史任务实例。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到历史任务实例。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

