# Especificación de requisitos de software

## Enunciado del problema
# Especificación de Requisitos de Software
## Sistema de Gestión para Nutricionista

---

## Enunciado del problema

Los nutricionistas profesionales enfrentan dificultades para gestionar la información de sus pacientes, planes alimentarios y seguimientos de evolución del paciente. Actualmente, muchos usan métodos tradicionales como planillas de cálculo, cuadernos físicos o aplicaciones genéricas no diseñadas específicamente para la práctica nutricional. Esto genera problemas como:

- Pérdida de tiempo al buscar información de pacientes en diferentes archivos o documentos
- Dificultad para visualizar la evolución histórica de mediciones antropométricas
- Riesgo de pérdida de información por falta de respaldos adecuados
- Imposibilidad de generar análisis y estadísticas rápidas sobre el progreso de los pacientes
- Desorganización en la agenda de citas y consultas
- Duplicación innecesaria de trabajo al crear planes alimentarios similares

Se necesita una solución integral que centralice toda la información, facilite el acceso rápido a los datos de los pacientes, automatice cálculos básicos (como el IMC), y permita hacer seguimiento efectivo de la evolución de cada persona atendida.

---

## Clientes potenciales

Los principales beneficiarios de este sistema son:

### Usuario Principal: Nutricionistas profesionales
- **Perfil**: Profesionales de la salud especializados en nutrición y dietética que atienden pacientes en consultorios privados o instituciones de salud
- **Necesidades**: Requieren organizar y acceder rápidamente a información clínica, crear planes alimentarios personalizados, hacer seguimiento de evolución y administrar su agenda de consultas
- **Características**: Edad entre 25-60 años, con nivel intermedio de conocimientos tecnológicos, familiarizados con aplicaciones web básicas

### Usuarios Secundarios (beneficiarios indirectos):
- **Pacientes**: Personas que reciben atención nutricional y que se beneficiarían de un seguimiento más ordenado y profesional
- **Secretarias/Asistentes de consultorio**: Personal administrativo que podría utilizar el módulo de agenda para gestionar turnos
- **Instituciones de salud**: Centros médicos o clínicas que podrían implementar el sistema para sus servicios de nutrición

### Alcance estimado:
- Nutricionistas independientes con consultorios propios
- Pequeños equipos de nutricionistas (2-5 profesionales)
- Centros de salud con servicios de nutrición

---

## Solución propuesta

Se propone desarrollar un **Sistema Web de Gestión para Nutricionista**, una aplicación accesible desde navegadores web que centralice toda la información relacionada con la práctica nutricional en un solo lugar.

El sistema permitirá:

1. **Gestionar la base de datos de pacientes**: Registro completo de datos personales, de contacto, antecedentes médicos y alimentarios, con búsqueda rápida y eficiente.

2. **Registrar y visualizar mediciones antropométricas**: Almacenamiento histórico de peso, altura, perímetros y pliegues cutáneos, con cálculo automático de indicadores como el IMC y visualización gráfica de la evolución temporal.

3. **Crear y asignar planes alimentarios personalizados**: Herramienta para diseñar planes nutricionales estructurados por comidas (desayuno, almuerzo, merienda, cena, colaciones), con la posibilidad de duplicar planes existentes para agilizar el trabajo.

4. **Llevar registro de consultas y seguimientos**: Documentación de cada visita del paciente con notas clínicas, observaciones y planificación de próximas citas.

5. **Administrar agenda de citas**: Calendario integrado para visualizar y organizar las consultas programadas, evitando superposiciones y facilitando la planificación.

6. **Generar informes y visualizaciones**: Reportes de evolución del paciente con gráficos que faciliten la comunicación profesional-paciente.

El sistema será intuitivo, rápido y accesible desde cualquier dispositivo con navegador web, garantizando la seguridad y privacidad de los datos sensibles de salud según las normativas vigentes. La solución se enfoca en simplificar el trabajo diario del nutricionista, permitiéndole dedicar más tiempo a la atención de calidad y menos a tareas administrativas.

---

## Requisitos

### Requisitos Funcionales Esenciales (Debe tener)

#### **RF-01: Gestión de Pacientes**
- El sistema debe permitir **registrar nuevos pacientes** con datos completos: nombre, apellido, DNI, fecha de nacimiento, teléfono, email, dirección
- El sistema debe permitir **editar información** de pacientes existentes
- El sistema debe permitir **buscar pacientes** por nombre, apellido o DNI
- El sistema debe permitir **visualizar lista completa** de todos los pacientes registrados
- El sistema debe permitir **dar de baja lógica** a pacientes (sin eliminar su historial)
- El sistema debe permitir **ver ficha completa** de cada paciente con toda su información

