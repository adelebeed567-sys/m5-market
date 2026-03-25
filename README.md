# m5-market
Create a Full Stack Grocery and Delivery system with Laravel Backend and React Dashboard for Saft Al-Laban and Bulaq Al-Dakrur area."
m5-market/
├── backend/        
# Laravel APIM5-Zone-Full-Project.zip (حجم الملف: ~450 MB)
│
├── 📁 01-backend-laravel/
│   ├── app/
│   │   ├── Models/
│   │   │   ├── User.php
│   │   │   ├── Vendor.php
│   │   │   ├── Product.php
│   │   │   ├── Category.php
│   │   │   ├── Order.php
│   │   │   ├── OrderItem.php
│   │   │   ├── Cart.php
│   │   │   ├── DeliveryAgent.php
│   │   │   ├── DeliveryTask.php
│   │   │   └── Notification.php
│   │   ├── Http/
│   │   │   ├── Controllers/
│   │   │   │   ├── Api/
│   │   │   │   │   ├── AuthController.php
│   │   │   │   │   ├── ProductController.php
│   │   │   │   │   ├── VendorController.php
│   │   │   │   │   ├── OrderController.php
│   │   │   │   │   ├── CartController.php
│   │   │   │   │   ├── DeliveryController.php
│   │   │   │   │   └── AdminController.php
│   │   │   │   └── Controller.php
│   │   │   └── Middleware/
│   │   │       ├── AdminMiddleware.php
│   │   │       ├── VendorMiddleware.php
│   │   │       └── DeliveryMiddleware.php
│   │   └── Providers/
│   ├── database/
│   │   ├── migrations/
│   │   │   ├── 2024_01_01_000001_create_users_table.php
│   │   │   ├── 2024_01_01_000002_create_vendors_table.php
│   │   │   ├── 2024_01_01_000003_create_categories_table.php
│   │   │   ├── 2024_01_01_000004_create_products_table.php
│   │   │   ├── 2024_01_01_000005_create_carts_table.php
│   │   │   ├── 2024_01_01_000006_create_orders_table.php
│   │   │   ├── 2024_01_01_000007_create_order_items_table.php
│   │   │   ├── 2024_01_01_000008_create_delivery_agents_table.php
│   │   │   ├── 2024_01_01_000009_create_delivery_tasks_table.php
│   │   │   └── 2024_01_01_000010_create_notifications_table.php
│   │   └── seeders/
│   │       ├── DatabaseSeeder.php
│   │       ├── UsersTableSeeder.php
│   │       ├── VendorsTableSeeder.php
│   │       └── ProductsTableSeeder.php
│   ├── routes/
│   │   └── api.php
│   ├── .env.example
│   ├── composer.json
│   └── artisan
│
├── 📁 02-admin-react/
│   ├── src/
│   │   ├── pages/
│   │   │   ├── Dashboard.js
│   │   │   ├── Vendors.js
│   │   │   ├── VendorDetails.js
│   │   │   ├── Products.js
│   │   │   ├── Orders.js
│   │   │   ├── OrderDetails.js
│   │   │   ├── Customers.js
│   │   │   ├── DeliveryAgents.js
│   │   │   ├── Reports.js
│   │   │   └── Settings.js
│   │   ├── components/
│   │   │   ├── Sidebar.js
│   │   │   ├── Header.js
│   │   │   ├── StatsCard.js
│   │   │   ├── DataTable.js
│   │   │   └── Chart.js
│   │   ├── services/
│   │   │   └── api.js
│   │   ├── context/
│   │   │   └── AuthContext.js
│   │   ├── utils/
│   │   │   └── formatters.js
│   │   ├── App.js
│   │   ├── index.js
│   │   └── index.css
│   ├── public/
│   │   └── index.html
│   ├── package.json
│   ├── tailwind.config.js
│   └── README.md
│
├── 📁 03-customer-app/
│   ├── lib/
│   │   ├── main.dart
│   │   ├── models/
│   │   │   ├── user.dart
│   │   │   ├── vendor.dart
│   │   │   ├── product.dart
│   │   │   ├── category.dart
│   │   │   ├── cart.dart
│   │   │   └── order.dart
│   │   ├── screens/
│   │   │   ├── splash_screen.dart
│   │   │   ├── onboarding_screen.dart
│   │   │   ├── auth/
│   │   │   │   ├── login_screen.dart
│   │   │   │   └── register_screen.dart
│   │   │   ├── home/
│   │   │   │   ├── home_screen.dart
│   │   │   │   └── vendor_detail_screen.dart
│   │   │   ├── product/
│   │   │   │   ├── product_detail_screen.dart
│   │   │   │   └── search_screen.dart
│   │   │   ├── cart/
│   │   │   │   └── cart_screen.dart
│   │   │   ├── order/
│   │   │   │   ├── orders_screen.dart
│   │   │   │   ├── order_detail_screen.dart
│   │   │   │   └── checkout_screen.dart
│   │   │   └── profile/
│   │   │       ├── profile_screen.dart
│   │   │       └── edit_profile_screen.dart
│   │   ├── widgets/
│   │   │   ├── product_card.dart
│   │   │   ├── vendor_card.dart
│   │   │   ├── category_chip.dart
│   │   │   └── loading_widget.dart
│   │   ├── providers/
│   │   │   ├── auth_provider.dart
│   │   │   ├── cart_provider.dart
│   │   │   └── order_provider.dart
│   │   ├── services/
│   │   │   ├── api_service.dart
│   │   │   └── notification_service.dart
│   │   └── utils/
│   │       ├── constants.dart
│   │       ├── theme.dart
│   │       └── helpers.dart
│   ├── assets/
│   │   ├── images/
│   │   └── fonts/
│   ├── pubspec.yaml
│   └── android/
│
├── 📁 04-vendor-app/
│   ├── lib/
│   │   ├── main.dart
│   │   ├── models/
│   │   │   ├── vendor.dart
│   │   │   ├── product.dart
│   │   │   └── order.dart
│   │   ├── screens/
│   │   │   ├── auth/
│   │   │   │   ├── login_screen.dart
│   │   │   │   └── register_screen.dart
│   │   │   ├── dashboard/
│   │   │   │   └── dashboard_screen.dart
│   │   │   ├── products/
│   │   │   │   ├── products_screen.dart
│   │   │   │   ├── add_product_screen.dart
│   │   │   │   └── edit_product_screen.dart
│   │   │   ├── orders/
│   │   │   │   ├── orders_screen.dart
│   │   │   │   └── order_detail_screen.dart
│   │   │   └── profile/
│   │   │       └── profile_screen.dart
│   │   ├── widgets/
│   │   │   ├── product_card.dart
│   │   │   ├── order_card.dart
│   │   │   └── stats_card.dart
│   │   ├── providers/
│   │   │   ├── auth_provider.dart
│   │   │   ├── product_provider.dart
│   │   │   └── order_provider.dart
│   │   └── services/
│   │       └── api_service.dart
│   ├── pubspec.yaml
│   └── android/
│
├── 📁 05-delivery-app/
│   ├── lib/
│   │   ├── main.dart
│   │   ├── models/
│   │   │   ├── delivery_task.dart
│   │   │   └── order.dart
│   │   ├── screens/
│   │   │   ├── auth/
│   │   │   │   └── login_screen.dart
│   │   │   ├── home/
│   │   │   │   ├── home_screen.dart
│   │   │   │   └── tasks_screen.dart
│   │   │   ├── task/
│   │   │   │   ├── task_detail_screen.dart
│   │   │   │   ├── delivery_confirmation_screen.dart
│   │   │   │   └── signature_pad.dart
│   │   │   ├── earnings/
│   │   │   │   └── earnings_screen.dart
│   │   │   └── profile/
│   │   │       └── profile_screen.dart
│   │   ├── widgets/
│   │   │   ├── task_card.dart
│   │   │   └── status_badge.dart
│   │   ├── providers/
│   │   │   ├── auth_provider.dart
│   │   │   ├── task_provider.dart
│   │   │   └── location_provider.dart
│   │   └── services/
│   │       ├── api_service.dart
│   │       └── location_service.dart
│   ├── pubspec.yaml
│   └── android/
│
├── 📁 06-database/
│   ├── m5zone.sql
│   └── sample-data.sql
│
├── 📁 07-postman/
│   └── M5Zone-API.postman_collection.json
│
├── 📁 08-docs/
│   ├── installation-guide.pdf
│   ├── api-documentation.pdf
│   └── user-manual.pdf
│
└── 📁 09-videos/
    └── setup-tutorial.mp4
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

