# Настройка деплоя

## Вариант 1: Деплой на собственный сервер

### 1. Настройка GitHub Secrets

В настройках репозитория (Settings > Secrets and variables > Actions) добавьте следующие секреты:

- `HOST` - IP адрес или домен вашего сервера
- `USERNAME` - имя пользователя для SSH подключения
- `SSH_KEY` - приватный SSH ключ для подключения к серверу
- `PORT` - порт для SSH подключения (обычно 22)

### 2. Настройка сервера

1. Установите Node.js на сервер:
```bash
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt-get install -y nodejs
```

2. Установите nginx:
```bash
sudo apt update
sudo apt install nginx
```

3. Создайте конфигурацию nginx:
```bash
sudo nano /etc/nginx/sites-available/your-domain
```

Добавьте конфигурацию:
```nginx
server {
    listen 80;
    server_name your-domain.com;
    root /var/www/your-project/dist;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

4. Активируйте сайт:
```bash
sudo ln -s /etc/nginx/sites-available/your-domain /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl reload nginx
```

### 3. Обновление пути в workflow

В файле `.github/workflows/deploy.yml` измените путь в секции "Deploy to server":
```yaml
script: |
  cd /var/www/your-project  # Измените на ваш путь
  git pull origin main
  npm ci
  npm run build
  sudo systemctl reload nginx
```

## Вариант 2: Деплой на GitHub Pages

### 1. Включение GitHub Pages

1. Перейдите в Settings > Pages
2. В разделе "Source" выберите "GitHub Actions"

### 2. Настройка домена (опционально)

Если у вас есть собственный домен:
1. Добавьте домен в настройках Pages
2. Создайте файл `public/CNAME` с вашим доменом

## Проверка деплоя

После настройки:

1. Сделайте push в ветку `main`
2. Перейдите в Actions в GitHub
3. Проверьте, что workflow выполнился успешно
4. Откройте ваш сайт в браузере

## Устранение проблем

### Ошибки SSH
- Проверьте правильность SSH ключа
- Убедитесь, что пользователь имеет права на сервер
- Проверьте настройки firewall

### Ошибки сборки
- Проверьте логи в Actions
- Убедитесь, что все зависимости установлены
- Проверьте конфигурацию TypeScript

### Проблемы с nginx
- Проверьте конфигурацию: `sudo nginx -t`
- Проверьте логи: `sudo tail -f /var/log/nginx/error.log`
- Убедитесь, что порт 80 открыт
