# Documento de Planificación - Iteración 4
## Sistema de Gestión para Nutricionistas

---

## Información General

| Aspecto | Detalle |
|---------|---------|
| **Iteración** | 4 |
| **Duración** | 3 semanas |
| **Objetivo** | Implementar gestión de mediciones antropométricas y visualización de evolución |
| **Puntos comprometidos** | 17 puntos |

---

## Equipo y Parejas XP

- Product Owner: [Andrea Natalia Cabra]
- Scrum Master: [Daniel Skromeda]
- Desarrolladores: [Kevin Kronbauer], [Ayelen Carla De León]

**Rotación de parejas** (vuelta a la configuración inicial):
- Pareja A: [Andrea Natalia Cabra] + [Kevin Kronbauer]
- Pareja B: [Ayelen Carla De León] + [Daniel Skromeda]

---

## Historias de Usuario Seleccionadas

| HU | Descripción | Criterios de Aceptación | Tareas Técnicas | Pareja | Puntos |
|----|-------------|------------------------|-----------------|---------|---------|
| **HU-06** | **Registrar Mediciones Antropométricas**<br><br>Como nutricionista, quiero registrar peso, altura, perímetro de cintura y cadera de mis pacientes para hacer seguimiento de su evolución física. | 1. Formulario con campos: fecha, peso (kg), altura (cm), cintura (cm), cadera (cm)<br>2. Seleccionar paciente desde su ficha<br>3. Fecha por defecto: hoy<br>4. Calcular IMC automáticamente (HU-07)<br>5. Todos los campos obligatorios<br>6. Validar valores positivos<br>7. Mensaje de éxito al guardar<br>8. Volver a ficha del paciente | - Crear entidad Medicion<br>- Crear MedicionRepository<br>- Crear formulario medicion.html<br>- Crear MedicionController<br>- Implementar cálculo de IMC<br>- Validaciones backend (valores > 0)<br>- Test unitario del cálculo de IMC<br>- Test de validaciones | **Pareja A** | 5 |
| **HU-07** | **Calcular IMC Automáticamente**<br><br>Como nutricionista, quiero que el sistema calcule automáticamente el IMC cuando ingreso peso y altura para ahorrar tiempo y evitar errores de cálculo. | 1. Cálculo automático al guardar medición<br>2. Fórmula: IMC = peso(kg) / (altura(m))²<br>3. Mostrar IMC en historial de mediciones<br>4. Redondear a 2 decimales<br>5. No editable manualmente | - Método calcularIMC() en service<br>- Conversión de cm a metros<br>- Redondeo a 2 decimales<br>- Test con casos conocidos<br>- Test de precisión | **Pareja A** (integrada con HU-06) | 2 |
| **HU-08** | **Ver Historial de Mediciones**<br><br>Como nutricionista, quiero ver el historial completo de mediciones de un paciente ordenadas por fecha para analizar su progreso en el tiempo. | 1. Mostrar tabla en ficha del paciente con: fecha, peso, altura, IMC, cintura, cadera<br>2. Ordenar por fecha descendente (más reciente primero)<br>3. Botón "Ver evolución" para cada medición<br>4. Si no hay mediciones, mostrar mensaje y botón "Nueva Medición"<br>5. Resaltar última medición con color diferente | - Agregar sección en ficha-paciente.html<br>- Método en controller para traer mediciones<br>- Consulta ordenada en repository<br>- Vista con tabla Bootstrap<br>- CSS para resaltar última medición<br>- Test de ordenamiento | **Pareja B** | 5 |
| **HU-09** | **Ver Diferencia entre Mediciones**<br><br>Como nutricionista, quiero ver la diferencia de peso y otras medidas entre consultas consecutivas para evaluar rápidamente si el paciente está progresando. | 1. En historial, mostrar columna "Cambios" con diferencia vs medición anterior<br>2. Calcular diferencias: peso, IMC, cintura, cadera<br>3. Mostrar con símbolo: ↓ (bajó), ↑ (subió), = (igual)<br>4. Colores: verde (mejoró), rojo (empeoró), gris (igual)<br>5. Primera medición no muestra cambios | - Lógica de comparación en service<br>- Método calcularDiferencias()<br>- Actualizar vista historial<br>- CSS condicional para colores<br>- Símbolos HTML (↑↓=)<br>- Test de cálculo de diferencias<br>- Test de casos especiales (primera medición, valores iguales) | **Pareja A** | 3 |
| **HU-21** | **Gráfico de Evolución de Peso**<br><br>Como nutricionista, quiero ver un gráfico de evolución del peso del paciente en el tiempo para visualizar su progreso de forma clara y comunicárselo mejor. | 1. Gráfico de línea con peso en eje Y y fecha en eje X<br>2. Mostrar en ficha del paciente, debajo del historial<br>3. Mínimo 2 mediciones para mostrar gráfico<br>4. Si hay menos de 2, mostrar mensaje "Se necesitan al menos 2 mediciones"<br>5. Usar Chart.js<br>6. Responsive en mobile<br>7. Línea de tendencia visible | - Integrar Chart.js (CDN)<br>- Endpoint JSON con datos para gráfico<br>- JavaScript para renderizar gráfico<br>- Configuración responsive<br>- Colores y estilos profesionales<br>- Test del endpoint JSON<br>- Test de validación mínimo 2 mediciones | **Pareja B** | 2 |

**Total**: 17 puntos (5+2+5+3+2)

---

## Planificación Semanal

### Semana 1 (06/01 - 12/01)
- **Lunes 06/01**: 
  - Sprint Planning (9:00 AM - 10:00 AM)
  - Crear documento de arquitectura técnica (Kevin - 2 hrs)
  - Setup inicial de ramas y tareas
