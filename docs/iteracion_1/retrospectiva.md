
# Documento de Planificación - Iteración 1
## Sistema de Gestión para Nutricionistas

---

##  Información General

| Aspecto | Detalle |
|---------|---------|
| **Iteración** | 1 |
| **Duración** | 2-3 semanas |
| **Objetivo** | Implementar funcionalidad básica de gestión de pacientes |
| **Puntos comprometidos** | 17 puntos |

---

##  Equipo y Parejas XP

- Product Owner: [Andrea Natalia Cabra]
- Scrum Master: [Daniel Skromeda]
- Desarrolladores: [Kevin Kronbauer], [Ayelen Carla De León]


---

## Historias de Usuario Seleccionadas

| HU | Descripción | Criterios de Aceptación | Tareas Técnicas | Pareja | Puntos |
|----|-------------|------------------------|-----------------|---------|---------|
| **HU-01** | **Registrar Nuevo Paciente**<br><br>Como nutricionista, quiero registrar nuevos pacientes con sus datos personales para llevar un registro ordenado. | 1. Formulario con campos: nombre, apellido, DNI, fecha nacimiento, teléfono, email<br>2. Todos los campos obligatorios excepto email<br>3. DNI debe ser único<br>4. Mostrar mensaje de éxito al guardar<br>5. Redirigir a lista de pacientes | - Crear formulario HTML (Thymeleaf)<br>- Crear PacienteController con método POST<br>- Crear PacienteService<br>- Validar campos en backend<br>- Verificar DNI único<br>- Test unitario del service | **Pareja A** | 5 |
| **HU-02** | **Ver Lista de Pacientes**<br><br>Como nutricionista, quiero ver todos mis pacientes para acceder a su información. | 1. Mostrar tabla con: nombre, apellido, DNI, teléfono<br>2. Ordenar por apellido<br>3. Mostrar botones "Ver" y "Editar"<br>4. Si no hay pacientes, mostrar mensaje | - Crear método GET en controller<br>- Crear vista lista.html<br>- Usar Bootstrap para tabla<br>- Test unitario | **Pareja B** | 3 |
| **HU-03** | **Buscar Paciente**<br><br>Como nutricionista, quiero buscar por nombre/apellido/DNI para encontrarlos rápido. | 1. Campo de búsqueda en lista<br>2. Buscar al presionar Enter o botón<br>3. Buscar por nombre, apellido o DNI<br>4. Mostrar resultados en la misma tabla<br>5. Si no hay resultados, mostrar mensaje | - Agregar formulario de búsqueda<br>- Método buscar en controller<br>- Implementar lógica en service<br>- Test de búsqueda | **Pareja A** | 3 |
| **HU-04** | **Ver Ficha Completa**<br><br>Como nutricionista, quiero ver toda la info de un paciente en una pantalla. | 1. Mostrar datos personales<br>2. Mostrar última medición (si existe)<br>3. Mostrar plan activo (si existe)<br>4. Botón "Editar" y "Volver" | - Crear vista detalle.html<br>- Método verDetalle en controller<br>- Consultar última medición<br>- Consultar plan activo | **Pareja B** | 3 |
| **HU-05** | **Editar Paciente**<br><br>Como nutricionista, quiero editar datos del paciente cuando cambien. | 1. Formulario precargado con datos actuales<br>2. Permitir modificar todos los campos<br>3. DNI no editable<br>4. Mensaje de éxito al actualizar<br>5. Volver a ficha del paciente | - Crear formulario editar.html<br>- Método GET y PUT en controller<br>- Lógica de actualización en service<br>- Test de actualización | **Pareja A** | 3 |

---

## 🔧 Configuración Técnica Adicional

### Bootstrap (para ls estilos)
Agregar en `templates/layout.html` (o en cada página):
```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet">
```

### Estructura de URLs
- `GET /pacientes` → Ver lista
- `GET /pacientes/nuevo` → Formulario registro
- `POST /pacientes` → Guardar nuevo
- `GET /pacientes/{id}` → Ver detalle
- `GET /pacientes/{id}/editar` → Formulario edición
- `PUT /pacientes/{id}` → Actualizar

---

## 📅 Planificación Semanal

### Semana 1
- **Pareja A**: HU-01 (Registrar Paciente)
- **Pareja B**: HU-02 (Ver Lista)
- **Daily meetings**: 15 min cada día

### Semana 2
- **Pareja A**: HU-03 (Buscar)
- **Pareja B**: HU-04 (Ver Ficha)
- **Code review** cruzado a mitad de semana

### Semana 3
- **Pareja A**: HU-05 (Editar)
- **Todos**: Integración y testing final
- **Sprint Review**: Demostración al PO
- **Retrospectiva**

---

## ✅ Definition of Done (criterios a cumplir)

Una HU está **TERMINADA** cuando:
1. ✅ Código implementado y funciona
2. ✅ Al menos 1 test unitario escrito y pasando
3. ✅ Code review hecho por otra pareja
4. ✅ Validaciones de formulario implementadas
5. ✅ Integrado en rama main
6. ✅ Probado manualmente por otro integrante

---

##  Notas

- **Commits**: Mensajes descriptivos (ej: "Agregar formulario de registro de paciente")
- **Branches**: Crear rama por cada HU (ej: `feature/hu-01-registrar-paciente`)
- **Pull Requests**: Revisar siempre el código antes de mergear

---
