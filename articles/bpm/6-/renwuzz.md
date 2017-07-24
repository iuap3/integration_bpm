# 任务的执行与管理服务

## 获取任务

`GET runtime/tasks/{taskId}
`
获取任务 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望获得的任务id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获取任务 - 响应码

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
     <td> <p> <span>表示找到了任务并返回。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
  "assignee" : "kermit", 
  "createTime" : "2013-04-17T10:17:43.902+0000", 
  "delegationState" : "pending", 
  "description" : "Task description", 
  "dueDate" : "2013-04-17T10:17:43.902+0000", 
  "execution" : "http://localhost:8182/runtime/executions/5", 
  "id" : "8", 
  "name" : "My task", 
  "owner" : "owner", 
  "parentTask" : "http://localhost:8182/runtime/tasks/9", 
  "priority" : 50, 
  "processDefinition" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4", 
  "processInstance" : "http://localhost:8182/runtime/process-instances/5", 
  "suspended" : false, 
  "taskDefinitionKey" : "theTask", 
  "url" : "http://localhost:8182/runtime/tasks/8", 
  "tenantId" : null 
}
`
● delegationState：任务的代理状态。可以为null，"pending" 或 "resolved"。

## 任务列表

`GET runtime/tasks
`
任务列表 - URL参数

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
     <td> <p> <span>name</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定的名称。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>nameLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定名称匹配的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>description</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定描述的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>priority</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Integer</span> </p> </td> 
     <td> <p> <span>只返回指定优先级的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>minimumPriority</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Integer</span> </p> </td> 
     <td> <p> <span>只返回比指定优先级大的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>maximumPriority</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Integer</span> </p> </td> 
     <td> <p> <span>只返回比指定优先级小的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>assignee</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回分配给指定用户的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>assigneeLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回负责人与指定值匹配的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>owner</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回原拥有人为指定用户的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>ownerLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回原拥有人与指定值匹配的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>unassigned</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>只返回没有分配给任何人的任务。如果传递false，这个值就会被忽略。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>delegationState</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定代理状态的任务。可选值为pending&nbsp;和&nbsp;resolved。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>candidateUser</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回可以被指定用户领取的任务。这包含将用户设置为直接候选人和用户作为候选群组一员的情况。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>candidateGroup</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回可以被指定群组中用户领取的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>candidateGroups</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回可以被指定群组列表中用户领取的任务。数值使用逗号分隔。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>involvedUser</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定用户参与过的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskDefinitionKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定任务定义id的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>taskDefinitionKeyLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回任务定义id与指定值匹配的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processInstanceId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回作为指定id的流程实例的一部分的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processInstanceBusinessKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回作为指定key的流程实例的一部分的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processInstanceBusinessKeyLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回业务key与指定值匹配的流程实例的一部分的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionKey</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回作为指定流程定义key的流程实例的一部分的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionKeyLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定流程定义key与指定值匹配的流程实例的一部分的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionName</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回作为指定流程定义名称的流程实例的一部分的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>processDefinitionNameLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回流程定义名称与指定值匹配的流程实例的一部分的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>executionId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回作为指定id分支的一部分的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>createdOn</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>ISO Date</span> </p> </td> 
     <td> <p> <span>只返回指定创建时间的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>createdBefore</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>ISO Date</span> </p> </td> 
     <td> <p> <span>只返回在指定时间之前创建的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>createdAfter</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>ISO Date</span> </p> </td> 
     <td> <p> <span>只返回在指定时间之后创建的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>dueOn</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>ISO Date</span> </p> </td> 
     <td> <p> <span>只返回指定持续时间的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>dueBefore</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>ISO Date</span> </p> </td> 
     <td> <p> <span>只返回持续时间在指定时间之前的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>dueAfter</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>ISO Date</span> </p> </td> 
     <td> <p> <span>只返回持续时间在指定时间之后的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>withoutDueDate</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>boolean</span> </p> </td> 
     <td> <p> <span>只返回没有设置持续时间的任务。如果值为false就会忽略这个属性。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>excludeSubTasks</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>只返回非子任务的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>active</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>如果为&nbsp;true，只返回未挂起的任务（作为未挂起流程的一部分，或者不属于任何流程）。如果为false，只返回作为挂起流程一部分的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>includeTaskLocalVariables</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>Indication to include task local variables in the result.</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>includeProcessVariables</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>表示在结果中包含变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>tenantId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定tenantId的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>tenantIdLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定tenantId匹配的任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>withoutTenantId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>如果为&nbsp;true，只返回未设置tenantId的任务。如果为&nbsp;false，会忽略&nbsp;withoutTenantId&nbsp;参数。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>candidateOrAssigned</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>选择已经被领取，或分配给某个用户，或者可以被用户领取（候选用户或组）。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>可以使用通用的&nbsp;</span><a href="http://www.mossle.com/docs/activiti/index.html%22 \l %22restPagingAndSort%22 \o %22%E5%88%86%E9%A1%B5%E4%B8%8E%E6%8E%92%E5%BA%8F"><span>分页和排序查询参数</span></a><span>&nbsp;。</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

任务列表 - 响应码 

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
     <td> <p> <span>表示传递的参数格式错误，或'delegationState'使用了不合法的数据('pending' 和 'resolved'以外的数据)。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{  "data": [  {  "assignee" : "kermit",  "createTime" : "2013-04-17T10:17:43.902+0000",  "delegationState" : "pending",  "description" : "Task description",  "dueDate" : "2013-04-17T10:17:43.902+0000",  "execution" : "http://localhost:8182/runtime/executions/5",  "id" : "8",  "name" : "My task",  "owner" : "owner",  "parentTask" : "http://localhost:8182/runtime/tasks/9",  "priority" : 50,  "processDefinition" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4",  "processInstance" : "http://localhost:8182/runtime/process-instances/5",  "suspended" : false,  "taskDefinitionKey" : "theTask",  "url" : "http://localhost:8182/runtime/tasks/8",  "tenantId" : null  }  ],  "total": 1,  "start": 0,  "sort": "name",  "order": "asc",  "size": 1 }`

