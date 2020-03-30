# 1. 图书管理系统的用例关系图
## 1.1 用例图PlantUML源码如下：

```csharp
@startuml
管理员-->(图书信息管理)
管理员-->(违者信息管理)
(新书信息录入)-->(图书信息管理):<<include>>
(预约通知)-->(图书信息管理)
(信息通知)-->(违者信息管理):<<include>>
(逾期通知)-->(信息通知):<<include>>
(逾期处罚)-->(逾期通知):<<extend>>
(预约通知)-->(信息通知):<<include>>
读者-->(借书)
读者-->(预约)
读者-->(还书)
(续借)-->(预约)
(续借)-->(借书):<<extend>>
@enduml
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330222547907.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)


### 1.2读者用例图源码如下：
```csharp
@startuml
读者-->(借书)
读者-->(预约)
读者-->(还书)
(续借)-->(预约)
(续借)-->(借书):<<extend>>
@enduml
```
### 1.3管理员用例图源码如下：

```csharp
@startuml
管理员-->(图书信息管理)
管理员-->(违者信息管理)
(新书信息录入)-->(图书信息管理):<<include>>
(预约通知)-->(图书信息管理)
(信息通知)-->(违者信息管理):<<include>>
(逾期通知)-->(信息通知):<<include>>
(逾期处罚)-->(逾期通知):<<extend>>
(预约通知)-->(信息通知):<<include>>
@enduml
```

### 1.4“读者”用例图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330143028203.png)
### 1.5“管理员”用例图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330143134964.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
## 2.参与者说明：
### 2.1读者
```csharp
主要职责是向图书馆借书，预约图书，续借图书以及在规定时间内还书
功能。续借和借书是拓展关系。
```
### 2.2管理员

```csharp
主要职责登记新书的信息到管理系统中，并接收并处理读者预约信息，
以及对逾期违规者处理

```

## 3.用例规约表：
### 3.1“读者”用例：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330145403646.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330150746902.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020033015172846.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330152916534.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
### “借书还书”用例流程图源码如下：

```csharp
@startuml
|借书|
start
:读者输入借阅信息;
if(系统判断?)then(合法)
:借阅成功;
else(非法)
fork
:输入借阅信息不合法
请重新输入;
fork again
:没有该图书;
fork again
:该书已被借出;
end fork
:借阅失败;
endif
:退出系统;
stop
|#AntiqueWhite|还书|
start
:读者归还图书;
if(系统判断逾期?)then(没有)
else(有)
:缴纳罚款;
endif
:归还成功;
stop
|续借|
start
:读者输入续借图书信息;
if(系统判断预约?)then(没有)
:续借成功;
else(有)
:续借失败;
endif
stop
|#AntiqueWhite|预约|
start
:读者输入预约图书信息;
if(系统查询预约记录?)then(没有)
:预约成功;
else(有)
:显示预约排名信息;
endif
stop
@enduml
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330153517253.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
### 3.2“管理员”用例
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330162827974.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020033016115071.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330161836648.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330164400428.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020033016535284.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020033017000793.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330170736861.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
### “管理员”用例流程图源码如下：

```csharp
@startuml
start
:管理员登录系统;
:选择业务;
split
repeat
:新书信息录入;
:填写新书信息录入表;
repeat while(录入是否成功?)
:录入成功;
split again
:逾期通知处理;
:查询已借时间和归还时间;
if(逾期?)then(yes)
:发送逾期通知消息;
:缴纳逾期金额;
else(no)
:不用提醒;
endif
split again
:预约通知处理;
:查询该书籍的情况;
if(是否有人预约)then(yes)
:发送预约排名给读者;
else(no)
if(是否借出)then(yes)
:发送该书已被借出，请等候通知;
else(no)
:切换到借阅界面;
endif
endif
:预约成功;
end split
:退出系统;
stop
@enduml

```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330181138206.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)

