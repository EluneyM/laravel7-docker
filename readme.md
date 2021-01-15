# Laravel 7 dockerizado para proyectos

Laravel 7 instalación limpia, dockerizado, con composer, npm y artisan en contenedores separados para evitar instalar dependencias en maquina host.

## Requerimientos

Se requiere la instalación de [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git), [docker](https://docs.docker.com/engine/install/) y [docker-compose](https://docs.docker.com/compose/install/).

## Instalación


1. Clonar el proyecto

    ```
    git clone https://github.com/EluneyM/laravel7-docker.git 
    ```

2. Moverse a la raíz del proyecto

    ```
    cd laravel7-docker
    ```

3. Copiar archivo .env.example de la raíz del proyecto

    ```
    cp .env.example .env
    ```

4. Copiar archivo src/.env.example de la carpeta de Laravel

    ```
    cp src/.env.example src/.env
    ```

5. Editar las variables de entorno en el archivo de la raíz del proyecto, puedes usar el editor que gustes. Ej: vim

    ```
    vim .env
    ```

6. Copiar el archivo docker-compose.dist.yml

    ```
    cp docker-compose.dist.yml docker-compose.yml
    ```

7. Editar los puertos si entran en conflicto con otros contenedores

    ```
    vim docker-compose.yml
    ```

8. Reconstruir imagen

    ```
    docker-compose up -d --build
    ```

9. Instalar dependencias

    ```
    docker-compose run --rm composer update
    ```

10. Instalar npm

    ```
    docker-compose run --rm npm install
    ```

11. Ejecutar

    ```
    docker-compose run --rm npm run dev
    ```

12. Ejecutar migraciones

    ```
    docker-compose run --rm artisan migrate:refresh
    ```


## Uso

* El proyecto esta disponible en la url por defecto

    ```
    localhost:9001
    ```

* Detener contenedores (en la raiz del proyecto)

    ```
    docker-compose down
    ```

* Ejecutar contenedores

    ```
    docker-compose up
    ```

* Ejecutar Composer

    ```
    docker-compose run --rm composer "ingrese-el-comando-sin-comillas"
    ```

* Ejecutar NPM

    ```
    docker-compose run --rm npm "ingrese-el-comando-sin-comillas"
    ```

* Ejecutar Artisan

    ```
    docker-compose run --rm artisan "ingrese-el-comando-sin-comillas"
    ```

## Licencia
Sin determinar
