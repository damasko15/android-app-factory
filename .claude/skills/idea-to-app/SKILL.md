---
name: idea-to-app
description: Orquesta el flujo completo desde una idea cruda hasta un PR listo para revisar, respetando las puertas de aprobación del dueño. Usar cuando el dueño dé una idea de app nueva o pida "arranca el proceso".
---
# De idea a app

Ejecuta las etapas EN ORDEN y detente en cada puerta. No avances sin aprobación explícita del dueño.

1. **Product**: delega al agente `product` la especificación en `docs/ideas/`. Resume al dueño el MVP y las preguntas abiertas.
2. **Architect**: delega al agente `architect` el diseño en `docs/design/` (usa el skill `design-doc`).
3. **PUERTA 1**: pide al dueño que responda "APROBADO" (o sus cambios). Sin eso, detente aquí.
4. **Developer**: delega al agente `developer` la primera tarea del plan, en rama `feature/*`, y abre el PR.
5. **QA**: delega al agente `qa` la revisión del PR. Si el veredicto es BLOQUEA, devuelve los hallazgos al developer y repite.
6. **Release**: con QA en PUEDE PASAR, delega al agente `release-manager` el PR de versión.
7. **PUERTAS 2 y 3**: informa al dueño que debe hacer merge y ejecutar el workflow "Release". Tú no lo haces.

Al terminar cada etapa, da un resumen de máximo 5 líneas y qué se espera del dueño.
