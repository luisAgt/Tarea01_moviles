# 4. Arquitectura de MCP (Model Context Protocol)

## Modelo Host / Cliente / Servidor

MCP sigue una arquitectura modular compuesta por tres roles principales:

1. **Host:** La aplicación de cara al usuario que orquesta el entorno (ej. VS Code, Cursor, Claude Desktop). Mantiene la interfaz de usuario, gestiona el LLM y controla los permisos de seguridad.
2. **Cliente MCP:** El módulo interno dentro del Host que establece las conexiones uno-a-uno con los servidores MCP, gestiona las negociaciones de protocolo y enruta las llamadas de herramientas.
3. **Servidor MCP:** Un programa independiente que expone capacidades específicas (acceso al sistema de archivos, bases de datos, APIs externas) mediante la interfaz MCP.