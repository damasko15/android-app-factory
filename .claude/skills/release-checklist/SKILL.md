---
name: release-checklist
description: Lista de verificación antes de proponer una versión de producción. Usar al preparar un release.
---
# Checklist de release

- [ ] Reporte QA reciente con veredicto PUEDE PASAR
- [ ] Pruebas, lint y typecheck en verde en CI
- [ ] Versión semántica elegida y justificada
- [ ] `versionCode` de Android mayor al anterior
- [ ] `CHANGELOG.md` actualizado
- [ ] Notas de release en lenguaje de usuario
- [ ] Sin secretos ni archivos de depuración en el diff
- [ ] Plan de rollback escrito (skill `rollback`)
- [ ] Migraciones de datos probadas hacia adelante y hacia atrás, si aplica
- [ ] Política de privacidad vigente si cambió el uso de datos o permisos
