# SOCIS Y AMIGOS - Backend

API REST construida con Spring Boot 3 para el sistema de gestión de prácticas pre-profesionales (PPP), matrículas y procesos académicos.

## 🛠️ Tecnologías

- **Java 17 / 21**
- **Spring Boot 3.3.5**
  - Spring Data JPA / Hibernate
  - Spring Security & JWT
  - Spring Web
- **Oracle Database**
- **Apache POI** (Manejo e importación de archivos Excel)
- **Lombok**
- **Maven Wrapper** (`mvnw`)

---

## ⚙️ Configuración y Variables de Entorno

El proyecto está preparado para ejecutarse sin exponer credenciales sensibles en el repositorio.

Puedes configurar las siguientes variables de entorno en tu sistema o mediante un archivo `.env`:

| Variable | Descripción | Valor por Defecto |
| :--- | :--- | :--- |
| `DB_URL` | URL JDBC de Oracle | `jdbc:oracle:thin:@//localhost:1521/XE` |
| `DB_USERNAME` | Usuario de base de datos Oracle | `system` |
| `DB_PASSWORD` | Contraseña del usuario Oracle | `password` |
| `JWT_SECRET` | Clave secreta para firma de tokens JWT (Base64/Hex) | *(Clave por defecto de desarrollo)* |
| `JWT_EXPIRATION_MILLISECONDS` | Tiempo de expiración del token (ms) | `3600000` (1 hora) |

### Configuración local alternativa:
Puedes crear un archivo `application-local.properties` dentro de `src/main/resources/` con tus credenciales locales. Este archivo está configurado en `.gitignore` para que nunca se suba al repositorio.

---

## 🚀 Ejecución del Proyecto

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/TheMauCX/socis-y-amigos-back.git
   cd socis-y-amigos-back
   ```

2. Configurar las variables de entorno o crear `src/main/resources/application-local.properties`.

3. Compilar y ejecutar con Maven Wrapper:
   ```bash
   # En Windows
   .\mvnw.cmd spring-boot:run

   # En Linux / Mac
   ./mvnw spring-boot:run
   ```

4. El servidor iniciará en el puerto configurado (por defecto `http://localhost:8080`).

---

## 🔒 Seguridad y Autenticación

- Autenticación stateless mediante **JSON Web Tokens (JWT)**.
- Endpoints de autenticación en `/api/auth/**`.
- Soporte para CORS habilitado para frontend local (`http://localhost:4200`).