#### **RF-02: Registro de Mediciones Antropométricas**
- El sistema debe permitir **registrar mediciones** en cada consulta: peso (kg), altura (cm), perímetro de cintura, perímetro de cadera
- El sistema debe **calcular automáticamente el IMC** al ingresar peso y altura
- El sistema debe **almacenar la fecha** de cada medición
- El sistema debe **mostrar historial completo** de mediciones de cada paciente ordenadas por fecha
- El sistema debe **calcular y mostrar variaciones** entre mediciones consecutivas (diferencia de peso, etc.)

#### **RF-03: Gestión de Planes Alimentarios**
- El sistema debe permitir **crear planes alimentarios** con título, objetivo y observaciones generales
- El sistema debe permitir **definir múltiples comidas** dentro de un plan (desayuno, colación AM, almuerzo, colación PM, merienda, cena)
- Cada comida debe incluir: descripción detallada de alimentos y horario sugerido
- El sistema debe permitir **asignar un plan a un paciente** específico con fecha de inicio
- El sistema debe mostrar **el plan alimentario activo** de cada paciente
- El sistema debe permitir **finalizar un plan** estableciendo fecha de fin

#### **RF-04: Registro de Consultas**
- El sistema debe permitir **registrar cada consulta** con fecha y hora
- El sistema debe permitir **agregar notas clínicas** de la consulta
- El sistema debe vincular **mediciones antropométricas** a cada consulta
- El sistema debe mostrar **historial de consultas** por paciente ordenadas cronológicamente
- El sistema debe permitir **programar próxima cita** desde el registro de consulta

#### **RF-05: Visualización de Historial del Paciente**
- El sistema debe mostrar en una vista unificada: datos personales, última medición, plan activo, última consulta y próxima cita
- El sistema debe permitir navegar fácilmente entre las diferentes secciones del historial

### Requisitos Funcionales Deseables (Es bueno tener)

#### **RF-06: Gestión de Agenda**
- El sistema debe mostrar un **calendario mensual** con las citas programadas
- El sistema debe permitir **agendar nuevas citas** seleccionando fecha, hora y paciente
- El sistema debe permitir **marcar citas como realizadas o canceladas**
- El sistema debe mostrar **alertas de citas del día actual**
- El sistema debe prevenir **superposición de horarios**

#### **RF-07: Duplicación de Planes Alimentarios**
- El sistema debe permitir **duplicar un plan existente** para crear uno nuevo basado en él
- Al duplicar, debe permitir modificar el contenido antes de guardarlo

#### **RF-08: Gráficos de Evolución**
- El sistema debe generar **gráfico de evolución de peso** en el tiempo
- El sistema debe generar **gráfico de evolución de IMC** en el tiempo
- Los gráficos deben ser interactivos y permitir ver valores específicos

#### **RF-09: Biblioteca de Alimentos**
- El sistema debe mantener una **base de datos de alimentos comunes** con información nutricional básica
- El sistema debe permitir **consultar alimentos** por nombre
- Cada alimento debe contener: nombre, calorías, proteínas, carbohidratos, grasas (por 100g)

#### **RF-10: Autenticación de Usuario**
- El sistema debe requerir **inicio de sesión** con usuario y contraseña
- El sistema debe mantener **sesión activa** mientras el usuario no cierre sesión
- El sistema debe permitir **cerrar sesión** de forma segura

#### **RF-11: Notas y Observaciones**
- El sistema debe permitir agregar **observaciones generales** en la ficha del paciente
- El sistema debe permitir agregar **antecedentes médicos** relevantes (alergias, patologías, medicación)

### Requisitos Funcionales Fuera del Alcance Inicial (No esenciales)

#### **RF-12: Generación de Reportes PDF**
- Generar reportes PDF imprimibles con evolución completa del paciente
- Exportar plan alimentario a formato imprimible

#### **RF-13: Notificaciones Automáticas**
- Envío de recordatorios de citas por email o SMS
- Notificaciones push en dispositivos móviles

#### **RF-14: Portal del Paciente**
- Acceso del paciente para consultar su plan alimentario
- Registro de adherencia al plan por parte del paciente
- Comunicación bidireccional nutricionista-paciente

#### **RF-15: Estadísticas Avanzadas**
- Dashboard con estadísticas generales del consultorio
- Análisis de tendencias y patrones
- Indicadores de desempeño profesional

#### **RF-16: Integración con Dispositivos**
- Sincronización con balanzas digitales inteligentes
- Importación de datos desde wearables o apps de salud

