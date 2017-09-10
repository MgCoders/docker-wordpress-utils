Es necesario crear una red compartida:

sudo docker network create nginx-proxy

Para cada sitio nuevo, hay que configurar un subdominio en AWS RouteS5 y poner eso como VIRTUAL_HOST en el docker compose.
