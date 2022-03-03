# Документация к API проекта YAMDB (v1)

## Описание
Проект YaMDb собирает отзывы пользователей на различные произведения;

## Как запустить проект:
- Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/afivan20/api_yamdb.git
cd infra_sp2; cd infra
``` 
- Запустить контейнеры Docker:
```
docker-compose up -d --build
```
- Выполнить миграции внутри проекта:
```
docker-compose exec web python manage.py migrate
```
- Создать Супер Пользовтеля:
```
docker-compose exec web python manage.py createsuperuser
```
- Подключить статику:
```
docker-compose exec web python manage.py collectstatic --no-input
```
- Загрузить тестовую Базу Данных:
```
docker-compose exec web python manage.py importcsv
```

### Дополнительные команды:
- Создать дамп (резервную копию) базы:
```
docker-compose exec web python manage.py dumpdata > fixtures.json
#(unicode != UTF-8)
```
- Удалить запущенные контейнеры:
```
docker-compose down -v
```

*Автор*
_Иван Афанасьев, python-devloper_