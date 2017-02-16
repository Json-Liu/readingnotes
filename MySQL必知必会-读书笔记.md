##MySQL必知必会读书笔记
###1.常用命令
<pre>
	show databases 显示当前 MYSQL 服务器上的数据库
	use database 指定使用某一数据库
	show tables 显示当前选择的数据库内可用表的列表
	show columns from tableName 或 desc tableName 显示表名为 tableName 的表结构信息
	show create database databaseName 用来显示创建数据名为 databaseName 的创建语句
	show create table tableName 用来显示创建表名为 tableName 的表创建语句
	show status 用于显示广泛的服务器状态信息
	show grants 用来显示用户的安全权限
	show errors 用来显示服务器错误消息
	show warnings 用来显示服务器警告消息
</pre>
###2.常用函数
<pre>
	Concat(column1,column2)  用来将多个列名拼接起来做为一个新的组合值返回 
		EXP：Concat(name,'(',age,')') 将返回 JonnyLiu(27) 
	AddDate() 增加一个时间
	DateDiff() 计算两个日期差
	Date_Format() 格式化日期函数
	Day() 返回一个日期的天数部分
	DayOfWeek() 返回一个日期对应的星期
	Hour() 返回一个日期中的小时部分
	Avg() 求某列的平均值
	count() 计数
	max() 求某列的最大值 
	main() 求某列的最小值 
	sum() 求某列的和
</pre>

###3、MYSQL不同引擎的区别

<pre>
	InnoDB 一个可靠的事务处理引擎，但不支持全文本搜索
	MEMORY 功能等同于 MyISAM 但由于数据存储在内存中，速度很快，适合于临时表
	MyISAM 一个性能极高的引擎，支持全文本搜索，但不支持事务处理。
	引擎类型可以混用
</pre>

###4、MYSQL 的三种插入方法
<pre>
	insert into table 主键冲突时会抛出 DuplicatedKeyException 异常
	insert ignore into table 主键冲突时会忽略当前的新数据而保留旧数据，不冲突则和 insert 一样。
	replace into table 主键冲突时，会将表中的旧数据替换为当前的新数据，不冲突则和 insert 一样。在 InnoDB 引擎下是 锁住当前替换行 ，在 MyISAM引擎下是锁住当前表
</pre>
