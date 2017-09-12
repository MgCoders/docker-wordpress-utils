Wordpress en contenedor Docker detrás de Nginx+LetsEncrypt
----------------------------------------------------------
### Sitio
Cada sitio debe configurar su virtual host en el docker-compose.yml y datos para el certificado LetsEncrypt en variables de entorno y el contenedor Nginx descubre el puerto interno al levantarlo. 
Para cada sitio nuevo, hay que configurar un subdominio en AWS que será el virtual host.

En env del docker-compose.yml

    VIRTUAL_HOST: silicon.mgcoders.com
    LETSENCRYPT_HOST: silicon.mgcoders.com
    LETSENCRYPT_EMAIL: info@mgcoders.com

### Servidor
Es necesario crear una red compartida:

	sudo docker network create nginx-proxy

### Secretos
Para crear los secretos:

	echo "secreto" | docker secret create nombre-del-secreto -
