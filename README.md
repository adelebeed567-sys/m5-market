# m5-market
Create a Full Stack Grocery and Delivery system with Laravel Backend and React Dashboard for Saft Al-Laban and Bulaq Al-Dakrur area."
m5-market/
├── backend/                  # Laravel API
│   ├── Dockerfile
│   ├── .env.example
│   ├── nginx.conf
│   └── (مشروع Laravel نفسه)
├── frontend/                 # React Dashboard
│   ├── Dockerfile
│   ├── nginx.conf
│   └── (مشروع React نفسه)
├── docker-compose.yml
├── .env
└── README.md
# backend/Dockerfile

FROM php:8.2-fpm

# تثبيت المتطلبات
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip \
    nodejs \
    npm

# تثبيت إضافات PHP
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

# تثبيت Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# تعيين دليل العمل
WORKDIR /var/www/html

# نسخ الملفات
COPY . .

# تثبيت تبعيات Laravel
RUN composer install --no-interaction --optimize-autoloader --no-dev

# إعداد التخزين
RUN chown -R www-data:www-data storage bootstrap/cache
RUN chmod -R 775 storage bootstrap/cache

# نشر التكوين
RUN php artisan config:cache
RUN php artisan route:cache
RUN php artisan view:cache
# backend/nginx.conf

server {
    listen 80;
    server_name localhost;
    root /var/www/html/public;
    index index.php index.html;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        fastcgi_pass backend:9000;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.ht {
        deny all;
    }
}


# frontend/Dockerfile

# مرحلة البناء
FROM node:18-alpine as build

WORKDIR /app

COPY package*.json ./
RUN npm ci --only=production

COPY . .
RUN npm run build

# مرحلة التشغيل
FROM nginx:alpine

COPY --from=build /app/build /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
EXPOSE 9000

CMD ["php-fpm"]


# frontend/nginx.conf

server {
    listen 80;
    server_name localhost;
    root /usr/share/nginx/html;
    index index.html;

    location / {
        try_files $uri /index.html;
    }

    location /api/ {
        proxy_pass http://backend:80;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
version: '3.8'

services:
  db:
    image: mysql:8.0
    container_name: m5_mysql
    restart: always
    environment:
      MYSQL_DATABASE: m5market
      MYSQL_ROOT_PASSWORD: rootpass
      MYSQL_USER: m5user
      MYSQL_PASSWORD: m5pass
    ports:
      - "3306:3306"
    volumes:
      - db_data:/var/lib/mysql
    networks:
      - m5_network

  redis:
    image: redis:7-alpine
    container_name: m5_redis
    restart: always
    ports:
      - "6379:6379"
    networks:
      - m5_network

  backend:
    build: ./backend
    container_name: m5_backend
    restart: always
    environment:
      - APP_ENV=production
      - APP_DEBUG=false
      - DB_CONNECTION=mysql
      - DB_HOST=db
      - DB_PORT=3306
      - DB_DATABASE=m5market
      - DB_USERNAME=m5user
      - DB_PASSWORD=m5pass
      - REDIS_HOST=redis
      - REDIS_PASSWORD=null
      - REDIS_PORT=6379
    volumes:
      - ./backend:/var/www/html
    depends_on:
      - db
      - redis
    networks:
      - m5_network

  nginx_backend:
    image: nginx:alpine
    container_name: m5_nginx_backend
    restart: always
    volumes:
      - ./backend/nginx.conf:/etc/nginx/conf.d/default.conf
      - ./backend:/var/www/html
    ports:
      - "8080:80"
    depends_on:
      - backend
    networks:
      - m5_network

  frontend:
    build: ./frontend
    container_name: m5_frontend
    restart: always
    ports:
      - "3000:80"
    depends_on:
      - backend
    networks:
      - m5_network

networks:
  m5_network:
    driver: bridge

volumes:
  db_data:
  smtp.mailtrap.io

  6th October
  docker-compose up -d --build
  docker exec m5_backend php artisan key:generate
docker exec m5_backend php artisan migrate --seed
