### 34Tính điểm cho user có email là minh82@example.com trong bảng comment
```mysql
SELECT 'minh82@example.com' as email, SUM(point) as point FROM (
  (SELECT '1' as point FROM comment
  WHERE user_id = (
    SELECT id FROM user
    WHERE email = 'minh82@example.com'
    )
  AND target_table = 'blog')
  UNION ALL
  (SELECT '2' as point FROM comment
  WHERE user_id = (
    SELECT id FROM user
    WHERE email = 'minh82@example.com'
    )
  AND target_table = 'news')) as total;
```
