# Biblioteca API - Post-Contenido 2 (Unidad 5)

[cite_start]Este proyecto representa la fase avanzada del laboratorio de **Patrones de Diseño **, donde se profesionaliza una API REST mediante el desacoplamiento de capas, el manejo global de excepciones y la documentación automatizada[cite: 444].

## 🏗️ Arquitectura y Patrones Aplicados

Para cumplir con los objetivos de la actividad, se implementaron los siguientes componentes arquitectónicos:

1.  **Patrón DTO (Data Transfer Object)**:
   Se definieron `LibroRequestDTO` y `LibroResponseDTO` para separar el modelo de dominio interno (Entity) del contrato público de la API
   Esto permite validar datos de entrada sin afectar la base de datos y controlar qué información se expone al cliente

2.  **Capa de Mapeo (Mapper)**:
    Se implementó `LibroMapper` como un componente `@Component` encargado de la conversión bidireccional entre Entidades JPA y DTOs

3.  **Manejo Global de Errores (@ControllerAdvice)**:
   Se configuró `GlobalExceptionHandler` para interceptar excepciones de forma centralizada [cite: 525-526].
   **404 Not Found**: Captura `NoSuchElementException` cuando no existe un ID [cite: 539-540].
   **400 Bad Request**: Captura `IllegalArgumentException` (reglas de negocio como ISBN duplicado) y `MethodArgumentNotValidException` (errores de validación de campos)

4.  **Documentación Interactiva (Swagger/OpenAPI)**:
    Integración de `SpringDoc OpenAPI` para generar la interfaz de Swagger UI, permitiendo probar los endpoints directamente desde el navegador

## 🚀 Guía de Ejecución

### Requisitos
**Java**: 17 o superior
**Maven**: 3.8+

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
<img width="1576" height="980" alt="image" src="https://github.com/user-attachments/assets/d62ba103-ac96-42c2-b2e0-f6467360c480" />


## 🧑‍💻 Autor
* **Nombre**: Juan Diego Contreras Garcia
* **Institución**: Universidad Francisco de Paula Santander (UFPS)
* **Programa**: Ingeniería de Sistemas
* **Año**: 2026

---
© 2026 UFPS - Facultad de Ingeniería
