# Fábrica de apps Android

Plantilla con un equipo de agentes de Claude Code: `product`, `architect`, `developer`, `qa`, `release-manager`.
Tú das ideas y apruebas; ellos diseñan, programan, prueban y preparan versiones.

## Puesta en marcha (una vez, ~15 min, todo desde el celular o navegador)
1. **GitHub**: crea un repo desde esta plantilla (o sube estos archivos). Un repo por app.
2. **Instala la app Claude en GitHub**: https://github.com/apps/claude (acceso solo a tus repos).
3. **Credencial de Claude para Actions** (elige una) en Settings -> Secrets and variables -> Actions:
   - `ANTHROPIC_API_KEY` (API de pago por uso), o
   - `CLAUDE_CODE_OAUTH_TOKEN` (suscripción Pro/Max; se genera con `claude setup-token` en una terminal donde tengas Claude Code). Si usas este, cambia la línea correspondiente en `.github/workflows/claude.yml`.
4. **Protege `main`**: Settings -> Branches -> regla para `main` con "Require a pull request before merging".
5. **Environment de producción**: Settings -> Environments -> `production` -> Required reviewers = tú.
   (En repos privados con cuenta gratuita estas protecciones pueden no estar disponibles; revisa tu plan de GitHub.)
6. Inicializa la app en `app/` (Expo + TypeScript). Pídeselo al agente `developer` tras aprobar el diseño.

## Cómo se usa (desde la app de GitHub o el navegador)
1. Crea un **Issue** con tu idea y menciona: `@claude usa el skill idea-to-app con esta idea: ...`
2. Claude responde con la especificación y el diseño. Si te gusta, comenta: `APROBADO`. Si no, di qué cambiar.
3. Comenta `@claude agente developer: implementa la tarea 1` -> abre un PR.
4. Comenta `@claude agente qa: revisa este PR` -> reporte en `docs/qa/`.
5. Comenta `@claude agente release-manager: prepara el release` -> PR de versión.
6. Tú haces **merge** a `main` (Puerta 2).
7. Actions -> **Release** -> Run workflow -> escribe la versión (ej. `v1.0.0`). Aprueba el environment `production` (Puerta 3). Se publica un GitHub Release con el APK.
8. Descarga el APK desde Releases en tu Xiaomi 13T e instálalo.

También puedes hacerlo con Claude Code (terminal o sesión remota) usando los mismos agentes: `claude --agent product`, o pidiendo "usa el agente qa para revisar esta rama".

## Rollback
Todos los APK quedan en Releases. Ver `.claude/skills/rollback/SKILL.md`.

## Límites conocidos
- El APK del workflow Release usa la firma de depuración de Expo: sirve para instalar en tu celular y pruebas, **no** para Google Play. Para Play hará falta un keystore real (guardado en Secrets) o EAS Build, y generar un AAB.
- Los agentes tienen reglas en `CLAUDE.md` y bloqueos en `.claude/settings.json`, pero la protección real es la de GitHub (rama protegida + environment con aprobación).
- Revisa los costos: cada ejecución de `@claude` consume tu API o suscripción.
