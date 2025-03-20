
## 合计/统计函数

### COUNT函数

- **返回行的总数**
- **语法**
	```MYSQL
	SELECT COUNT(*) | `column_name` FROM `table_name` [WHERE where_definition]
	```
- ***EXAMPLE:***
	1. **统计所有student表的记录数量（行）**
		```MYSQL
		SELECT COUNT(*) FROM `student`;
		```
	2. **统计总分大于250的学生**
		```MYSQL
		SELECT COUNT(*) FROM `STUDENT`
			WHERE (`math` + `english` + `chinese`) > 250; 
		```
- **注意**:
	- **count( * )和coun(列)的区别**
		- count(\*)返回满足条件的记录的行数
		- count(列)：统计满足条件的某列有多少个，***但是会排除为nul1***

### SUM函数

- **返回满足WHERE条件的行的和**，一般使用在**数值列**
- **语法**
	```MYSQL
	SELECT SUM(`COLUMN_NAME`) [, SUM(`COLUMN_NAME)...] 
		FROM `TABLE_NAME` [WHERE `WHERE_DEFINITION]
	```
- ***EXAMPLE***:
	1. **统计一个班级数学总成绩**
		```MYSQL
		SELECT SUM(`MATH`) FROM `STUDENT`;
		```
	2. **统计各科总成绩**
		```MYSQL
		SELECT SUM(`MATH`), SUM(`ENGLISH`), SUM(`CHINESE`) FROM `STUDENT`;
		```
	3. **统计所有成绩总和**
		```MYSQL
		SELECT SUM(`MATH`+`CHINESE`+`ENGLISH`) FROM `STUDENT`;
		```
	4. **统计一个班级语文成绩*平均分***
		```mysql
		SELECT SUM(`CHINESE`) / COUNT(*) FROM `STUDENT`; 
		```
- **注意：**
	- 仅对数值起作用，否则会报错

### AVG函数

- **返回满足WHERE条件的一列的平均值**
- **语法**
	```mysql
	SELECT AVG(`COLUMN_NAME`) [, AVG(`C_N)...] FROM `TABLE_NAME`
	[WHERE `WHERE_DEFINITION];
	```
- ***EXAMPLE***
	1. **求数学平均分**
		```MYSQL
		SELECT AVG(`MATH`) FROM `STUDENT`;
		```
	2. **求总平均分**
		```MYSQL
		SELECT AVG(`MATH`+`ENGLISH`+`CHINESE`) FROM `STUDENT`;
		```
### MAX/MIN函数

- **返回满足WHERE条件的一列的最大值/最小值**
- **语法**
	```MYSQL
	SELECT MAX(`COLUMN_NAME`) FROM `TABLE_NAME` [WHERE `WHERE_DEFINITION`]; 
	```
- ***EXAMPLE***
	1. **求班级最高分和最低分**
		```MYSQL
		SELECT MAX(`MATH`+`ENGLISH`+`CHINESE`), MIN(`MATH`+`ENGLISH`+`CHINESE`)
		FROM `TABLE_NAME`;
		```
- **针对于数值列**
