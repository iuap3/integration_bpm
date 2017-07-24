# 租户、子租户与用户管理服务

## 新增租户

`POST identity/ext/tenants`

请求体：

`{

"code ":"Tenant Code",

"name":"Tenant name",

"parent":"Parent ID",

"address ":"Tenant Address",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"Model category",

"enable ":true,

"admin ":"Admin ID"

}`

新建租户 - 响应码

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
     <td> <p> <span>表示成功创建了租户。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{

"id ":"Tenant Id",

"code ":"Tenant Code",

"name":"Tenant name",

"parent":"Parent ID",

"address ":"Tenant Address",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"2015-07-09 12:12:12",

"enable ":true,

"admin ":"Admin ID"

}`

## 更新租户

`POST identity/ext/tenants `

请求体：

`{

"id ":"Tenant Id",

"code ":"Tenant Code",

"name":"Tenant name",

"parent":"Parent ID",

"address ":"Tenant Address",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"2015-07-09 12:12:12",

"enable ":true,

"admin ":"Admin ID"

}`

修改租户 - 响应码 

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
     <td> <p> <span>表示成功更新了租户。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{

"id ":"Tenant Id",

"code ":"Tenant Code",

"name":"Tenant name",

"parent":"Parent ID",

"address ":"Tenant Address",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":2015-07-09 12:12:12",

"enable ":true,

"admin ":"Admin ID"

}`

## 获取指定租户

`GET identity/ext/tenants/{tenantId}`

获得一个租户 - URL参数 

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
     <td> <p> <span>tenantId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望获得的租户id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获得一个租户- 响应码 

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
     <td> <p> <span>表示找到了租户并成功返回了。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的租户。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{

"id ":"Tenant Id",

"code ":"Tenant Code",

"name":"Tenant name",

"parent":"Parent ID",

"address ":"Tenant Address",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"2015-07-09 12:12:12",

"enable ":true,

"admin ":"Admin ID"

}`

## 获取租户列表

`GET query/ext/tenants`

获得租户列表 - URL参数 

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
     <td> <p> <span>tenantId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>指返回指定id的租户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>admin</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定管理员的租户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>name</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定名称的租户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>nameLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定名称匹配的租户。使用</span><span>%</span><span>作为通配符。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>address</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定地址的模型。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>addressLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定地址匹配的租户。使用</span><span>%</span><span>作为通配符。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>createBefore</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回创建时间早于指定时间的租户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>createAfter</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回创建时间晚于指定时间的租户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>modifyBefore</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回修改时间早于指定时间的租户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>modifyAfter</span> </p> </td> 
     <td> <p></p> </td> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>只返回修改时间晚于指定时间的租户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>code</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定code的租户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>codeLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定Code匹配的租户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>enable</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>Boolean</span> </p> </td> 
     <td> <p> <span>如果为&nbsp;true，只返回未启用的租户。如果为&nbsp;false，忽略此</span><span>&nbsp;</span><span>参数。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>sort</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p></p> </td> 
     <td> <p> <span>排序的字段，和'order'一起使用。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>可以使用通用的，分页和排序查询参数</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获得租户列表 - 响应码 

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
     <td> <p> <span>表示请求成功，并返回了租户</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示传递的参数格式错误。状态信息中包含更多信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
   "data":[ 
      {

"id ":"Tenant Id",

"code ":"Tenant Code",

"name":"Tenant name",

"parent":"Parent ID",

"address ":"Tenant Address",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"2015-07-09 12:12:12",

"enable ":true,

"admin ":"Admin ID"

      }, 
   ], 
   "total":2, 
   "start":0, 
   "sort":"id", 
   "order":"asc", 
   "size":2 
}`

## 删除特定租户

`DELETE identity/ext/tenants/{tenantId}`

删除租户 - URL参数 

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
     <td> <p> <span>tenantId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望删除的租户id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

删除租户 - 响应码 

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
     <td> <p> <span>表示找到了租户并成功删除。响应体为空。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的租户。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

## 创建用户

`POST identity/ext/users`

请求体：

