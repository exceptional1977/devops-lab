# DevOps Lab: от кода до Kubernetes

Простое Flask-приложение, упакованное в Docker, с Nginx в качестве reverse proxy, и деплой в Minikube.

## Как запустить локально (Docker Compose)
1. Склонируйте репозиторий.
2. Выполните: `docker compose up -d`
3. Откройте http://localhost

## Как запустить в Kubernetes (Minikube)
1. Запустите Minikube: `minikube start`
2. Переключите docker: `eval $(minikube docker-env)`
3. Соберите образ: `docker build -t devops-lab:v1 ./app`
4. Примените манифесты: `kubectl apply -f k8s/`
5. Откройте приложение: `minikube service devops-lab-service`

## Структура
- `app/` — Flask приложение, Dockerfile
- `nginx/` — конфигурация Nginx
- `k8s/` — манифесты Kubernetes
- `docker-compose.yml` — локальный запуск
