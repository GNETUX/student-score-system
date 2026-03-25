# 学生选课成绩系统 - 数据库表结构

## 组员分工

组长：GNETUX
组员：deletewu

## 1\. 学生表（student）

|字段名|数据类型|约束|注释|
|-|-|-|-|
|stu\_id|INT|PRIMARY KEY, NOT NULL, AUTO\_INCREMENT|学生学号（主键）|
|stu\_name|VARCHAR(20)|NOT NULL|学生姓名|
|gender|CHAR(1)|NOT NULL|性别（男/女）|
|age|INT|NOT NULL|年龄|
|major|VARCHAR(50)|NOT NULL|所属专业 |
|phone|VARCHAR(11)||联系电话 |

## 2\. 教师表（teacher）

|字段名|数据类型|约束|注释|
|-|-|-|-|
|teacher\_id|INT|PRIMARY KEY, NOT NULL, AUTO\_INCREMENT|教师工号（主键）|
|teacher\_name|VARCHAR(20)|NOT NULL|教师姓名|
|gender|CHAR(1)|NOT NULL|性别|
|department|VARCHAR(50)|NOT NULL|所属院系|
|title|VARCHAR(20)|NOT NULL|职称（讲师/教授等）|

## 3\. 课程表（course）

字段名         数据类型        约束
course\_id      INT            主键、非空、自增  -- 课程号
course\_name    VARCHAR(50)    非空             -- 课程名称
credit         INT            非空             -- 学分
class\_hour     INT            非空             -- 课时
teacher\_id     INT            外键(教师表)      -- 授课教师编号

## 4\. 选课成绩表（score）

字段名         数据类型        约束
score\_id       INT            主键、非空、自增  -- 成绩记录编号
student\_id     INT            外键(学生表)、非空 -- 学号
course\_id      INT            外键(课程表)、非空 -- 课程号
score          DECIMAL(5,1)   非空             -- 分数
exam\_time      DATE           非空             -- 考试时间

