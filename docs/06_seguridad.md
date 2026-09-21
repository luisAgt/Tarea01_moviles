---

### `docs/06-seguridad.md`

```markdown
# 6. Consideraciones de Seguridad en MCP

## Riesgos Concretos

1. **Inyección de Instrucciones (Prompt Injection) Indirecta:** Ocurre cuando un archivo leído por el servidor MCP contiene instrucciones maliciosas ocultas. Cuando el LLM procesa el archivo, estas instrucciones pueden manipular al modelo para que ejecute herramientas perjudiciales (ej. borrar otros archivos o filtrar credenciales).
2. **Path Traversal (Acceso fuera de ruta):** Intentos de acceder a rutas relativas no autorizadas usando secuencias como `../../etc/passwd`.
3. **Escritura y Borrado No Deseados:** Modificación destructiva o sobreescritura accidental de código de producción por errores de razonamiento del modelo.

## Mitigaciones Implementadas

- **Confirmación Humana (Human-in-the-Loop):** El Host intercepta cada llamada a herramientas del servidor MCP y exige una confirmación manual por parte del usuario antes de ejecutar la acción en el sistema local.
- **Validación de Rutas (Path Normalization):** El servidor MCP resuelve rutas absolutas y verifica estrictamente que se encuentren dentro de la lista de directorios autorizados en la configuración.
- **Principio de Mínimo Privilegio:** Iniciar el servidor únicamente con permisos de lectura cuando no se requieran modificaciones, y delimitar la ejecución al directorio de trabajo estricto del proyecto.
- **Inspección de Herramientas:** Capacidad del usuario para revisar el catálogo de herramientas y deshabilitar aquellas que considere de alto riesgo.