# 5. El Servidor MCP de Sistema de Archivos (FileSystem MCP Server)

## Naturaleza del Servidor FS

El servidor de sistema de archivos (`@modelcontextprotocol/server-filesystem`) **no forma parte del protocolo MCP en sí**. Es una implementación de referencia mantenida por la comunidad/Anthropic que demuestra cómo exponer capacidades I/O locales mediante las primitivas de MCP.

## Herramientas Expuestas por el Servidor

El servidor de referencia expone las siguientes herramientas estándar:

- `list_directory`: Lista los archivos y subcarpetas dentro de una ruta.
- `read_file`: Lee el contenido completo de un archivo permitido.
- `write_file`: Crea o sobrescribe un archivo con nuevo contenido.
- `create_directory`: Crea carpetas en el sistema de archivos.
- `move_file`: Mueve o renombra archivos y directorios.
- `search_files`: Busca archivos que coincidan con patrones específicos.
- `get_file_info`: Retorna metadatos de un archivo (tamaño, fechas de creación/modificación).

## Delimitación del Alcance (Sandboxing)

El servidor MCP de sistema de archivos requiere explícitamente una lista de rutas permitidas durante su arranque:

```bash
npx -y @modelcontextprotocol/server-filesystem /ruta/al/directorio/permitido