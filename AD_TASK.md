Прочитай файл AD\_TASK.md и реализуй backend AD Management Portal.



Используй LDAP подключение:



\- url: ldap://10.1.10.11:389

\- domain: dmuk.edu.kz

\- username: zkt@dmuk.edu.kz



Пароль НЕ хардкодить.

Использовать environment variable AD\_BIND\_PASSWORD из .env файла.



Использовать конфигурацию:



ad:

&#x20; url: ${AD\_SERVER\_URL:ldap://10.1.10.11:389}

&#x20; domain: ${AD\_DOMAIN:dmuk.edu.kz}

&#x20; username: ${AD\_BIND\_USERNAME:zkt@dmuk.edu.kz}

&#x20; password: ${AD\_BIND\_PASSWORD}

&#x20; read-only: ${AD\_READ\_ONLY:true}



ВАЖНО:

\- read-only режим по умолчанию = true

\- любые изменения в AD запрещены при read-only=true

\- сначала реализовать только READ операции



Сделай backend как:

\- Spring Boot monolith

\- Java 21

\- PostgreSQL только для:

&#x20; - audit logs

&#x20; - access templates

&#x20; - settings

&#x20; - OU history



Модули:

\- auth

\- ad (LDAP integration)

\- users

\- groups

\- access-template

\- audit

\- settings



LDAP функционал:

\- получить всех пользователей

\- получить пользователя по username

\- получить группы пользователя

\- получить список OU

\- поиск пользователей



НЕ делать пока:

\- create user

\- delete user

\- move OU

\- add/remove groups



(это будет позже после теста)



Сначала сделай:



1\. LDAP config (LdapTemplate / connection)

2\. AD service (read-only)

3\. Users API (GET)

4\. Groups API (GET)

5\. DTO

6\. REST endpoints

7\. тестовый endpoint /api/users



После этого остановись и жди команды.

