# 7. Casos de Uso y Herramientas que Implementan MCP

## Herramientas Actuales con Soporte MCP

1. **Claude Code (CLI):** Herramienta de línea de comandos agéntica desarrollada por Anthropic que utiliza MCP para integrarse con servidores locales (como Git, sistemas de archivos o bases de datos) directamente desde la terminal.
2. **Cursor / VS Code (con extensiones agénticas):** Entornos de desarrollo integrados (IDEs) que actúan como Hosts de MCP, conectando el modelo de lenguaje directamente con herramientas locales y servidores de contexto.
3. **Google Antigravity:** Entorno de desarrollo agéntico que utiliza MCP para conectar agentes inteligentes con el ecosistema de herramientas del usuario (sistema de archivos, ejecución de pruebas, entornos de compilación).

## Edición de Repositorios Completos sin Cargas Manuales

Antes de MCP, la persona debía copiar y pegar fragments de código o subir archivos manualmente al chat del navegador. 

Con herramientas basadas en MCP:
1. El modelo invoca `list_directory` para entender la estructura del proyecto.
2. Utiliza `search_files` o `read_file` para inspeccionar únicamente los componentes y dependencias relevantes.
3. Modifica directamente el código en el entorno local con `write_file`.

Todo esto ocurre dentro de un bucle de retroalimentación en tiempo real en la propia máquina del usuario, garantizando sincronización inmediata sin interacción manual de copiar/pegar.