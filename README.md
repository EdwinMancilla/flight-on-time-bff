# ✈️ Flight On Time BFF

> 🏆 **Proyecto desarrollado durante el Hackathon ONE - Alura Latam & No Country (Enero 2025)**

[![Java](https://img.shields.io/badge/Java-17-orange)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-green)](https://spring.io/projects/spring-boot)

Backend for Frontend (BFF) que actúa como intermediario entre las interfaces de cliente y los servicios del núcleo. Gestiona las solicitudes de predicción de puntualidad de vuelos, validando datos y orquestando la comunicación con el servicio de predicción.

---

## 📋 Descripción

**Flight On Time BFF** es una API REST desarrollada con Spring Boot que facilita la comunicación entre el frontend y el servicio Core de predicción de vuelos. Implementa validación de datos, transformación de requests y manejo de respuestas de forma eficiente.

---

## 🚀 Mi Contribución al Proyecto

Como **Backend Developer** en este proyecto, mis responsabilidades incluyeron:

- ✅ **Desarrollo de API REST** con endpoints claros y estandarizados
- ✅ **Validación de datos** robusta utilizando Bean Validation (Jakarta Validation)
- ✅ **Orquestación de servicios** para comunicación eficiente con el Core
- ✅ **Arquitectura modular** con separación de responsabilidades
- ✅ **Manejo de errores** y respuestas HTTP apropiadas

---

## 💻 Tecnologías Utilizadas

### Backend
- **Java 17**: Lenguaje principal
- **Spring Boot 3.x**: Framework principal
- **Spring Boot Starter Validation**: Validación de datos
- **Lombok**: Reducción de código repetitivo

### Herramientas
- **Maven**: Gestión de dependencias
- **RestTemplate/WebClient**: Cliente HTTP para comunicación con servicios

---

## 🛠️ Instalación y Configuración

### Prerrequisitos

- JDK 17 instalado
- Maven instalado
- Servicio Core corriendo en `http://localhost:8081`

### Configuración

El archivo `application.properties` contiene:

```properties
server.port=8080
spring.application.name=bff-service
core.service.url=http://localhost:8081
```

### Construcción

```bash
mvn clean install
```

### Ejecución

```bash
mvn spring-boot:run
```

La aplicación estará disponible en `http://localhost:8080`.

---

## 🔌 Uso del API

### Predicción de Vuelo

Evalúa la probabilidad de puntualidad de un vuelo.

**Endpoint:** `POST /predict`

**Content-Type:** `application/json`

#### Request Body

```json
{
  "aerolinea": "AA",
  "origen": "JFK",
  "destino": "LAX",
  "fecha_partida": "2023-12-25T08:00:00",
  "distancia_km": 3980.5
}
```

#### Response (200 OK)

```json
{
  "prevision": "A tiempo",
  "probabilidad": 0.85
}
```

#### Response (400 Bad Request)

```json
{
  "timestamp": "2023-12-30T10:15:30.123+00:00",
  "status": 400,
  "error": "Bad Request",
  "path": "/predict"
}
```

---

## 📂 Estructura del Proyecto

```
src/main/java/com/flightontime/bff
├── BffApplication.java          # Clase principal de entrada
├── config/                      # Configuración (Beans, Properties)
├── controller/                  # Controladores REST (Endpoints)
├── dto/                         # Data Transfer Objects
└── service/                     # Lógica de negocio y clientes externos
```

---

## 🔄 Flujo de Trabajo

1. **Cliente** envía request al BFF (`/predict`)
2. **BFF** valida los datos de entrada
3. **BFF** transforma el request si es necesario
4. **BFF** envía request al servicio Core
5. **Core** procesa con el modelo de IA
6. **BFF** recibe respuesta del Core
7. **BFF** transforma y retorna respuesta al cliente

---

## 👥 Equipo de Desarrollo

Este proyecto fue desarrollado colaborativamente durante el Hackathon ONE:

- **Luisa Valencia** - Líder del proyecto
- **Edwin Mancilla** - Backend Developer (Java/Spring Boot)
- **Marco Hernández** - Colaborador
- **Eliana Méndez** - Colaboradora
- Y más colaboradores

---

## 🔗 Repositorio Original

Este es un fork del proyecto original desarrollado durante el hackathon:
- **Repositorio original**: [luvalenciaq/flight-on-time-bff](https://github.com/luvalenciaq/flight-on-time-bff)

---

## 📫 Contacto

**Edwin Javier Mancilla Rios**
- 📧 Email: edwinmancilla1017@gmail.com
- 💼 LinkedIn: [linkedin.com/in/edwin-mancilla-rios-79b051346](https://www.linkedin.com/in/edwin-mancilla-rios-79b051346/)
- 🐙 GitHub: [github.com/EdwinMancilla](https://github.com/EdwinMancilla)

---

## 📄 Licencia

Este proyecto fue desarrollado con fines educativos durante el Hackathon ONE de Alura Latam & No Country.
