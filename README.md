# Práctica: Implementación e Investigación de Model Context Protocol (MCP)

Este repositorio contiene la investigación sobre la evolución de la interacción con Inteligencia Artificial, la arquitectura del protocolo **Model Context Protocol (MCP)** y la documentación paso a paso de la instalación de un servidor MCP de sistema de archivos local.

---

## Estructura del Repositorio

- `docs/`: Documentación teórica y análisis detallado de MCP.
  - `01_evolucion_modelos.md`
  - `02_problema_aislamiento.md`
  - `03_mcp_ante_api.md`
  - `04_arquitectura_mcp.md`
  - `05_servidor_sistema_archivos.md`
  - `06_seguridad.md`
  - `07_casos_uso.md`
- `screenshots/`: Evidencias de la implementación práctica y pruebas de seguridad.

---

## Justificación del Cliente Elegido

Para esta práctica se seleccionó **[Escribe aquí el cliente que usaste: ej. Claude Desktop / VS Code con Roo Code]**.

**Razones de la elección:**
1. Soporte nativo y estable para la especificación del Model Context Protocol mediante transporte `stdio`.
2. Interfaz clara para la gestión de permisos en tiempo de ejecución (confirmación humana antes de ejecutar operaciones de lectura/escritura).
3. Facilidad para la inspección visual del catálogo de herramientas publicadas por el servidor.

---

## Guía de Instalación y Configuración del Servidor FS

### Requisitos Previos
- Node.js (v18 o superior) y `npx` instalados.
- El cliente **[Tu cliente]** instalado.

### Pasos de Configuración

1. **Creación del directorio delimitado:**
   ```bash
   mkdir -p ~/mcp-sandbox