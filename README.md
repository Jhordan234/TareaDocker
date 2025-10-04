# 📦 Gestión de Contactos - API REST con Node.js, Express y MongoDB

Este proyecto es una **API REST** para la gestión de contactos, construida con **Node.js**, **Express** y **MongoDB**, y desplegada usando **Docker Compose**.  

---

## 🚀 Características

- CRUD de contactos (crear, leer, actualizar, eliminar).
- Conexión a MongoDB mediante Mongoose.
- Middleware personalizado para manejo de errores.
- Configuración lista para usar con Docker y Docker Compose.
- Soporte para CORS y JSON en las peticiones.

---

## 📂 Estructura del proyecto

gestion-contactos/
├── app.js # Punto de entrada principal
├── package.json
├── Dockerfile # Configuración de la app en Node.js
├── docker-compose.yml # Orquestación con MongoDB + App
├── routes/
│ └── contactRoutes.js # Rutas de la API
├── middleware/
│ └── errorHandler.js # Middleware de errores
└── models/
└── contactModel.js # Esquema de Contacto (Mongoose)


---

## 🐳 Configuración con Docker

### 1️⃣ Levantar los contenedores

Ejecuta en la raíz del proyecto:

```bash
docker-compose up --build

Esto levantará dos servicios:

mongo → Base de datos MongoDB en mongodb://mongo:27017/contactsDB

app → API en http://localhost:3000

2️⃣ Detener los contenedores
docker-compose down

3️⃣ Ver logs en tiempo real
docker-compose logs -f

🌐 Endpoints principales

Todos los endpoints están bajo /api/contacts.

Método	Endpoint	Descripción
GET	/api/contacts	Obtener todos los contactos
POST	/api/contacts	Crear un nuevo contacto
GET	/api/contacts/:id	Obtener un contacto por ID
PUT	/api/contacts/:id	Actualizar un contacto
DELETE	/api/contacts/:id	Eliminar un contacto

Ejemplo de body JSON para crear un contacto:

{
  "name": "Juan Pérez",
  "email": "juanperez@mail.com",
  "phone": "987654321"
}

⚙️ Variables de entorno

En el archivo .env (o en docker-compose.yml) se definen:

PORT=3000
MONGODB_URI=mongodb://mongo:27017/contactsDB

🛠️ Desarrollo sin Docker

Si prefieres correr el proyecto en tu máquina local:

Instala dependencias:

npm install


Levanta MongoDB localmente (por defecto en mongodb://localhost:27017/contactsDB).

Ejecuta la app:

npm start

👨‍💻 Autor

Proyecto de práctica con Node.js, Express, MongoDB y Docker.
Ideal para aprender sobre APIs REST, contenedores Docker y bases de datos NoSQL.