---

### Requisitos No Funcionales

#### **RNF-01: Usabilidad**
- La interfaz debe ser **intuitiva y fácil de usar** sin necesidad de capacitación extensa
- Los formularios deben tener **validaciones claras** que indiquen errores antes de enviar
- Los mensajes de error deben ser **comprensibles y específicos**
- La navegación debe ser **consistente** en todas las secciones
- Debe ser **responsive** y adaptarse a tablets (no es prioritario para móviles pequeños)

#### **RNF-02: Rendimiento**
- El sistema debe **cargar la lista de pacientes** en menos de 2 segundos
- Las **búsquedas** deben mostrar resultados en menos de 1 segundo
- El **tiempo de respuesta general** para operaciones comunes no debe superar los 3 segundos
- El sistema debe soportar al menos **100 pacientes registrados** sin degradación de rendimiento

#### **RNF-03: Seguridad**
- Las **contraseñas** deben almacenarse encriptadas (nunca en texto plano)
- Los **datos personales y de salud** deben protegerse según normativas de protección de datos
- Solo **usuarios autenticados** pueden acceder al sistema
- Debe implementarse protección contra inyecciones SQL y ataques XSS básicos

#### **RNF-04: Confiabilidad y Disponibilidad**
- El sistema debe estar **disponible 99% del tiempo** durante horario de consultorio
- Debe implementarse **respaldo automático** de la base de datos
- Los datos no deben perderse ante fallos del sistema

#### **RNF-05: Mantenibilidad**
- El código debe estar **documentado** con comentarios claros
- El código debe seguir **patrones de diseño** reconocidos (MVC)
- La estructura del proyecto debe ser **clara y organizada**
- El sistema debe permitir **futuras extensiones** sin reescritura masiva

#### **RNF-06: Compatibilidad**
- Debe funcionar correctamente en **navegadores modernos**: Chrome, Firefox, Edge, Safari (últimas 2 versiones)
- Debe ser compatible con **sistemas operativos** Windows, macOS y Linux
- La resolución mínima soportada debe ser **1366x768 píxeles**

#### **RNF-07: Privacidad y Cumplimiento Legal**
- Debe cumplir con normativas de **protección de datos personales** (Ley 25.326 en Argentina o equivalente)
- Los datos de salud deben tratarse como **información sensible** con máxima protección
- Debe implementarse política de **retención y eliminación de datos**

---

## Arquitectura de software

### Tipo de Aplicación
**Aplicación Web** - El sistema será una aplicación web accesible desde navegadores, siguiendo el modelo cliente-servidor. No se desarrollará inicialmente como aplicación de escritorio ni móvil nativa, aunque la interfaz será responsive para adaptarse a tablets.

### Arquitectura General
**Cliente-Servidor con Arquitectura en Capas (MVC)**

```
┌─────────────────────────────────────────┐
│         CLIENTE (Navegador)             │
│    HTML5 + CSS3 + JavaScript            │
│         Thymeleaf (Vistas)              │
└─────────────────┬───────────────────────┘
                  │ HTTP/HTTPS
                  │ Requests/Responses
┌─────────────────▼───────────────────────┐
│           SERVIDOR (Backend)            │
│                                         │
│  ┌─────────────────────────────────┐   │
│  │   CAPA DE PRESENTACIÓN          │   │
│  │   Controllers (Spring MVC)      │   │
│  └─────────────┬───────────────────┘   │
│                │                        │
│  ┌─────────────▼───────────────────┐   │
│  │   CAPA DE LÓGICA DE NEGOCIO     │   │
│  │   Services (Spring)             │   │
│  └─────────────┬───────────────────┘   │
│                │                        │
│  ┌─────────────▼───────────────────┐   │
│  │   CAPA DE ACCESO A DATOS        │   │
│  │   Repositories (Spring Data)    │   │
│  │   JPA / Hibernate               │   │
│  └─────────────┬───────────────────┘   │
│                │                        │
└────────────────┼────────────────────────┘
                 │
┌────────────────▼────────────────────────┐
│        BASE DE DATOS                    │
│           MySQL                         │
└─────────────────────────────────────────┘
```

### Tecnologías a Utilizar

#### **Frontend (Cliente)**
- **HTML5**: Estructura de las páginas web
- **CSS3**: Estilos y diseño visual (posiblemente Bootstrap para agilizar)
- **JavaScript**: Interactividad del lado del cliente (validaciones, efectos)
- **Thymeleaf**: Motor de plantillas del lado del servidor para generar HTML dinámico

