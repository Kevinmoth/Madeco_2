 
# Documento de Planificación - Iteración 0
## Sistema de Gestión para Nutricionistas

---

## Información General

| Aspecto | Detalle |
|---------|---------|
| **Iteración** | 1 (Setup) |
| **Duración** | 1 semana |
| **Objetivo** | Configurar entorno de desarrollo y estructura base del proyecto |

---

## Equipo

- **Product Owner**: [Andrea Natalia Cabra]
- **Scrum Master**: [Daniel Skromeda]
- **Desarrolladores**: [Kevin Kronbauer], [Ayelen Carla De León]

**Parejas XP**:
- Pareja A: [Andrea Natalia Cabra] + [Kevin Kronbauer]
- Pareja B: [Ayelen Carla De León] + [Daniel Skromeda]

---

## Tareas de Configuración

### 1. Instalación de Herramientas (Todos - 2-3 horas)
- Instalar JDK 11
- Instalar IDE (IntelliJ IDEA / Eclipse)
- Instalar MySQL 8.1
- Instalar Git y configurar usuarios

### 2. Crear Repositorio GitHub (Pareja A - 1 hora) 
- Crear repo: `sistema-gestion-nutricionista` [LINK](https://github.com/Kevinmoth/sistema-gestion-nutricionista)
- Invitar colaboradores
- Crear estructura de carpetas: `docs/iteracion_X/`
- Subir archivo `erp.md`

### 3. Configurar Proyecto Spring Boot (Pareja A - 2 horas)
- Generar proyecto en https://start.spring.io/
  - Maven, Java 11, Spring Boot 2.7.x
  - Dependencias: Spring Web, Spring Data JPA, MySQL Driver, Thymeleaf, DevTools
- Subir al repositorio

### 4. Configurar Base de Datos (Pareja B - 1 hora)

### 5. Crear Modelos Básicos (Pareja B - 2 horas)

### 6. Crear Repositorios (Pareja A - 30 min)

### 7. Página de Prueba (Todos - 30 min)

---

## ✅ Criterios de Completitud

- ✅ Todos pueden ejecutar `mvn spring-boot:run`
- ✅ La aplicación abre en `http://localhost:8080`
- ✅ Las tablas se crean en MySQL automáticamente
- ✅ Repositorio accesible para todos los integrantes

---

**Total estimado**: 10-12 horas de trabajo por cada persona
