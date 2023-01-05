# Let-s-share-comics
Publish comics xkcd in VK

## Скрипт для публикации комиксов с сайта [xkcd.com](https://xkcd.com) в социальную сеть [ВКонтакте](https://vk.com/)
___
### Установка:

1. Скачайте код.
2. Для работы скрипта нужен Python версии не ниже 3.6 (должен быть уже установлен).
3. Установите зависимости, указанные в файле requirements.txt командой:

```
pip install -r requirements.txt
```

4. Для работы скрипта необходимо:

  * Получить access_token:

  * Зарегистрировать приложение:

    [Ссылка для регистрации приложения](https://vk.com/dev) 

  - меню "Мои приложения" вверху страницы;
  - в качестве типа приложения следует указать standalone — это подходящий тип для приложений, которые просто запускаются на компьютере.

  * После регистрации приложения, если нажать на кнопку “Редактировать”, 
  в адресной строке вы увидите его client_id (он пригодится при формировании токена).

  * Получить токен: 

    [Ссылка для получения токена](https://vk.com/dev/implicit_flow_user). 

  - необходимо убрать параметр `redirect_uri` у запроса на ключ, а в параметр scope указать через запятую, вот так: 

    ```
    scope=photos, groups, wall, offline
    ```

  * Токен выглядит как строка наподобие `533bacf01e1165b57531ad114461ae8736d6506a3`, 
  она появится в адресной строке, подписанная как `access_token=v1.a.13......`

  * Cоздать группу и получить group_id:

  [Ссылка для получения group_id](https://regvk.com/id/)

5. Полученные в предыдущем пункте переменные (access_token и group_id) необходимо записать в созданный в корне проекта файл ``.env`` следующим образом:

```
VK_TOKEN=v1.a.136791528.bb7d... 
VK_GROUP_ID=9926..

``` 
___
### Запуск
Скрипт запускается командой:

```
python3 main.py
```

Результатом запуска будет опубликованный в созданной группе комикс.