## 查询任务

`POST query/tasks`

请求体：

`{  "name" : "My task",  "description" : "The task description",

 "taskVariables" : [  {  "name" : "myVariable",  "value" : 1234,  "operation" : "equals",  "type" : "long"  }  ],  "processInstanceVariables" : [  {  ...  }  ]  ] }`

查询任务 - 响应码

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
     <td> <p> <span>表示传递了格式错误的参数，或'delegationState'传递了非法数据 ( 'pending' 和 'resolved'之外的值)。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
  "data": [ 
    { 
      "assignee" : "kermit", 
      "createTime" : "2013-04-17T10:17:43.902+0000", 
      "delegationState" : "pending", 
      "description" : "Task description", 
      "dueDate" : "2013-04-17T10:17:43.902+0000", 
      "execution" : "http://localhost:8182/runtime/executions/5", 
      "id" : "8", 
      "name" : "My task", 
      "owner" : "owner", 
      "parentTask" : "http://localhost:8182/runtime/tasks/9", 
      "priority" : 50, 
      "processDefinition" : "http://localhost:8182/repository/process-definitions/oneTaskProcess%3A1%3A4", 
      "processInstance" : "http://localhost:8182/runtime/process-instances/5", 
      "suspended" : false, 
      "taskDefinitionKey" : "theTask", 
      "url" : "http://localhost:8182/runtime/tasks/8", 
          "tenantId" : null 
    } 
  ], 
  "total": 1, 
  "start": 0, 
  "sort": "name", 
  "order": "asc", 
  "size": 1 
}
`
## 更新任务

`PUT runtime/tasks/{taskId}
`
请求JSON体：

`{ 
  "assignee" : "assignee", 
  "delegationState" : "resolved", 
  "description" : "New task description", 
  "dueDate" : "2013-04-17T13:06:02.438+02:00", 
  "name" : "New task name", 
  "owner" : "owner", 
  "parentTaskId" : "3", 
  "priority" : 20 
}
`
所有请求参数都是可选的。比如，你可以在请求体的JSON对象中只包含'assignee'属性，只更新任务的负责人，其他字段都不填。当包含的字段值为null时，任务的对应属性会被更新为null。比如：{"dueDate" : null}会清空任务的持续时间。

更新任务 - 响应码

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
     <td> <p> <span>表示成功更新了任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>409</span> </p> </td> 
     <td> <p> <span>表示请求的任务正在被更新。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体： 参考runtime/tasks/{taskId}的响应。

## 操作任务

`POST runtime/tasks/{taskId}
`
完成任务 - JSON体：

`{ 
  "action" : "complete", 
  "variables" : ... 
}
`
完成任务。可以使用variables参数传递可选的variable数组，此处忽略变量作用域，变量会设置到上级作用域，除非本地作用域应包含了同名变量。这与TaskService.completeTask(taskId, variables) 的行为是相同的。

认领任务 - JSON体：

`{ 
  "action" : "claim", 
  "assignee" : "userWhoClaims" 
}
`
根据指定的assignee认领任务。如果assignee为null，任务的执行人会变成空，又可以重新认领了。

代理任务 - JSON体：

`{ 
  "action" : "delegate", 
  "assignee" : "userToDelegateTo" 
}
`
指定assignee代理任务。assignee是必填项。

前加签任务 - JSON体：

`{ 
  "action" : " counterSignAdd", 
  "assignees" : "[]" 
}
`
指定assignees加签出任务。assignees是必填项。

代办任务 - JSON体：

`{ 
  "action" : "delegateCompletely", 
  "assignee" : "userToDelegateTo" 
}
`
指定assignee代办任务。assignee是必填项。

处理任务 - JSON体：

`{ 
  "action" : "resolve" 
}
`
处理任务代理。任务会返回给任务的原负责人（如果存在）。

操作任务 - 响应码

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
     <td> <p> <span>表示操作成功执行。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>当请求包含了非法数据或当操作需要assignee参数时，却没有传。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>409</span> </p> </td> 
     <td> <p> <span>表示因为冲突导致无法执行操作。可能任务正在被更新，或者，在'</span><span>claim</span><span>'认清任务时，任务已经被其他用户认领了。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体： 参考runtime/tasks/{taskId}的响应。

## 删除任务

`DELETE runtime/tasks/{taskId}?cascadeHistory={cascadeHistory}&deleteReason={deleteReason}
`
删除任务 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望删除的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>cascadeHistory</span> </p> </td> 
     <td> <p> <span>False</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>删除任务时是否删除对应的任务历史（如果存在）。如果没有设置这个参数，默认为false。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>deleteReason</span> </p> </td> 
     <td> <p> <span>False</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>删除任务的原因。</span><span>cascadeHistory</span><span>为true时，忽略此参数。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

删除任务 - 响应码 

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
     <td> <p> <span>表示找到任务，并成功删除。响应体为空。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>403</span> </p> </td> 
     <td> <p> <span>表示无法删除任务，因为它是流程的一部分。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 获得任务的变量

`GET runtime/tasks/{taskId}/variables?scope={scope}`

获得任务的变量 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>变量对应的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>scope</span> </p> </td> 
     <td> <p> <span>False</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>返回的变量作用于。如果为 '</span><span>local</span><span>'，只返回任务本身的变量。如果为 '</span><span>global</span><span>'，只返回任务上级分支的变量。如果不指定这个变量，会返回所有局部和全局的变量。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获得任务的变量 - 响应码 

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
     <td> <p> <span>表示找到了任务并返回了请求的变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`[ 
  { 
    "name" : "doubleTaskVar", 
    "scope" : "local", 
    "type" : "double", 
    "value" : 99.99 
  }, 
  { 
    "name" : "stringProcVar", 
    "scope" : "global", 
    "type" : "string", 
    "value" : "This is a ProcVariable" 
  }, 

  ... 

]
`

## 获取任务的一个变量

`GET runtime/tasks/{taskId}/variables/{variableName}?scope={scope}
`
获取任务的一个变量 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>获取变量对应的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>variableName</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>获取变量对应的名称。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>scope</span> </p> </td> 
     <td> <p> <span>False</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>返回的变量作用于。如果为 'local'，只返回任务本身的变量。如果为 'global'，只返回任务上级分支的变量。如果不指定这个变量，会返回所有局部和全局的变量。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获取任务的一个变量 - 响应码

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
     <td> <p> <span>表示找到了任务并返回了请求的变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或者任务不包含指定名称的变量（在指定作用域下）。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
  "name" : "myTaskVariable", 
  "scope" : "local", 
  "type" : "string", 
  "value" : "Hello my friend" 
}
`
## 获取变量的二进制数据

