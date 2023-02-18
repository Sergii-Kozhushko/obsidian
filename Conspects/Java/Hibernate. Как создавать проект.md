1. Создаем проект Гредл
2. Добавляем в зависимости в build.gradle по ссылке  https://mvnrepository.com/artifact/org.hibernate/hibernate-core/6.1.7.Final строку 'implementation 'org.hibernate:hibernate-core:6.1.7.Final'
4. открываем наше бд в Идее для удобства, можно просматривать таблицы. View-Tool-Database. Жмем плюс-Data Source-Postgres. Вводим логин-пароль. На вкладке Schemas  выбрать нужную схему
5. Добавить фасет Hibernate для main. Project Structure-Project Settings-Facets-+Hibernate
6. Persistance. Правой кнопкой на hibernate Выбрать наш датасорс
7. Прописать connection_url в hibernate.cfg.xml. Значение взять из вкладки Databse
8. Подлючаем JDBC Driver Postgres. Набрать в гугле "Postgres Maven", подключить библиотеку в гредл в build.gradle
9. Прописываем в hibernate.cfg.xml. driver class "org.postgresql.Driver" и логин и пароль к базе 
10. Далее создать класс
```Java
// Фабрика для создания сессий
import org.hibernate.SessionFactory;  
import org.hibernate.cfg.Configuration;  
  
import java.io.File;  
  
public class HibernateUtil {  
   private static final SessionFactory sessionFactory = buildSessionFactory();  
  
   //Метод вызывает  
   private static SessionFactory buildSessionFactory(){  
      try {  
         return new Configuration().configure(new File("src\\main\\resources\\hibernate.cfg.xml")).buildSessionFactory();  
      }  
      catch (Throwable ex){  
         System.err.println("Initial SessionFactory creation failed," + ex);  
         throw new ExceptionInInitializerError(ex);  
      }  
   }  
  
   public static SessionFactory getSessionFactory(){  
      if (sessionFactory == null) buildSessionFactory();  
      return sessionFactory;  
   }  
  
   public static void close(){  
      getSessionFactory().close();  
   }  
}

// Main
import org.hibernate.Session;  
  
public class Main {  
    public static void main(String[] args) {  
        Session session = HibernateUtil.getSessionFactory().openSession();  
        session.close();  
        HibernateUtil.close();  
    }  
}
```

11. Прописываем диалект, значние берем прямо из того, что выдает хибернейт в консоль```
```xml
<property name="hibernate.dialect">org.hibernate.dialect.PostgreSQLDialect</property>
```
12. Делаем Mapping таблиц и классов в коде (таблица становится объектом). Persistance-правой на hibernate-generate persistance mapping. Выбираем пекедж для entities (классы которые будут для таблиц). Ставим галочку на Generate JPA, убираем галочки на дженерейт XML.  в файл конфига хибернет добавляется строчка ```<mapping class="de.javabegin.hibernatetest.entity.UserData"/>```
13. Ставми галочку напротив той таблицы, для которй хотим сделать энтити-класс, например user_data
14. В классы проекта автоматом добавится класс UserName, в который будут попадать поля таблиц бд Туда пишутся все аннотации

13. Подключаем Lombok. Добавить в build.gradle ```compileOnly 'org.projectlombok:lombok:1.18.26'
	annotationProcessor 'org.projectlombok:lombok:1.18.26'```  
14. Включить Annotation processing. Setings-Compiler-Aonnotation 
15. В энтити класс UserData добавляем аннотации ломбок @Setter  
@Getter  
@AllArgsConstructor  
@NoArgsConstructor

