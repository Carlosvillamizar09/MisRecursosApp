# 🎬📚 Mis Recursos App - MongoDB

**Mis Recursos App** es una base de datos creada en MongoDB que simula una aplicación donde los usuarios pueden llevar el control de su progreso al ver series, películas, leer libros, y consumir otros tipos de contenido multimedia. Esta entrega se enfoca exclusivamente en el diseño y estructura de la base de datos, sin implementar una interfaz o backend funcional.

---

## 📌 Objetivo del Proyecto

Diseñar e implementar una base de datos NoSQL en MongoDB que soporte funcionalidades de CRUD (Crear, Leer, Actualizar, Eliminar), filtros y búsquedas sobre los recursos personales de entretenimiento de los usuarios.

---

## 🧱 Estructura de la Base de Datos

La base de datos contiene las siguientes colecciones:

### 1. `usuarios`
Contiene la información de los usuarios registrados.

| Campo         | Tipo     | Descripción           |
|---------------|----------|------------------------|
| id_usuario    | Number   | ID único del usuario   |
| nombre        | String   | Nombre del usuario     |

---

### 2. `plataformas`
Representa las plataformas de streaming, lectura, etc.

| Campo         | Tipo     | Descripción                  |
|---------------|----------|-------------------------------|
| id_plataforma | Number   | ID único de la plataforma     |
| nombre        | String   | Nombre de la plataforma       |

---

### 3. `generos`
Contiene los géneros de los recursos.

| Campo      | Tipo     | Descripción               |
|------------|----------|----------------------------|
| id_genero  | Number   | ID único del género        |
| nombre     | String   | Nombre del género          |

---

### 4. `formatos`
Describe el tipo de recurso.

| Campo       | Tipo     | Descripción               |
|-------------|----------|----------------------------|
| id_formato  | Number   | ID único del formato       |
| nombre      | String   | Ej: Serie, Película, Libro |

---

### 5. `recursos`
Colección principal que almacena los recursos vistos o pendientes por cada usuario.

| Campo              | Tipo     | Descripción                                                              |
|--------------------|----------|---------------------------------------------------------------------------|
| id_recurso         | Number   | ID único del recurso                                                      |
| nombre             | String   | Título del recurso                                                        |
| id_genero          | Number   | Referencia a la colección `generos`                                       |
| id_plataforma      | Number   | Referencia a la colección `plataformas`                                   |
| estado             | String   | Estado del recurso: Terminado, En progreso, Pendiente                     |
| id_formato         | Number   | Referencia a la colección `formatos`                                      |
| fecha_terminacion  | Date     | Fecha en que se terminó el recurso (nullable)                             |
| valoracion_final   | Number   | Valoración personal del recurso (1 a 10 o null)                           |
| id_usuario         | Number   | Referencia al usuario que añadió el recurso                               |
| reseña_personal    | String   | Comentarios u opinión personal sobre el recurso (nullable)               |

---

## ⚙️ Comandos para MongoDB

Puedes ejecutar los siguientes comandos en MongoDB para importar cada colección desde sus respectivos archivos `.json`:

```bash
# Cambiar a la base de datos (crea si no existe)
use mis_recursos_app

# Importar colecciones
mongoimport --db mis_recursos_app --collection usuarios --file usuarios.json --jsonArray
mongoimport --db mis_recursos_app --collection plataformas --file plataformas.json --jsonArray
mongoimport --db mis_recursos_app --collection generos --file generos.json --jsonArray
mongoimport --db mis_recursos_app --collection formatos --file formatos.json --jsonArray
mongoimport --db mis_recursos_app --collection recursos --file recursos.json --jsonArray
```

🔎 Asegúrate de que los archivos `.json` estén en el mismo directorio donde ejecutes los comandos.

---

## 📂 Archivos Incluidos

| Archivo           | Colección destino |
|------------------|--------------------|
| `usuarios.json`  | usuarios           |
| `plataformas.json` | plataformas       |
| `generos.json`   | generos            |
| `formatos.json`  | formatos           |
| `recursos.json`  | recursos           |

---

## 👀 Funcionalidades Representadas

Aunque esta entrega no incluye desarrollo de frontend/backend, la estructura de la base de datos permite implementar:

- ✅ CRUD completo sobre los recursos
- ✅ Filtros por estado, formato y plataforma
- ✅ Búsquedas por nombre
- ✅ Valoraciones, reseñas y progreso de cada usuario

---

## 👨‍💻 Autor

**Carlos Mario Villamizar Medina**  


---
