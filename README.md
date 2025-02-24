# Дипломный проект сервиса Яндекс.Самокат

## Задачи

### Протестировать веб-приложение Яндекс.Самокат

1. Изучить [требования](https://drive.google.com/file/d/188S-PgaJf2KE6PsSSYmiAVrikrY-973F/view?usp=sharing) и [макеты(figma)](https://www.figma.com/design/rXmJXOcsGV221qYJNN8N1V/web-(Copy)?node-id=0-1&t=NzCxLKwJnu8ACjJR-1)
2. Составить чек-лист “**Задание 1: чек-лист Статус заказа**“ по требованиям к экрану “Статус заказа”
3. Для экрана “Сделать заказ” составить проверки на валидацию полей в чек-листе “**Задание 1: данные валидации**“
4. Провести тестирование всей функцилнальности не только по получившимся чек-листам и таблицам, но и по остальным макетам и требованиям. Проверять главную страницу (лендинг) не нужно. Результаты в виде баг-репортов поместить на листе “**Задание 1: баги вне тестовой документации**”

### Протестировать мобильное приложение Яндекс.Самокат

1. Изучить требования [требования](https://drive.google.com/file/d/1ZkuitySMcuJ73ZRMiir1KqTyfB0VoKiH/view?usp=sharing) и [макеты(figma)](https://www.figma.com/design/msO5TfCaAZLIYFHy2vBw2P/mobile-(Copy)?t=NzCxLKwJnu8ACjJR-1)
2. Спроектировать тест-кейсы вёрстки и логики, которая выделена жирным шрифтом в требованиях на листе “**Задание 2: тест-кейсы Мобильного приложения”**
3. Установить [мобильное приложение](https://drive.google.com/file/d/1vOPyHMAkU_fEhY3rROPSbW7WyXPr7KMo/view?usp=sharing), протестировать его по подготовленным тест-кейсам и оформить баг-репорты

### Протестировать функциональность API Яндекс.Самокат

1. Изучить [требования к бэкенду](https://drive.google.com/file/d/1_nEqG-7VL4Gc5hM2CLeU2Pf82RyLRt9m/view?usp=sharing) и [Apidoc](https://github.com/orakul99/QA-Yandex-Samokat/blob/main/apidoc.md)
2. Разработать чек-лист “**Задание 3: чек-лист API**“
3. Протестировать API по требованиям, которые выделены жирным шрифтом и оформить баг-репорты

## Тестовая документация

**[Задание 1: чек-лист Статус заказа](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=943703744#gid=943703744)**

**[Задание 1: данные валидации Сделать заказ](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1540465171#gid=1540465171)**

**[Задание 1: баги вне тестовой документации](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=70743743#gid=70743743)**

**[Задание 2: тест-кейсы Мобильного приложения](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=424948590#gid=424948590)**

**[Задание 3: чек-лист API](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=336872680#gid=336872680)**

**[Баг-репорты](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015)**

## Отчёт

Проведено комплексное тестирование сервиса Яндекс.Самокат. В части веб-приложения это форма бронирования самоката на экране “Сделать заказ“, включая вёрстку, логику работы и механизмы валидации полей. А также вёрстка и логика работы статусов заказа и информации о заказе. В мобильном приложении исследован новый функционал уведомления курьера с напоминанием о заказе, а также механизм реакции активных зон приложения на отстуствующее интернет-соединение. Функциональность API покрыта ручками Создания и Удаления курьера, а также получения заказа по его номеру.

### Результаты

В процессе выполнения тестирования было найдено множество серьезных ошибок:

- В веб-приложении блокирующий [BUGTST-14](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=70743743#gid=70743743&range=15:15) ломает форму оформления заказа в поле Станция метро, если нажать Enter. Другой блокирующий [BUGTST-19](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=70743743#gid=70743743&range=20:20) делает невозможным отправку формы заказа в браузере Chrome, которым пользуется около половины ЦА.
- Блокирующий с точки зрения бизнес-логики [BUG-19](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=25:25) делает возможным заказ самоката на пустой адрес. По такой же причине блокирующий баг [BUG-22](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=28:28) позволяет заказать самокат на непредусмотренный логистикой сервиса сегодняшний день или даже в прошлое. Критический [BUG-23](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=29:29) позволяет ввести в поле даты заказа значение вручную.
- На экране “Статус заказа“ веб-приложения из-за блокирующего [BUG-13](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=18:18) никогда не заработает статус “Курьер на месте“. Критический [BUG-2](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=4:4) разваливает вёрстку несущих столбцов с данными и статусами заказа в Яндекс.Браузере. Значения полей “Станция метро” и “Дата доставки” из формы заказа на экран его статуса передаются с критическими ошибками – [BUG-9](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=12:12) и [BUG-9-1](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=13:13). А заказ в принципе отменить невозможно из-за критических [BUG-10](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=14:14) и [BUG-10-1](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=15:15)
- Уведомление мобильного приложения "2 часа до конца заказа" приходит в любое время дня заказа - блокирующий [BUG-25](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=32:32), критический [BUG-26](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=33:33), а также еще в день после - критический [BUG-27](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=34:34) и в статусе заказа "Ну всё, теперь кататься" из-за критического [BUG-28](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=35:35). Переход через само уведомление вызывает блокирующий работу приложения [BUG-31](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=38:38). Также довольно неприятный критический [BUGTST-20](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=70743743#gid=70743743&range=21:21) задваивает карточки заказа после перевода его в статус “Курьер едет к вам”. А если приложение свернуть, открыть заново и попытаться выйти из учётной записи это приведёт к остановке приложения из-за критического [BUGTST-21](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=70743743#gid=70743743&range=22:22)
- В API возможно отправлять запросы с некорректными данными для полей логин и пароль из-за критических багов [BUG-34](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=42:42) и [BUG-35](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=43:43). Удалённый курьер оставляет связанные с ним заказы в БД - критический [BUG-37](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=45:45) и соответственно заказ удалённого курьера можно найти по его номеру [BUG-40](https://BUG-40). Последствия задваивания статуса “Курьер едет к вам” в мобильном приложении найдены и в БД при его проверке - критический [BUG-38](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=46:46). Также найдена причина неработающей отмены заказа - критический баг [BUG-39](https://docs.google.com/spreadsheets/d/1jaxpTg5M6bN5v7tTA4IV74pWXPZbkPo6BMU79w4mRKc/edit?gid=1983909015#gid=1983909015&range=47:47) неработающей ручки отмены заказа.

### Вывод

Состояние работы сервиса просто пугающее.

Данные на этапе оформления заказа теряются, передаются с ошибками или форма падает, а может даже и не отправиться. В мобильном приложении очень некомфортно пользоваться переходом заказа в другие статусы, уведомление о своевременном выполнении заказа для курьера не рабочее и вызывает падение приложения. Баги в API и вовсе засоряют БД некорректными данными полей и остатками неудаляемых сущностей.

В таком состоянии сервисом пользоваться очень неприятно и даже практически невозможно.

Релиз категорически невозможен до правки хотя бы всех блокирующих и критических багов.

