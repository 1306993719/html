## 数据库的概念
	数据库(Database)是按照数据结构来组织、存储和管理数据的仓库。
	库：仓库
	表：一个仓库被分为了许多部分，很像类
	字段：很像类的每个属性。
	每个字段的数据类型：
	如：
		int ----> 整数
		varchar ----->字符串
		blob -----> 二进制数据
		date -----> 日期
	
## 常见的数据库
	常见的数据库
		关系型数据库：
			Oracle、MySQL、SQLServer、DB2、sybase
	非关系型的数据库。
		Redis，Tokyo Cabinet，Cassandra，Voldemort，MongoDB，Dynomite， HBase，CouchDB，Hypertable， Riak，Ti，
	
## mySQL简单介绍
	mySQL
		一种开源的数据库软件，市场占有率很高，现在属于Oracle公司。

## 创建数据库和表(用SQL语句代码)
	进入 SQL编辑器
		创建数据库：
			可视化：点击鼠标右键
			代码： create database 数据库名
			如： create database db20170203
	打开某一个库 use db20170203;
	
	创建表：
		create table students(
			id int not null primary key,-- primary key表示主键
			name varchar(8) not null,
			sex char(4) not null,
			age tinyint not null,
			tel char(13) null default "-"
		); 
	
## SQL语句（增删改查）
	增（insert）：
	insert [into] 表 名 [(列 名 1, 列 名 2, 列 名 3, ...)]
		values (值 1, 值 2, 值 3, ...);
	如：
		insert into students (name, sex, age) values("孙丽华", "女", 21);
	
	查询（ select ）：
		select 列名称 from 表名称 [查询条件];
		
	如：
		select name, age from students;
		select * from students;
		select * from students where age > 21 ;
		select * from students where name like "%王%"; --模糊查询
		select * from students where id<5 and age>20; 	
	
	删除（ delete）：
		delete from 表名称 where 删除条件; 
	
	如：
		delete from students; 删除表中的所有数据，
		delete from students where id=2; //删除表中，id是2的数据。
		delete from students where age<20; 
	
	修改（ update）：
		update 表名称 set 列名称=新值 where 更新条件;
	
	如：
		update students set tel=110 where id=5;
		update students set age=age+1;
		update students set name="张伟鹏", age=19 where tel="13288097888";;
	
## PHP连接mySQL

### 连接数据库
	语法：
		mysql_connect(servername,username,password);
	
	参数描述
		•servername可选。规定要连接的服务器。默认是 "localhost:3306"。
		•username可选。规定登录所使用的用户名。默认值是拥有服务器进程的用户的名称。
		•password可选。规定登录所用的密码。默认是 ""。
	如：
	<?php
		header("content-type","text/html;charset=utf-8");
		$con = mysql_connect("localhost","root","qianfeng");// $con是连接对象
		if (!$con) {
			die('Could not connect:'.mysql_error());
		}else{
			echo('连接成功');
		}
	?>
	
### 关闭数据库
	脚本一结束，就会关闭连接。如需提前关闭连接，请使用 mysql_close() 函数
	
	语法：
		mysql_close(连接对象变量);
		
	如：
	<?php
		header("content-type","text/html;charset=utf-8");
		$con = mysql_connect("ocalhost","root","qianfeng");// $con是连接对象
		if (!$con) {
			die('Could not connect: ' . mysql_error());
		}else{
			echo('连接成功');
		}
		………………………………
		
		mysql_close($con);
	?>
	
### Php执行SQL语句(建库)
	语法：
		mysql_query(SQL语句);
	
	如：
	<?php
		header("content-type","text/html;charset=utf-8");
		$con = mysql_connect("localhost","root","qianfeng");
		if (!$con) {
			die('Could not connect: ' . mysql_error());
		}
			mysql_query("create database mydb20170215",$con); //创建数据库
			mysql_close($con);
	?>
	
### Php执行SQL语句(建表)
	如：
	<?php
		header("content-type","text/html;charset=utf-8");
		$con = mysql_connect("localhost","root","qianfeng");
		if (!$con) {
			die('Could not connect: ' . mysql_error());
		}
			//1、选择库
			mysql_select_db("mydb20170215", $con);
			//2、在选择的库上创建表
			$sql = "CREATE TABLE student
		(
			stuId char(10),stuName varchar(15),age int,sex char(2)
		)";
		mysql_query($sql,$con);
		mysql_close($con);
	?>
	
### Php执行SQL语句(插入一条数据)
	如：
	<?php
		header("content-type","text/html;charset=utf-8");
		$con = mysql_connect("localhost","root","qianfeng");
		if (!$con){
			die('Could not connect: ' . mysql_error());
		}
		//1、选择库
		mysql_select_db("mydb20170215", $con);
		//2、给student表中插入数据
		$sql = "insert into student values('xa20160801','刘德华',22,'男')";
		mysql_query($sql,$con);
		mysql_close($con);
	?>	

### Php执行SQL语句(查询)
	//1、建立连接
	//2、选择数据库
	//3、执行SQL语句
	$sqlstr = “select * from vipinfo “;
	$result = mysql_query($sqlstr,$conn);//执行查询的sql语句后，返回的是查询结果
	//查询列数 $query_cols = mysql_num_fields($result)
	//查询行数 $query_num =mysql_num_rows($result);
	$str="[“;
	$query_row = mysql_fetch_array($result);//游标下移,拿出结果集中的某一行，返回值是拿到的行；
	while($query_row){
		$str = $str."{ 'id':'".$query_row[0]."','userName':'".$query_row[1]."'}";
		$query_row = mysql_fetch_array($result);
		if($query_row){ $str = $str.",“;}
	}
	$str = $str."]";
	//4、关闭数据库
	mysql_close($conn);
	echo $str;
	?>

### 添加记录（增）：
	insert [into] 表 名 [(列 名 1, 列 名 2, 列 名 3, ...)]
	values (值 1, 值 2, 值 3, ...);

	如：
		insert into students (name, sex, age) values("孙丽华", "女", 21);