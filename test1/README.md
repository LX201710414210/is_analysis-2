# 《期末考试流程图》要点总结
### 1.确定泳道为4个，分别为其表明2种颜色
### 2.在教师泳道出卷处，此时应该有并行(fork)写入A、B试卷，打印审批表。
### 3.在不及格处应用if语句判断输出，末尾没流程时加入detach结束。
- 代码如下`@startuml|教务处|start:安排考试;:考试安排表;|#AntiqueWhite|教师|:出卷;fork :A、B试卷forkagain:打印审批表;|系主任|:审批签字;:打印审批表;end fork|教务处|:打印试卷;:试卷;|#AntiqueWhite|学生|:参加考试;:答卷;|#AntiqueWhite|教师|:阅卷出成绩;fork:成绩单;|教务处|if(有不合格？)then(yes)
endif:安排补考;:补考安排表;fork again|#AntiqueWhite|教师|:答卷;:装订存档;end fork:期末流程结束;stop
@enduml
- 截图如下：
- ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200309193253723.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
- # 《客户维修服务流程》要点总结
##  1.确定泳道为4个
## 2.在判断是否为新客户采用if语句,endif结束。随后在后面写上上门勘察。
## 3.在安排工人以及安排材料处采用并行fork语句一起执行
## 4.注意每个流程是在那个泳道下执行的。
- 代码如下：@startuml|客户|start:申请服务;|#AntiqueWhite|业务经理|if(是新客户)then(是):登记客户信息;else(不是)endif:上门勘察;:制定方案;|客户|if(满意吗？)then(否)stopelse(是):签到服务合同;endif|#AntiqueWhite|业务经理|fork:安排工人;fork again:安排材料;end fork:填写派工单;|工人|:领取材料;:上门服务;|客户|:验收并填写反馈意见;|#AntiqueWhite|业务经理|:交回派工单;|#AntiqueWhite|财务人员|:结算验收;stop@enduml
-  截图如下：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200309200210824.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)


