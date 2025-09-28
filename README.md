# Proyecto Full-Stack con Angular y Spring Boot 3

Este proyecto integra un **frontend** desarrollado con **Angular** y un **backend** con **Spring Boot 3**, conectados a través de **APIs RESTful**.  
La arquitectura está pensada para construir aplicaciones **SPA (Single Page Application)** seguras, escalables y listas para producción.

---

## 🚀 Tecnologías principales

- **Frontend**: Angular 17+ (compatible con versiones anteriores desde Angular 12 hasta 18)
- **Backend**: Spring Boot 3 (Java + Spring Framework 6)
- **Base de datos**: JPA / Hibernate
- **Seguridad**: Spring Security + JWT
- **Estado global**: Redux / NgRx
- **Comunicación en tiempo real**: WebSockets (SockJS, StompJS)
- **Despliegue**: AWS (EC2, RDS, S3) / Docker

---

## 📌 Frontend (Angular)

Angular es un framework creado por Google para construir aplicaciones **web reactivas, modulares y escalables**.

### Conceptos clave
- **Componentes** → Bloques que encapsulan vista, lógica y estilos.  
- **Directivas** → Alteran el comportamiento de elementos del DOM.  
- **Pipes** → Transforman datos directamente en la vista (ej. fechas, texto, monedas).  
- **Services** → Lógica reutilizable, comunicación con backend.  
- **Routing** → Navegación entre vistas y parámetros en la URL.  
- **Formularios (Template-driven & Reactive)** → Captura y validación de datos.  
- **HTTPClient** → Peticiones asíncronas con verbos HTTP (GET, POST, PUT, DELETE).  
- **Observables (RxJS)** → Flujos de datos reactivos para manejar eventos y respuestas.  
- **Redux / NgRx** → Gestión del estado global de la aplicación.  
- **Interceptors** → Añadir cabeceras (JWT), manejar errores, refrescar tokens.  
- **WebSockets (SockJS, StompJS)** → Comunicación en tiempo real (ej. chat, notificaciones).  

---

## 📌 Backend (Spring Boot 3)

Spring Boot permite construir **APIs RESTful seguras y escalables** con mínima configuración.

### Conceptos clave
- **Spring MVC** → Controladores REST para manejar peticiones HTTP.  
- **Entidades (JPA/Hibernate)** → Mapear clases Java a tablas de base de datos.  
- **Repositorios (Spring Data JPA)** → Operaciones CRUD automáticas.  
- **DTOs** → Transferencia de datos entre capas.  
- **Validaciones** → Integridad de datos con anotaciones (@NotNull, @Email, etc).  
- **Manejo de excepciones** → Control centralizado de errores.  
- **Spring Security + JWT** → Autenticación y autorización seguras.  
- **Paginación y ordenación** → Control de resultados en las consultas.  
- **Subida de archivos** → Manejo de contenido multimedia.  
- **CORS** → Comunicación segura entre frontend y backend.  
- **Swagger / OpenAPI** → Documentación automática de la API.  
- **Testing (JUnit, Mockito)** → Pruebas unitarias e integración.  

---

## 🔗 Integración Frontend - Backend

- El **frontend (Angular)** consume servicios REST expuestos por el **backend (Spring Boot)**.  
- Las peticiones viajan en formato **JSON** y usan **observables** para manejar datos de forma reactiva.  
- La seguridad se gestiona mediante **JWT**:  
  - El usuario se autentica y recibe un token.  
  - El token se envía en cada petición para acceder a recursos protegidos.  

---

## ☁️ Despliegue en Producción

Opciones comunes para llevar el proyecto a producción:  
- **AWS EC2** → Backend desplegado en un servidor virtual.  
- **AWS RDS** → Base de datos relacional gestionada.  
- **AWS S3** → Almacenamiento de archivos estáticos.  
- **Docker & Kubernetes** → Contenedores y orquestación.  

---

## 📖 Resumen

Este proyecto combina:
- **Frontend Angular** → dinámico, modular y reactivo.  
- **Backend Spring Boot 3** → robusto, seguro y conectado a bases de datos.  
- **Comunicación** → APIs RESTful + JWT + WebSockets.  
- **Prácticas avanzadas** → Validación, paginación, subida de archivos, deploy en la nube y pruebas automatizadas.  

---
