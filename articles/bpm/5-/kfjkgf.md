# 开发接口规范

## 用户签名验证

iUAP BPM 审通过使用Access Key ID/Access Key Secret对称加密的方法来验证某个请求的发送者身份。AccessKey ID用于标示用户身份，AccessKeySecret是用户用于加密签名字符串和用来验证签名字符串的密钥，其中AccessKeySecret必须保密，只有用户和U审知道。每个Access Key对（Access KeyID和Access Key Secret）都有active/inactive两种状态。active表明用户可以用此ID对签名验证请求；inactive表明用户暂停此ID对签名验证的功能。

## 公共HTTP投和响应

公共请求头：

<table> 
   <tbody> 
    <tr> 
     <td> <p> <span>名称</span> </p> </td> 
     <td> <p> <span>描述</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>Authorization</span> </p> </td> 
     <td> <p> <span>用于验证请求合法性的认证信息。</span> </p> <p> <span>类型：字符串</span> </p> <p> <span>默认值：无</span> </p> <p> <span>使用场景：非匿名请求</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>Content-Length</span> </p> </td> 
     <td> <p> <span>RFC 2616</span><span>中定义的</span><span>HTTP</span><span>请求内容长度。</span> </p> <p> <span>类型：字符串</span> </p> <p> <span>默认值：无</span> </p> <p> <span>使用场景：需要向</span><span>U审</span><span>提交数据的请求</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>Content-Type</span> </p> </td> 
     <td> <p> <span>RFC 2616</span><span>中定义的</span><span>HTTP</span><span>请求内容类型。</span> </p> <p> <span>类型：字符串</span> </p> <p> <span>默认值：无</span> </p> <p> <span>使用场景：需要向</span><span>U审</span><span>提交数据的请求</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>HTTP 1.1</span><span>协议中规定的</span><span>GMT</span><span>时间，例如：</span><span>Wed, 05 Sep. 2012 23:00:00 GMT</span> </p> <p> <span>类型：字符串</span> </p> <p> <span>默认值：无</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>Host</span> </p> </td> 
     <td> <p> <span>访问</span><span>Host</span><span>值，格式为：</span><span>&lt;name&gt;.bpm.yyuap.com</span><span>。</span> </p> <p> <span>类型：字符串</span> </p> <p> <span>默认值：无</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

公共响应头：

