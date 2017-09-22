# Use postman for interface testing (2017.09.22)
  ## npm install  typings install 这两个命令是安装相关的依赖库
  ## ctrl+shift+B / tsc -p  表示编译程序  Alt + 键盘的向左移动的键 ： 表示返回
  ## F5 ： VScode进行调试  res.body 需要依赖模块 body-praser 如果不依赖则写成 (res as any).body
1. post的方法测试
```
1)选择post的方法 添加URL:
http://localhost:3000/crm/api/advertiser/newadv
这里的 /crm/api/advertiser 为映射路径
举例如下：
{ cgiPath: "/crm/api/advertiser", filePath: "./router/crm/advertiser" },

而 /newadv 为  ./router/crm/advertiser文件下的路径
```
```
2)选择body----raw----JSON(application/json)
```
```
3)在文本框中输入：

{
  //这里的contacts为字段名 aaaa为通过postman传给程序的值，
  //我们可以把鼠标放在程序的字段中来查看是否已正常传值过来
	"contacts":"aaaa",        
	"description":"sdasdas",
	"phone":"dasdsadasda",
	"imgarr":[1,2,3,4,5]      //传数组的方式
}
```
```
4)send
```
2. get的方法测试
```
1) 输入URL和需要get的字段内容
http://localhost:3000/crm/api/advertiser/list/advertiser/content?page=1&count=10
```
```
2) &的作用就好像是and的意思，表示输入多个键值对
   这里的page=1 count=10 就是要输入的键值对
```
```
3)send
4)application中 编写get的方法，let {page,count} ; console.log(page,count)可查看get的值内容
```
3. 打开前端的网站方法：
```
1)启动application
2)浏览器中输入http://localhost:3000/main.html
3)账号：root2 密码：root
```