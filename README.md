项目性能测试报告

01-测试目的
主要是让开发者对hero_mall项目的性能负载和容量有个准确的认知。同时，协助技术管理者更好的管
理业务系统性能质量，科学评估业务系统的负荷，拒绝盲目上线。

02-测试工具

03-测试环境
3.1 环境

3.2 设置启动参数

04-测试场景
测试场景一般情况下是都是最重要接口：验证hero_mall服务获取商品信息接口在不同并发规模的表现
情况01-模拟低延时场景，用户访问接口并发逐渐增加的过程。接口的响应时间为20ms，线程梯度：5、
10、15、20、25、30、35、40个线程，5000次;
时间设置：Ramp-up period(inseconds)的值设为对应线程数
测试总时长：约等于20ms x 5000次 x 8 = 800s = 13分
情况02-模拟高延时场景，用户访问接口并发逐渐增加的过程。接口的响应时间为500ms，线程梯度：
100、200、300、400、500、600、700、800个线程，200次;
时间设置：Ramp-up period(inseconds)的值设为对应线程数的1/10；
测试总时长：约等于500ms x 200次 x 8 = 800s = 13分

05-核心接口的测试结果

一、商品详情页涉及到的接口
1、获取商品信息接口
验证hero_mall服务获取商品信息接口能力性能。目标峰值TPS：10000，P99响应时间：300ms
Active Threads：注意压力机的活动线程数并不等同于在线用数中，并发的用户数。压力活动线程数是
用来模拟用户发出并发请求的操作。
压力机-活动线程数 =模拟=> 系统并发用户数
系统并发用户数 =不等于=> 压力机-活动线程数 
TPS、RT

1.1 25Mbps, 3.8KB 