<table> 
   <tbody> 
    <tr> 
     <td> <p> <span>名称</span> </p> </td> 
     <td> <p> <span>描述</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>Content-Length</span> </p> </td> 
     <td> <p> <span>RFC 2616</span><span>中定义的</span><span>HTTP</span><span>请求内容长度。</span> </p> <p> <span>类型：字符串</span> </p> <p> <span>默认值：无</span> </p> <p> <span>使用场景：需要向</span><span>U审</span><span>提交数据的请求</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>Connection</span> </p> </td> 
     <td> <p> <span>标明客户端和</span><span>U审</span><span>服务器之间的链接状态。</span> </p> <p> <span>类型：枚举</span> </p> <p> <span>有效值：</span><span>open | close</span> </p> <p> <span>默认值：无</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>Date</span> </p> </td> 
     <td> <p> <span>HTTP 1.1</span><span>协议中规定的</span><span>GMT</span><span>时间，例如：</span><span>Wed, 05 Sep. 2012 23:00:00 GMT</span> </p> <p> <span>类型：字符串</span> </p> <p> <span>默认值：无</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>ETag</span> </p> </td> 
     <td> <p> <span>ETag (entity tag) </span><span>在每个</span><span>Object</span><span>生成的时候被创建，用于标示一个</span><span>Object</span><span>的内容。对于</span><span>Put Object</span><span>请求创建的</span><span>Object</span><span>，</span><span>ETag</span><span>值是其内容的</span><span>MD5</span><span>值；对于其他方式创建的</span><span>Object</span><span>，</span><span>ETag</span><span>值是其内容的</span><span>UUID</span><span>。</span><span>ETag</span><span>值可以用于检查</span><span>Object</span><span>内容是否发生变化。</span> </p> <p> <span>类型：字符串</span> </p> <p> <span>默认值：无</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>Server</span> </p> </td> 
     <td> <p> <span>生成</span><span>Response</span><span>的服务器。</span> </p> <p> <span>类型：字符串</span> </p> <p> <span>默认值：</span><span>yybpm</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>x-yybpm-request-id</span> </p> </td> 
     <td> <p> <span>x-yybpm-request-id</span><span>是由</span><span>U审</span><span>创建，并唯一标识这个</span><span>response</span><span>的</span><span>UUID</span><span>。如果在使用</span><span>U审</span><span>服务时遇到问题，可以凭借该字段联系</span><span>U审</span><span>工作人员，快速定位问题。</span> </p> <p> <span>类型：字符串</span> </p> <p> <span>默认值：无</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>响应</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>200 - Ok</span> </p> </td> 
     <td> <p> <span>操作成功，响应返回（GET和PUT请求）。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>201 - Created</span> </p> </td> 
     <td> <p> <span>操作成功，实体已创建，并返回到响应体中（POST请求）。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>204 - No content</span> </p> </td> 
     <td> <p> <span>操作成功，实体已删除，不会返回响应体（DELETE请求）。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>401 - Unauthorized</span> </p> </td> 
     <td> <p> <span>操作失败。操作要求设置Authentication头部。如果请求中已经设置了头部，对应的凭证是无效的或者用户不允许执行这个操作。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>403 - Forbidden</span> </p> </td> 
     <td> <p> <span>禁止操作，不要重试。这不是认证和授权的问题，这是禁止操作。比如：删除一个执行中流程的任务是不允许的，无论用户或流程任务的状态。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>404 - Not found</span> </p> </td> 
     <td> <p> <span>操作失败。找不到请求的资源。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>405 - Method not allowed</span> </p> </td> 
     <td> <p> <span>操作失败。使用的资源方法不允许调用。比如：想更新（PUT）已部署的资源会返回405结果。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>409 - Conflict</span> </p> </td> 
     <td> <p> <span>操作失败。更新其他操作应更新的资源，会导致更新不合法。也可以表示一个结合中新创建的资源的id已经存在了。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>415 - Unsupported Media Type</span> </p> </td> 
     <td> <p> <span>操作失败。请求体包含了不支持的媒体类型。当请求体的JSON中包含未知的属性或值时，也会返回这个响应，一般是因为无法处理的错误格式或类型。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>500 - Internal server error</span> </p> </td> 
     <td> <p> <span>操作失败。执行操作时出现了预期外的异常。响应体中包含错误的细节。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>

分页与排序

分页与排序参数可以添加到URL的query-string中（比如http://host/ubpm-web-rest/service/runtime/tasks?sort=name(根据name排序)

分页排序的 查询JSON参数

<table> 
   <thead> 
    <tr> 
     <th> <p> <span>参数</span> </p> </th> 
     <th> <p> <span>默认值</span> </p> </th> 
     <th> <p> <span>描述</span> </p> </th> 
    </tr> 
   </thead> 
   <tbody> 
    <tr> 
     <td> <p> <span>sort</span> </p> </td> 
     <td> <p> <span>根据查询实现而不同</span> </p> </td> 
     <td> <p> <span>查询的名称，对于不同的查询实现，默认值也不同。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>order</span> </p> </td> 
     <td> <p> <span>asc</span> </p> </td> 
     <td> <p> <span>排序的方式，可以为'asc'或'desc'。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>start</span> </p> </td> 
     <td> <p> <span>0</span> </p> </td> 
     <td> <p> <span>分页查询开始的值，默认从0开始。</span> </p> </td> 
    </tr> 
    <tr> 
     <td> <p> <span>size</span> </p> </td> 
     <td> <p> <span>10</span> </p> </td> 
     <td> <p> <span>分页查询每页显示的记录数。默认为10。</span> </p> </td> 
    </tr> 
   </tbody> 
  </table>









