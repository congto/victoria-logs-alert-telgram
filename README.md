# victoria-logs-alert-telgram
Victorialogs - vmalert - alertmanager - telegram

Các bước thực hiện


Tải repo

```
git clone https://github.com/congto/victoria-logs-alert-telgram.git
cd victoria-logs-alert-telgram/
```

Sửa file `.env` để thay thế các tham số cần thiết như: tele, slack


Chạy container 

```
docker compose up -d --build
```

Kiểm tra lại

```
docker ps
```


Truy cập vào các ip và port

Test cảnh báo của alertmanager

```
curl -X POST http://localhost:9093/api/v2/alerts -H 'Content-Type: application/json' -d '[{"labels":{"alertname":"TEST"}}]'

curl -X POST http://172.16.91.30:9093/api/v2/alerts -H 'Content-Type: application/json' -d '[{"labels":{"alertname":"TEST"}}]'
```