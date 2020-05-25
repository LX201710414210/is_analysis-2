# 基于GitHub的实验管理平台的分析与设计
## 1.概述：
- 基于GitHub的实验管理平台的作用是在线管理实验成绩的Web应用系统。学生和老师的实验内容均存放在GitHUB 页面上。
- 学生的功能主要有：一是设置自己的GitHub用户名，二是查询自己的实验成绩。学生的GitHub用户名是公开的，但成绩不公开。
- 老师的功能主要有：一是批改每个学生的成绩，二是查看每个学生的成绩。
- 老师和学生都能通过本系统的链接方便地跳转到学生的每个GitHUB实验目录，以便批改实验或者查看实验情况。
- 实验成绩按数字分数计算，每项实验的满分为100分，最低为0分。
- 系统自动计算每个学生的所有实验的平均分。
## 2.系统总体流程图：
![](.README_images/1.png)
界面设计参见：https://201710414222.github.io/is_analysis_pages/ui1/index.html
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200525180536673.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
## 3.用例图设计：([源码](源码/1.puml))
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200525180536784.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
## 4.类图设计：([源码](源码/2.puml))
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200525180537117.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
## 5.数据库设计：
[参见数据库设计](数据库设计.md)
## 6.用例及界面详细设计
- ["当前学生列表"用例](用例/当前课程学生列表.md),[界面](https://201710414222.github.io/is_analysis_pages/ui1/学生页面.html)

- ["评定课程成绩”用例](用例/评定成绩.md),[界面](https://201710414222.github.io/is_analysis_pages/ui1/评定成绩第一学期软分页面.html)

- ["查看课程成绩”用例](用例/查看成绩.md),[界面](https://201710414222.github.io/is_analysis_pages/ui1/第一学期软分成绩.html)

- ["选择课程和学期”用例](用例/选择课程.md),[界面](https://201710414222.github.io/is_analysis_pages/ui1/选择页面.html)

- ["修改用户信息”用例](用例/修改用户信息用例.md),[界面](https://201710414222.github.io/is_analysis_pages/ui1/修改用户信息.html)

- ["查看用户信息”用例](用例/查看用户信息.md),[界面](https://201710414222.github.io/is_analysis_pages/ui1/查看用户信息.html)

- ["登出”用例](用例/登出.md),[界面](https://201710414222.github.io/is_analysis_pages/ui1/index.html)

- ["登录”用例](用例/登录.md),[界面](https://201710414222.github.io/is_analysis_pages/ui1/登录.html)
