# docker-laravel
setup docker: connect Laravel + ubuntu + nginx + mysql<br>
Website: http://127.0.0.1:8080<br>
Database: http://127.0.0.1:8081<br>

# How to build
<b>1. Pull code</b><br>
<code>git clone https://github.com/dungnv93/docker-laravel.git</code>

<b>2. In root folder(docker-laravel), start docker compose</b><br>
<code>docker-compose up -d</code>

<b>3. ssh to docker app server</b><br>
<code>docker-compose exec app bash</code>

<b>4. run composer install</b><br>
<code>composer install</code>

<b>5. setting permission for storage and bootstrap</b><br>
<code>chown -R root:www-data storage/</code><br>
<code>chmod -R 775 storage/</code><br>
<code>chown -R root:www-data bootstrap/</code><br>
<code>chmod -R 775 bootstrap/</code><br>

<b>6. Create file .env</b><br>
<code>cp .env.example .env</code><br>
Change value params in .env:<br>
<code>DB_HOST=mysql</code><br>
<code>DB_USERNAME=root</code><br>
<code>DB_PASSWORD=123456</code><br>
<code>DB_DATABASE=sample</code><br>
<code>APP_PORT=8080</code><br>
<code>APP_ADMINER=8081</code><br>

<b>7. generate laravel key</b><br>
<code>php artisan key:generate</code>

<b>8. run migrate create database</b><br>
<code>php artisan migrate</code>

<b>9. Finished: Check by go to browser</b><br>
<code>Website: </code><br>
<code>127.0.0.1:8080</code><br>
<code>Database: </code><br>
<code>127.0.0.1:8081</code><br>
