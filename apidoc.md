# Apidoc

## Создание курьера

POST /api/v1/courier

### **Параметры**

| Название | Тип | Описание |
|----|----|----|
| login | string | Логин курьера, записывается в поле login таблицы Couriers |
| password | number | Пароль курьера, хэш от значения записывается в поле passwordHash таблицы Couriers |
| firstName
**необязательный** | string | Имя курьера, записывается в поле firstName таблицы Couriers |

### Запрос

POST /api/v1/courier

{ 

    "login": "ninja",

    "password": "1234",

    "firstName": "saske"

}

### Ответ

Успешное создание учетной записи

HTTP/1.1 201 Created

{

        ok: true

}

### Ответ-ошибка

Запрос без логина и пароля

HTTP/1.1 400 Bad Request

{

     "message": "Недостаточно данных для создания учетной записи"

}  

### Ответ-ошибка

Запрос с повторяющимся логином

HTTP/1.1 409 Сonflict

{

   "message": "Этот логин уже используется"

}  

## Удаление курьера

DELETE /api/v1/courier/:id

### **Параметр**

| Название | Тип | Описание |
|----|----|----|
| id | string | Номер курьера, хранится в поле id таблицы Couriers |

### Ответ

Успешное удаление курьера

HTTP/1.1 200 OK

{

     ok: true

}  

### Ответ-ошибка

Запрос без id:

HTTP/1.1 400 Bad Request

{

   "message":  "Недостаточно данных для удаления курьера"

}  

### Ответ-ошибка

Запрос с несуществующим id:

HTTP/1.1 404 Not Found

{

   "message": "Курьера с таким id нет"

}  

## **Получить заказ по его номеру**

GET /api/v1/orders/track

### **Параметр**

| Название | Тип | Описание |
|----|----|----|
| t | number | Трекинговый номер заказа |

### Запрос

GET /api/v1/orders/track?t=123456  

### Ответ

HTTP/1.1 200

    {

         "order": {

             "id": 2,

             "firstName": "Naruto",

             "lastName": "Uzumaki",

             "address": "Kanoha, 142 apt.",

             "metroStation": "1",

             "phone": "+7 800 355 35 35",

             "rentTime": 5,

             "deliveryDate": "2020-06-06T00:00:00.000Z",

             "track": 521394,

             "status": 1,

             "color": \[

                 "BLACK"

             \],

             "comment": "Saske, come back to Kanoha",

             "cancelled": false,

             "finished": false,

             "inDelivery": false,

             "courierFirstName": "Kaneki"

             "createdAt": "2020-06-08T14:40:28.219Z",

             "updatedAt": "2020-06-08T14:40:28.219Z"

  }

}

### Ответ-ошибка

Запрос без номера

HTTP/1.1 400 Bad Request

{

  "message":  "Недостаточно данных для поиска"

}

### Ответ-ошибка

Запрос с несущесвующим номером

HTTP/1.1 404 Not Found

{

  "message": "Заказ не найден"

}
