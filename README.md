
# Дипломный проект по профессии «Тестировщик»
**Дипломный проект — автоматизация тестирования комплексного сервиса, взаимодействующего с СУБД и API Банка**

Приложение — это веб-сервис, который предлагает купить тур по определенной цене двумя способами:

- Обычная оплата по дебетовой карте

- Уникальная технология: выдача кредита по данным банковской карты

## Документация
**[План автоматизации](https://github.com/AleksandrMukhin/QA_Diploma_project/blob/main/documentation/Plan.md)**

**[Отчётные документы по итогам тестирования](https://github.com/AleksandrMukhin/QA_Diploma_project/blob/main/documentation/Report.md)**

**[Отчётные документы по итогам автоматизации](https://github.com/AleksandrMukhin/QA_Diploma_project/blob/main/documentation/Summary.md)**

## Процедура запуска автотестов
### Предварительные условия:
1. Установить [Docker Desktop](https://docs.docker.com/desktop/) на локальной машине
2. Установить среду разработки [IntelliJ IDEA](https://www.jetbrains.com/ru-ru/idea/download/#section=windows) для вашей ОС
3. Установить плагины для работы с БД из IntelliJ IDEA: [Database navigation](https://plugins.jetbrains.com/plugin/1800-database-navigator)
4. Установить на локальной машине [Git](https://git-scm.com/book/ru/v2/%D0%92%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5-%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-Git)

### Запуск приложения, тестов и отчета:

**1. Запустить приложение Docker Desktop и войти в свою учетную запись**

**2. Запустить IntelliJ IDEA**

**3. Клонировать репозиторий с дипломным проектом на удаленный сервер командой из IntelliJ IDEA:**
* Открыть приложение IntelliJ IDEA
* Нажать на кнопку `Get From VCS`
  ![Welcome to IntelliJ IDEA 2023-06-11 16 31 52](https://github.com/AleksandrMukhin/QA_Diploma_project/assets/120710840/04412033-6de8-48bc-9d14-ad880b0ffda1)
* В открывшимся окне в поле `URL` ввести:
  `git clone https://github.com/AleksandrMukhin/QA_Diploma_project.git`
* Нажать кнопку `clone`

**4. В терминале IntelliJ IDEA для запуска контейнеров ввести команду:** `docker-compose up`

**5. В IntelliJ IDEA в новой вкладке терминала для запуска приложения введите команды:**

**MySQL:**

`java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/app" "-Dspring.datasource.username=app" "-Dspring.datasource.password=pass" -jar artifacts/aqa-shop.jar`

или

**PostgresSQL:**

`java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/app" "-Dspring.datasource.username=app" "-Dspring.datasource.password=pass" -jar artifacts/aqa-shop.jar`

В зависимости от необходимой БД

**6. В новой вкладке терминала IntelliJ IDEA запустить автотесты при помощи команды:**

**MySQL:**

`./gradlew test "-Dselenide.headless=true" "-Ddb.url=jdbc:mysql://localhost:3306/app" "-Ddb.username=app" "-Ddb.password=pass"`

или

**PostgresSQL:**

`./gradlew test "-Dselenide.headless=true" "-Ddb.url=jdbc:postgresql://localhost:5432/app" "-Ddb.username=app" "-Ddb.password=pass"`

*Команда `-Dselenide.headless=true` уберет визуальное отображение UI тестов. При необходимости команду можно удалить и не использовать данный функционал*

**7. Создание и отображение отчета в браузере:**

В новой вкладке терминала IntelliJ IDEA введите команду:

`./gradlew allureServe`

Сгенерированный отчет откроется в браузере автоматически

**9. Перезапуск приложения и тестов (для использования другой БД)**

Во вкладке терминала IntelliJ IDEA введите команду:

`Ctrl+C`

**10. Остановить контейнеры:**

`docker-compose down`
=======
# Дипломный проект по профессии «Тестировщик»
**Дипломный проект — автоматизация тестирования комплексного сервиса, взаимодействующего с СУБД и API Банка**

Приложение — это веб-сервис, который предлагает купить тур по определенной цене двумя способами:

- Обычная оплата по дебетовой карте

- Уникальная технология: выдача кредита по данным банковской карты

## Документация
**[План автоматизации](https://github.com/AleksandrMukhin/QA_Diploma_project/blob/main/documentation/Plan.md)**

**[Отчётные документы по итогам тестирования](https://github.com/AleksandrMukhin/QA_Diploma_project/blob/main/documentation/Report.md)**

**[Отчётные документы по итогам автоматизации](https://github.com/AleksandrMukhin/QA_Diploma_project/blob/main/documentation/Summary.md)**

## Процедура запуска автотестов
### Предварительные условия:
1. Установить [Docker Desktop](https://docs.docker.com/desktop/) на локальной машине
2. Установить среду разработки [IntelliJ IDEA](https://www.jetbrains.com/ru-ru/idea/download/#section=windows) для вашей ОС
3. Установить плагины для работы с БД из IntelliJ IDEA: [Database navigation](https://plugins.jetbrains.com/plugin/1800-database-navigator) 
4. Установить на локальной машине [Git](https://git-scm.com/book/ru/v2/%D0%92%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5-%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-Git)

### Запуск приложения, тестов и отчета:

**1. Запустить приложение Docker Desktop и войти в свою учетную запись**

**2. Запустить IntelliJ IDEA**

**3. Клонировать репозиторий с дипломным проектом на удаленный сервер командой из IntelliJ IDEA:**
* Открыть приложение IntelliJ IDEA
* Нажать на кнопку `Get From VCS`
![Welcome to IntelliJ IDEA 2023-06-11 16 31 52](https://github.com/AleksandrMukhin/QA_Diploma_project/assets/120710840/04412033-6de8-48bc-9d14-ad880b0ffda1)
* В открывшимся окне в поле `URL` ввести: 

`git clone https://github.com/AleksandrMukhin/QA_Diploma_project.git`
* Нажать кнопку `clone`


**4. В терминале IntelliJ IDEA для запуска контейнеров ввести команду:** `docker-compose up`

**5. В IntelliJ IDEA в новой вкладке терминала для запуска приложения введите команды:**

**MySQL:** 

`java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/app" "-Dspring.datasource.username=app" "-Dspring.datasource.password=pass" -jar artifacts/aqa-shop.jar`

или

**PostgresSQL:**

`java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/app" "-Dspring.datasource.username=app" "-Dspring.datasource.password=pass" -jar artifacts/aqa-shop.jar`

В зависимости от необходимой БД

**6. В новой вкладке терминала IntelliJ IDEA запустить автотесты при помощи команды:** 

**MySQL:** 

`./gradlew test "-Dselenide.headless=true" "-Ddb.url=jdbc:mysql://localhost:3306/app" "-Ddb.username=app" "-Ddb.password=pass"`

или

**PostgresSQL:**

`./gradlew test "-Dselenide.headless=true" "-Ddb.url=jdbc:postgresql://localhost:5432/app" "-Ddb.username=app" "-Ddb.password=pass"`

*Команда `-Dselenide.headless=true` уберет визуальное отображение UI тестов. При необходимости команду можно удалить и не использовать данный функционал*

**7. Создание и отображение отчета в браузере:**

В новой вкладке терминала IntelliJ IDEA введите команду:

`./gradlew allureServe`

Сгенерированный отчет откроется в браузере автоматически

**9. Перезапуск приложения и тестов (для использования другой БД)**

Во вкладке терминала IntelliJ IDEA введите команду:

`Ctrl+C`

**10. Остановить контейнеры:** 

`docker-compose down`


