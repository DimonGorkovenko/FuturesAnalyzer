# FuturesAnalyzer
# Запуск проекта:
1. Скачать FuturesAnalyzer.rar, распаковать.
2. 1. Взять образы микросервисов в моем докер хабе (https://hub.docker.com/repositories/divaeed). Названия образов: divaeed/databaseservice, divaeed/datafetcherservice.
   2. Установка секрета: kubectl create secret generic postgresql-password --from-literal=PASSWORD="password"
   3. Установка всех файлов из архива kubernetes.rar через kubectl apply
# Http запросы для k8s:
- GET http://localhost:31374/api/records/all - вывод всех FuturesRecords.
- POST JSON http://localhost:32129/api/fetcher/records/send/sync - добавление FuturesRecord из JSON.
- GET http://localhost:32129/api/fetcher/records/send/async - считывание цен на BTCUSDT_251226 и BTCUSDT_250926, а затем добавление FuturesRecord.

# База данных PostgreSql:
![DataBase](https://github.com/user-attachments/assets/cecd736c-0ca7-41e7-9706-f8e9c310b8b1)
# Контейнеры:
![Containers](https://github.com/user-attachments/assets/e5bfe4c1-44f1-4e1c-857b-0e83703d5fd9)
