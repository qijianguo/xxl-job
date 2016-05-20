# 分布式任务调度平台xxl-job
github地址：https://github.com/xuxueli/xxl-job

git.osc地址：http://git.oschina.net/xuxueli0323/xxl-job

博客地址(内附使用教程)：http://www.cnblogs.com/xuxueli/p/5021979.html

技术交流群(仅作技术交流)：367260654

# 特点：集群任务调度管理
	1、简单：支持通过Web页面对任务进行CRUD操作，操作简单，一分钟上手；
	2、动态：支持动态修改任务状态，动态暂停/恢复任务，即时生效；
	3、服务HA：任务信息持久化到mysql中，Job服务天然支持集群，保证服务HA；
	4、任务HA：某台Job服务挂掉，任务会平滑分配给其他的某一台存活服务，即使所有服务挂掉，重启时或补偿执行丢失任务；
	5、一个任务只会在其中一台服务器上执行；
	6、任务串行执行；
	7、支持任务执行日志；
	8、支持自定义参数；
	9、支持任务失败次数超阈值邮件报警；
	10、支持在线查看，执行器详细日志；
	11、支持远程任务执行终止；
	12、支持登录验证；
	
# 新版本 V1.1.x，特性【于V1.1.x版本，XXL-JOB正式应用于我司，内部定制别名为 “Ferrari”】
	1、简单：支持通过Web页面对任务进行CRUD操作，操作简单，一分钟上手；
	2、动态：支持动态修改任务状态，动态暂停/恢复任务，即时生效；
	3、服务HA：任务信息持久化到mysql中，Job服务天然支持集群，保证服务HA；
	4、任务HA：某台Job服务挂掉，任务会平滑分配给其他的某一台存活服务，即使所有服务挂掉，重启时或补偿执行丢失任务；
	5、一个任务只会在其中一台服务器上执行；
	6、任务串行执行；
	7、支持自定义参数；
	8、支持远程任务执行终止；

# 新版本 V1.2.x，新特性
	1、支持任务分组；
	2、支持“本地任务”、“远程任务”；
	3、底层通讯支持两种方式，Servlet方式 + JETTY方式；
	4、支持“任务日志”；
	5、支持“串行执行”，并行执行；
	
	说明：V1.2版本将系统架构按功能拆分为：
		调度模块[xxl-job-admin]：负责管理调度信息，按照调度配置发出调度请求；
		任务模块[xxl-job-client-demo]：负责接收调度请求并执行任务逻辑；任务模块可以方便的嵌入web项目，可以参考此demo；
		通讯模块[xxl-job-client]：负责调度模块和任务模块之间的信息通讯；
	优点：
		解耦：任务模块提供任务接口，调度模块维护调度信息，业务相互独立；
		高扩展性；
		稳定性；

# 新版本 V1.3.x，新特性
	1、遗弃“本地任务”模式，推荐使用“远程任务”，易于系统解耦，任务对应的JobHander统称为“执行器”；
	2、遗弃“servlet”方式底层系统通讯，推荐使用JETTY方式，重构通讯逻辑；
	3、UI交互优化：左侧菜单展开状态优化，菜单项选中状态优化，任务列表打开表格有压缩优化；
	4、【重要】“执行器”细分为：BEAN、GLUE两种开发模式，简介见下文：
	
		“执行器” 模式简介：
			BEAN模式执行器：每个执行器都是Spring的一个Bean实例，XXL-JOB通过注解@JobHander识别和调度执行器；
			GLUE模式执行器：每个执行器对应一段代码，在线Web编辑和维护，动态编译生效，执行器负责加载GLUE代码和执行；
		
	
# 其他说明
	清楚僵尸任务：qrtz_cron_triggers、qrtz_triggers、qrtz_job_details顺序删除

# 规划中
	1、任务执行器支持远程加载Groovy；
	
# Tips
	感谢您对XXL-JOB的关注，经过一年时间的完善和发展XXL-JOB已经应用到许多线上产品线，如大数据处理、电商和O2O（如我司大众点评，内部在XXL-JOB的基础上定制更名为Ferrari）...
	更多接入公司，欢迎在https://github.com/xuxueli/xxl-job/issues/1 登记
	
	
![image](http://images2015.cnblogs.com/blog/554415/201605/554415-20160513183306234-1939652116.png)

技术的发展离不开你的支持，请作者喝杯咖啡吧！