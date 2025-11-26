```mermaid
C4Container
title Контейнерная диаграмма FitLife

    Person(member, "Клиент", "Посетитель фитнес-клуба")

    System_Boundary(fitlife_system, "FitLife System") {
        Container(mobile_app, "Мобильное приложение", "React Native", "Запись на занятия, просмотр расписания")
        Container(web_app, "Личный кабинет", "Angular", "Управление абонементом и платежами")
        Container(api, "API Gateway", "Spring Boot", "Обработка запросов")
        Container(auth, "Auth Service", "Java", "Аутентификация")
        Container(scheduler, "Scheduler Service", "Python", "Управление расписанием")
        Container(payment, "Payment Service", "Java", "Обработка платежей")
        Container(db, "Database", "PostgreSQL", "Хранение данных пользователей и занятий")
    }

    Rel(member, mobile_app, "Использует приложение")
    Rel(member, web_app, "Входит в ЛК")
    Rel(mobile_app, api, "API запросы")
    Rel(web_app, api, "API запросы")
    Rel(api, auth, "Проверка доступа")
    Rel(api, scheduler, "Получение расписания")
    Rel(api, payment, "Инициирует платежи")
    Rel(api, db, "Чтение/запись данных")