# 学生信息管理系统

# 数据库设计方案
## 学生信息表设计

| 中文名称 | 表名 | 字段属性 | 默认值 | 备注 |
|---------|------|--------|-------|------|
| 学号 | id | int（11）| 必填 | 主键 |
| 姓名 | name | char(20)| 必填 | 无 |
| 电话 | tel | int(11) | 必填 | 无 |
| 性别 | sex | char(20) | 必填 | 无 |
| 标志位 | sta | int(4) | 必填 | 1 |

## 学校设计表设计
| 中文名称 | 表名 | 字段属性 | 默认值 | 备注 |
|---------|-----|---------|-------|------|
| 课程号 | cno | int(11) | 必填 | 主键 |
| 课程名 | sub | char(20) | 必填 | 无 |
| 学分 | credit | int（11） | 必填 | 无 |

## 学生成绩表设计
| 中文名称 | 表名 | 字段属性 | 默认值 | 备注 |
|---------|-----|---------|-------|------|
| 学号 | id | int(11) | 必填 | 外键 |
| 姓名 | cno | int（11) | 必填 | 外键 |
| 分数 | score | char(20) | 必填 | 无 |
### 主键为（sno，cno）
##CGI接口
```sql
create table student(
id int not null primary key,
name varchar(20) not null, 
age int not null,
tel int not null,
sex varchar(20) not nul)
```
```sql
create table school(
cno int(4) not null,
sub char(20) not null,
credit int(4) not null)
```
```sql
create table grade(
id int(11) not null,
cno int(11) not null,
score char(20) not null,
foreignb key(id) references student(id)
on delete cascade
on update cascade;
foreign key(cno) references school(cno)
on delete cascade
on update cascade;
primery key(id,cno))
```
