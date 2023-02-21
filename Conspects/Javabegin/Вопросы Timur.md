
1. Почему не создавтаь индексы на все поля подряд, что теряем?
2. Как сохранять нужные скл срипты прямо в базе?
3. Что такое версии JDK? Amzon итд Какого вендор выбирать?
4. как  включить в дамп схемы в пгадмин удаление таблиц?
5. странно что пассворд к базе прописывается плейном в файле конфига
6. Почему в хибернейт конфиге диалект указывается без версии? На сайте хибернейта указан 9-й ```PostgreSQL9

Support for the PostgreSQL database, version 9. May work with later versions.```
7. Депрекейтед метод save здесь - https://javabegin.ru/courses/osnovy-hibernate/lessons/dobavlenie-novogo-obekta-user/ Заменить на session.persist(user);?
8. Как посмотреть реализацию метода Session.persist? Переводит на интерфейс и все
9. выдает ошибку при попытке удалить пользователя "ERROR: insert or update on table "category" violates foreign key constraint "user_fkey" DETAIL: Key (user_id)=(5605) is not present in table "user_data". CONTEXT: SQL statement "UPDATE todolistm.category SET uncompleted_count=(coalesce(uncompleted_count,0)-1) WHERE id=OLD.category_id AND user_id=OLD.user_id" PL/pgSQL function todolistm.delete_task_trigger() line 10 at SQL statement SQL statement "DELETE FROM ONLY "todolistm"."task" WHERE $1 OPERATOR(pg_catalog.=) "user_id"" SQL state: 23503"
10. Не выводятся параметры запроса в консоль Main