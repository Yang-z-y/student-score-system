# 学生选课成绩系统 表结构设计

## 1\. 学生表（student）

|字段名|数据类型|约束|说明|
|-|-|-|-|
|student\_id|INT|PRIMARY KEY AUTO\_INCREMENT|学号|
|stu\_name|VARCHAR(20)|NOT NULL|学生姓名|
|gender|CHAR(2)||性别|
|age|INT||年龄|
|class\_name|VARCHAR(30)||班级|

## 2\. 教师表（teacher）

|字段名|数据类型|约束|说明|
|-|-|-|-|
|teacher\_id|INT|PRIMARY KEY AUTO\_INCREMENT|教师编号|
|tea\_name|VARCHAR(20)|NOT NULL|教师姓名|
|subject|VARCHAR(30)|NOT NULL|授课科目|
|phone|VARCHAR(11)||联系电话|

## 3\. 课程表（course）

|字段名|数据类型|约束|说明|
|-|-|-|-|
|course\_id|INT|PRIMARY KEY AUTO\_INCREMENT|课程号|
|course\_name|VARCHAR(50)|NOT NULL, UNIQUE|课程名称|
|teacher\_id|INT|NOT NULL, FOREIGN KEY → teacher(teacher\_id)|授课教师编号|
|credit|DECIMAL(3,1)|NOT NULL|学分|

## 4\. 选课成绩表（score）

|字段名|数据类型|约束|说明|
|-|-|-|-|
|id|INT|PRIMARY KEY AUTO\_INCREMENT|记录编号|
|student\_id|INT|NOT NULL, FOREIGN KEY → student(student\_id)|学号|
|course\_id|INT|NOT NULL, FOREIGN KEY → course(course\_id)|课程号|
|score|DECIMAL(5,2)|CHECK (score BETWEEN 0 AND 100)|成绩（0-100分）|
|||UNIQUE(student\_id, course\_id)|防止重复选课|

## 冲突解决记录

* 冲突文件：model.md
* 冲突原因：学生表和教师表内容合并
* 解决方式：保留所有4张表，统一格式
* 解决人：郑茂林，杨子羽，刘俊哲
* 解决时间：2025-03-26

