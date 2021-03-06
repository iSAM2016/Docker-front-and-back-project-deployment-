# Docker-front-and-back-project-deployment
Docker环境下的前后端分离项目部署与运维

# 前言

回想起来，从开始慢慢接触*Java*到后来接触到*Spring Boot*，*Spring*等过去也有两年时间了，从最开始刚入实验室到后来的学习Java再到后来开始做*Spring Boot*项目，也算是没少走弯路，虽然实验室里面有学长带着，但是大部分时间还都是看自己。还记得自己在大一的暑假，那时候在家里也没有怎么玩把慕课网上的*Java*入门从第一季到第三季都给完完整整看了一遍（**具体可搜索慕课网 java入门**），现在回想起来那段时间也算是充裕，也想不通当时是怎么的决心。对于慕课网上的学习现在已经学习了200多个小时，也算是最开始入门的地方。

后来就转战到了B站，虽然在大二期间做了一些项目，但是也都是跟在学长的后面，一直没有时间真正补习自己的底子就开始了项目的实战，于是到了大二的暑假申请了留校，在学校放假之后又在学校里面待了一个月将B站上一门Spring Boot项目的入门视频又从基础学习了一遍（B站搜**码匠笔记**），然后后续还学习了*Spring*，*Spring Mvc*，你可能不相信，我是先开始学习Spring Boot 后来再开始学习一些基础的Spring 的原理与基础，虽然现在都忘记的差不多了。

当时做的前后端分离项目不知道算不算是真正意义上的前后端分离项目，因为虽然说是前后端分离，也确实是在前端代码中没有嵌入任何的*Java*代码，但是却都是在一个编译器（Idea）中运行，只不是将前端的代码都放在**resource**目录下，进行映射访问。但是前段时间接触到的就是后端代码在idea中运行，然后前端代码在*VSCode*中使用到**node**进行初始化和运行，觉得确实也算是真正意义上的前后端分离。

就这样的项目学习了几个，也算是有所收获，后来觉得这样的项目太过于单薄，加上之前经常看到一些高并发，高负载，高可用的一些知识，于是这里就来具体介绍一下下面的内容：**Docker环境下的前后端分离项目部署与运维**，主要讲诉的是在Docker环境下配置高可用的持久层**MySql**数据库集群与**Redis**集群来实现缓存处理，后端多后台程序配置上负载均衡与双机热备保证在一个后端节点异或是一个负载均衡出现问题时候仍然能够正常访问。前端配置多个nginx服务器节点，加上nginx进行负载均衡，最后再进行双机热备处理，保证在每一个可能出现问题的关键结点上都有冗余的节点保证访问的可靠性，来模拟出最真实（应该是吧）当代的互联网环境下各大主流网站的配置与部署。

![http://maycope.cn/github-TIM%E5%9B%BE%E7%89%8720200502101127.jpg](http://maycope.cn/github-TIM%E5%9B%BE%E7%89%8720200502101127.jpg)

# 目录

这里我已经将自己所学的全部内容写在了个人的**CSDN**博客上，这里就算是做一个更加系统的概括与轮廓图，也会提供上一些配置文件供大家学习与下载。

* [MySql数据库集群搭建](https://github.com/maycope/Docker-front-and-back-project-deployment-/blob/master/%E6%95%B4%E4%BD%93%E6%80%A7%E6%A6%82%E8%BF%B0/MySql%E6%95%B0%E6%8D%AE%E5%BA%93%E9%9B%86%E7%BE%A4.md)
* [Redis数据库集群搭建](https://github.com/maycope/Docker-front-and-back-project-deployment-/blob/master/%E6%95%B4%E4%BD%93%E6%80%A7%E6%A6%82%E8%BF%B0/Redis%E9%9B%86%E7%BE%A4%E6%90%AD%E5%BB%BA.md)
* [前端项目部署与负载均衡](https://github.com/maycope/Docker-front-and-back-project-deployment-/blob/master/%E6%95%B4%E4%BD%93%E6%80%A7%E6%A6%82%E8%BF%B0/%E5%89%8D%E7%AB%AF%E9%A1%B9%E7%9B%AE%E9%83%A8%E7%BD%B2%E4%B8%8E%E8%B4%9F%E8%BD%BD%E5%9D%87%E8%A1%A1.md)
* [后端项目部署与负载均衡](https://github.com/maycope/Docker-front-and-back-project-deployment-/blob/master/%E6%95%B4%E4%BD%93%E6%80%A7%E6%A6%82%E8%BF%B0/%E5%90%8E%E7%AB%AF%E9%A1%B9%E7%9B%AE%E9%83%A8%E7%BD%B2%E4%B8%8E%E8%B4%9F%E8%BD%BD%E5%9D%87%E8%A1%A1.md)


