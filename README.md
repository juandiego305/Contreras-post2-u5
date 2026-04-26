# Biblioteca API - Post-Contenido 2 (Unidad 5)

[cite_start]Este proyecto representa la fase avanzada del laboratorio de **Patrones de Diseño **, donde se profesionaliza una API REST mediante el desacoplamiento de capas, el manejo global de excepciones y la documentación automatizada[cite: 444].

## 🏗️ Arquitectura y Patrones Aplicados

Para cumplir con los objetivos de la actividad, se implementaron los siguientes componentes arquitectónicos:

1.  **Patrón DTO (Data Transfer Object)**:
    * [cite_start]Se definieron `LibroRequestDTO` y `LibroResponseDTO` para separar el modelo de dominio interno (Entity) del contrato público de la API[cite: 476].
    * [cite_start]Esto permite validar datos de entrada sin afectar la base de datos y controlar qué información se expone al cliente[cite: 476, 480].

2.  **Capa de Mapeo (Mapper)**:
    * [cite_start]Se implementó `LibroMapper` como un componente `@Component` encargado de la conversión bidireccional entre Entidades JPA y DTOs[cite: 505, 510].

3.  **Manejo Global de Errores (@ControllerAdvice)**:
    * [cite_start]Se configuró `GlobalExceptionHandler` para interceptar excepciones de forma centralizada [cite: 525-526].
    * [cite_start]**404 Not Found**: Captura `NoSuchElementException` cuando no existe un ID [cite: 539-540].
    * [cite_start]**400 Bad Request**: Captura `IllegalArgumentException` (reglas de negocio como ISBN duplicado) y `MethodArgumentNotValidException` (errores de validación de campos)[cite: 545, 552].

4.  **Documentación Interactiva (Swagger/OpenAPI)**:
    * [cite_start]Integración de `SpringDoc OpenAPI` para generar la interfaz de Swagger UI, permitiendo probar los endpoints directamente desde el navegador[cite: 459, 474].

## 🚀 Guía de Ejecución

### Requisitos
* [cite_start]**Java**: 17 o superior[cite: 177].
* [cite_start]**Maven**: 3.8+[cite: 178].

### Instalación y Arranque
1.  Clonar el repositorio:
    ```bash
    git clone [https://github.com/juandiego305/Contreras-post2-u5.git](https://github.com/juandiego305/Contreras-post2-u5.git)
    ```
2.  Compilar el proyecto:
    ```bash
    mvn clean compile
    ```
3.  Ejecutar la aplicación:
    ```bash
    mvn spring-boot:run
    ```
4.  Acceder a Swagger UI:
    👉 [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html).

## 🛰️ API Endpoints (v2)

| Método | Endpoint | Descripción | Código Éxito |
| :--- | :--- | :--- | :--- |
| **GET** | `/api/v2/libros` | Listar todos los libros (vía DTO) | 200 OK |
| **GET** | `/api/v2/libros/{id}` | Obtener detalle de un libro por ID | 200 OK |
| **POST** | `/api/v2/libros` | Registrar un nuevo libro con validación | 201 Created |
| **DELETE** | `/api/v2/libros/{id}` | Eliminar un libro permanentemente | 204 No Content |


### 1. Documentación Swagger UI
[cite_start]*<img width="1576" height="980" alt="image" src="https://github.com/user-attachments/assets/d62ba103-ac96-42c2-b2e0-f6467360c480" />
*

### 2. Manejo de Errores (400 Bad Request)
[cite_start]*(Inserta aquí la captura de Postman mostrando el error al enviar un título vacío o ISBN duplicado)* 

### 3. Manejo de Errores (404 Not Found)
[cite_start]*(Inserta aquí la captura de Postman al buscar un ID que no existe)*

## 🧑‍💻 Autor
* **Nombre**: Juan Diego Contreras Garcia
* **Institución**: Universidad Francisco de Paula Santander (UFPS)
* **Programa**: Ingeniería de Sistemas
* **Año**: 2026

---
© 2026 UFPS - Facultad de Ingeniería
