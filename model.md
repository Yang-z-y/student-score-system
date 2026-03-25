**# 学生选课成绩系统 表结构设计**





**## 3. 课程表（course）**

**| 字段名 | 数据类型 | 约束 | 说明 |**

**|--------|----------|------|------|**

**| course\_id | INT | PRIMARY KEY AUTO\_INCREMENT | 课程号 |**

**| course\_name | VARCHAR(50) | NOT NULL, UNIQUE | 课程名称 |**

**| teacher\_id | INT | NOT NULL, FOREIGN KEY → teacher(teacher\_id) | 授课教师编号 |**

**| credit | DECIMAL(3,1) | NOT NULL | 学分 |**



**## 4. 选课成绩表（score）**

**| 字段名 | 数据类型 | 约束 | 说明 |**

**|--------|----------|------|------|**

**| id | INT | PRIMARY KEY AUTO\_INCREMENT | 记录编号 |**

**| student\_id | INT | NOT NULL, FOREIGN KEY → student(student\_id) | 学号 |**

**| course\_id | INT | NOT NULL, FOREIGN KEY → course(course\_id) | 课程号 |**

**| score | DECIMAL(5,2) | CHECK (score BETWEEN 0 AND 100) | 成绩（0-100分） |**

**| | | UNIQUE(student\_id, course\_id) | 防止重复选课 |**