`GET runtime/tasks/{taskId}/variables/{variableName}/data?scope={scope}
`
获取变量的二进制数据 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>获取变量数据对应的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>variableName</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>获取数据对应的变量名称。只能使用&nbsp;</span><span>binary</span><span>&nbsp;和&nbsp;</span><span>serializable</span><span>&nbsp;类型的变量。如果使用了其他类型的变量，会返回&nbsp;</span><span>404</span><span>&nbsp;。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>scope</span> </p> </td> 
     <td> <p> <span>False</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>返回的变量作用于。如果为 '</span><span>local</span><span>'，只返回任务本身的变量。如果为 '</span><span>global</span><span>'，只返回任务上级分支的变量。如果不指定这个变量，会返回所有局部和全局的变量。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获取变量的二进制数据 - 响应码 

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
     <td> <p> <span>表示找到了任务并返回了请求的变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或者任务不包含指定名称的变量（在指定作用域下），或变量的二进制流不可用。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体： 响应体包含了变量的二进制值。当类型为 binary时，无论请求的accept-type头部设置了什么值，响应的content-type都为application/octet-stream。当类型为 serializable时， content-type为application/x-java-serialized-object。

## 创建任务变量

`POST runtime/tasks/{taskId}/variables
`

创建任务变量 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>创建新变量对应的任务id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

