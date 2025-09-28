down:
	cd srcs && docker-compose down -v && rm -rf ./requirements/wordpress/data && rm -rf ./requirements/mariadb/data
build:
	cd srcs && docker-compose up --build
ps:
	cd srcs && docker-compose ps
logs:
	cd srcs && docker-compose logs
nginx:
	cd srcs && docker-compose exec nginx sh
re: down build


mhanz:
	docker system prune -af --volumes ; docker volume prune -af ;

cr7: mhanz build