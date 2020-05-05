# EmailPusher

## Зависимости
Надо иметь установленные python>=3.6 и pip к нему.  
В командной строке вводим:
```shell
pip3 install aiohttp asyncpg python-dateutil pyyaml
```

## Начало работы
### Конфигурационный файл
Копируем (или переименовываем) файл config-sample.yml в config.yml и прописываем в нём данные от Postgres базы данных, а также ключ api и нужный список в Unisender.
### Запуск
Просто вводим в консоли...
```shell
python3 main.py
```
...и готово, сервис висит на порту 8080.  
Можно запускать вместе с системой, но как – тут не описано :)

## Запросы
Все запросы совершаются GET-методом
### Добавление email в очередь на отправку
Путь: **/add_entry**  
Параметры:  
*email* - email для внесения в список  
*time* - время внесения в список в формате YYYY-MM-DD HH:MM:SS  
### Очистить день от очереди
Путь: **/remove_day**  
Параметры:  
*day* - день для очистки в формате YYYY-MM-DD  