创建简单（非二进制）变量的请求体：

`[ 
  { 
    "name" : "myTaskVariable", 
    "scope" : "local", 
    "type" : "string", 
    "value" : "Hello my friend" 
  }, 
  { 
    ... 
  } 
]
`
请求体应该是包含一个或多个JSON对象的数组，对应应该创建的变量。

● name：必须的变量名称。

● scope:创建的变量的作用域。如果忽略，假设为local。

● type：创建的变量的类型。如果忽略，转换为对应的JSON的类型 (string, boolean, integer 或 double)。

● value：变量值。

成功响应体：

`[ 
  { 
    "name" : "myTaskVariable", 
    "scope" : "local", 
    "type" : "string", 
    "value" : "Hello my friend" 
  }, 
  { 
    ... 
  } 
]
`
创建任务变量 - 响应码

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
     <td> <p> <span>表示创建了变量，并返回了结果。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示没有传变量名，或尝试使用global作用域为独立任务（没有关联到流程）创建变量，或请求中的变量为空，或请求没有包含变量数组。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>409</span> </p> </td> 
     <td> <p> <span>表示任务已经存在指定名称的变量了。可以使用PUT方法来更新任务变量。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 创建二进制任务变量

`POST runtime/tasks/{taskId}/variables
`
创建二进制任务变量 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>创建新变量对应的任务id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

请求体： 请求应该是multipart/form-data类型。应该只有一个文件区域，包含源码的二进制内容。除此之外，需要提供以下表单域：

name：必须的变量名称。

scope：创建的变量的作用域。如果忽略，假设使用 local。

type：创建的变量类型。如果忽略，会假设使用binary，请求的二进制数据会当做二进制数组保存起来。

成功响应体：

