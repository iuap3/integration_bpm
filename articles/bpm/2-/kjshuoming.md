# 控件说明

## 启动事件类

### 启动事件

1、描述

不指定启动流程实例的触发条件。

2、图形标志

![](/articles/bpm/2-/images/image6.png)

3、属性说明

![](/articles/bpm/2-/images/image200.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 1 </p> </td> 
     <td rowspan="3"> <p> 常用 </p> </td> 
     <td> <p> ID </p> </td> 
     <td> <p> 控件的唯一标识 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 名称 </p> </td> 
     <td> <p> 控件的名称 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 说明 </p> </td> 
     <td> <p> 对控件的说明 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="2"> <p> 2 </p> </td> 
     <td rowspan="2"> <p> 实现 </p> </td> 
     <td> <p> 发起人 </p> </td> 
     <td> <p> 填写发起人变量名 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 表单 </p> </td> 
     <td> <p> 填写外接表单的表单ID </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 3 </p> </td> 
     <td> <p> 高级 </p> </td> 
     <td> <p> 执行监听器 </p> </td> 
     <td> <p> 配置执行监听器 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：启动事件的属性说明图

### 定时启动事件

1、描述

按照设定的时间启动流程实例。

2、图形标志

![](/articles/bpm/2-/images/image7.png)

3、属性说明

![](/articles/bpm/2-/images/image201.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 1 </p> </td> 
     <td rowspan="3"> <p> 常用 </p> </td> 
     <td> <p> ID </p> </td> 
     <td> <p> 控件的唯一标识 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 名称 </p> </td> 
     <td> <p> 控件的名称 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 说明 </p> </td> 
     <td> <p> 对控件的说明 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 2 </p> </td> 
     <td rowspan="3"> <p> 实现 </p> </td> 
     <td> <p> 循环时间(例如:R3/PT10H) </p> </td> 
     <td> <p> 设置流程重复启动次数及本次启动到下次启动的事件间隔 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 日期时间(ISO-8601) </p> </td> 
     <td> <p> 配置触发启动事件的时间 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 持续时间(例如:PT5M) </p> </td> 
     <td> <p> 流程部署后定时器之前要等待多长时间启动流程 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 3 </p> </td> 
     <td> <p> 监听 </p> </td> 
     <td> <p> 执行监听 </p> </td> 
     <td> <p> 配置执行监听器 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：定时启动事件的属性说明图

### 错误启动事件

1、描述

错误开始事件可以用来触发一个事件子流程，错误开始事件不能用来启动流程实例。

2、图形标志

![](/articles/bpm/2-/images/image8.png)

3、属性说明

![](/articles/bpm/2-/images/image202.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 1 </p> </td> 
     <td rowspan="3"> <p> 常用 </p> </td> 
     <td> <p> ID </p> </td> 
     <td> <p> 控件的唯一标识 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 名称 </p> </td> 
     <td> <p> 控件的名称 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 说明 </p> </td> 
     <td> <p> 对控件的说明 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 2 </p> </td> 
     <td> <p> 错误 </p> </td> 
     <td> <p> 错误 </p> </td> 
     <td> <p> 定义一个错误，其他错误时间处理器通过该引用捕获这个错误。 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 3 </p> </td> 
     <td> <p> 高级 </p> </td> 
     <td> <p> 执行监听器 </p> </td> 
     <td> <p> 配置执行监听器 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：错误启动事件的属性说明图

## 活动类

### 用户任务

1、描述

用户任务用来设置必须由人员完成的工作。当流程执行到用户任务，会创建一个新任务， 并把这个新任务加入到分配人或群组的任务列表中。

2、图形标志

![](/articles/bpm/2-/images/image9.png)

3、属性说明

![](/articles/bpm/2-/images/image203.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 1 </p> </td> 
     <td rowspan="3"> <p> 常用 </p> </td> 
     <td> <p> ID </p> </td> 
     <td> <p> 控件的唯一标识 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 名称 </p> </td> 
     <td> <p> 控件的名称 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 说明 </p> </td> 
     <td> <p> 对控件的说明 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="5"> <p> 2 </p> </td> 
     <td rowspan="5"> <p> 实现 </p> </td> 
     <td> <p> 办理人 </p> </td> 
     <td> <p> 设置活动的办理人 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 候选办理人 </p> </td> 
     <td> <p> 设置候选办理人后，候选人可以领取任务 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 表单 </p> </td> 
     <td> <p> 设置外接表单的ID </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 到期时间 </p> </td> 
     <td> <p> 设置任务到期时间，可以是具体日期也可以是变量值 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 优先级 </p> </td> 
     <td> <p> 设置优先级，可以是具体的值也可以是变量值 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 3 </p> </td> 
     <td> <p> 监听 </p> </td> 
     <td> <p> 任务监听 </p> </td> 
     <td> <p> 设置任务监听 </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
     <td> <p> 执行监听 </p> </td> 
     <td> <p> 设置执行监听 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="5"> <p> 4 </p> </td> 
     <td rowspan="5"> <p> 多实例 </p> </td> 
     <td> <p> 顺序 </p> </td> 
     <td> <p> 并行执行，顺序执行。并行执行时会一次性产生实例数个实例；顺序执行是指一个任务完成后才会产生下一个任务实例，当完成条件为true时则不再循环产生实例 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 实例数 </p> </td> 
     <td> <p> 可以是动态计算的表达式，也可以是固定值 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 集合 </p> </td> 
     <td> <p> 设置集合 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 成员变量 </p> </td> 
     <td> <p> 设置成员变量 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 完成条件 </p> </td> 
     <td> <p> 多实例时设置任务可以被提交到下一个活动的条件，当条件返回值为true时任务提交到下一个活动 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 5 </p> </td> 
     <td rowspan="3"> <p> 高级 </p> </td> 
     <td> <p> 异步 </p> </td> 
     <td> <p> 是否异步执行 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 独占 </p> </td> 
     <td> <p> 是否独占执行 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 仅用于补偿 </p> </td> 
     <td> <p> 选择为“是”时，如果是边界补偿事件输出流到此用户任务上，到补偿时则执行用户任务，如果不是补偿则不执行该用户任务 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：用户任务的属性说明图

### 脚本任务

1、描述

脚本任务时一个自动节点。当流程到达脚本任务，会执行对应的脚本。

2、图形标志

![](/articles/bpm/2-/images/image10.png)

3、属性说明

![](/articles/bpm/2-/images/image204.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 1 </p> </td> 
     <td rowspan="3"> <p> 常用 </p> </td> 
     <td> <p> ID </p> </td> 
     <td> <p> 控件的唯一标识 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 名称 </p> </td> 
     <td> <p> 控件的名称 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 说明 </p> </td> 
     <td> <p> 对控件的说明 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="2"> <p> 2 </p> </td> 
     <td rowspan="2"> <p> 实现 </p> </td> 
     <td> <p> 脚本格式 </p> </td> 
     <td> <p> 选择脚本格式，目前支持javascript和groovy </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 脚本 </p> </td> 
     <td> <p> 输入脚本信息 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 3 </p> </td> 
     <td> <p> 监听 </p> </td> 
     <td> <p> 执行监听 </p> </td> 
     <td> <p> 配置执行监听 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="5"> <p> 4 </p> </td> 
     <td rowspan="5"> <p> 多实例 </p> </td> 
     <td> <p> 实例类型 </p> </td> 
     <td> <p> 并行执行，顺序执行 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 实例数 </p> </td> 
     <td> <p> 可以是动态计算的表达式，也可以是固定值 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 集合 </p> </td> 
     <td> <p> 设置集合 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 变量 </p> </td> 
     <td> <p> 设置任务变量 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 完成条件 </p> </td> 
     <td> <p> 脚本任务的完成条件 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 5 </p> </td> 
     <td rowspan="3"> <p> 高级 </p> </td> 
     <td> <p> 异步 </p> </td> 
     <td> <p> 是否异步 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 独占 </p> </td> 
     <td> <p> 是否独占执行 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 是否补偿 </p> </td> 
     <td> <p> 选择为“是”时，如果是边界补偿事件输出流到此用户任务上，到补偿时则执行用户任务，如果不是补偿则不执行该用户任务 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：脚本任务的属性说明图

### 服务任务

1、描述

服务任务用来调用外部java类。

2、图形标志

![](/articles/bpm/2-/images/image11.png)

3、属性说明

属性中的多实例和高级属性和监听后面的不再描述，参见用户任务中的描述。

![](/articles/bpm/2-/images/image205.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 1 </p> </td> 
     <td rowspan="3"> <p> 常用 </p> </td> 
     <td> <p> ID </p> </td> 
     <td> <p> 控件的唯一标识 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 名称 </p> </td> 
     <td> <p> 控件的名称 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 说明 </p> </td> 
     <td> <p> 对控件的说明 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="5"> <p> 2 </p> </td> 
     <td rowspan="5"> <p> 实现 </p> </td> 
     <td> <p> 类名称 </p> </td> 
     <td> <p> 系统可以通过该类名对该类进行调用 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 表达式 </p> </td> 
     <td> <p> 可以通过该表达式调用某个对象 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 委托表达式 </p> </td> 
     <td> <p> 定义委托表达式 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 字段 </p> </td> 
     <td> <p> 表达式的参数 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 结果变量 </p> </td> 
     <td> <p> 设置结果变量信息 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：服务任务的属性说明图

### 邮件任务

1、描述

支持了自动邮件任务，它可以发送邮件给一个或多个参与者。

2、图形标志

![](/articles/bpm/2-/images/image12.png)

3、属性说明

属性中的多实例和高级属性和监听后面的不再描述，参见用户任务中的描述。

![](/articles/bpm/2-/images/image206.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 1 </p> </td> 
     <td> <p> 常用 </p> </td> 
     <td> <p> ID </p> </td> 
     <td> <p> 控件的唯一标识 </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
     <td> <p> 名称 </p> </td> 
     <td> <p> 控件的名称 </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
     <td> <p> 说明 </p> </td> 
     <td> <p> 对控件的说明 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 3 </p> </td> 
     <td> <p> 邮件 </p> </td> 
     <td> <p> 收件人 </p> </td> 
     <td> <p> 设置收件人，多个收件人之间用逗号分隔 </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
     <td> <p> 发件人 </p> </td> 
     <td> <p> 设置邮件的发件人。如果邮件服务器配置中配置了默认的发件人，这里可以不设置。 </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
     <td> <p> 主题 </p> </td> 
     <td> <p> 邮件的主题 </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
     <td> <p> 抄送 </p> </td> 
     <td> <p> 设置邮件要抄送给的人员，多人时逗号分隔。 </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
     <td> <p> 密件抄送 </p> </td> 
     <td> <p> 设置密件抄送给的人 </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
     <td> <p> 正文 </p> </td> 
     <td> <p> 设置邮件正文 </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
     <td> <p> 正文(Html) </p> </td> 
     <td> <p> 以Html格式展示的邮件正文形式，支持表达式 </p> </td> 
    </tr> 
    <tr> 
     <td> <p></p> </td> 
     <td> <p></p> </td> 
     <td> <p> 字符编码 </p> </td> 
     <td> <p> 设置邮件的字符编码方式，比如UTF8 </p> </td> 
    </tr> 
   </tbody> 
  </table>

### 手工任务

1、描述

表示工作需要某人完成，而引擎不需要知道，也没有对应的系统和UI接口。

2、图形标志

![](/articles/bpm/2-/images/image13.png)

3、属性说明

属性中的多实例和高级属性和监听后面的不再描述，参见用户任务中的描述。

![](/articles/bpm/2-/images/image207.png)

### 接收任务

1、描述

接收任务是一个简单任务，它会等待对应消息的到达。 当前，我们只实现了这个任务的java语义。 当流程达到接收任务，流程状态会保存到存储里。 意味着流程会等待在这个等待状态， 直到引擎接收了一个特定的消息， 这会触发流程穿过接收任务继续执行。

2、图形标志

![](/articles/bpm/2-/images/image14.png)

3、属性说明

属性中的多实例和高级属性和监听后面的不再描述，参见用户任务中的描述。

![](/articles/bpm/2-/images/image208.png)

### 业务规则任务

1、描述

业务规则用户用来同步执行一个或多个规则。

2、图形标志

![](/articles/bpm/2-/images/image15.png)

3、属性说明

属性中的多实例和高级属性和监听后面的不再描述，参见用户任务中的描述。

![](/articles/bpm/2-/images/image209.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="4"> <p> 1 </p> </td> 
     <td rowspan="4"> <p> 实现 </p> </td> 
     <td> <p> 规则 </p> </td> 
     <td> <p> 具体的业务规则 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 传入变量 </p> </td> 
     <td> <p> 设置传入的变量信息 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 排除 </p> </td> 
     <td> <p> 哪些规则不必执行 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 结果变量 </p> </td> 
     <td> <p> 设置结果变量的信息 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：业务规则任务的属性说明图

### 调用活动

1、描述

调用节点引用流程定义外部的一个流程。

2、图形标志

![](/articles/bpm/2-/images/image18.png)

3、属性说明

属性中的多实例和高级属性和监听后面的不再描述，参见用户任务中的描述。

![](/articles/bpm/2-/images/image210.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 1 </p> </td> 
     <td rowspan="3"> <p> 调用 </p> </td> 
     <td> <p> 被调元素 </p> </td> 
     <td> <p> 被调用的流程ID </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 传入参数 </p> </td> 
     <td> <p> 传给子流程的流程变量 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 传出参数 </p> </td> 
     <td> <p> 子流程传给主流程的流程变量 </p> </td> 
    </tr> 
   </tbody> 
  </table>

### 子流程

1、描述

是一个包含其他节点，网关，事件等等的节点。 它自己就是一个流程，同时是更大流程的一部分。 子流程是完全定义在父流程里的。

2、图形标志

![](/articles/bpm/2-/images/image17.png)

3、属性说明

属性中的多实例和高级属性和监听后面的不再描述，参见用户任务中的描述。

![](/articles/bpm/2-/images/image211.png)

### 事件子流程

1、描述

由事件触发的子流程。

2、图形标志

![](/articles/bpm/2-/images/image16.png)

3、属性说明

属性中的多实例和高级属性和监听后面的不再描述，参见用户任务中的描述。

![](/articles/bpm/2-/images/image212.png)

## 网关类

### 独占网关

1、描述

当流程执行到这个网关，所有外出顺序流都会被处理一遍。 其中条件解析为true的顺序流（或者没有设置条件，概念上在顺序流上定义了一个'true'） 会被选中，让流程继续运行。

2、图形标志

![](/articles/bpm/2-/images/image20.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见用户任务中的描述。

![](/articles/bpm/2-/images/image213.png)

### 并行网关

1、描述

将流程分成多条分支，也可以把多条分支汇聚到一起。

2、图形标志

![](/articles/bpm/2-/images/image19.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见用户任务中的描述。属性见下图：

![](/articles/bpm/2-/images/image214.png)

### 包含网关

1、描述

是独占网关和并行网关的结合体。和独占网关一样，可以在外出顺序流上定义条件，包含网关会解析它们。 但是主要的区别是包含网关可以选择多于一条顺序流，这和并行网关一样。

2、图形标志

![](/articles/bpm/2-/images/image21.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见用户任务中的描述。属性见下图：

![](/articles/bpm/2-/images/image215.png)

### 事件网关

1、描述

据事件判断流向。网关的每个外出顺序流都要连接到一个中间捕获事件。 当流程到达一个基于事件网关，网关会进入等待状态：会暂停执行。 与此同时，会为每个外出顺序流创建相对的事件订阅。

2、图形标志

![](/articles/bpm/2-/images/image22.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见用户任务中的描述。属性见下图：

![](/articles/bpm/2-/images/image216.png)

## 事件类

### 定时边界事件

1、描述

一个暂停等待警告的时钟。当流程执行到绑定了边界事件的环节， 会启动一个定时器。 当定时器触发时（比如，一定时间之后），环节就会中断， 并沿着定时边界事件的外出连线继续执行。

2、图形标志

![](/articles/bpm/2-/images/image23.png)

3、属性说明

属性中的常用，实现和监听后面的不再描述，参见定时启动事件中的描述。属性见下图：

![](/articles/bpm/2-/images/image217.png)

### 错误边界事件

1、描述

定义一个边界错误事件，大多用于内嵌子流程， 或调用节点，对于子流程的情况，它会为所有内部的节点创建一个作用范围。 错误是由错误结束事件抛出的。 这个错误会传递给上层作用域，直到找到一个错误事件定义向匹配的边界错误事件。

2、图形标志

![](/articles/bpm/2-/images/image24.png)

3、属性说明

属性中的常用，实现和监听后面的不再描述，参见错误启动事件中的描述。属性见下图：

![](/articles/bpm/2-/images/image218.png)

### 信号边界事件

1、描述

节点边界的中间捕获信号， 或简称为边界信号事件， 它会捕获信号定义引用的相同信号名的信号。

2、图形标志

![](/articles/bpm/2-/images/image25.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见用户任务中的描述。属性见下图：

![](/articles/bpm/2-/images/image219.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="2"> <p> 1 </p> </td> 
     <td rowspan="2"> <p> 实现 </p> </td> 
     <td> <p> 取消活动 </p> </td> 
     <td> <p> 设置常用属性中的取消为未勾中状态，则运行时自动根据定时器输出流产生新任务，但不会自动完成附属任务的任务，附属任务依然可以继续办理； </p> <p> 设置常用属性中的取消为勾中状态，运行时自动完成附属任务的任务的同时根据定时器输出流产生新的任务。 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 信号引用 </p> </td> 
     <td> <p> 设置引用的信号 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：信号边界事件的属性说明图

### 消息边界事件

1、描述

捕获信号定义引用的相同信号名的信号。

2、图形标志

![](/articles/bpm/2-/images/image26.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见信号边界事件中的描述。属性见下图：

![](/articles/bpm/2-/images/image220.png)

### 补偿边界事件

1、描述

在节点的边界捕获补偿，用来设置一个节点的补偿处理器。

2、图形标志

![](/articles/bpm/2-/images/image27.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见信号边界事件中的描述。属性见下图：

![](/articles/bpm/2-/images/image221.png)

### 定时中间事件（捕获）

1、描述

定时中间事件作为一个监听器。当执行到达捕获事件节点， 就会启动一个定时器。 当定时器触发（比如，一段时间之后），流程就会沿着定时中间事件的外出节点继续执行。

2、图形标志

![](/articles/bpm/2-/images/image28.png)

3、属性说明

属性中的常用，实现和监听后面的不再描述，参见定时启动事件中的描述。属性见下图：

![](/articles/bpm/2-/images/image222.png)

### 信号中间事件（捕获）

1、描述

中间捕获信号事件通过引用信号定义来捕获相同信号名称的信号。

2、图形标志

![](/articles/bpm/2-/images/image29.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见信号边界事件中的描述。属性见下图：

![](/articles/bpm/2-/images/image223.png)

### 消息中间事件（捕获）

1、描述

一个中间捕获消息事件，捕获特定名称的消息。

2、图形标志

![](/articles/bpm/2-/images/image30.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见消息边界事件中的描述。属性见下图：

![](/articles/bpm/2-/images/image224.png)

### 信号中间事件（抛投）

1、描述

中间触发信号事件为定义的信号抛出一个信号事件。

2、图形标志

![](/articles/bpm/2-/images/image31.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见信号边界事件中的描述。属性见下图：

![](/articles/bpm/2-/images/image225.png)

### 补偿中间事件（抛掷）

1、描述

中间触发补偿事件 可以用来触发补偿。

2、图形标志

![](/articles/bpm/2-/images/image32.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见用户任务中的描述。属性见下图：

![](/articles/bpm/2-/images/image226.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 1 </p> </td> 
     <td> <p> 实现 </p> </td> 
     <td> <p> 补偿引用 </p> </td> 
     <td> <p> 补偿内嵌子流程 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：补偿中间事件(抛投)的属性说明图 

## 结束类

### 结束

1、描述

表示（子）流程（分支）的结束。

2、图形标志

![](/articles/bpm/2-/images/image33.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见用户任务中的描述。属性见下图：

![](/articles/bpm/2-/images/image227.png)

### 错误结束

1、描述

当流程执行到错误结束事件，流程的当前分支就会结束，并抛出一个错误。

2、图形标志

![](/articles/bpm/2-/images/image34.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见错误启动事件中的描述。属性见下图：

![](/articles/bpm/2-/images/image228.png)

### 终止结束

1、描述

当到达终止结束事件时，终止事件。

2、图形标志

![](/articles/bpm/2-/images/image35.png)

3、属性说明

属性中的常用和监听后面的不再描述，参见用户任务中的描述。属性见下图：

![](/articles/bpm/2-/images/image229.png)

## 连接类

### 顺序流程

1、描述

顺序流程是连接两个流程节点的连线。 流程执行完一个节点后，会沿着节点的所有外出顺序流继续执行。

2、图形标志

![](/articles/bpm/2-/images/image36.png)

3、属性说明

![](/articles/bpm/2-/images/image230.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="2"> <p> 1 </p> </td> 
     <td rowspan="2"> <p> 实现 </p> </td> 
     <td> <p> 条件 </p> </td> 
     <td> <p> 定义条件表达式 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 缺省 </p> </td> 
     <td> <p> 选择，支持两个外出顺序流会创造两个单独的，并发流程分支 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：顺序流程的属性说明图

### 关联

1、描述

在图元之间建立关联。比如连接注释图元到活动图元。

2、图形标志

![](/articles/bpm/2-/images/image37.png)

3、属性说明

![](/articles/bpm/2-/images/image231.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td rowspan="3"> <p> 1 </p> </td> 
     <td rowspan="3"> <p> 常用 </p> </td> 
     <td> <p> ID </p> </td> 
     <td> <p> 控件唯一标识 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 名称 </p> </td> 
     <td> <p> 控件名称 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 说明 </p> </td> 
     <td> <p> 控件说明 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：关联的属性说明图

## 工件类

### 注释

1、描述

对流程中的元素增加文字注释。

2、图形标志

![](/articles/bpm/2-/images/image38.png)

3、属性说明

![](/articles/bpm/2-/images/image232.png)

<table> 
   <tbody> 
    <tr> 
     <td> <p> No. </p> </td> 
     <td> <p> 属性分类 </p> </td> 
     <td> <p> 属性 </p> </td> 
     <td> <p> 描述 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 1 </p> </td> 
     <td> <p> 常用 </p> </td> 
     <td> <p> ID </p> </td> 
     <td> <p> 控件唯一标识 </p> </td> 
    </tr> 
    <tr> 
     <td> <p> 2 </p> </td> 
     <td> <p> 实现 </p> </td> 
     <td> <p> 文本 </p> </td> 
     <td> <p> 注释内容 </p> </td> 
    </tr> 
   </tbody> 
  </table>

表：注释的属性说明图







