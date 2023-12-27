Задание:
1. Перенесите классы и зависимости из предыдущей задачи.
2. Создайте класс Role и свяжите User с ролями так, чтобы юзер мог иметь несколько ролей.
3. Имплементируйте модели Role и User интерфейсами GrantedAuthority и UserDetails соответственно. Измените настройку секьюрности с inMemory на userDetailService.
4. Все CRUD-операции и страницы для них должны быть доступны только пользователю с ролью admin по url: /admin/.
5. Пользователь с ролью user должен иметь доступ только к своей домашней странице /user, где выводятся его данные. Доступ к этой странице должен быть только у пользователей с ролью user и admin. Не забывайте про несколько ролей у пользователя!
6. Настройте logout с любой страницы с использованием возможностей thymeleaf.
7. Настройте LoginSuccessHandler так, чтобы админа после аутентификации направляло на страницу /admin, а юзера на его страницу /user.

Для создания первого пользователя в бд:
Имя - user
Пароль - user
Роль - admin

insert into roles (name)
values
('ROLE_USER'), ('ROLE_ADMIN');

insert into users (username, password)
values
('user', '$2a$12$JSYjkbR.SUVQpn/Vp7Y3bOD2.IsS17QvRqCtjK9OATUo/rVdFX/Ym');

insert into users_roles (user_id, role_id) values (1, 2);