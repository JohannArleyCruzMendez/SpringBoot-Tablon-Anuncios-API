# API REST - Tablón de Anuncios con Spring Boot

Una API RESTful construida con Java y Spring Boot que simula un sistema de tablón de anuncios. Permite a los usuarios crear, leer, actualizar y eliminar publicaciones (CRUD).

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white)

---

## 📄 Descripción

Este proyecto es una API backend que expone una serie de endpoints para gestionar "posts" o anuncios. Los datos se persisten en memoria para facilitar la demostración, sin necesidad de una base de datos externa. Es un ejemplo práctico de cómo construir APIs robustas y bien estructuradas con el ecosistema de Spring.



## 📸 Muestra Visual

<img width="1267" height="782" alt="image" src="https://github.com/user-attachments/assets/2e171f3a-e294-4a62-814f-019faaafb5d1" />

---

## Endpoints de la API

La URL base para todos los endpoints es `/posts`.

### **1. Obtener todas las publicaciones**
* **`GET /posts`**
* **Respuesta Exitosa (200 OK):**
```json
{
  "ok": true,
  "data": [
    {
      "id": "uuid-...",
      "title": "Perro perdido en el parque",
      "description": "Labrador retriever macho...",
      "imgURL": "[https://...url-imagen](https://...url-imagen)..."
    }
  ],
  "message": "lista de publicaciones"
}
2. Obtener una publicación por ID
GET /posts/{id}

Respuesta Exitosa (200 OK): Devuelve el objeto de la publicación.

Respuesta de Error (404 Not Found): Si la publicación no existe.

Respuesta de Error (400 Bad Request): Si el id proporcionado no es un UUID válido.

3. Crear una nueva publicación
POST /posts

Cuerpo de la Petición (Request Body):

JSON

{
  "title": "Nuevo Título",
  "description": "Descripción del nuevo post.",
  "imgURL": "[https://...url-imagen](https://...url-imagen)..."
}
Respuesta Exitosa (201 Created): Devuelve el objeto de la publicación recién creada con su nuevo id.

4. Actualizar una publicación existente
PUT /posts/{id}

Cuerpo de la Petición (Request Body): Similar al POST, con los campos que se desean actualizar.

Respuesta Exitosa (200 OK): Devuelve el objeto completo de la publicación actualizada.

Respuesta de Error (404 Not Found): Si la publicación a actualizar no existe.

5. Eliminar una publicación
DELETE /posts/{id}

Respuesta Exitosa (200 OK):

JSON

{
  "ok": true,
  "data": "",
  "message": "publicación eliminada"
}
Respuesta de Error (404 Not Found): Si la publicación a eliminar no existe.

🛠️ Stack Tecnológico
Lenguaje: Java

Framework: Spring Boot

Dependencias Clave:

spring-boot-starter-web

lombok (para reducir código repetitivo en los modelos)

Herramienta de Construcción: Gradle

🚀 Cómo Ejecutar Localmente
Clona el repositorio:

Bash

git clone [https://github.com/tu-usuario/nombre-del-repositorio.git](https://github.com/tu-usuario/nombre-del-repositorio.git)
Navega al directorio del proyecto:

Bash

cd nombre-del-repositorio
Ejecuta la aplicación usando el wrapper de Gradle:

En Windows:

Bash

./gradlew.bat bootRun
En macOS/Linux:

Bash

./gradlew bootRun
La API estará disponible en http://localhost:8080. Puedes usar herramientas como Postman o Insomnia para probar los endpoints.
