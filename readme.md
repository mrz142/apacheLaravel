# to install laravel Run this
 docker-compose run --rm composer create-project laravel/laravel
# if you have problem with laravel ==> 
## file_put_contents(/var/www/html/laravel/storage/framework/views/823ba0f21fb92d4957f115f907d5ac44.php): Failed to open stream: Permission denied
### inter this comond in php container 
docker exec -it php /bin/sh
cd laravel
chmod -R gu+w storage
chmod -R guo+w storage
php artisan cache:clear
# if you have problem with laravel ==> Internal Server Error
## Illuminate\Database\QueryException
## SQLSTATE[HY000]: General error: 8 attempt to write a readonly database (Connection: sqlite, SQL: update "sessions" set "payload" = YTozOntzOjY6Il90b2tlbiI7czo0MDoiYkZCd094ZmN6TzBtMzFtNW42Rk9aS3JVNnJLblJVbk9FSWU0alYzNyI7czo5OiJfcHJldmlvdXMiO2E6MTp7czozOiJ1cmwiO3M6MTY6Imh0dHA6Ly9sb2NhbGhvc3QiO31zOjY6Il9mbGFzaCI7YToyOntzOjM6Im9sZCI7YTowOnt9czozOiJuZXciO2E6MDp7fX19, "last_activity" = 1733811449, "user_id" = ?, "ip_address" = 172.19.0.1, "user_agent" = Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36, "id" = rJNbpc0o2TTRzT7rvTiyoaRc0KEGVBt6eHI85JC2 where "id" = rJNbpc0o2TTRzT7rvTiyoaRc0KEGVBt6eHI85JC2)
correct .env file if the error occurred again run the in php container : 
chmod -R 775 database/
chown -R www-data:www-data database/