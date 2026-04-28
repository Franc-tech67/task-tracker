# Task Tracker API

REST API для управления задачами на Spring Boot 4.

## Технологический стек

| Технология | Версия | Назначение |
|------------|--------|------------|
| Java | 17     | Язык программирования |
| Spring Boot | 4.0.6  | Фреймворк |
| Spring Data JPA | 4.0.6 | Работа с БД |
| H2 Database | 2.3.x | Встроенная БД |
| Lombok | 1.18.46 | Сокращение кода |
| Validation | 3.1.x | Валидация данных |

## Как запустить

1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/Franc-tech67/task-tracker.git
2. Перейдите в папку проекта:
   ```bash
   cd task-tracker
   ```
3. Запустите приложение:
   ```bash
   ./mvnw spring-boot:run
   (Windows: mvnw.cmd spring-boot:run)
   ```
4. Приложение доступно по адресу:
   ```bash
   ./mvnw spring-boot:run
   ```
## API Эндпоинты

| Метод | URL | Описание |
|-------|-----|----------|
| GET | `/api/tasks` | Получить все задачи |
| GET | `/api/tasks/{id}` | Получить задачу по ID |
| POST | `/api/tasks` | Создать задачу |
| PUT | `/api/tasks/{id}` | Обновить задачу |
| DELETE | `/api/tasks/{id}` | Удалить задачу |
| GET | `/api/tasks/completed` | Выполненные задачи (Stream API) |
| GET | `/api/tasks/search?keyword=...` | Поиск (Stream API) |

## Примеры запросов

### Создать задачу
```bash
   POST http://localhost:8080/api/tasks
   Content-Type: application/json
   
   {
     "title": "Изучить Spring Boot",
     "description": "Пройти курс",
     "status": "NEW"
   }
```
### Получить все задачи
```bash
   GET http://localhost:8080/api/tasks
```
### Получить задачу по ID
```bash
   GET http://localhost:8080/api/tasks/1
```
### Обновить задачу
```bash
   PUT http://localhost:8080/api/tasks/1
   Content-Type: application/json
   
   {
     "title": "Изучить Spring Boot",
     "description": "Пройти курс и сделать пет-проект",
     "status": "IN_PROGRESS"
   }
```
### Удалить задачу
```bash
   DELETE http://localhost:8080/api/tasks/1
```
### Поиск задач по названию
```bash
   GET http://localhost:8080/api/tasks/search?keyword=Spring
```
### Получить выполненные задачи
```bash
   GET http://localhost:8080/api/tasks/completed
```
## 🗄 База данных

H2 консоль доступна по адресу: `http://localhost:8080/h2-console`

- **JDBC URL:** `jdbc:h2:mem:testdb`
- **Username:** `sa`
- **Password:** (пустой)

## 📁 Структура проекта
```
task-tracker/
├── src/main/java/com/example/tasktracker/
│   ├── TaskTrackerApplication.java      # Главный класс
│   ├── controller/
│   │   └── TaskController.java          # REST контроллер
│   ├── model/
│   │   └── Task.java                    # Entity задача
│   ├── repository/
│   │   └── TaskRepository.java          # JPA Repository
│   └── service/
│       └── TaskService.java             # Бизнес-логика
├── src/main/resources/
│   └── application.properties           # Конфигурация
├── pom.xml                              # Maven зависимости
└── README.md                            # Документация
```

## Ключевые особенности

- **CRUD операции** — полный цикл работы с задачами
- **Валидация данных** — @Valid с кастомными сообщениями об ошибках
- **Stream API** — фильтрация и поиск задач функциональным стилем
- **H2 Database** — встроенная база для быстрой разработки
- **Lombok** — минимизация шаблонного кода
- **RESTful дизайн** — соблюдение принципов REST

## Автор

Хохлов Франц — Java Developer Intern Candidate

Email: Dydocer3068@gmail.com  
GitHub: https://github.com/Franc-tech67

## Дата создания

2026

## Лицензия

MIT License — свободное использование в образовательных и коммерческих целях.