#### **Backend (Servidor)**
- **Lenguaje**: Java 11 (LTS - Long Term Support)
- **Framework**: Spring Boot 2.x
  - Spring MVC (para controladores web)
  - Spring Data JPA (para acceso a datos)
  - Spring Security (para autenticación - si se implementa)
- **Patrón de arquitectura**: MVC (Modelo-Vista-Controlador)
- **Build Tool**: Maven o Gradle para gestión de dependencias

#### **Base de Datos**
- **Sistema Gestor**: MySQL 8.x
- **ORM**: Hibernate (incluido en Spring Data JPA)
- **Modelado**: Diagrama Entidad-Relación con entidades principales:
  - Paciente
  - MedicionAntropometrica
  - PlanAlimentario
  - ComidaPlan
  - Consulta
  - Cita
  - Usuario (Nutricionista)

#### **Testing**
- **Framework de pruebas**: JUnit 5 (Jupiter)
- **Testing de integración**: Spring Boot Test
- **Cobertura de código**: JaCoCo (opcional)

#### **Control de Versiones**
- **Sistema**: Git
- **Repositorio remoto**: GitHub
- **Metodología**: GitFlow simplificado con ramas main/master y develop

#### **Servidor de Aplicaciones**
- **Embebido**: Tomcat (incluido en Spring Boot)
- **Puerto**: 8080 (configurable)

#### **Entorno de Desarrollo**
- **IDE recomendado**: IntelliJ IDEA, Eclipse o Spring Tool Suite (STS)
- **JDK**: OpenJDK 11 o superior

### Despliegue (Futuro)
En fases posteriores se podría considerar:
- **Contenedorización**: Docker
- **Hosting**: Heroku, AWS, Azure o servidor VPS
- **CI/CD**: GitHub Actions para integración continua

### Estructura de Directorios del Proyecto

```
sistema-gestion-nutricionista/
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/nutricion/sistema/
│   │   │       ├── controllers/      # Controladores MVC
│   │   │       ├── models/           # Entidades JPA
│   │   │       ├── repositories/     # Interfaces de repositorios
│   │   │       ├── services/         # Lógica de negocio
│   │   │       └── dto/              # Data Transfer Objects
│   │   │
│   │   └── resources/
│   │       ├── static/               # CSS, JS, imágenes
│   │       ├── templates/            # Vistas Thymeleaf
│   │       └── application.properties # Configuración
│   │
│   └── test/
│       └── java/                     # Tests unitarios
│
├── docs/                             # Documentación del proyecto
├── pom.xml                           # Configuración Maven
└── README.md                         # Información del proyecto
```

### Justificación de Tecnologías Elegidas

- **Spring Boot**: Framework maduro, ampliamente usado en la industria, con gran cantidad de documentación y comunidad activa. Simplifica enormemente la configuración inicial.

- **MySQL**: Base de datos relacional robusta, gratuita, con excelente soporte y ideal para el modelo de datos estructurado que requiere el sistema.

- **Thymeleaf**: Motor de plantillas bien integrado con Spring, permite crear vistas dinámicas de forma natural y es fácil de aprender.

- **Java**: Lenguaje orientado a objetos, maduro, con tipado fuerte que reduce errores, y ampliamente usado en aplicaciones empresariales.

- **Arquitectura MVC**: Separa responsabilidades claramente, facilitando el mantenimiento, testing y escalabilidad futura del sistema.

---

**Documento elaborado por**: Equipo de Desarrollo  
**Fecha**: Noviembre 2025  
**Versión**: 1.0  
**Estado**: Aprobado para desarrollo
Escriban algunas oraciones que describan el problema que están tratando de resolver, es decir, justifiquen por qué se necesita este software.

## Clientes potenciales
 
¿Quiénes están afectados por este problema y se beneficiarían de la solución propuesta? *(es decir, los usuarios potenciales del software que están por construir)*.

## Solución propuesta 
A
Escriban algunas oraciones que describan cómo la solución de software resolverá el problema descrito anteriormente.

## Requisitos

Enumeren los requisitos *(funcionales)* que debe tener el software para resolver el problema mencionado anteriormente. Es útil tratar de agrupar los requisitos en los que son esenciales *(debe estar)* y los que no son esenciales *(sería bueno que estén)*.
 
## Arquitectura de software


¿Será esta una aplicación web / de escritorio / móvil *(todas o algún otro tipo)*? ¿Se ajustaría a la arquitectura de software Cliente-Servidor? ¿Qué lenguajes de programación, frameworks, bases de datos,... se utilizarán para desarrollar e implementar el software?