فيا باشمهندس، بعد أن جهزنا ملفات Docker، الآن ننتقل إلى رفع الموقع على سيرفر حقيقي (سواء كان VPS أو سحابة مثل AWS، DigitalOcean). سأشرح لك خطوات التشغيل النهائية.

---

🌐 خطوات رفع الموقع (Deployment)

1. متطلبات السيرفر

· سيرفر Linux (Ubuntu 22.04 مثلاً)
· Docker و Docker Compose مثبتان.
· Domain (اختياري، لكن يفضل لاحقاً).

2. نقل الملفات إلى السيرفر

```bash
# على السيرفر، أنشئ مجلداً للمشروع
mkdir ~/m5-market
cd ~/m5-market

# إذا كان الكود في GitHub، استنسخه
git clone https://github.com/your-username/m5-market.git .

# أو انسخ الملفات عبر SCP من جهازك
scp -r ./m5-market root@your-server-ip:~
```

3. إعداد المتغيرات البيئية

```bash
# انسخ ملفات .env.example
cp backend/.env.example backend/.env
cp .env.example .env   # إذا كان هناك ملف عام

# عدّل backend/.env (ضبط قاعدة البيانات)
# استخدم قيم الحاويات:
# DB_HOST=db
# DB_DATABASE=m5market
# DB_USERNAME=m5user
# DB_PASSWORD=m5pass
# REDIS_HOST=redis
```

