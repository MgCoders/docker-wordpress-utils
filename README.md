Configuración para varios sitios WP detrás de una proxy reverso Nginx.

Nginx y los sitios estan en contenedores Docker. Cada sitio debe configurar su virtual host en el docker-compose.yml y el contenedor Nginx descubre el puerto interno al levantarlo. Para cada sitio nuevo, hay que configurar un subdominio en AWS RouteS5 que será en virtual host.

Es necesario crear una red compartida:

sudo docker network create nginx-proxy

