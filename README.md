### Integrantes del equipo:

 **Product Owner**: [ *Andrea Natalia Cabra* ]

 **Scrum Master**: [ *Daniel Skromeda* ]

 **Desarrolladores**: [ *Kevin Kronbauer* ], [ *Ayelen Carla De León* ].


<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/6df78a77-cbf1-4824-b350-55eca75bedfc" />

## Sistema de Gestión para Nutricionistas

---

## Enunciado del problema

Los nutricionistas profesionales enfrentan problemas para gestionar la información de sus pacientes de manera eficiente. Actualmente utilizan métodos tradicionales como planillas Excel, cuadernos físicos o aplicaciones genéricas que no están diseñadas para la práctica nutricional. Esto les genera una pérdida de tiempo al buscar información, dificultad para ver la evolución histórica de los pacientes, riesgo de pérdida de datos y desorganización general en la gestión del consultorio.

---

## Clientes potenciales

**Usuarios principales:**
- Nutricionistas profesionales que atienden en consultorios privados
- Pequeños equipos de nutricionistas (2-5 profesionales)
- Centros de salud con servicios de nutrición

**Características del usuario:**
- Edad entre 25-60 años
- Nivel intermedio de conocimientos tecnológicos
- Familiarizados con aplicaciones web básicas

---

## Solución propuesta

Se va a desarrollar un **Sistema Web de Gestión para Nutricionistas** que centralice toda la información relacionada con la práctica nutricional en una aplicación accesible desde navegadores web. El sistema permitirá gestionar pacientes, registrar mediciones antropométricas con cálculo automático de IMC, crear y asignar planes alimentarios personalizados, llevar registro de consultas, y visualizar la evolución de los pacientes mediante gráficos. La solución simplificará el trabajo diario del nutricionista, permitiéndole dedicar más tiempo a la atención de calidad y menos a tareas administrativas.

---

## Arquitectura de software

### Tipo de Aplicación
**Aplicación Web** - Sistema cliente-servidor accesible desde navegadores web con interfaz responsive para adaptarse a tablets.

### Stack Tecnológico

**Frontend:**
- HTML5, CSS3, JavaScript
- Bootstrap 5 (framework CSS)
- Thymeleaf (motor de plantillas)
- Chart.js (gráficos)

**Backend:**
- Java 11 (OpenJDK)
- Spring Boot 2.7.x
  - MVC (controladores web)
- Maven (gestión de dependencias)

**Base de Datos:**
- MySQL 8.1
- Modelo relacional con entidades: Paciente, Medicion, PlanAlimentario, PlanPaciente, Consulta

**Desarrollo:**
- IDE: IntelliJ IDEA / Eclipse / STS
- Control de versiones: Git + GitHub
- Testing: JUnit 5, Mockito
- Servidor embebido: Tomcat (puerto 8080)

### Justificación de Tecnologías

- **Spring Boot**: Framework Java perfecto apra el proyecto, muy usado en la industria, con excelente documentación y comunidad
- **MySQL**: Base de datos relacional gratuita, robusta y ideal para el modelo de datos estructurado
- **Bootstrap**: Framework CSS que nos va a agilizar el desarrollo de interfaces responsive
- **Arquitectura MVC**: Separa responsabilidades, facilita mantenimiento y testing

---
