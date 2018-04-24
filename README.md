# Overview
Laravelが動作可能なDockerコンテナです

# Requirement
* Docker
* Docker Compose

# Environment
* PHP 5.6
* PostgreSQL
* Nginx
* PHP-FPM

```
git clone this-repo
cd laravel_container
```

* line 23のlaravel_project_dirを任意のプロジェクト名に変更
```
vi docker-compose.yml
```
```
### Laravel Application Code Container ######################

    application:
        build: ./application
        volumes:
            - ./laravel_project_dir:/var/www/laravel
```

```
docker-compose up
```
__初回起動の場合は完了するまで時間がかかります__

* workspaceコンテナでcomposerを実行
```
docker exec -it workspace_container bash
composer install
php artisan key:generate
```
