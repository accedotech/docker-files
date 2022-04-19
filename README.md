Cuando se clone un proyecto de GITHUB este no viene con los paquetes de laravel
instalados, para hacer esta instalacion del "vendor" se debe ejecutar el
siguiente comando:

```
docker run --rm -v "$(pwd):/var/www/html" -w /var/www/html laravelsail/php81-composer:latest composer install --ignore-platform-reqs
```

La seccion de `php81-composer:latest` se debe de acomodar con la version de php
**(74, 80, 81)**

**NOTA:** Se debe de estar ubicado dentro de la carpeta del proyecto en la
terminal.

---

- Para ejecutar el `docker-compose.yml` se debe usar el comando:

```
docker-compose up -d --build
```

La bandera `--build` se debe usar cuando en el archivo del `docker-compose.yml`
hay una seccion build que usa un `dokerfile` si no existe no se coloca en el
anterior comando.

- Para entrar a un contenedor y poder ejecutar los comandos (artisan, npm,
  composer etc..) se usa:

```
docker exec -it <nombre_contenedor> bash
```

- La ip de docker para comunicase entre contenedores es:

```
172.17.0.1:<puerto_contenedor>
```

**NOTA:** Para que los contenedores se comuniquen entre ellos se debe de usar la
misma red entre contenedores.
