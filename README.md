Activity 6: Interact with the Artisan Command Console

1. Introducción

El objetivo de esta actividad fue aprender a utilizar los comandos de Laravel Artisan para crear componentes comunes de una aplicación y administrar las migraciones de la base de datos. La parte práctica consistió en crear un proyecto de Laravel llamado activity-6, generar un modelo Product con su migración, crear un controlador de recursos, preparar tres vistas Blade y publicar el proyecto en GitHub.
Se utilizó Laravel 12 porque funcionaba con la versión de PHP instalada en el entorno de desarrollo.

2. Parte 1: Comandos Artisan

Artisan es la interfaz de línea de comandos de Laravel. Ayuda a los desarrolladores a generar archivos, iniciar un servidor local, consultar los comandos disponibles y realizar tareas relacionadas con la base de datos sin tener que crear cada componente manualmente.

1. Generar una clave para la aplicación

php artisan key:generate

Este comando genera una clave de cifrado para la aplicación y la guarda en la configuración APP_KEY del archivo .env. Laravel utiliza esta clave para las funciones relacionadas con el cifrado. Normalmente, se genera durante la configuración inicial del proyecto.

2. Iniciar el servidor de desarrollo local

php artisan serve

Este comando inicia el servidor de desarrollo integrado de Laravel, normalmente en la dirección http://127.0.0.1:8000. Es útil para abrir y probar la aplicación en un navegador durante el desarrollo.

3. Crear un enlace simbólico para el almacenamiento

php artisan storage:link

Este comando crea un enlace simbólico desde public/storage hacia storage/app/public. Permite acceder mediante direcciones URL públicas a los archivos almacenados en el disco público de Laravel, como las imágenes subidas, siempre que la configuración sea adecuada.

4. Crear un modelo llamado Product

php artisan make:model Product

Este comando crea una clase de modelo Eloquent para Product, normalmente en app/Models/Product.php. Un modelo representa un tipo de dato de la aplicación y proporciona una manera sencilla de trabajar con sus registros en la base de datos.

5. Crear un controlador Product y un controlador de recursos

php artisan make:controller ProductController
php artisan make:controller ProductController --resource

El primer comando crea un controlador básico. El segundo crea un controlador de recursos con métodos utilizados comúnmente para las operaciones CRUD: index, create, store, show, edit, update y destroy.

Un controlador de recursos organiza las acciones para listar, crear, consultar, actualizar y eliminar productos.

6. Crear una migración para la tabla Product

php artisan make:migration create_products_table --create=products

Este comando crea un archivo de migración en database/migrations. La migración define la estructura de la tabla products y permite aplicar o revertir cambios en su estructura.

En este proyecto, el modelo y la migración se generaron juntos mediante el siguiente comando:

php artisan make:model Product -m

7. Crear un seeder para Product

php artisan make:seeder ProductSeeder

Este comando crea una clase seeder en database/seeders. Un seeder permite insertar registros de ejemplo o datos iniciales en la base de datos, lo cual es útil durante el desarrollo y las pruebas.

La creación del seeder no inserta datos automáticamente; es necesario programarlo y ejecutarlo.

8. Crear una factory para Product

php artisan make:factory ProductFactory --model=Product

Este comando crea una factory del modelo en database/factories. Una factory define valores de ejemplo para los atributos de un modelo y permite generar datos de prueba de manera repetible.

La factory debe configurarse con los campos correspondientes de Product antes de poder crear registros válidos.

9. Mostrar los comandos Artisan disponibles

php artisan list

Este comando muestra los comandos Artisan disponibles en el proyecto. Es útil para descubrir comandos y verificar sus nombres.

Para consultar las opciones de un comando específico, también se puede utilizar php artisan help, seguido del nombre del comando.

10. Ejecutar, revertir, actualizar y poblar las migraciones

php artisan migrate
php artisan migrate:rollback
php artisan migrate:refresh
php artisan migrate --seed
php artisan migrate:refresh --seed

El comando migrate ejecuta las migraciones pendientes.

El comando migrate:rollback revierte el último grupo de migraciones ejecutadas.

El comando migrate:refresh revierte todas las migraciones y las vuelve a ejecutar.

La opción --seed ejecuta los seeders de la base de datos después de las migraciones.

Por lo tanto, migrate --seed ejecuta las migraciones pendientes y después los seeders, mientras que migrate:refresh --seed reconstruye la estructura de la base de datos mediante las migraciones y posteriormente ejecuta los seeders.

El comando refresh puede eliminar datos existentes, por lo que debe utilizarse con cuidado, especialmente cuando se trabaja con bases de datos importantes.

3. Parte 2: Desarrollo del proyecto

3.1 Configuración del proyecto

El proyecto de Laravel se creó con el nombre activity-6. La versión instalada del framework se verificó mediante el siguiente comando:

php artisan --version

El resultado obtenido fue Laravel Framework 12.70.0.

3.2 Modelo Product, migración y controlador de recursos

El modelo Product y su migración se generaron juntos mediante el siguiente comando:

php artisan make:model Product -m

El modelo generado se encuentra en app/Models/Product.php. La migración se creó en database/migrations con un nombre de archivo que incluye una marca de tiempo y termina en create_products_table.php.

El controlador de recursos se generó mediante el siguiente comando:

php artisan make:controller ProductController --resource

El controlador se encuentra en app/Http/Controllers/ProductController.php.

Esta actividad permitió generar los archivos del modelo, la migración y el controlador. No fue necesario ejecutar la migración para completar la parte de la actividad relacionada con la generación de archivos.

3.3 Vistas Blade

Se creó una carpeta llamada products dentro de resources/views. Posteriormente, se agregaron tres archivos Blade con los títulos HTML solicitados:

resources/views/products/index.blade.php — <title>Product View</title>

resources/views/products/edit.blade.php — <title>Product Editing</title>

resources/views/products/create.blade.php — <title>New Product Creation</title>

También se configuraron las rutas en routes/web.php para que las tres vistas pudieran abrirse en un navegador.

Las páginas se probaron utilizando el servidor de desarrollo local de Laravel.

3.4 Git y GitHub

El proyecto se inicializó como un repositorio Git y se publicó en GitHub utilizando GitHub Desktop.

El commit se verificó en GitHub Desktop y los archivos del proyecto se visualizaron en el repositorio de GitHub.

El archivo README.md contiene únicamente el título de la actividad, tal como se solicitó.

Repositorio de GitHub: https://github.com/diegocfl99/activity-6

Mensaje del commit: Base Products

Contenido del README.md: Activity 6: Interact with the Artisan Command Console

4. Conclusión

En esta actividad practiqué el uso de Artisan para generar componentes de Laravel y aprendí la función de los modelos, las migraciones, los controladores, los seeders, las factories y los comandos de desarrollo.

También creé vistas Blade, configuré rutas para mostrarlas y utilicé GitHub Desktop para publicar el proyecto.

Estos pasos me ayudaron a comprender la estructura básica de un proyecto Laravel y un flujo de trabajo sencillo para el control de versiones.
