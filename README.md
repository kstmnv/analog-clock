# analog-clock

## Введение
Этот репозиторий содержит Web-приложение, которое показывает время.

## Архитектура
Приложение написано Javascript.

## Установка
### Docker
Для установки приложения воспользуйтесь образом с Dockerhub:
```
docker pull kstmnv/clock:latest
```
Для проверки установки воспользуйтесь командой:
```
docker ps
```
### Minikube K8s cluster
Для установки приложения в кластер внутри minikube в первую очередь потребуется [установить сам minikube](https://minikube.sigs.k8s.io/docs/start/). Для корректной работы приложения с подключенным мониторингом внутри minikube потребуется минимум 2 CPU и 4Гб оперативной памяти.
Клонирование репозитория на машину
```
git clone https://github.com/kstmnv/analog-clock
```
Запуск minikube
```
minikube start
```
Создание deployment и service
```
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```
Для доступа к приложению из внешней сети можно воспользоваться port-forward: 
```
kubectl port-forward service/clock-service 8080:8080
```
После приложение будет доступно по адресу http://localhost:8080/
## Как пользоваться?
Самая тонкая и быстрая стрелка – это секундная;

Стрелка потолще – это минутная;

Самая толстая и короткая стрелка – это часовая.

## Автор
* Ксения Таманова