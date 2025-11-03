# Nexora Service - API REST

API REST para gestión de voluntariados y ONGs usando json-server.

## 🚀 Inicio Rápido

### Instalación

```bash
npm install
```

### Ejecutar servidor

```bash
npm start
# o
npm run dev
```

El servidor se ejecutará en `http://localhost:3000`

## 📚 Endpoints Disponibles

### Usuarios
- `GET /usuarios` - Listar todos los usuarios
- `GET /usuarios/:id` - Obtener un usuario específico
- `POST /usuarios` - Crear un nuevo usuario
- `PUT /usuarios/:id` - Actualizar un usuario
- `DELETE /usuarios/:id` - Eliminar un usuario

### ONGs
- `GET /ongs` - Listar todas las ONGs
- `GET /ongs/:id` - Obtener una ONG específica
- `POST /ongs` - Crear una nueva ONG
- `PUT /ongs/:id` - Actualizar una ONG
- `DELETE /ongs/:id` - Eliminar una ONG

### Voluntarios
- `GET /voluntarios` - Listar todos los voluntarios
- `GET /voluntarios/:id` - Obtener un voluntario específico
- `POST /voluntarios` - Crear un nuevo voluntario
- `PUT /voluntarios/:id` - Actualizar un voluntario
- `DELETE /voluntarios/:id` - Eliminar un voluntario

### Oportunidades
- `GET /oportunidades` - Listar todas las oportunidades
- `GET /oportunidades/:id` - Obtener una oportunidad específica
- `POST /oportunidades` - Crear una nueva oportunidad
- `PUT /oportunidades/:id` - Actualizar una oportunidad
- `DELETE /oportunidades/:id` - Eliminar una oportunidad

### Postulaciones
- `GET /postulaciones` - Listar todas las postulaciones
- `GET /postulaciones/:id` - Obtener una postulación específica
- `POST /postulaciones` - Crear una nueva postulación
- `PUT /postulaciones/:id` - Actualizar una postulación
- `DELETE /postulaciones/:id` - Eliminar una postulación

## 📝 Ejemplos de Uso

### Crear una ONG (Usuario)
```bash
POST /usuarios
Content-Type: application/json

{
  "nombre": "Fundación Nueva Esperanza",
  "email": "contacto@nuevaesperanza.org",
  "password": "12345",
  "rol": "ong"
}
```

### Crear una oportunidad
```bash
POST /oportunidades
Content-Type: application/json

{
  "titulo": "Voluntariado de reforestación",
  "descripcion": "Plantación de árboles en la zona sur",
  "ubicacion": "Cusco",
  "fechaPublicacion": "2024-01-15T10:00:00.000Z",
  "estadoPublicacion": true,
  "ongId": 1
}
```

### Listar oportunidades
```bash
GET /oportunidades
```

### Postularse a una oportunidad
```bash
POST /postulaciones
Content-Type: application/json

{
  "voluntarioId": 1,
  "oportunidadId": 1,
  "estado": "enviada",
  "fecha": "2024-01-16T10:00:00.000Z"
}
```

## 🔍 Búsquedas y Filtros

json-server soporta búsquedas y filtros automáticos:

- `GET /usuarios?rol=ong` - Filtrar usuarios por rol
- `GET /oportunidades?ubicacion=Cusco` - Filtrar por ubicación
- `GET /postulaciones?estado=enviada` - Filtrar por estado
- `GET /usuarios?email=juan@example.com` - Buscar por email

## 📂 Estructura del Proyecto

```
nexora-service/
├── db.json          # Base de datos JSON
├── package.json
└── README.md
```

## 🔧 Configuración

Para cambiar el puerto, modifica el script en `package.json`:

```json
"start": "json-server --watch db.json --port 3000"
```