![jmeter-25Mbps-3-8KB-Test](https://user-images.githubusercontent.com/96624836/187077707-efa2c2d8-8543-4000-b711-5fa116227a5d.png)

![jmeter-25Mbps-3-8KB-Threads](https://user-images.githubusercontent.com/96624836/187077974-b748e2ed-689d-4796-bde4-ff6d64c7a2dd.png)

![jmeter-25Mbps-3-8KB-RT](https://user-images.githubusercontent.com/96624836/187078096-8a21307b-27d9-4e8d-a808-abd1be64d896.png)

![jmeter-25Mbps-3-8KB-TPS](https://user-images.githubusercontent.com/96624836/187078002-38d61401-8c77-49e0-a21b-e9ab969cfc0f.png)

![grafana-25Mbps-3-8KB-apache-jmeter-dashboard](https://user-images.githubusercontent.com/96624836/187078111-0c3c9ba8-886b-48e9-8d76-3cfddc9a202e.PNG)

![grafana-25Mbps-3-8KB-jmeter-dashboard](https://user-images.githubusercontent.com/96624836/187078124-7155951d-9fa6-46a7-9a53-b69a4ff49ffc.PNG)

![grafana-25Mbps-3-8KB-node-exporter-1-1](https://user-images.githubusercontent.com/96624836/187078140-a8fb4d0b-d79e-4c58-89ee-b2236caa6723.PNG)

![grafana-25Mbps-3-8KB-node-exporter-1-2](https://user-images.githubusercontent.com/96624836/187078154-734fc93b-ee42-4d30-8c4f-e283d7fa11c7.PNG)

![grafana-25Mbps-3-8KB-node-exporter-1-3](https://user-images.githubusercontent.com/96624836/187078191-e98b4413-d84e-4cf3-97f5-d77c59f3a588.PNG)

![grafana-25Mbps-3-8KB-node-exporter-2-1](https://user-images.githubusercontent.com/96624836/187078222-e01704b2-ce50-48b9-8216-9ca078b3741b.PNG)

![grafana-25Mbps-3-8KB-node-exporter-2-2](https://user-images.githubusercontent.com/96624836/187078237-0700500e-0b95-41b2-a851-8b7181ebf152.PNG)


1.2 25Mbps, 1.1KB 

![jmeter-25Mbps-1-1KB-Test](https://user-images.githubusercontent.com/96624836/187078296-0eabaa06-2a80-4f79-ab77-b8ef3381d2e9.png)

![jmeter-25Mbps-1-1KB-Threads](https://user-images.githubusercontent.com/96624836/187078310-288d473b-9f09-4866-baee-4e98eb4f53a5.png)

![jmeter-25Mbps-1-1KB-RT](https://user-images.githubusercontent.com/96624836/187078344-3633ee3e-a867-4b67-8893-d265bb4d7c2e.png)

![jmeter-25Mbps-1-1KB-TPS](https://user-images.githubusercontent.com/96624836/187078364-a5097c20-f537-47ee-8219-652be300892a.png)

![grafana-25Mbps-1-1KB-apache-jmeter-dashboard](https://user-images.githubusercontent.com/96624836/187078396-a43c6865-c93c-4f84-8c13-0dff40a11f95.PNG)

![grafana-25Mbps-1-1KB-jmeter-dashboard](https://user-images.githubusercontent.com/96624836/187078406-577a0ae4-3398-4008-aa1c-484109589cc2.PNG)

![grafana-25Mbps-1-1KB-node-exporter-1-1](https://user-images.githubusercontent.com/96624836/187078444-fbed46d9-a1cb-4e78-942b-d7ffbe8802d3.PNG)

![grafana-25Mbps-1-1KB-node-exporter-1-2](https://user-images.githubusercontent.com/96624836/187078454-cfcc7c35-c598-4685-b67a-65b5f18081b9.PNG)

![grafana-25Mbps-1-1KB-node-exporter-1-3](https://user-images.githubusercontent.com/96624836/187078468-819f73a7-ddcb-44a1-8d4b-3cd83db1a893.PNG)

![grafana-25Mbps-1-1KB-node-exporter-2-1](https://user-images.githubusercontent.com/96624836/187078483-aa729c09-c605-4f5e-858a-57b608dfc3c3.PNG)

![grafana-25Mbps-1-1KB-node-exporter-2-2](https://user-images.githubusercontent.com/96624836/187078490-0dffdd93-98b3-4de3-abb7-aca391c2a184.PNG)


1.3 100Mbps, 3.8KB 

![jmeter-100Mbps-3-8KB-Test](https://user-images.githubusercontent.com/96624836/187078542-e130adf7-f606-4ede-810c-1ede1d8e7f67.png)

![jmeter-100Mbps-3-8KB-Threads](https://user-images.githubusercontent.com/96624836/187078557-135ea379-ce70-4c24-bdb3-f1c765f25d8e.png)

![jmeter-100Mbps-3-8KB-RT](https://user-images.githubusercontent.com/96624836/187078569-efa29c85-018e-45ef-b932-f9121b18eb72.png)

![jmeter-100Mbps-3-8KB-TPS](https://user-images.githubusercontent.com/96624836/187078591-f254d513-1a1b-4f89-a5d6-df49d759b6ca.png)

![grafana-100Mbps-3-8KB-apache-jmeter-dashboard](https://user-images.githubusercontent.com/96624836/187078713-5a4020cd-96bf-4ee1-8686-2d2d98f444b5.PNG)

![grafana-100Mbps-3-8KB-jmeter-dashboard](https://user-images.githubusercontent.com/96624836/187078756-d6b48f5e-6d9e-4bb1-89fc-50f6483df51d.PNG)

![grafana-100Mbps-3-8KB-node-exporter-1-1](https://user-images.githubusercontent.com/96624836/187078783-40e55df3-3aca-4b26-bfa3-9b7b22dcb174.PNG)

![grafana-100Mbps-3-8KB-node-exporter-1-2](https://user-images.githubusercontent.com/96624836/187078797-3cbcd17b-d861-44e8-b1a4-4037222aca00.PNG)

![grafana-100Mbps-3-8KB-node-exporter-1-3](https://user-images.githubusercontent.com/96624836/187078806-eea2eaa4-dfac-49b3-9abe-8a15536f7ff3.PNG)

![grafana-100Mbps-3-8KB-node-exporter-2-1](https://user-images.githubusercontent.com/96624836/187078819-319958b5-374e-435a-a5f9-ef7c1d8c4391.PNG)

![grafana-100Mbps-3-8KB-node-exporter-2-2](https://user-images.githubusercontent.com/96624836/187078833-1abb265b-260f-4d2a-889a-4bac0febf137.PNG)








