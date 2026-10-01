---
name: design-doc
description: Plantilla y criterios para escribir el documento de diseño de una app en docs/design/. Usar al diseñar una app o una función nueva.
---
# Documento de diseño

Crea `docs/design/<nombre>.md` con estas secciones:

1. **Resumen** (3 líneas) y enlace a la especificación en `docs/ideas/`
2. **Alcance del MVP** y lo que queda fuera
3. **Arquitectura**: diagrama en texto o Mermaid, componentes y responsabilidades
4. **Stack** y justificación (alternativas descartadas)
5. **Modelo de datos** y dónde se guarda (local, backend)
6. **Pantallas y flujos** principales
7. **Seguridad y privacidad**: datos personales, permisos de Android, política de privacidad
8. **Monetización** elegida y cómo se integra
9. **Plan de pruebas**: qué se prueba y cómo
10. **Plan de tareas**: lista ordenada, cada una cabe en un PR
11. **Riesgos** y spike inicial
12. **Estado**: `PENDIENTE DE APROBACIÓN` (el dueño lo cambia a `APROBADO`)