`{ 
  "name" : "binaryVariable", 
  "scope" : "local", 
  "type" : "binary", 
  "value" : null, 
  "valueUrl" : "http://.../runtime/tasks/123/variables/binaryVariable/data" 
}
`
创建二进制任务变量 - 响应码

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
     <td> <p> <span>表示创建了变量，并返回了结果。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示没有传变量名，或尝试使用</span><span>global</span><span>作用域为独立任务（没有关联到流程）创建变量。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>409</span> </p> </td> 
     <td> <p> <span>表示任务已经存在指定名称的变量了。可以使用PUT方法来更新任务变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>415</span> </p> </td> 
     <td> <p> <span>表示序列化数据包含的对象的类并不在运行Activiti引擎的JVM中，所以无法反序列化。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 更新任务的一个已有变量

`PUT runtime/tasks/{taskId}/variables/{variableName}`

更新任务的一个已有变量 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望更新的变量对应的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>variableName</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望更新的变量名称。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

更新简单（非二进制）变量的请求体：

`{ 
  "name" : "myTaskVariable", 
  "scope" : "local", 
  "type" : "string", 
  "value" : "Hello my friend" 
}
`
● name：必须的变量名称。

● scope：更新的变量的作用域。如果忽略，假设为local。

● type：更新的变量的类型。如果忽略，转换为对应的JSON的类型 (string, boolean, integer 或 double)。

● value：变量值。

成功响应体：

{ 
  "name" : "myTaskVariable", 
  "scope" : "local", 
  "type" : "string", 
  "value" : "Hello my friend" 
}

更新任务的一个已有变量 - 响应码

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
     <td> <p> <span>表示成功更新了变量并返回了结果。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示没有传变量名，或尝试使用global作用域为独立任务（没有关联到流程）创建变量。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或任务在指定作用域不包含指定名称的变量。状态信息包含错误的详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 更新一个二进制任务变量

PUT runtime/tasks/{taskId}/variables/{variableName}

更新一个二进制任务变量 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望更新的变量对应的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>variableName</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望更新的变量名称。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

请求体： 请求应该是multipart/form-data类型。应该只有一个文件区域，包含源码的二进制内容。除此之外，需要提供以下表单域：

● name：必须的变量名称。

● scope：创建的变量的作用域。如果忽略，假设使用 local。

● type：创建的变量类型。如果忽略，会假设使用binary，请求的二进制数据会当做二进制数组保存起来。

成功响应体：

`{ 
  "name" : "binaryVariable", 
  "scope" : "local", 
  "type" : "binary", 
  "value" : null, 
  "valueUrl" : "http://.../runtime/tasks/123/variables/binaryVariable/data" 
}
`
更新一个二进制任务变量 - 响应码

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
     <td> <p> <span>表示更新了变量，并返回了结果。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示没有传变量名，或尝试使用global作用域为独立任务（没有关联到流程）创建变量。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或任务在指定作用域不包含指定名称的变量。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>415</span> </p> </td> 
     <td> <p> <span>表示序列化数据包含的对象的类并不在运行Activiti引擎的JVM中，所以无法反序列化。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 删除任务变量

`DELETE runtime/tasks/{taskId}/variables/{variableName}?scope={scope}
`
删除任务变量 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望删除的变量对应的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>variableName</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望删除的变量名称。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>scope</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望删除的变量的作用域。可以是local&nbsp;或&nbsp;global。如果忽略，假设为local。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

删除任务变量 - 响应码

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
     <td> <p> <span>表示找到了任务变量，并成功删除。响应体为空。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或任务不包含指定名称的变量。状态信息包含错误的详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 删除任务的所有局部变量

`DELETE runtime/tasks/{taskId}/variables
`
删除任务的所有局部变量 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望删除的变量对应的任务id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

删除任务的所有局部变量 - 响应码

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
     <td> <p> <span>表示已经删除了任务的所有局部变量。响应体为空。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 为任务创建评论

`POST runtime/tasks/{taskId}/comments
`
为任务创建评论 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>创建评论对应的任务id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

请求体：

