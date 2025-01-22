
# Challenge ForoHub 🖥️🙂💬  
ForoHub es una API RESTful construida con Spring Boot que gestiona un foro de discusión. Permite a los usuarios autenticarse, crear, modificar, eliminar y visualizar temas del foro, garantizando la integridad de los datos con validaciones y autenticación segura mediante JWT. La API también soporta paginación para la obtención de temas.  

## Funcionalidades 🌟  
- **Autenticación de Usuarios:** Los usuarios pueden autenticarse utilizando JWT (JSON Web Token).  
- **Gestión de Temas:** Los usuarios pueden crear, modificar, eliminar y recuperar temas del foro.  
- **Validación de Datos:** Asegura que no se creen temas con títulos o mensajes duplicados.  
- **Paginación:** Resultados de temas paginados para una mejor navegación y manejo de grandes volúmenes de datos.  
- **Gestión de Errores:** La API gestiona errores y excepciones, devolviendo códigos de estado HTTP apropiados y mensajes de error informativos.  
- **Arquitectura Segura:** La autenticación y autorización de usuarios se gestionan de forma segura con Spring Security y JWT.  

## Tecnologías Utilizadas ⚙️  
- **Java 17**  
- **Spring Boot**  
- **Spring Security:** Para la autenticación y gestión de seguridad.  
- **JPA (Java Persistence API):** Para la interacción con la base de datos.  
- **JWT (JSON Web Tokens):** Para la autenticación basada en tokens.  
- **BCrypt:** Para el cifrado de contraseñas.  
- **Swagger:** Para la documentación interactiva de la API.  

## Documentación de la API 📄  
La documentación interactiva de la API generada con Swagger está disponible en:  
- **Swagger UI:** [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)  
- **Especificación OpenAPI:** [http://localhost:8080/v3/api-docs](http://localhost:8080/v3/api-docs)  

**Nota:** Asegúrate de que la aplicación esté ejecutándose localmente para que los enlaces funcionen.  

## Endpoints 🚪  
### **Autenticación**  
- **POST /login:** Permite a los usuarios autenticarse con su nombre de usuario y contraseña. Devuelve un token JWT.  

  **Cuerpo de la solicitud:**  
  ```json
  { "user": "nombreUsuario", "pass": "contraseña" }
  ```  

  **Respuesta:**  
  ```json
  { "jwtToken": "token_jwt_generado" }
  ```  

### **Gestión de Temas**  
- **POST /topics:** Crea un nuevo tema en el foro.  

  **Cuerpo de la solicitud:**  
  ```json
  { "title": "Título del tema", "message": "Mensaje del tema", "author": "Nombre del autor", "course": "Nombre del curso" }
  ```  

  **Respuesta:**  
  ```json
  { "title": "Título del tema", "message": "Mensaje del tema", "author": "Nombre del autor", "course": "Nombre del curso" }
  ```  

- **GET /topics/{id}:** Recupera los detalles de un tema por su ID.  

  **Respuesta:**  
  ```json
  { "title": "Título del tema", "message": "Mensaje del tema", "date": "Fecha de creación", "status": true, "author": "Nombre del autor", "course": "Nombre del curso" }
  ```  

- **GET /topics:** Recupera una lista paginada de todos los temas.  

  **Respuesta (Paginada):**  
  ```json
  { "content": [ { "title": "Título del tema", "message": "Mensaje del tema", "date": "Fecha de creación", "status": true, "author": "Nombre del autor", "course": "Nombre del curso" } ], "totalPages": 1, "totalElements": 1 }
  ```  

- **PUT /topics/{id}:** Actualiza un tema existente por ID.  

  **Cuerpo de la solicitud:**  
  ```json
  { "title": "Nuevo título", "message": "Nuevo mensaje", "author": "Nuevo autor", "course": "Nuevo curso" }
  ```  

  **Respuesta:**  
  ```json
  { "title": "Nuevo título", "message": "Nuevo mensaje", "author": "Nuevo autor", "course": "Nuevo curso" }
  ```  

- **DELETE /topics/{id}:** Elimina un tema por ID.  

  **Respuesta:**  
  ```json
  {}
  ```  

## Instalación y Configuración 🚀  
### **Requisitos Previos**  
- Java 17 o superior  
- Maven o Gradle  
- Base de Datos: Configura una base de datos compatible con JPA (como MySQL o H2) y ajusta la configuración en el archivo `application.properties`.  

### **Pasos para Instalar**  
1. Clona el repositorio:  
   ```bash
   git clone https://github.com/Davidalp383/Challenge--ForoHub.git
   ```  

2. Navega al directorio del proyecto:  
   ```bash
   cd Challenge--ForoHub
   ```  

3. Instala las dependencias:  
   - **Con Maven:**  
     ```bash
     mvn install
     ```  
   - **Con Gradle:**  
     ```bash
     gradle build
     ```  

4. Ejecuta la aplicación:  
   - **Con Maven:**  
     ```bash
     mvn spring-boot:run
     ```  
   - **Con Gradle:**  
     ```bash
     gradle bootRun
     ```  

## Cómo Contribuir 🤝  
¡Las contribuciones son bienvenidas! Para contribuir, sigue estos pasos:  
1. Haz un fork del repositorio.  
2. Crea una nueva rama para tu funcionalidad:  
   ```bash
   git checkout -b feature-nueva-funcionalidad
   ```  
3. Realiza tus cambios y haz un commit:  
   ```bash
   git commit -am 'Agrega nueva funcionalidad'
   ```  
4. Envía tus cambios a tu rama:  
   ```bash
   git push origin feature-nueva-funcionalidad
   ```  
5. Crea un pull request.  

## Licencia 📄  
Distribuido bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles.  

¡Explora, comparte y colabora con Challenge ForoHub! 😊  
```
