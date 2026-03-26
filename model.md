\# 学生选课成绩系统 表结构设计



\## 1. 学生表（student）

student\_id     INT             主键、非空、自增    学号

stu\_name       VARCHAR(20)     非空                学生姓名

gender         CHAR(2)                             性别

age            INT                                 年龄

class\_name     VARCHAR(30)                           班级



\## 2. 教师表（teacher）

teacher\_id     INT             主键、非空、自增    教师编号

tea\_name       VARCHAR(20)     非空                教师姓名

subject        VARCHAR(30)     非空                授课科目

phone          VARCHAR(11)                           联系电话

