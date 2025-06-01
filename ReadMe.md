# People Enricher API

### 📌 Описание

People Enricher — это REST API-сервис на Go, который принимает ФИО человека, обогащает его данными (возраст, пол, национальность) через внешние API и сохраняет результат в базу данных PostgreSQL.

---

### 🚀 Возможности API

- Добавление нового человека (`POST /people`)
- Получение списка людей с фильтрами и пагинацией (`GET /people`)
- Обновление данных по ID (`PUT /people/:id`)
- Удаление записи по ID (`DELETE /people/:id`)
- Документация Swagger (`GET /swagger/index.html`)

---

### 📦 Формат запроса на добавление

```json
{
  "name": "Dmitriy",
  "surname": "Ushakov",
  "patronymic": "Vasilevich" // не обязательно
}

### 🧠 Обогащение данных происходит с помощью:
https://api.agify.io — возраст
https://api.genderize.io — пол
https://api.nationalize.io — национальность

###🛠 Используемые технологии
Go + Gin
PostgreSQL + sqlx
Swagger (через swaggo)
.env конфигурация
pgAdmin (для работы с БД)
HTTP-клиенты для интеграции с внешними API

### ⚙️ Настройка
Создайте файл .env по примеру:
PORT=8080
DB_URL=postgres://username:password@localhost:5432/people_db?sslmode=disable
Выполните миграции (если используете утилиту вроде migrate)
Запустите приложение:
go run main.go

### 📖 Swagger-документация
После запуска доступна по адресу:

http://localhost:8080/swagger/index.html
