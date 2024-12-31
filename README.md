> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

开发的个人博客系统，有管理员，用户，博主三个角色。



管理员功能有个人中心，用户管理，博主管理，文章分类管理，博主文章管理，系统公告管理，轮播图管理。



博主可以注册登录，修改个人信息，对自己发布的博主文章进行管理操作。



用户可以注册登录，查看管理员发布的公告信息和博主发布的文章信息，还可以对博主文章进行收藏评论以及评论操作。



# 环境要求



1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。 

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA; 

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可 

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS; 

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目 

6.数据库：MySql5.7/8.0等版本均可；





# 技术栈



运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：SpringBoot + MyBatis + Vue + Bootstrap + jQuery





# 使用说明





1.使用Navicat或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件； 

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目； 

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；





# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq 

源码地址：[http://www.codegym.top](http://www.codegym.top/)





# 运行截图

![img](https://img-blog.csdnimg.cn/img_convert/0097c2ac915b87aef615972bda954cda.png)





## 前台

![springboot200个人博客系统的设计与实现8](https://img-blog.csdnimg.cn/img_convert/16058f4e63f70a8d8f818c1173b71cce.png)

![springboot200个人博客系统的设计与实现9](https://img-blog.csdnimg.cn/img_convert/32fba2a73781cad05d8685d23e8677db.png)



## 后台

![springboot200个人博客系统的设计与实现3](https://img-blog.csdnimg.cn/img_convert/7e824dd61c6acb43fe03ee1946559b41.png)

![springboot200个人博客系统的设计与实现4](https://img-blog.csdnimg.cn/img_convert/32c81e9a14d46028f05a067c3e224956.png)

![springboot200个人博客系统的设计与实现5](https://img-blog.csdnimg.cn/img_convert/26138167dbc9ee072deddf12e503dab5.png)

![springboot200个人博客系统的设计与实现6](https://img-blog.csdnimg.cn/img_convert/541490447639474757253703343d40a3.png)

![springboot200个人博客系统的设计与实现7](https://img-blog.csdnimg.cn/img_convert/8d4c18b7f94f2694a57eb08adb3d6122.png)

### 代码

```java
	@IgnoreAuth
    @RequestMapping("/list")
    public R list(@RequestParam Map<String, Object> params,CaipinxinxiEntity caipinxinxi, HttpServletRequest request){
        EntityWrapper<CaipinxinxiEntity> ew = new EntityWrapper<CaipinxinxiEntity>();
		PageUtils page = caipinxinxiService.queryPage(params, MPUtil.sort(MPUtil.between(MPUtil.likeOrEq(ew, caipinxinxi), params), params));
        return R.ok().put("data", page);
    }
```





