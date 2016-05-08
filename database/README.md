### 要求

1. 创建至少两个表，要求有关联关系。并插入一些数据。
2. 写 5 条较复杂的查询程序。
3. 在周二 5-9 12:00 前完成。

参考资料有内部视频、http://www.w3schools.com/sql/ 。

### 示例

此目录下的 github.sqlite3。

查询语句 5 条：

1）用户名 z 开头的人的项目： 

select * from repos where owner in (select id from users where name like 'z%');

2）查询项目，并且联表 users：

select * from repos join users on users.id=repos.owner;

3) 创建时间升序找出用户，如果时间相同则按名字降序排：

select * from users order by created_at, name desc;

4）按住用户名的长度排序：

select *,length(name) from users order by length(name);

5) 找出名字含有 z 的用户：

select * from users where name like '%z%';

