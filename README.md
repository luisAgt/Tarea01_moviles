# Investigación e Implementación de Model Context Protocol (MCP)

## PORTADA
- **Nombre Completo:** Agustin Fuentes Luis Angel
- **Número de Boleta:** 2024630134
- **Grupo:** 7CV4
- **Fecha de Entrega:** 21 de septiembre de 2026

---

## RESUMEN
En esta actividad se investigó la evolución del acceso de la inteligencia artificial a entornos locales, pasando de ser modelos aislados en la nube a agentes capaces de interactuar directamente con el entorno de desarrollo mediante **Model Context Protocol (MCP)**. Además, se realizó la instalación práctica de un servidor MCP de sistema de archivos (`filesystem`), verificando su funcionamiento, límites de seguridad y aplicando las mejores prácticas de documentación.

### INDICE `docs/`
- [01. Evolución de los Modelos de Lenguaje](docs/01-evolucion-de-los-modelos.md)
- [02. El Problema del Aislamiento](docs/02-el-problema-del-aislamiento.md)
- [03. MCP Frente a una API Tradicional](docs/03-mcp-frente-a-una-api.md)
- [04. Arquitectura de MCP (Host, Cliente y Servidor)](docs/04-arquitectura-de-mcp.md)
- [05. El Servidor de Sistema de Archivos](docs/05-el-servidor-de-sistema-de-archivos.md)
- [06. Seguridad y Mitigación de Riesgos](docs/06-seguridad.md)
- [07. Casos de Uso y Herramientas Agénticas](docs/07-casos-de-uso.md)

---

## Tabla Comparativa: MCP frente a una API Tradicional

| Criterio | API Tradicional (REST / gRPC) | Model Context Protocol (MCP) |
| :--- | :--- | :--- |
| **¿Quién decide qué se invoca?** | El desarrollador humano mediante código estático. | El modelo de lenguaje / agente IA dinámicamente en tiempo de ejecución. |
| **Descubrimiento de capacidades** | Documentación estática (OpenAPI / Swagger). | Catálogo dinámico de herramientas, recursos y prompts expresados en JSON Schema. |
| **Acoplamiento Cliente-Servicio** | Alto (el código cliente depende directamente de la estructura del endpoint). | Desacoplado (el modelo interactúa mediante abstracciones expuestas por el servidor). |
| **Formato de Mensajes** | HTTP/REST, gRPC, Protobuf, GraphQL. | JSON-RPC 2.0 sobre `stdio` o `Streamable HTTP`. |
| **Manejo de Autenticación y Consentimiento** | Tokens/Keys configurados en el código de la aplicación. | Control del Host con confirmación humana en tiempo de ejecución antes de cada acción. |
| **Reutilización entre Aplicaciones** | Requiere programar un conector o SDK específico para cada cliente. | Un solo servidor MCP funciona para cualquier cliente agéntico compatible (VS Code, Claude Desktop, Cursor, Zed, etc.). |

> **Aclaración Conceptual Clave:** MCP **no sustituye** a las APIs tradicionales. MCP es un protocolo abierto y estandarizado que se sitúa por encima de las APIs o recursos existentes para hacerlos descubribles y consumibles de forma autónoma por un modelo de lenguaje.

---

## Instrucciones de Instalación Paso a Paso

### Entorno de Prueba
- **Sistema Operativo:** macOS Sonoma 14.5 / Ubuntu 22.04 LTS / Windows 11 Home 
- **Node.js:** v20.11.0 (LTS)
- **npx:** v10.2.4
- **Cliente MCP:** Claude Desktop (v0.7.1) / VS Code con extensión Roo Code (v3.2.0)
- **Especificación MCP Consultada:** Especificación Abierta MCP (Revisión `2024-11-05`)

---

### Pasos de Instalación

1. **Clonar el repositorio:**
   ```bash
   
   git clone [https://github.com/luisAgt/Tarea01_moviles.git](https://github.com/luisAgt/Tarea01_moviles.git)

   cd [ubicacion_repositorio]