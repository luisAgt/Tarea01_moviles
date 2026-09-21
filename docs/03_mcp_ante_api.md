# 3. Model Context Protocol (MCP) frente a una API Tradicional

## Concepto de API Tradicional
Una **API (Application Programming Interface)** es un contrato estático entre programas. El desarrollador humano lee la documentación, determina los endpoints exactos, arma las peticiones HTTP/JSON de antemano y programa de forma determinista cómo procesar la respuesta. El código cliente define rígida y previamente qué se llama y cuándo.

## Concepto de MCP (Model Context Protocol)
**MCP** es un protocolo abierto cliente-servidor basado en **JSON-RPC 2.0**. Un servidor MCP no exige que el desarrollador programe llamadas fijas. En su lugar, el servidor publica dinámicamente un **catálogo de capacidades (herramientas, recursos, prompts)** descritas con esquemas JSON Schema. 

El cliente (un LLM o un entorno de desarrollo agéntico) descubre dicho catálogo en **tiempo de ejecución** y decide de forma autónoma cuál herramienta invocar, con qué parámetros y en qué momento, en función de las peticiones del usuario.

---

## Tabla Comparativa

| Criterio | API Tradicional (REST / gRPC) | Model Context Protocol (MCP) |
| :--- | :--- | :--- |
| **¿Quién decide qué se invoca?** | El desarrollador humano (código determinista). | El modelo de lenguaje / Agente IA en tiempo de ejecución. |
| **Descubrimiento de capacidades** | Lectura manual de documentación (OpenAPI, Swagger). | Automático y dinámico mediante catálogos descritos en JSON Schema. |
| **Acoplamiento Cliente-Servicio** | Alto (el cliente depende de la estructura exacta del endpoint). | Desacoplado (el modelo interactúa mediante la abstracción del catálogo). |
| **Formato de los Mensajes** | HTTP GET/POST, REST, gRPC, Protobuf, GraphQL. | Mensajes estándar JSON-RPC 2.0 (sobre `stdio` o `Streamable HTTP`). |
| **Autenticación y Consentimiento** | Tokens API, OAuth2, Bearer Headers programados en cliente. | Control de acceso a nivel del Host/Cliente, con confirmación humana por acción. |
| **Reutilización entre aplicaciones** | Requiere escribir un SDK/Cliente específico para cada app. | Un solo servidor MCP funciona para cualquier cliente compatible (VS Code, Claude, Zed, etc.). |

---

## Relación entre MCP y las APIs Tradicionales

> **Aclaración Importante:** MCP **no sustituye** a las APIs tradicionales. 

Un servidor MCP actúa como un **adaptador o capa de abstracción** sobre sistemas, herramientas o APIs preexistentes. Por ejemplo, un servidor MCP de GitHub no reemplaza la API REST/GraphQL de GitHub; simplemente expone sus endpoints en forma de "herramientas descritas en JSON Schema" para que un modelo de inteligencia artificial pueda descubrir e invocar la API de GitHub de manera autónoma.