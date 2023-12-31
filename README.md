## LAM Music Store
Descripción del Proyecto
LAM Music Store es un sitio web de comercio electrónico dedicado a la venta de artículos musicales. Ofrecemos una amplia variedad de instrumentos, equipos de sonido, accesorios y más, para músicos de todos los niveles y estilos. Nuestro objetivo es brindar a los amantes de la música una plataforma confiable y conveniente para adquirir los productos que necesitan.

## Equipo de Desarrollo
Este proyecto fue desarrollado por el equipo de LAM Music Store, compuesto por:

Lorenzo Albornoz
Franco Salas
Bruno Busnelli

## Instalación

Para comenzar a trabajar con este proyecto en tu entorno local, sigue estos pasos:

Clona el repositorio desde GitHub:

git clone https://github.com/LorenzoAlbornoz/Backend-Music-Store.git
Esto descargará el código fuente del proyecto a tu máquina y te llevará al directorio del proyecto.

Instala las dependencias usando npm:

npm install
Este comando instalará todas las dependencias necesarias para ejecutar la aplicación.

## Inicia la aplicación:

npm run dev

Instala Express:
Express es el framework utilizado para gestionar las rutas y las solicitudes HTTP. Para instalarlo, ejecuta el siguiente comando:

npm install express

## Tecnologia Principal
NodeJS - FrameWork Back-End

## Frameworks adicionales y otras implementaciones

- Express - Infraestructura web rápida, minimalista y flexible para Node.js
- nodemon - Actualiza tu servidor de Node cuando realizas cambios en algun archivo
- Bcrypt - Encriptación
- JWT - Generar tokens
- Mongoose - Modelado de objetos MongoDB para Node.js
- morgan - HTTP request logger middleware for node.js
- passport - Autenticaciones en NodeJs
- passport-jwt - Estrategia de Passport para la autenticación basada en tokens JWT (JSON Web Tokens).
- jsonwebtoken - Librería para la implementación de tokens JWT (JSON Web Tokens) en la autenticación de usuarios.
- dotenv - Variables de Entorno
- cors - Control de Acceso HTTP
- multer - Manejo de archivos en NodeJS
- cloudinary - Almacenamiento de imagenes y videos
- Base de Datos
- MongoDB Atlas - Cloud

## Routes

## Users

- GET /api/v1/user
- GET /api/v1/user/:id
- DELETE /api/v1/user/:id
- PUT /api/v1/user/:id
- PUT /api/v1/admin/rol/:id
- POST /api/v1/recoverPassword
- POST /api/v1/user/favorite/:id
- GET /api/v1/favorite/:id

## Registrar un nuevo usuario
- POST /api/v1/user/register

## Para loguearse y obtener el token de autenticacion:
- POST /api/v1/user/login

## Categorias Routes
- GET /api/v1/categories
- POST /api/v1/category

## Products Routes
- GET /api/v1/products
- GET /api/v1/product/:_id
- POST /api/v1/product
- DELETE /api/v1/product/:id
- PUT /api/v1/product/:id
- PUT /api/v1/product/feature/:id

## Controlador de Usuarios (userController)
Los controladores son funciones que manejan las solicitudes HTTP entrantes y gestionan la lógica de negocio de la aplicación. El controlador de usuarios (userController) incluye las siguientes funciones:

getAllUsers
Esta función recupera todos los usuarios registrados en la base de datos.

getUserByID
Esta función recura un producto por su id registrado en la base de datos

register
La función register permite registrar nuevos usuarios en la aplicación. Además, se instala la librería bcrypt para habilitar la encriptación segura de contraseñas en la aplicación, garantizando la seguridad de las credenciales de usuario.

login
La función login permite a los usuarios registrados iniciar sesión en la aplicación. Para la autenticación y autorización de usuarios, se instala e importa la librería jsonwebtoken para la generación y validación de tokens JWT (Json Web Tokens).

recoverPassword
En caso de querer recuperar la contraseña, la función recoverPassword verifica que el nombre de usuario coincida con uno registrado en la base de datos.

deleteUser
La función deleteUser está diseñada para que los administradores puedan eliminar usuarios de la aplicación.

changeToAdmin
La función changeToAdmin permite a los administradores cambiar el rol de un usuario entre "user" y "admin" y viceversa.

addToFavorites
Esta función permite modificar un producto de no favorito a favorito en la base de datos

getFavoriteProducts
Esta función pertime traer todos los productos que sean favoritos 

## Esquema de Usuario (userSchema)
El esquema userSchema define la estructura en la que se guardan los datos de usuario en la base de datos. Incluye los siguientes campos:

- name: Nombre del usuario.
- username: Nombre de usuario único.
- password: Contraseña del usuario (encriptada de manera segura).
- rol: Rol del usuario, que puede ser "user" o "admin".
- favoritos: Lista de productos favoritos

## Controlador de Categorías (categoryController)
El controlador de categorías (categoryController) incluye las siguientes funciones:

createCategory
La función createCategory permite crear nuevas categorías en la aplicación.

getAllCategory
La función getAllCategory recupera todas las categorías creadas en la base de datos.

## Esquema de Categoría (categorySchema)
El esquema categorySchema define la estructura en la que se guardan los datos de categoría en la base de datos. Incluye los siguientes campos:

- name: El nombre de la categoría.
- createdAt: La fecha en que se creó la categoría (tipo de dato Date).
products: Una relación uno a muchos que conecta una categoría con los productos relacionados. Esto se logra a través del ID de la categoría en los productos.

## Controlador de Productos (productController)
El controlador de productos (productController) incluye las siguientes funciones:

createProduct
La función createProduct permite la creación de nuevos productos en la base de datos.

getAllProducts
La función getAllProducts recupera todos los productos disponibles en la base de datos.

getProductById
La función getProductById recupera un producto específico mediante su identificador (ID).

deleteProduct
La función deleteProduct elimina un producto de la base de datos.

toggleProductFeaturedStatus
La funcion toggleProductFeaturedStatus cambia los productos de no destacados a destacados.

updateProduct
La función updateProduct actualiza la información de un producto existente en la base de datos.

Instalar Multer
Para manejar la carga de archivos, como imágenes, en la aplicación, se instala Multer, una biblioteca de middleware que permite recibir archivos enviados a través de formularios.
Para instalar multer:

npm install multer

Instalar Cloudinary
Se utiliza Cloudinary para gestionar y almacenar las imágenes de productos. Al subir una imagen en el formulario, Cloudinary devuelve una URL que se guarda en la base de datos.

Para instalar cloudinary:

npm install cloudinary

## Esquema de Producto (productSchema)
El esquema productSchema define la estructura en la que se guardan los datos de productos en la base de datos. Incluye los siguientes campos:

- title: El título del producto.
- description: Una breve descripción del producto.
- price: El precio del producto.
- category: La categoría a la que pertenece el producto.
- image: La URL o referencia a la imagen del producto (almacenada en Cloudinary).
- stock: La cantidad de unidades disponibles en el stock.
- shortDescription: Una descripción detallada del producto.
- isFeatured:  Un indicador que puede utilizarse para marcar el producto como destacado.
- isFavorite: Un indicador que puede utilizarse para marcar el producto como favorito.
- quantity: La cantidad de unidades del producto.

Instalación de Passport y Estrategia Passport-JWT
Para gestionar la autenticación de usuarios, utilizamos la librería Passport y la estrategia Passport-JWT para autenticación basada en tokens JWT. Esto permite una autenticación segura y eficiente en el servidor.

npm install passport passport-jwt