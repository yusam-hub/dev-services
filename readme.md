#### сеть
    
    docker network ls
    docker network create --driver=bridge --subnet=10.0.0.0/16 --gateway=10.0.0.254 dev-network
    docker network inspect dev-network
    docker network rm dev-network
	
#### exec

    docker exec -it dev-php74 sh
    docker exec -it dev-pgsql sh
    
    psql -h localhost -U postgres
    \l
