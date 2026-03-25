# 学生选课成绩系统 表结构设计

## 1. 学生表（student）
字段名         数据类型         约束                说明
student_id     INT             主键、非空、自增    学号
stu_name       VARCHAR(20)     非空                学生姓名
gender         CHAR(2)                             性别
age            INT                                 年龄
class_name     VARCHAR(30)                           班级

## 2. 教师表（teacher）
字段名         数据类型         约束                说明
teacher_id     INT             主键、非空、自增    教师编号
tea_name       VARCHAR(20)     非空                教师姓名
subject        VARCHAR(30)     非空                授课科目
phone          VARCHAR(11)                           联系电话

## 3. 课程表（course）
字段名         数据类型         约束                说明
course_id      INT             主键、非空、自增    课程号
course_name    VARCHAR(50)     非空                课程名称
teacher_id     INT             外键（teacher）     授课教师编号
credit         INT             非空                学分

## 4. 选课成绩表（score）【核心关联表】
字段名         数据类型         约束                说明
id             INT             主键、自增          记录编号
student_id     INT             外键（student）非空  学号
course_id      INT             外键（course）非空   课程号
score          DECIMAL(5,2)                          成绩