`{ 
  "message" : "This is a comment on the task.", 
  "saveProcessInstanceId" : true 
}

saveProcessInstanceId参数是可选的，如果为 true 会为评论保存任务的流程实例id。

成功响应体：

{ 
  "id" : "123", 
  "taskUrl" : "http://localhost:8081/activiti-rest/service/runtime/tasks/101/comments/123", 
  "processInstanceUrl" : "http://localhost:8081/activiti-rest/service/history/historic-process-instances/100/comments/123", 
  "message" : "This is a comment on the task.", 
  "author" : "kermit", 
  "time" : "2014-07-13T13:13:52.232+08:00" 
  "taskId" : "101", 
  "processInstanceId" : "100" 
}
`
为任务创建评论 - 响应码

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
     <td> <p> <span>表示创建了评论，并返回了结果。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示请求不包含评论。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
    </tr> 
   </tbody> 
  </table>

## 获得任务的所有评论

`GET runtime/tasks/{taskId}/comments
`
获得任务的所有评论 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>获取评论对应的任务id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`[ 
  { 
    "id" : "123", 
    "taskUrl" : "http://localhost:8081/activiti-rest/service/runtime/tasks/101/comments/123", 
    "processInstanceUrl" : "http://localhost:8081/activiti-rest/service/history/historic-process-instances/100/comments/123", 
    "message" : "This is a comment on the task.", 
    "author" : "kermit" 
    "time" : "2014-07-13T13:13:52.232+08:00" 
    "taskId" : "101", 
    "processInstanceId" : "100" 
  }, 
  { 
    "id" : "456", 
    "taskUrl" : "http://localhost:8081/activiti-rest/service/runtime/tasks/101/comments/456", 
    "processInstanceUrl" : "http://localhost:8081/activiti-rest/service/history/historic-process-instances/100/comments/456", 
    "message" : "This is another comment on the task.", 
    "author" : "gonzo", 
    "time" : "2014-07-13T13:13:52.232+08:00" 
    "taskId" : "101", 
    "processInstanceId" : "100" 
  } 
]
`
获得任务的所有评论 - 响应码

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
     <td> <p> <span>表示找到了任务，并返回了评论。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 获得任务的一个评论

`GET runtime/tasks/{taskId}/comments/{commentId}
`
获得任务的一个评论 - URL参数

成功响应体：

`{ 
  "id" : "123", 
  "taskUrl" : "http://localhost:8081/activiti-rest/service/runtime/tasks/101/comments/123", 
  "processInstanceUrl" : "http://localhost:8081/activiti-rest/service/history/historic-process-instances/100/comments/123", 
  "message" : "This is a comment on the task.", 
  "author" : "kermit", 
  "time" : "2014-07-13T13:13:52.232+08:00" 
  "taskId" : "101", 
  "processInstanceId" : "100" 
}
`
获得任务的一个评论 - 响应码

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
     <td> <p> <span>表示找到了任务和评论，并返回了评论。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或任务不包含指定id的评论。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 删除任务的一条评论

`DELETE runtime/tasks/{taskId}/comments/{commentId}`

删除任务的一条评论 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>删除评论对应的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>commentId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>评论的id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

删除任务的一条评论 - 响应码

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
     <td> <p> <span>表示找到了任务和评论，并删除了评论。响应体为空。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或任务不包含id的评论。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 为任务创建一个附件，包含附件文件

`POST runtime/tasks/{taskId}/attachments
`
为任务创建一个附件，包含附件文件 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>创建附件对应的任务id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

请求体： 请求应该是multipart/form-data类型。应该只有一个文件区域，包含源码的二进制内容。除此之外，需要提供以下表单域：

● name：必须的变量名称。

● description：附件的描述，可选。

● type：创建的变量类型。如果忽略，会假设使用binary，请求的二进制数据会当做二进制数组保存起来。

成功响应体：

