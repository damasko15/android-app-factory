---
name: rollback
description: Procedimiento para revertir producción a una versión anterior. Usar al documentar el plan de rollback de un release o cuando una versión falle.
---
# Rollback

Cada release publicado queda como un GitHub Release con su APK adjunto; nunca se borran.

**Opción A — APK directo (pruebas / sideload)**
1. Ve a Releases, descarga el APK del tag anterior.
2. Instálalo. Si Android lo rechaza por versión menor, desinstala primero (se pierden datos locales) o publica la opción B.

**Opción B — revertir en código (recomendada)**
1. `git revert <merge-commit>` en una rama `fix/revert-vX.Y.Z` y abre un PR.
2. Tras merge, ejecuta el workflow "Release" con una versión PATCH nueva.

**Google Play**
- Play no permite bajar el `versionCode`: sube de nuevo el build anterior con un `versionCode` mayor (opción B hace esto de forma natural).

Antes de revertir, avisa al dueño qué datos de usuarios podrían verse afectados.
