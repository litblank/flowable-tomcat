# flowable-tomcat
tomcat启动flowable工作流




## 1、项目介绍
基于flowable-6.4版本。可直接绘制流程，表单，提交发布，生成任务。  
官方的包始终下不下来。放百度云地址：
> 链接: https://pan.baidu.com/s/1oseHaGfFSAlEgUxgvHXxfA 提取码: e24m 

- 包含SQL/数据库的SQL，一般是自动生成
- flowable官方案例/包含XML两个例子

百度云下载的项目放入到tomcat中启动。需要修改：
- 如端口占用需要修改端口
- 如不使用内存数据库，需要修改每个项目中的数据库连接，或者修改需要的项目的连接。

## 2、支持
官方使用文档：https://paulhh.wordpress.com/2017/01/31/flowable-6-instant-gratification/  

springboot 使用文档 https://blog.flowable.org/2018/12/19/building-your-own-flowable-spring-boot-application/


## 3、使用例子
启动后，访问http://localhost:8080/flowable-modeler/#/apps，在应用程序中导入flowable官方案例/官方测试.bar 文件，即可查看流程图，表单。  
访问http://localhost:8080/flowable-task 生成任务。

## 4、flowable6.4 与springboot2 整合遇到的问题
https://juejin.im/post/5c4e6891e51d4521ef1ec7d1

## 5、工作流在项目中的使用 

- 流程根据角色划分，若节点需要某一角色处理。此角色可在代办任务中查询。流程图中节点处理人写角色名称即可。  

- 项目使用的工作流数据库与tomcat启动的工作流数据库为同一个。

- 定义的流程，可以添加表单，将数据记录到表单，最终调用处理结果，每个节点可添加Task listeners 添加处理事件，例如com.exch.platform.modular.flowable.handler.BossTaskHandler类。也可是最终处理事件

- 代办事务中的图表需要需要针对不同的流程单独绘制
