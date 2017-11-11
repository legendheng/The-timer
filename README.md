## Windows制作定时器(以xampp集成环境为例子)
### 第一步、新建一个.bat的文件（定时器脚本），一个.php文件（定时内容），建议放在xampp的运行目录下，既xampp\htdocs目录下
* 首先编写bat文件的格式为
```php
"D:\xampp\php\php.exe" -f "D:\xampp\htdocs\test.php"
```
* 然后编写定时执行的php内容，例如：定时插一条数据
```php
<?php
$conn=mysqli_connect('','','');
mysqli_set_charset($conn,'utf8');
if(!$conn){
echo 'error';
}else{
$sql='insert into test(name) values('test')';
$res=$conn->query($sql);
}
```
### 第二步、在windows配置定时任务
* (1)打开服务器的计算机管理,点击任务计划程序库，点击创建任务
* (2)在常规中填写名称、选择【不管用户是否登陆都运行】【使用最高权限】
* (3)在触发器中点击新建，设置每天几点执行几次
* (4)最后在操作点击新建，选择上面建好bat定时器,然后填写本机密码确认
