<p align="center">
    <a href="https://igc.su" target="_blank" style="color: inherit; text-decoration: none; display: flex; align-items: center; justify-content: center;">
        <img src="https://igc.su/images/IGC.png" height="100">
        <span style="font-size: 70px;">IGC</span>
    </a>
</p>

## О проекте

Это сайт небольшого интернет-сообщества IGC.\
Сайт используется для публикации Устава сообщества, проведения выборов и для вывода статистики. 

### API
Для использования API требуется авторизация через долгосрочный `Bearer`-токен. REST API.

- <span style="color: green">GET</span> `/api/members` - [Получение всех участников сообщества](#memberIndex)
- <span style="color: green">GET</span> `/api/members/{id}` - [Получение участника сообщества](#memberShow)
- <span style="color: SteelBlue">PUT</span> `/api/members/{id}` - [Обновление участника сообщества](#memberUpdate)
- <span style="color: Gold">POST</span> `/api/members` - Создание участника сообщества (не поддерживается)
- <span style="color: Crimson">DELETE</span> `/api/members/{id}` - Удаление участника сообщества (не поддерживается)


- <span style="color: green">GET</span> `/api/members` - [Получение всех ролей](#roleIndex)
- <span style="color: green">GET</span> `/api/roles/{id}` - [Получение роли](#roleShow)
- <span style="color: SteelBlue">PUT</span> `/api/roles/{id}` - [Обновление роли](#roleUpdate)
- <span style="color: Gold">POST</span> `/api/roles` - Создание роли (не поддерживается)
- <span style="color: Crimson">DELETE</span> `/api/roles/{id}` - [Удаление роли](#roleDelete)


- <span style="color: green">GET</span> `/api/channels` - [Получение всех каналов](#channelIndex)
- <span style="color: green">GET</span> `/api/channels/{id}` - [Получение канала](#channelShow)
- <span style="color: SteelBlue">PUT</span> `/api/channels/{id}` - [Обновление канала](#channelUpdate)
- <span style="color: Gold">POST</span> `/api/channels` - Создание канала (не поддерживается)
- <span style="color: Crimson">DELETE</span> `/api/channels/{id}` - [Удаление канала](#channelDelete)

---
<h5 name="memberIndex"><span style="color: green">GET</span> `/api/members` Получение всех участников сообщества</h5>
Params:
- `page` - Страница (optional, default. 1)
- `count` - Кол-во элементов на одной странице (optional, default. 10000)
```json
{
    "current_page": 1,
    "data": [
        {
            "id": 256114365894230018,
            "name": "Русиш",
            "discriminator": "0197",
            "avatar": "avatars/256114365894230018/b09f871fbb4b2ec25883a72ae71eea03",
            "search": "256114365894230018русиш#0197",
            "roles": "['562545964708134912', '613412133715312641', '648762974277992448']",
            "headRole": "607650874097139733",
            "created_at": "2022-07-24T16:48:38.000000Z",
            "updated_at": "2022-07-24T16:48:38.000000Z"
        }
    ],
    "first_page_url": "https://igc.su/api/members?page=1",
    "from": 1,
    "last_page": 1,
    "last_page_url": "https://igc.su/api/members?page=1",
    "links": [
        {
            "url": null,
            "label": "&laquo; Previous",
            "active": false
        },
        {
            "url": "https://igc.su/api/members?page=1",
            "label": "1",
            "active": true
        },
        {
            "url": null,
            "label": "Next &raquo;",
            "active": false
        }
    ],
    "next_page_url": null,
    "path": "https://igc.su/api/members",
    "per_page": 10000,
    "prev_page_url": null,
    "to": 1,
    "total": 1
}
```
---
<h5 name="memberShow"><span style="color: green">GET</span> `/api/members/{id}` Получение участника сообщества</h5>
```json
{
    "id": 256114365894230018,
    "name": "Русиш",
    "discriminator": "0197",
    "avatar": "avatars/256114365894230018/b09f871fbb4b2ec25883a72ae71eea03",
    "search": "256114365894230018русиш#0197",
    "roles": "['562545964708134912', '613412133715312641', '648762974277992448']",
    "headRole": "607650874097139733",
    "created_at": "2022-07-24T16:48:38.000000Z",
    "updated_at": "2022-07-24T16:48:38.000000Z"
}
```
---
<h5 name="memberUpdate"><span style="color: SteelBlue">PUT</span> `/api/members/{id}` Обновление участника сообщества</h5>
Params:
- `name` - Имя участника в сообществе (required, string, max:1000)
- `discriminator` - Дискриминатор участника (required, string, size:4)
- `avatar` - Кол-во элементов на одной странице (required, string, nullable)
- `roles` - Кол-во элементов на одной странице (required, json)
```json
{
    "id": 256114365894230018,
    "name": "Русиш",
    "discriminator": "0197",
    "avatar": "avatars/256114365894230018/b09f871fbb4b2ec25883a72ae71eea03",
    "search": "256114365894230018русиш#0197",
    "roles": "['562545964708134912', '613412133715312641', '648762974277992448']",
    "headRole": "607650874097139733",
    "created_at": "2022-07-24T16:48:38.000000Z",
    "updated_at": "2022-07-24T16:48:38.000000Z"
}
```
---
<h5 name="roleIndex"><span style="color: green">GET</span> `/api/roles` Получение всех ролей</h5>
Params:
- `page` - Страница (optional, default. 1)
- `count` - Кол-во элементов на одной странице (optional, default. 10000)
```json
{
    "current_page": 1,
    "data": [
        {
            "id": 648762974277992448,
            "name": "alive",
            "color": "13565893",
            "position": "90",
            "created_at": "2022-07-24T18:19:38.000000Z",
            "updated_at": "2022-07-24T18:19:38.000000Z"
        }
    ],
    "first_page_url": "https://igc.su/api/roles?page=1",
    "from": 1,
    "last_page": 1,
    "last_page_url": "https://igc.su/api/roles?page=1",
    "links": [
        {
            "url": null,
            "label": "&laquo; Previous",
            "active": false
        },
        {
            "url": "https://igc.su/api/roles?page=1",
            "label": "1",
            "active": true
        },
        {
            "url": null,
            "label": "Next &raquo;",
            "active": false
        }
    ],
    "next_page_url": null,
    "path": "https://igc.su/api/roles",
    "per_page": 10000,
    "prev_page_url": null,
    "to": 1,
    "total": 1
}
```
---
<h5 name="roleShow"><span style="color: green">GET</span> `/api/roles/{id}` Получение роли</h5>
```json
{
    "id": 648762974277992448,
    "name": "alive",
    "color": "13565893",
    "position": "90",
    "created_at": "2022-07-24T18:19:38.000000Z",
    "updated_at": "2022-07-24T18:19:38.000000Z"
}
```
---
<h5 name="roleUpdate"><span style="color: SteelBlue">PUT</span> `/api/roles/{id}` Обновление роли</h5>
Params:
- `name` - Название роли (required, string, max:1000)
- `color` - Цвет роли (required, string)
- `position` - Позиция роли (required, integer)
```json
{
    "id": 648762974277992448,
    "name": "alive",
    "color": "13565893",
    "position": "90",
    "created_at": "2022-07-24T18:19:38.000000Z",
    "updated_at": "2022-07-24T18:19:38.000000Z"
}
```
---
<h5 name="roleDelete"><span style="color: Crimson">DELETE</span> `/api/roles/{id}` Удаление роли</h5>
```json
{
    "id": 648762974277992448,
    "name": "alive",
    "color": "13565893",
    "position": "90",
    "created_at": "2022-07-24T18:19:38.000000Z",
    "updated_at": "2022-07-24T18:19:38.000000Z"
}
```
---
<h5 name="channelIndex"><span style="color: green">GET</span> `/api/channels` Получение всех каналов</h5>
Params:
- `page` - Страница (optional, default. 1)
- `count` - Кол-во элементов на одной странице (optional, default. 10000)
```json
{
    "current_page": 1,
    "data": [
        {
            "id": 453272494724349963,
            "type": "0",
            "position": "12",
            "name": "основной",
            "topic": "Основной канал для общения",
            "nsfw": "0",
            "parent_id": "500034754406645760",
            "created_at": "2022-07-24T18:52:58.000000Z",
            "updated_at": "2022-07-24T18:52:58.000000Z"
        }
    ],
    "first_page_url": "https://igc.su/api/channels?page=1",
    "from": 1,
    "last_page": 1,
    "last_page_url": "https://igc.su/api/channels?page=1",
    "links": [
        {
            "url": null,
            "label": "&laquo; Previous",
            "active": false
        },
        {
            "url": "https://igc.su/api/channels?page=1",
            "label": "1",
            "active": true
        },
        {
            "url": null,
            "label": "Next &raquo;",
            "active": false
        }
    ],
    "next_page_url": null,
    "path": "https://igc.su/api/channels",
    "per_page": 10000,
    "prev_page_url": null,
    "to": 1,
    "total": 1
}
```
---
<h5 name="channelShow"><span style="color: green">GET</span> `/api/channels/{id}` Получение канала</h5>
```json
{
    "id": 453272494724349963,
    "type": "0",
    "position": "12",
    "name": "основной",
    "topic": "Основной канал для общения",
    "nsfw": "0",
    "parent_id": "500034754406645760",
    "created_at": "2022-07-24T18:52:58.000000Z",
    "updated_at": "2022-07-24T18:52:58.000000Z"
}
```
---
<h5 name="channelUpdate"><span style="color: SteelBlue">PUT</span> `/api/channels/{id}` Обновление канала</h5>
Params:
- `type` - Тип канала (required, integer)
- `position` - Позиция канала (required, integer)
- `name` - Название канала (required, string, max:1000)
- `topic` - Описание канала (required, string, max:1000)
- `nsfw` - NSFW-метка канала (required, boolean)
- `parent_id` - ID канала родителя (required, integer)
```json
{
    "id": 453272494724349963,
    "type": "0",
    "position": "12",
    "name": "основной",
    "topic": "Основной канал для общения",
    "nsfw": "0",
    "parent_id": "500034754406645760",
    "created_at": "2022-07-24T18:52:58.000000Z",
    "updated_at": "2022-07-24T18:52:58.000000Z"
}
```
---
<h5 name="channelDelete"><span style="color: Crimson">DELETE</span> `/api/channels/{id}` Удаление канала</h5>
```json
{
    "id": 453272494724349963,
    "type": "0",
    "position": "12",
    "name": "основной",
    "topic": "Основной канал для общения",
    "nsfw": "0",
    "parent_id": "500034754406645760",
    "created_at": "2022-07-24T18:52:58.000000Z",
    "updated_at": "2022-07-24T18:52:58.000000Z"
}
```
