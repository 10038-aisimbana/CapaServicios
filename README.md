
# API de Gestión de Cursos y Usuarios

Este documento describe las operaciones disponibles en los microservicios de gestión de cursos y usuarios.

## 1. Matrícula de Usuarios en un Curso

**Método:** `POST`

**URL:**
```
http://localhost:8002/api/cursos/1
http://localhost:8002/api/cursos/{id_curso}
```

**Cuerpo de la solicitud (JSON):**
```json
{
    "id": 1,
    "nombre": "Martin",
    "apellido": "Chavez",
    "email": "Martin@gmial.com",
    "telefono": "0998000888",
    "fechaNacimiento": "2001-09-24",
    "creadoEn": "2025-01-15T23:40:11.392+00:00"
}
```

### Descripción:
Este endpoint permite matricular un usuario en un curso específico. El ID del curso debe ser proporcionado en la URL.

---

## 2. Añadir Nuevos Usuarios al Sistema desde el Microservicio de Cursos

**Método:** `POST`

**URL:**
```
http://localhost:8004/api/usuarios
```

**Cuerpo de la solicitud (JSON):**
```json
{
    "nombre": "Alex",
    "apellido": "Simbana",
    "email": "hola@prueba.com",
    "telefono": "0995033874",
    "fechaNacimiento": "2000-09-01",
    "creadoEn": "2025-01-23"
}
```

### Descripción:
Este endpoint permite agregar nuevos usuarios al sistema desde el microservicio de cursos.

---

## 3. Desmatricular Usuarios de un Curso

**Método:** `DELETE`

**URL:**
```
http://localhost:8002/api/cursos/1/usuarios/1
http://localhost:8002/api/cursos/{id_curso}/usuarios/{id_usuario}
```

### Descripción:
Este endpoint permite desmatricular a un usuario de un curso específico. Los ID del curso y del usuario deben ser proporcionados en la URL.

---

## 4. Listar Usuarios por Curso

**Método:** `GET`

**URL:**
```
http://localhost:8002/api/cursos/1/usuarios
http://localhost:8002/api/cursos/{id_curso}/usuarios
```

### Descripción:
Este endpoint permite listar todos los usuarios matriculados en un curso específico. El ID del curso debe ser proporcionado en la URL.

---

## Notas

- Asegúrate de que los IDs de curso y usuario sean válidos antes de realizar las peticiones.
- Los datos deben enviarse en formato JSON para todos los endpoints.
- Si un usuario no se encuentra en el sistema, el microservicio responderá con un error.
