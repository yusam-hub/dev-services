#### алгоритм запуска
    
    1) Смотрим сети 
	- docker network ls
    2) Создаем сеть локальную для проектов
	- docker network create --driver=bridge --subnet=10.0.0.0/16 --gateway=10.0.0.254 dev-network
	3) Запускаем 
		- в папку configs/ssh - нужно добавить из windows id_rsa + id_rsa.pub + known_hosts (и потом в контейнере проставить права chmod 0600 на все файлы /root/.ssh/*, иначе composer не скачает файлы из локально репозитария)
		- docker compose up -d (или d_up_d.bat)
	4) Проверяем конейнеры
		- docker ps
	5) Проверяем сервисы
		- mailcatcher - http://localhost:8026
		- rabbitmq - http://localhost:8672
		- winpty docker exec -it dev-redis sh -c "redis-cli PING"
		- nginx+php74 - http://localhost:8074/
	