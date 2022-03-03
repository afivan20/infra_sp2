docker-compose up -d --build

docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input

docker-compose exec web python manage.py importcsv


docker-compose exec web python manage.py dumpdata > fixtures.json
(unicode != UTF-8)

docker-compose down -v