# Mysql服务器支持三种注释风格：  
1.从‘#’字符到行尾。  
2.从‘-- ’序列到行尾。请注意‘-- ’(双破折号)注释风格要求第2个破折号后面至少跟一个空格符(例如空格、tab、换行符等等)。该语法与标准SQL注释语法稍有不同。  
3.从/\*序列到后面的\*/序列。结束序列不一定在同一行中，因此该语法允许注释跨越多行。  
# SQL注入攻击：  
指针对Web应用使用的数据库，通过运行非法的SQL而产生的攻击。  
攻击者将SQL语句改变成开发者意想不到的形式以达到破坏结构的攻击。  
以某购物网站的搜索功能为例，该功能允许将作者的名字作为搜索的关键字，查询该作者所有著作（不显示已经绝版的）：  
URL：  
>http://example.com/search?name=张三  

URL的查询字段已经指定name=张三，这个值由Web应用传入到SQL语句中，构成下面的SQL语句：  
`SELECT * FROM bookTb WHERE author='张三' AND flag=1；`  
## SQL注入攻击操作示例：  
将指定查询字段的张三改为“张三'#”,或者“张三'-- ”  
构成的SQL语句为：  
`SELECT * FROM bookTb WHERE author='张三'#' AND flag=1；`  
#之后全视为注释，即flag=1这个条件被忽略了。  

