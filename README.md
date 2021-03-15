# CRUD Modelo Vista Controlador (MVC)
## Generando Migraciones Y Model para Categoria

.............
php artisan make:model Categoria -m
.............

## Generar el controlador con recursos para (CategoriaController)

.............
php artisan make:controller CategoriaController --resource

php artisan make:controller CategoriaController --r
..............

## Registrar las rutas en (routes/web.php) para Categoria

......................
use App\Http\Controllers\CategoriaController;

Route::resource("/categoria",CategoriaController::class)
......................

## para verificar la lista de rutas de nuestro proyecto

.....................
php artisan route:list
.....................
## Creamos manualmente 4 vistas en la carpeta (resources/viiews/categoria)
...........
listar.blade.php
mostrar.blade.php
editar.blade.php
crear.blade.php
...........
## Ahora para Producto

...........
php artisan make:model producto -a
............

## Registrar las rutas en (routes/web.php) para Producto

......................
use App\Http\Controllers\ProductoController;

Route::resource("/producto",ProductoController::class)
......................

## Para las migraciones de Categoria
..........................
$table->string("nombre",30)
$table->text("descripcion")-> nullable();
..........................

## Para las migraciones de Producto
..........................
$table->string("nombre");
            $table->decimal("precio",10,2)->default(0);
            $table->integer("cantidad")->default(1);
            $table->text("descripcion")->nullable();
            $table->bigInteger("categoria_id")->unsigned();

            $table->foreign("categoria_id")->references("id")->on("categorias");
..........................
## Conexion y creacion de la Base de Datos "taller6"(.env)

...........
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=taller6
DB_USERNAME=root
DB_PASSWORD=
............

## Migracion de las tablas

...............
php artisan migrate
...............

## Consultas en Controladores


## Levantar el Servidor

........
php artisan serve
..........