`{

"code ":"User Code",

"name":"User name",

"password ":"User password",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"2015-07-09 12:12:12",

"enable ":true,

"tenanted ":"tenanted ID",

"phone ":"phone ",

"sysadmin ":true,

"source ":"source ",

}`

新建用户 - 响应码 

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
     <td> <p> <span>表示成功创建了用户。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{

"id ":"User Id",

"code ":"User Code",

"name":"User name",

"password ":"User password",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"2015-07-09 12:12:12",

"enable ":true,

"tenanted ":"tenanted ID",

"phone ":"phone ",

"sysadmin ":true,

"source ":"source ",

}`

## 更新用户

`POST identity/ext/users`

请求体：

`{

"id ":"User Id",

"code ":"User Code",

"name":"User name",

"password ":"User password",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"2015-07-09 12:12:12",

"enable ":true,

"tenanted ":"tenanted ID",

"phone ":"phone ",

"sysadmin ":true,

"source ":"source ",

}`

修改用户 - 响应码

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
     <td> <p> <span>表示成功更新了用户</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

`{

"id ":"User Id",

"code ":"User Code",

"name":"User name",

"password ":"User password",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"2015-07-09 12:12:12",

"enable ":true,

"tenanted ":"tenanted ID",

"phone ":"phone ",

"sysadmin ":true,

"source ":"source ",

}`

## 获取特定用户

`GET identity/ext/users/{ userId }`

获得一个用户 - URL参数

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
     <td> <p> <span>userId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望获得的用户id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获得一个用户 - 响应码 

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
     <td> <p> <span>表示找到了用户并成功返回了。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的用户。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{

"id ":"User Id",

"code ":"User Code",

"name":"User name",

"password ":"User password",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"2015-07-09 12:12:12",

"enable ":true,

"tenanted ":"tenanted ID",

"phone ":"phone ",

"sysadmin ":true,

"source ":"source ",

}`

## 获取用户列表

`GET query/ext/users`

获得用户列表 - URL参数

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
     <td> <p> <span>Id</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>指返回指定用户Id的用户</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>tenantId</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>指返回指定租户的用户</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>tenantIdLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定租户匹配的用户。使用</span><span>%</span><span>作为通配符。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>name</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定名称的用户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>nameLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定名称匹配的用户。使用</span><span>%</span><span>作为通配符。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>code</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回指定code的用户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>codeLike</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定code匹配的用户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>mail</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定邮箱匹配的用户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>phone</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>只返回与指定手机匹配的用户。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>sort</span> </p> </td> 
     <td> <p> <span>否</span> </p> </td> 
     <td> <p></p> </td> 
     <td> <p> <span>排序的字段，和'order'一起使用。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>可以使用通用的，分页和排序查询参数</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
     <td> <p> <span>&nbsp;</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

获得用户列表 - 响应码

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
     <td> <p> <span>表示请求成功，并返回了用户</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>400</span> </p> </td> 
     <td> <p> <span>表示传递的参数格式错误。状态信息中包含更多信息。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

成功响应体：

`{ 
   "data":[ 
      {

"id ":"User Id",

"code ":"User Code",

"name":"User name",

"password ":"User password",

"createTime ":"2015-07-09 12:12:12",

"modifyTime ":"2015-07-09 12:12:12",

"enable ":true,

"tenanted ":"tenanted ID",

"phone ":"phone ",

" sysadmin ":true,

" source ":"source ",

      }, 
   ], 
   "total":2, 
   "start":0, 
   "sort":"id", 
   "order":"asc", 
   "size":2 
}`

## 删除特定用户

`DELETE identity/ext/users/{userId}
`
删除用户 - URL参数

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
     <td> <p> <span>userId</span> </p> </td> 
     <td> <p> <span>是</span> </p> </td> 
     <td> <p> <span>String</span> </p> </td> 
     <td> <p> <span>希望删除的用户id。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

删除用户 - 响应码

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
     <td> <p> <span>表示找到了用户并成功删除。响应体为空。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404</span> </p> </td> 
     <td> <p> <span>表示找不到请求的用户。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>






