{ 
      "id":"5", 
      "url":"http://localhost:8182/runtime/tasks/2/attachments/5", 
      "name":"Binary attachment", 
      "description":"Binary attachment description", 
      "type":"binaryType", 
      "taskUrl":"http://localhost:8182/runtime/tasks/2", 
      "processInstanceUrl":null, 
      "externalUrl":null, 
      "contentUrl":"http://localhost:8182/runtime/tasks/2/attachments/5/content" 
   }

为任务创建一个附件，包含附件文件 - 响应码

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
     <td> <p> <span>表示创建了附件，并返回了结果。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示请求中缺少附件名称，或请求中未包含文件。错误信息中包含了详细信息。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 获得任务的所有附件

GET runtime/tasks/{taskId}/attachments

获得任务的所有附件 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>获取附件对应的任务id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`[  {  "id":"3",  "url":"http://localhost:8182/runtime/tasks/2/attachments/3",  "name":"Simple attachment",  "description":"Simple attachment description",  "type":"simpleType",  "taskUrl":"http://localhost:8182/runtime/tasks/2",  "processInstanceUrl":null,  "externalUrl":"http://activiti.org",  "contentUrl":null  },  {  "id":"5",  "url":"http://localhost:8182/runtime/tasks/2/attachments/5",  "name":"Binary attachment",  "description":"Binary attachment description",  "type":"binaryType",  "taskUrl":"http://localhost:8182/runtime/tasks/2",  "processInstanceUrl":null,  "externalUrl":null,  "contentUrl":"http://localhost:8182/runtime/tasks/2/attachments/5/content"  } ]
`
获得任务的所有附件 - 响应码

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
     <td> <p> <span>表示找到了任务，并返回了附件。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 获得任务的一个附件

`GET runtime/tasks/{taskId}/attachments/{attachmentId}`

 获得任务的一个附件 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>获取附件对应的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>attachmentId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>附件的id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

  { 
    "id":"5", 
    "url":"http://localhost:8182/runtime/tasks/2/attachments/5", 
    "name":"Binary attachment", 
    "description":"Binary attachment description", 
    "type":"binaryType", 
    "taskUrl":"http://localhost:8182/runtime/tasks/2", 
    "processInstanceUrl":null, 
    "externalUrl":null, 
    "contentUrl":"http://localhost:8182/runtime/tasks/2/attachments/5/content" 
  }

● externalUrl - contentUrl：如果附件是一个外部资源链接，externalUrl包含外部内容的URL。如果附件内容保存在Activiti引擎中，contentUrl会包含获取二进制流内容的URL。

● type：可以是任何有效值。包含一个格式合法的media-type时（比如application/xml, text/plain），二进制HTTP响应的content-type会被设置为对应值。

获得任务的一个附件 - 响应码

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
     <td> <p> <span>表示找到了任务和附件，并返回了附件。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或任务不包含对应id的附件。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 获取附件的内容

GET runtime/tasks/{taskId}/attachment/{attachmentId}/content

获取附件的内容 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>获取附件数据对应的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>attachmentId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>附件的id，当附件指向外部URL，而不是Activiti中的内容，就会返回</span><span>404</span><span>。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获取附件的内容 - 响应码 

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
     <td> <p> <span>表示找到了任务和附件，并返回了请求的内容。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或任务不包含对应id的任务，或附件不包含二进制流。状态信息包含了详细信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体： 响应体包含了二进制内容。默认，响应的content-type设置为application/octet-stream，除非附件类型包含了合法的Content-Type。

## 删除任务的一个附件

`DELETE runtime/tasks/{taskId}/attachments/{attachmentId}
`
删除任务的一个附件 - URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望删除附件对应的任务id。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>attachmentId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>附件的id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

删除任务的一个附件 - 响应码

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
     <td> <p> <span>表示找到了任务和附件，并删除了附件。响应体为空。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或任务不包含对应id的附件。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 任务撤回

`DELETE runtime/ext/jump/{taskId}
`
任务撤回- URL参数

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
     <td> <p> <span>taskId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望执行撤回任务的任务id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

任务撤回- 响应码

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
     <td> <p> <span>任务撤回成功。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到任务，或任务不包含对应id的任务。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>







