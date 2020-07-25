# Mesto 

### Version 0.1.6

## Процесс установки:

```bash
# установка пакетов
$ npm install

# сборка с локальным сервером
$ npm run start
# сборка с локальным сервером и hot reload
$ npm run dev
```

## О проекте: 

**Сервис для добавления фотографий различных мест**

**Цель проекта:** Создание своего сервера для проекта

**Стек:** JavaScript ES6, Express.js, ESLint

**Функционал:**

- Регистрация
- Вход в аккаунт
- Запросить информацию пользователя
- Запросить информацию всех пользователей
- Создать карточку
- Удалить свою карточку
- Запросить все карточки

**Реализованные задачи проекта:**

- В схеме пользователя есть обязательные email и password;
- Поле email уникально и валидируется;
- В контроллере createUser почта и хеш пароля записываются в базу;
- Есть контроллер login, он проверяет, полученные в теле запроса почту и пароль;
- Если почта и пароль верные, контроллер login создаёт JWT, в пейлоуд которого записано свойство _id с идентификатором пользователя; срок жизни токена — 7d
- Eсли почта и пароль верные, контроллер login возвращает созданный токен в ответе;
- Eсли почта и пароль не верные, контроллер login возвращает ошибку 401;
- В app.js есть обработчики POST-запросов на роуты /signin и /signup;
- Eсть файл middlewares/auth.js, в нём мидлвэр для проверки JWT;
- При правильном JWT авторизационный мидлвэр добавляет в объект запроса пейлоуд и пропускает запрос дальше;
- При неправильном JWT авторизационный мидвэр возвращает ошибку 401;
- Все роуты, кроме /signin и /signup, защищены авторизацией;
- Удалён хардкод req.user из самостоятельного проекта предыдущего спринта;
- Пользователь не может удалить карточку, которую он не создавал;
- API не возвращает хеш пароля;
