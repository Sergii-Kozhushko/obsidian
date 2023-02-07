**Сложный полный запрос:**

```sql
select * from pg_indexes  
where schemaname like ‘%todolist%’
c.title,  
u.username
from todolist.task t
left join todolist.category c  
on t.category_id = c.id
left join todolist.user_data u  
on t.user_id = u.id
where t.title like ‘а%’  
–where t.id < 500

group by c.title, u.username

order by c.title
```

Скрипт генерации тестовых значений 
``
```sql
DO $GEN_DATA$  
BEGIN  
FOR i IN 1..1000 LOOP  
RAISE NOTICE 'Добавлена строка номер: %', i; -- аналог console.log

EXECUTE $$ INSERT INTO todolistm.user_data(email, username, userpassword) VALUES (
'email' || $1 || '@gmail.com', 'username' || $1, gen_random_uuid ()) returning id; $$  
USING i;

END LOOP;  
END;  
$GEN_DATA$
```


**Обнуление автоинкрементов**
```sql
TRUNCATE table todolistm.task, todolistm.priority, todolistm.category, todolistm.user_data, todolistm.stat, todolistm.user_role, todolistm.activity RESTART IDENTITY

```

Посмотреть текущие запросы
```sql
select * from pg_stat_activity;
```

