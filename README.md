# Installation

Run project using these commands:

```
git clone https://github.com/aitym/laravel_docker.git aitym_test_task
cd aitym_test_task
cp .env.example .env
docker compose up -d
docker exec -it test-task-php composer install
docker exec -it test-task-php php artisan key:generate
docker exec -it test-task-php php artisan migrate
```

After that you can visit [http://127.0.0.1](http://127.0.0.1) in your browser and view the result.
