# IT Alligator

## Описание
Агрегатор IT-мероприятий по типу "Яндекс Афишы"

*Аминов Джурабек Тимурмаликович 20.Б11-пу*


*Павлов Алексей Владимирович 20.Б12-пу*

*Ненахов Иван Владимирович 20.Б13-пу*

## Предметная область
It-мероприятия, выгруженные из других источников.

## Данные
<img width="536" alt="Снимок экрана 2022-11-16 в 17 51 34" src="https://user-images.githubusercontent.com/61906886/202213525-530e2da2-a572-463f-9884-d03e4639700a.png">

- user collection - Коллекция пользователей
  - name
  - lastName
  - email
  - password 
  - phone
  
- event collection - Коллекция мероприяйтий
  - title
  - kind - формат мероприятия (конференция, лекция, ...)
  - full_date_time 
  - full_place
  - site - сайт мероприятия
  - organizers
  - decription - описание с сайта
  - category_list - список категорий мероприятия (бэкенд, mobile, business analysis, ...)
  - cluster - к какому кластеру принадлежит мероприятие 
  - description_vec - числовое представление *description*
 
 - userActions collection - Коллекция действий пользователя
    - event_uid - id мероприятия в БД
    - user_uid - id пользователя в БД
    - kind - тип действия (добавить в избранное, посетить сайт мероприятия)
    - grade - оценка меропрития от 1 до 5
  
 - recommendations collection - Коллекция рекомендаций пользователя
    - user_uid
    - interest_vec - числовой вектор того же пространства что и *description_vec*, отображающий интересы пользователя
    - cluster_vec - числовой вектор, отображающий распределение интересов пользователя среди кластеров
    - rating - отранжированный список индексов мероприятий согласно интересам пользователя
    - updated_at - время последнего обновления рекомендаций

## Общие ограничения целостности
- Пользователь может поменять свои данные (имя, пароль, почту, телефон, список избранных мероприятий, оценки).
- Все остальное можно изменить напрямую в БД.

## Пользовательские роли

#### guest
- может просматривать мероприятия, размещенные на сайте

#### user
- может просматривать мероприятия, размещенные на сайте
- может добавлять любые мероприятия на сайте в избранное
- может оценивать посещенные мероприятия
- для начального определения рекомендаций может пройти анкетирование

## UI/API
Веб-сервис 

<img width="1901" alt="Снимок экрана 2022-11-16 в 19 23 04" src="https://user-images.githubusercontent.com/61906886/202236312-d452ffb4-2eef-4521-9d53-737a26b377b0.png">
<img width="1014" alt="Снимок экрана 2022-11-16 в 19 23 40" src="https://user-images.githubusercontent.com/61906886/202236337-5d1624d3-3a9c-4f52-9069-d49622389d02.png">



## Технологии разработки

Языки программирования
- Python
- TypeScript
- HTML
- CSS

Развертывание на виртуальной машине:
- 2 vCPU 
- 4 RAM 
- 10HDD

Библиотеки и фреймворки
- Frontend: React, Axios, MUI, Mobox, ...
- Backend: FastAPI, Pydantic, BeautifulSoup, ...
- Data Science: tensorflow, numpy, pandas, scikit-learn.

СУБД
- MongoDB

## Ссылка на проект:

https://gitlab.com/creators15/event-loader - ETL бэкенд для мероприятий

https://gitlab.com/creators15/frontend - Frontend проекта

https://gitlab.com/creators15/agregator_ds - Data Science репозиторий(для экспериментов)

https://gitlab.com/creators15/alligator - бэкенд сервиса (основной)