- **Martes-Viernes**:
  - **Pareja A**: HU-06 + HU-07 (Registrar Mediciones con cálculo de IMC)
  - **Pareja B**: HU-08 (Ver Historial de Mediciones)
- **Daily meetings**: 9:00 AM TODOS los días (10 min)
- **Viernes**: Code review cruzado de HU-06/07 y HU-08

### Semana 2 (13/01 - 19/01)
- **Lunes-Miércoles**:
  - **Pareja A**: HU-09 (Ver Diferencia entre Mediciones)
  - **Pareja B**: HU-21 (Gráfico de Evolución)
- **Jueves**: 
  - Code review cruzado de HU-09 y HU-21
  - Testing cruzado inicial
- **Viernes**: 
  - Mejoras visuales en UI de planes (Ayelen - 2 hrs)
  - Crear scripts de datos de prueba (Todos - 1 hr)

### Semana 3 (20/01 - 26/01)
- **Lunes-Martes**: 
  - Refactoring de código duplicado (Todos - 3 hrs)
  - Integración final y corrección de bugs
- **Miércoles**: Testing completo end-to-end del sistema
- **Jueves 23/01**: Sprint Review - Demostración al PO (10:00 AM)
- **Viernes 24/01**: 
  - Retrospectiva (10:00 AM)
  - Cierre del proyecto y celebración 

---

##  Definition of Done

Una HU está **TERMINADA** cuando:
1. ✅ Código implementado y funciona correctamente
2. ✅ Al menos 2 tests unitarios escritos y pasando (casos positivo y negativo)
3. ✅ Code review aprobado por otra pareja
4. ✅ Validaciones de formulario implementadas (frontend y backend)
5. ✅ Integrado en rama main sin conflictos
6. ✅ Probado manualmente por integrante de la otra pareja (checklist firmado)
7. ✅ Documentación de código (JavaDocs en métodos públicos)
8. ✅ Sin warnings en consola del navegador
9. ✅ Funciona correctamente en mobile (responsive)

---

##  Objetivos Específicos de Mejora

Basados en retrospectiva 3:

1. **Documento de arquitectura**: Crear doc con modelo de datos y decisiones técnicas
2. **Buffer para HU grandes**: HU-06 y HU-08 tienen 5 pts, considerar +20% tiempo
3. **Scripts de datos de prueba**: Facilitar testing manual
4. **Mejoras visuales**: Mejorar UI de planes alimentarios
5. **Refactoring dedicado**: Eliminar código duplicado
6. **Mantener disciplina**: Daily meetings y testing cruzado

---

##  Stack Técnico

- **Backend**: Spring Data JPA
- **Frontend**: Bootstrap 5
- **Base de datos**: MySQL 8.1
- **Testing**: JUnit 5
- **Control de versiones**: Git/GitHub

---


## 📝 Notas Importantes

### Fórmulas y Cálculos
- **IMC**: `peso(kg) / (altura(m))²`
- **Conversión altura**: `altura_metros = altura_cm / 100`
- **Redondeo**: Usar `Math.round(valor * 100.0) / 100.0` para 2 decimales

### Commits y Branches
- **Commits**: Mensajes descriptivos (ej: "Implementar cálculo automático de IMC ")
- **Branches**: 
  - `feature/hu-06-registrar-mediciones`
  - `feature/hu-08-historial-mediciones`
  - `feature/hu-09-diferencia-mediciones`
  - `feature/hu-21-grafico-evolucion`
- **Pull Requests**: Asignar a revisor de la otra pareja, no mergear sin aprobación!

---

##  Riesgos Identificados

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|--------------|---------|------------|
| Cálculos de IMC incorrectos | Baja | Alto | Tests exhaustivos con casos conocidos, revisar fórmula |
| Lógica de comparación entre mediciones | Media | Medio | Tests con casos especiales (primera medición, valores iguales, valores null) |
| Refactoring puede introducir bugs | Baja | Alto | Mantener tests pasando, refactorizar de a poco |
| Integración de todas las funcionalidades puede revelar bugs | Media | Alto | Testing end-to-end exhaustivo en semana 3 |

---

##  Velocity de Referencia

- **Iteración 2**: 17 puntos completados
- **Iteración 3**: 17 puntos completados
- **Velocity consolidada**: 17 puntos por iteración
- **Compromiso Iteración 4**: 17 puntos

---

##  Tareas Técnicas Adicionales

| Tarea | Responsable | Estimación | Cuándo |
|-------|-------------|------------|--------|
| Documento de arquitectura técnica | Kevin | 2 hrs | Lunes 06/01 |
| Scripts de datos de prueba | Todos | 1 hr | Viernes 17/01 |
| Mejoras visuales UI planes | Ayelen | 2 hrs | Viernes 17/01 |
| Refactoring código duplicado | Todos | 3 hrs | Lunes-Martes 20-21/01 |
| Testing end-to-end completo | Todos | 4 hrs | Miércoles 22/01 |

---

##  Documentación a Entregar

Al final de la iteración:
1. ✅ Código fuente en GitHub (rama main)
2. ✅ Documento de arquitectura técnica
3. ✅ Scripts SQL de datos de prueba
4. ✅ Documento de retrospectiva 4
5. ✅ Presentación del Sprint Review

---

**Fecha de inicio**: 06/01/2026  
**Fecha de finalización**: 26/01/2026  
**Sprint Review**: 23/01/2026 - 10:00 AM  
**Retrospectiva**: 24/01/2026 - 10:00 AM  
**Cierre del Proyecto**: 24/01/2026 - 12:00 PM
---
