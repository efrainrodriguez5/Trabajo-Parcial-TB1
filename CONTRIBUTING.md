# Cómo contribuir

1. Crear la rama desde `develop`: `git checkout -b feature/HU03-registro-ticket develop`.
2. Hacer commits pequeños con Conventional Commits y el código de la historia:
   - `feat(HU03): agrega listas de área, categoría y prioridad`
   - `fix(HU01): oculta credenciales del mensaje de error`
   - `test(HU07): prueba de UI del cambio de estado`
3. Subir la rama y abrir un pull request hacia `develop`.
4. Otro integrante revisa el pull request antes de integrarlo.
5. En cada Sprint Review, `develop` se integra a `main` con una etiqueta (`v0.1`, `v0.2`…).

## Definición de terminado

- Cumple todos los escenarios de aceptación de la historia.
- Respeta el prototipo v2 de Stitch (colores, textos y navegación).
- Tiene al menos una prueba de UI o unitaria.
- Compila sin errores y sin advertencias críticas de Lint.
