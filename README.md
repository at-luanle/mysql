### 33. Liệt kê email user các user có tên(user.full_name) có chứa ký tự "Khi"
```mysql
select group_concat(email) as email_users
from user
where full_name like '%khi%';
```
