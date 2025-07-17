# FuturesAnalyzer
# Запуск проекта:
1. Скачать FuturesAnalyzer.rar, распаковать.
2. 1. Взять образы микросервисов в моем докер хабе (https://hub.docker.com/repositories/divaeed). Названия образов: divaeed/databaseservice, divaeed/datafetcherservice.
   2. Установка секрета: kubectl create secret generic postgresql-password --from-literal=PASSWORD="password"
   3. Установка всех файлов из архива kubernetes.rar через kubectl apply
# Http запросы для k8s:
- GET http://localhost:31374/api/records/all - вывод всех FuturesRecords.
- POST JSON http://localhost:32129/api/fetcher/records/send/sync - синхронное добавление FuturesRecord из JSON.
- POST JSON http://localhost:32129/api/fetcher/records/send/async - aсинхронное добавление FuturesRecord из JSON.
- GET http://futuresanalyzer.com/api/fetcher/binance/publish - считывание цен на BTCUSDT_251226 и BTCUSDT_250926, а затем добавление FuturesRecord.

# База данных PostgreSql:
![DataBase](https://github.com/user-attachments/assets/cecd736c-0ca7-41e7-9706-f8e9c310b8b1)

Пример, при котором подключение к интернету пропадает, из-за чего DataFetcherService не может взять информацию из binance, поэтому отправляет нулевую информацию, которую особым образом принимает DataBaseService:
<img width="860" height="104" alt="image" src="https://github.com/user-attachments/assets/e3180b92-fcfd-4466-8482-cf3fa41ab1ae" />
# Контейнеры:
![Containers](https://github.com/user-attachments/assets/e5bfe4c1-44f1-4e1c-857b-0e83703d5fd9)
