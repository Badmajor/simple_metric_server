# simple_metric_server

Быстро установить и настроить систему мониторинга для отслеживания
потребления ресурсов и состояния сервера с просмотром состояния через web страницу.

Что необходимо: 
1. Docker compose
2. Открытый порт 3000
3. 10 мин времени

### Клонируем репозиторий
git clone https://github.com/Badmajor/simple_metric_server.git

### Переходим в каталог с docker файлом
cd simple_metric_server/

### Создаем .env
echo "USER=root
PASSWORD=<ВАШ_ПАРОЛЬ>" > .env

замените ВАШ_ПАРОЛЬ на ваш пароль

### Запускаем оркестр контейнеров
sudo docker compose up -d

### Настроим отображение метрик
переходим по адресу <АДРЕС_ВАШЕГО_СЕРВЕРА>:3000 
login: root
password: Который вы указали выше

После успешного логина, переходим <АДРЕС_ВАШЕГО_СЕРВЕРА>:3000/dashboards и жмем на "+ Create Dashboard", 
далее "Import a dashboard". В поле Find and import dashboards  вводим ID нужного нам dashboard. 
Мне понравился 1860, но вы можете выбрать другой тут: https://grafana.com/grafana/dashboards/

Жмем Load и в поле Prometeus выбираем Prometeus. Жмем импорт и всё готово!

