# Especificación de Requisitos de Software
## Sistema de Gestión para Nutricionistas

---

## Enunciado del problema

Los nutricionistas profesionales enfrentan problemas para gestionar la información de sus pacientes de manera eficiente. Actualmente utilizan métodos tradicionales como planillas Excel, cuadernos físicos o aplicaciones genéricas que no están diseñadas para la práctica nutricional. Esto genera pérdida de tiempo al buscar información, dificultad para visualizar la evolución histórica de los pacientes, riesgo de pérdida de datos y desorganización general en la gestión del consultorio.

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

## Requisitos

### Requisitos Funcionales Esenciales (Debe tener)

**RF-01: Gestión de Pacientes**
- Registrar nuevos pacientes con datos personales completos (nombre, apellido, DNI, fecha de nacimiento, teléfono, email)
- Editar información de pacientes existentes
- Buscar pacientes por nombre, apellido o DNI
- Visualizar lista completa de pacientes
- Ver ficha completa de cada paciente

**RF-02: Mediciones Antropométricas**
- Registrar mediciones en cada consulta (peso, altura, cintura, cadera)
- Calcular automáticamente el IMC al ingresar peso y altura
- Mostrar historial de mediciones ordenado por fecha
- Calcular y mostrar diferencias entre mediciones consecutivas
- Visualizar gráfico de evolución de peso en el tiempo

**RF-03: Planes Alimentarios**
- Crear planes alimentarios con título y objetivo
- Definir múltiples comidas (desayuno, colaciones, almuerzo, merienda, cena)
- Asignar un plan a un paciente específico
- Mostrar el plan alimentario activo de cada paciente
- Solo puede haber un plan activo por paciente

**RF-04: Consultas**
- Registrar cada consulta con fecha y notas clínicas
- Mostrar historial de consultas por paciente ordenadas cronológicamente

### Requisitos Funcionales Deseables (Es bueno tener)

**RF-05: Gestión de Agenda**
- Calendario mensual con citas programadas
- Agendar nuevas citas seleccionando fecha, hora y paciente
- Marcar citas como realizadas o canceladas

**RF-06: Funcionalidades Adicionales**
- Duplicar planes alimentarios existentes
- Gráfico de evolución de IMC
- Agregar observaciones generales en ficha del paciente
- Registrar antecedentes médicos relevantes

**RF-07: Autenticación**
- Inicio de sesión con usuario y contraseña
- Cerrar sesión de forma segura

### Requisitos No Funcionales

**RNF-01: Usabilidad**
- Interfaz intuitiva y fácil de usar
- Validaciones claras en formularios
- Diseño responsive para tablets

**RNF-02: Rendimiento**
- Cargar lista de pacientes en menos de 2 segundos
- Búsquedas en menos de 1 segundo
- Soportar al menos 100 pacientes sin degradación

**RNF-03: Seguridad**
- Contraseñas encriptadas
- Protección de datos personales y de salud
- Protección contra inyecciones SQL y XSS básicos

**RNF-04: Compatibilidad**
- Navegadores modernos: Chrome, Firefox, Edge, Safari
- Sistemas operativos: Windows, macOS, Linux
- Resolución mínima: 1366x768 píxeles

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
  - Spring MVC (controladores web)
  - Spring Data JPA (acceso a datos)
  - Hibernate (ORM)
- Maven (gestión de dependencias)

**Base de Datos:**
- MySQL 8.1
- Modelo relacional con entidades: Paciente, Medicion, PlanAlimentario, PlanPaciente, Consulta

**Desarrollo:**
- IDE: IntelliJ IDEA / Eclipse / STS
- Control de versiones: Git + GitHub
- Testing: JUnit 5, Mockito
- Servidor embebido: Tomcat (puerto 8080)

### Estructura del Proyecto
```
sistema-gestion-nutricionista/
├── src/main/java/com/nutricion/sistema/
│   ├── controllers/    # Controladores del MVC
│   ├── models/         # Entidades JPA
│   ├── repositories/   # Repositorios de la Spring Data
│   └── services/       # Aca se agrega la lógica de negocio
├── src/main/resources/
│   ├── static/         # CSS, JS y imágenes
│   ├── templates/      # Vistas del Thymeleaf (Motor de plantillas que elegimos)
│   └── application.properties
├── src/test/java/      # Para los tests unitarios
└── pom.xml             # Configuración del Maven de java
```

### Justificación de Tecnologías

- **Spring Boot**: Framework Java perfecto apra el proyecto, muy usado en la industria, con excelente documentación y comunidad
- **MySQL**: Base de datos relacional gratuita, robusta y ideal para el modelo de datos estructurado
- **Thymeleaf**: Motor de plantillas bien integrado con Spring, fácil de aprender
- **Bootstrap**: Framework CSS que nos va a agilizar el desarrollo de interfaces responsive
- **Chart.js**: Librería JavaScript simple para crear gráficos interactivos
- **Arquitectura MVC**: Separa responsabilidades, facilita mantenimiento y testing

---
