# 🚀 Guía Definitiva de Mejores Prácticas para Claude Code

¡Bienvenido! Esta es una recopilación adaptada al español de las mejores estrategias y conceptos para dominar **Claude Code**, la herramienta de CLI de Anthropic que está revolucionando el desarrollo de software.

Esta guía está diseñada para ser compartida. Si te resulta útil, ¡no dudes en recomendarla!

---

## 🧠 Conceptos Fundamentales

Para usar Claude Code como un profesional, primero debes entender sus piezas clave:

| Característica | Descripción |
| :--- | :--- |
| **Subagentes** | Actores autónomos en contextos aislados. Tienen sus propias herramientas, permisos y memoria. |
| **Comandos** | Plantillas de prompts invocadas por el usuario para orquestar flujos de trabajo. |
| **Skills (Habilidades)** | Conocimiento inyectado que Claude puede auto-descubrir y usar según sea necesario. |
| **Hooks (Ganchos)** | Scripts o agentes que se ejecutan automáticamente ante eventos específicos (fuera del bucle principal). |
| **MCP Servers** | Conexiones (Model Context Protocol) a herramientas externas, bases de datos y APIs. |
| **Memoria (CLAUDE.md)** | Contexto persistente mediante archivos de reglas que guían el comportamiento del modelo. |

---

## 🔥 Funciones Imprescindibles (Hot)

Estas son las herramientas que te darán una ventaja competitiva:

*   **Revisión de Código:** Análisis multi-agente de Pull Requests para detectar errores y vulnerabilidades.
*   **Tareas Programadas:** Ejecuta prompts de forma recurrente o programa recordatorios.
*   **Dictado por Voz (`/voice`):** Entrada de voz con soporte para más de 20 idiomas.
*   **Equipos de Agentes:** Varios agentes trabajando en paralelo en la misma base de código.
*   **Control Remoto:** Continúa tus sesiones locales desde cualquier dispositivo (móvil, tablet o navegador).

---

## 💡 Trucos y Consejos de Expertos

### 1. Prompting Estratégico 🚫👶
*   **Desafía a Claude:** No aceptes la primera solución. Dile: "Cuestiona estos cambios y no hagas el PR hasta que pase tu prueba".
*   **Borra y Empieza de Nuevo:** Si una solución es mediocre, dile: "Con lo que sabes ahora, descarta esto e implementa la solución más elegante".
*   **Usa Subagentes:** Delega tareas pesadas a subagentes para mantener tu contexto principal limpio y enfocado.

### 2. Planificación y Specs
*   **Modo Plan Primero:** Siempre inicia con el modo de planificación antes de ejecutar código.
*   **Entrevista de Requisitos:** Pide a Claude que te "entreviste" sobre una especificación antes de empezar a construir.
*   **Prototipo > PRD:** Es tan barato construir que es mejor hacer 20 versiones que escribir una especificación de 50 páginas.

### 3. El archivo CLAUDE.md
*   **Mantenlo Corto:** Intenta que tenga menos de 200 líneas (idealmente 60-100).
*   **Reglas Específicas:** Usa etiquetas `<important if="...">` para que Claude no ignore reglas en archivos largos.
*   **Monorepos:** Usa múltiples archivos `CLAUDE.md` (ancestros y descendientes) para organizar proyectos grandes.

---

## 🛠 Flujo de Trabajo Ganador

Todos los flujos de éxito siguen este patrón:
**Investigar 🔍 → Planear 📋 → Ejecutar 🛠 → Revisar ✅ → Enviar 🚀**

---

## 📢 ¡Comparte y Aprende!

¿Quieres llevar tu desarrollo al siguiente nivel? 

1. **Dale una estrella ⭐** a este repositorio.
2. **Comenta "CLAUDE"** en mi publicación y te enviaré contenido exclusivo y actualizaciones sobre estas herramientas.

---
*Adaptado y traducido con ❤️ para la comunidad hispana.*