4. تشغيل الحاويات

```bash
docker-compose up -d --build
```

بعد الانتهاء، تحقق من تشغيل الحاويات:

```bash
docker-compose ps
```

5. تثبيت تبعيات Laravel وإعداد قاعدة البيانات

```bash
# الدخول إلى حاوية backend
docker exec -it m5_backend bash

# داخل الحاوية:
composer install
php artisan key:generate
php artisan migrate --seed
exit
```

6. ضبط الصلاحيات (إن لزم)

```bash
docker exec m5_backend chown -R www-data:www-data storage bootstrap/cache
docker exec m5_backend chmod -R 775 storage bootstrap/cache
```

7. اختبار الموقع

· Backend API: افتح http://<server-ip>:8080 – يجب أن ترى صفحة Laravel الافتراضية.
· Frontend Dashboard: http://<server-ip>:3000 – يجب أن تظهر واجهة React.

8. ربط دومين (اختياري)

إذا كان لديك دومين، يمكنك توجيهه عبر Nginx Proxy Manager أو تعديل docker-compose لإضافة domain في nginx.

مثال على تعديل docker-compose.yml:

```yaml
nginx_backend:
  ports:
    - "80:80"
    - "443:443"
  volumes:
    - ./certs:/etc/nginx/certs
```

ثم إعداد SSL باستخدام Let's Encrypt (يمكنك استخدام Certbot أو Nginx Proxy Manager).

---

✅ الخلاصة

· المشروع جاهز للإطلاق بمجرد تنفيذ الخطوات أعلاه.
· الخدمات: Laravel API على منفذ 8080، React Dashboard على 3000.
· المناطق المدعومة حالياً: صفط اللبن، بولاق الدكرور (قابلة للإضافة عبر واجهة المشرف أو قاعدة البيانات).

هل تريد مني توثيق خطوات إعداد SSL وربط الدومين بشكل مفصل؟
