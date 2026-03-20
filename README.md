La práctica hace al claude perfecto

[![Mejor Práctica](!/tags/best-practice.svg)](best-practice/) [![Implementado](!/tags/implemented.svg)](implementation/) [![Flujo de Orquestación](!/tags/orchestration-workflow.svg)](orchestration-workflow/orchestration-workflow.md) [![Boris](!/tags/boris-cherny.svg)](#-tips-and-tricks) ![Haz clic en estas insignias de abajo para ver las fuentes reales](!/tags/click-badges.svg)<br>

<p align="center">
  <img src="!/claude-jumping.svg" alt="Mascota de Claude Code saltando" width="120" height="100">
</p>


## 🧠 CONCEPTOS

| Característica | Ubicación | Descripción |
|---------|----------|-------------|
| <img src="a.svg" height="14"> [**Subagentes**](https://code.claude.com/docs/en/sub-agents) | `.claude/agents/<nombre>.md` | [![Mejor Práctica](!/tags/best-practice.svg)](best-practice/claude-subagents.md) [![Implementado](!/tags/implemented.svg)](implementation/claude-subagents-implementation.md) Actor autónomo en un contexto fresco y aislado — herramientas personalizadas, permisos, modelo, memoria e identidad persistente |
| <img src="c.svg" height="14"> [**Comandos**](https://code.claude.com/docs/en/slash-commands) | `.claude/commands/<nombre>.md` | [![Mejor Práctica](!/tags/best-practice.svg)](best-practice/claude-commands.md) [![Implementado](!/tags/implemented.svg)](implementation/claude-commands-implementation.md) Conocimiento inyectado en el contexto existente — plantillas de prompts simples invocadas por el usuario para la orquestación de flujos de trabajo |
| <img src="s.svg" height="14"> [**Habilidades (Skills)**](https://code.claude.com/docs/en/skills) | `.claude/skills/<nombre>/SKILL.md` | [![Mejor Práctica](!/tags/best-practice.svg)](best-practice/claude-skills.md) [![Implementado](!/tags/implemented.svg)](implementation/claude-skills-implementation.md) Conocimiento inyectado en el contexto existente — configurable, precargable, autodescubrible, con bifurcación de contexto y divulgación progresiva · [Habilidades Oficiales](https://github.com/anthropics/skills/tree/main/skills) |
| [**Flujos de trabajo**](https://code.claude.com/docs/en/common-workflows) | [`.claude/commands/weather-orchestrator.md`](.claude/commands/weather-orchestrator.md) | [![Flujo de Orquestación](!/tags/orchestration-workflow.svg)](orchestration-workflow/orchestration-workflow.md) |
| [**Hooks (Ganchos)**](https://code.claude.com/docs/en/hooks) | `.claude/hooks/` | [![Mejor Práctica](!/tags/best-practice.svg)](https://github.com/dimoni26/claude-code-hooks) [![Implementado](!/tags/implemented.svg)](https://github.com/dimoni26/claude-code-hooks) Controladores definidos por el usuario (scripts, HTTP, prompts, agentes) que se ejecutan fuera del bucle de agentes en eventos específicos · [Guía](https://code.claude.com/docs/en/hooks-guide) |
| [**Servidores MCP**](https://code.claude.com/docs/en/mcp) | `.claude/settings.json`, `.mcp.json` | [![Mejor Práctica](!/tags/best-practice.svg)](best-practice/claude-mcp.md) [![Implementado](!/tags/implemented.svg)](.mcp.json) Conexiones del Protocolo de Contexto del Modelo a herramientas externas, bases de datos y APIs |
| [**Plugins**](https://code.claude.com/docs/en/plugins) | paquetes distribuibles | Paquetes de habilidades, subagentes, hooks y servidores MCP · [Marketplaces](https://code.claude.com/docs/en/discover-plugins) |
| [**Ajustes**](https://code.claude.com/docs/en/settings) | `.claude/settings.json` | [![Mejor Práctica](!/tags/best-practice.svg)](best-practice/claude-settings.md) [![Implementado](!/tags/implemented.svg)](.claude/settings.json) Sistema de configuración jerárquico · [Permisos](https://code.claude.com/docs/en/permissions) · [Configuración del Modelo](https://code.claude.com/docs/en/model-config) · [Estilos de Salida](https://code.claude.com/docs/en/output-styles) · [Sandboxing](https://code.claude.com/docs/en/sandboxing) · [Atajos de Teclado](https://code.claude.com/docs/en/keybindings) · [Modo Rápido](https://code.claude.com/docs/en/fast-mode) |
| [**Línea de Estado**](https://code.claude.com/docs/en/statusline) | `.claude/settings.json` | [![Mejor Práctica](!/tags/best-practice.svg)](https://github.com/dimoni26/claude-code-status-line) [![Implementado](!/tags/implemented.svg)](.claude/settings.json) Barra de estado personalizable que muestra el uso del contexto, el modelo, el costo y la información de la sesión |
| [**Memoria**](https://code.claude.com/docs/en/memory) | `CLAUDE.md`, `.claude/rules/`, `~/.claude/rules/`, `~/.claude/projects/<proyecto>/memory/` | [![Mejor Práctica](!/tags/best-practice.svg)](best-practice/claude-memory.md) [![Implementado](!/tags/implemented.svg)](CLAUDE.md) Contexto persistente a través de archivos CLAUDE.md e importaciones `@path` · [Memoria Automática](https://code.claude.com/docs/en/memory) · [Reglas](https://code.claude.com/docs/en/memory#organize-rules-with-clauderules) |
| [**Puntos de Control (Checkpointing)**](https://code.claude.com/docs/en/checkpointing) | automático (basado en git) | Seguimiento automático de ediciones de archivos con rebobinado (`Esc Esc` o `/rewind`) y resumen específico |
| [**Flags de Inicio de CLI**](https://code.claude.com/docs/en/cli-reference) | `claude [flags]` | [![Mejor Práctica](!/tags/best-practice.svg)](best-practice/claude-cli-startup-flags.md) Flags de línea de comandos, subcomandos y variables de entorno para lanzar Claude Code · [Modo Interactivo](https://code.claude.com/docs/en/interactive-mode) |
| **Términos de IA** | | [![Mejor Práctica](!/tags/best-practice.svg)](https://github.com/dimoni26/claude-best-practices/blob/main/reports/ai-terms.md) Ingeniería Agéntica · Ingeniería de Contexto · Vibe Coding |
| [**Mejores Prácticas**](https://code.claude.com/docs/en/best-practices) | | Mejores prácticas oficiales · [Ingeniería de Prompts](https://github.com/anthropics/prompt-eng-interactive-tutorial) · [Extender Claude Code](https://code.claude.com/docs/en/features-overview) |

### 🔥 Destacado (Hot)

| Característica | Ubicación | Descripción |
|---------|----------|-------------|
| [**Revisión de Código**](https://code.claude.com/docs/en/code-review) ![beta](!/tags/beta.svg) | Aplicación de GitHub (gestionada) | [![Mejor Práctica](!/tags/best-practice.svg)](https://x.com/claudeai/status/2031088171262554195) Análisis de PR multi-agente que detecta errores, vulnerabilidades de seguridad y regresiones · [Blog](https://claude.com/blog/code-review) |
| [**Tareas Programadas**](https://code.claude.com/docs/en/scheduled-tasks) | `/loop`, herramientas cron | [![Mejor Práctica](!/tags/best-practice.svg)](https://x.com/bcherny/status/2030193932404150413) [![Implementado](!/tags/implemented.svg)](implementation/claude-scheduled-tasks-implementation.md) Ejecuta prompts en un horario recurrente (hasta 3 días), establece recordatorios únicos, sondea despliegues y compilaciones |
| [**Dictado por Voz**](https://code.claude.com/docs/en/voice-dictation) ![beta](!/tags/beta.svg) | `/voice` | [![Mejor Práctica](!/tags/best-practice.svg)](https://x.com/trq212/status/2028628570692890800) Entrada de voz push-to-talk para prompts con soporte para 20 idiomas y tecla de activación reasignable |
| [**Simplificar y Lote**](https://x.com/bcherny/status/2027534984534544489) | `/simplify`, `/batch` | [![Mejor Práctica](!/tags/best-practice.svg)](https://x.com/bcherny/status/2027534984534544489) Habilidades integradas para la calidad del código y operaciones masivas — simplifica refactorizaciones para reutilización y eficiencia, ejecuta comandos en lote a través de archivos |
| [**Equipos de Agentes**](https://code.claude.com/docs/en/agent-teams) ![beta](!/tags/beta.svg) | integrado (var de entorno) | [![Mejor Práctica](!/tags/best-practice.svg)](https://x.com/bcherny/status/2019472394696683904) [![Implementado](!/tags/implemented.svg)](implementation/claude-agent-teams-implementation.md) Múltiples agentes trabajando en paralelo en la misma base de código con coordinación de tareas compartida |
| [**Control Remoto**](https://code.claude.com/docs/en/remote-control) | `/remote-control`, `/rc` | [![Mejor Práctica](!/tags/best-practice.svg)](https://x.com/noahzweben/status/2032533699116355819) Continúa sesiones locales desde cualquier dispositivo — teléfono, tablet o navegador · [Modo Headless](https://code.claude.com/docs/en/headless) |
| [**Git Worktrees**](https://code.claude.com/docs/en/common-workflows) | integrado | [![Mejor Práctica](!/tags/best-practice.svg)](https://x.com/bcherny/status/2025007393290272904) Ramas de git aisladas para desarrollo paralelo — cada agente obtiene su propia copia de trabajo |
| [**Bucle Ralph Wiggum**](https://github.com/anthropics/claude-code/tree/main/plugins/ralph-wiggum) | plugin | [![Mejor Práctica](!/tags/best-practice.svg)](https://github.com/ghuntley/how-to-ralph-wiggum) [![Implementado](!/tags/implemented.svg)](https://github.com/dimoni26/novel-llm-26) Bucle de desarrollo autónomo para tareas de larga duración — itera hasta completar |

<p align="center">
  <img src="!/claude-jumping.svg" alt="divisor de sección" width="60" height="50">
</p>

<a id="orchestration-workflow"></a>

## <a href="orchestration-workflow/orchestration-workflow.md"><img src="!/tags/orchestration-workflow-hd.svg" alt="Flujo de Orquestación"></a>

Consulta [orchestration-workflow](orchestration-workflow/orchestration-workflow.md) para detalles de implementación del patrón <img src="c.svg" height="14"> **Comando** → <img src="a.svg" height="14"> **Agente** → <img src="s.svg" height="14"> **Habilidad**.


<p align="center">
  <img src="orchestration-workflow/orchestration-workflow.svg" alt="Flujo de Arquitectura Comando Habilidad Agente" width="100%">
</p>

<p align="center">
  <img src="orchestration-workflow/orchestration-workflow.gif" alt="Demo de Flujo de Orquestación" width="600">
</p>

![Cómo usar](!/tags/how-to-use.svg)

```bash
claude
/weather-orchestrator
```

<p align="center">
  <img src="!/claude-jumping.svg" alt="divisor de sección" width="60" height="50">
</p>

## ⚙️ FLUJOS DE TRABAJO DE DESARROLLO

Todos los flujos de trabajo principales convergen en el mismo patrón arquitectónico: **Investigar → Planear → Ejecutar → Revisar → Enviar**

| Nombre | ★ | Singularidad | Plan | <img src="a.svg" height="14"> | <img src="c.svg" height="14"> | <img src="s.svg" height="14"> |
|------|---|------------|------|---|---|---|
| [Superpowers](https://github.com/obra/superpowers) | 98k | ![TDD-primero](https://img.shields.io/badge/TDD--primero-ddf4ff) ![Leyes de Hierro](https://img.shields.io/badge/Leyes_de_Hierro-ddf4ff) ![revisión de plan completo](https://img.shields.io/badge/revisión_de_plan_completo-ddf4ff) | <img src="s.svg" height="14"> [writing-plans](https://github.com/obra/superpowers/tree/main/skills/writing-plans) | 5 | 3 | 14 |
| [Everything Claude Code](https://github.com/affaan-m/everything-claude-code) | 87k | ![puntuación de instinto](https://img.shields.io/badge/puntuación_de_instinto-ddf4ff) ![AgentShield](https://img.shields.io/badge/AgentShield-ddf4ff) ![reglas multi-idioma](https://img.shields.io/badge/reglas_multi--idioma-ddf4ff) | <img src="a.svg" height="14"> [planner](https://github.com/affaan-m/everything-claude-code/blob/main/agents/planner.md) | 25 | 57 | 108+ |
| [Spec Kit](https://github.com/github/spec-kit) | 79k | ![basado en especificaciones](https://img.shields.io/badge/basado_en_especificaciones-ddf4ff) ![constitución](https://img.shields.io/badge/constitución-ddf4ff) ![22+ herramientas](https://img.shields.io/badge/22%2B_herramientas-ddf4ff) | <img src="c.svg" height="14"> [speckit.plan](https://github.com/github/spec-kit/blob/main/templates/commands/plan.md) | 0 | 9+ | 0 |
| [Get Shit Done](https://github.com/gsd-build/get-shit-done) | 35k | ![contextos frescos de 200K](https://img.shields.io/badge/contextos_frescos_de_200K-ddf4ff) ![ejecución en ola](https://img.shields.io/badge/ejecución_en_ola-ddf4ff) ![planes XML](https://img.shields.io/badge/planes_XML-ddf4ff) | <img src="a.svg" height="14"> [gsd-planner](https://github.com/gsd-build/get-shit-done/blob/main/agents/gsd-planner.md) | 16 | 46 | 0 |
| [OpenSpec](https://github.com/Fission-AI/OpenSpec) | 32k | ![especificaciones delta](https://img.shields.io/badge/especificaciones_delta-ddf4ff) ![brownfield](https://img.shields.io/badge/brownfield-ddf4ff) ![DAG de artefactos](https://img.shields.io/badge/DAG_de_artefactos-ddf4ff) | <img src="c.svg" height="14"> [opsx:propose](https://github.com/Fission-AI/OpenSpec/blob/main/src/commands/workflow/new-change.ts) | 0 | 11 | 11 |
| [gstack](https://github.com/garrytan/gstack) | 26k | ![personas de rol](https://img.shields.io/badge/personas_de_rol-ddf4ff) ![revisión /codex](https://img.shields.io/badge/revisión_/codex-ddf4ff) ![sprints paralelos](https://img.shields.io/badge/sprints_paralelos-ddf4ff) | <img src="s.svg" height="14"> [plan-eng-review](https://github.com/garrytan/gstack/blob/main/.claude/skills/plan-eng-review/SKILL.md) | 0 | 0 | 21 |
| [HumanLayer](https://github.com/humanlayer/humanlayer) | 10k | [![RPI](https://img.shields.io/badge/RPI-ddf4ff)](development-workflows/rpi/rpi-workflow.md) ![ingeniería de contexto](https://img.shields.io/badge/ingeniería_de_contexto-ddf4ff) ![300k+ LOC](https://img.shields.io/badge/300k%2B_LOC-ddf4ff) | <img src="a.svg" height="14"> [create_plan](https://github.com/humanlayer/humanlayer/blob/main/agents/create_plan.md) | 6 | 27 | 0 |

### Otros
- [Flujo de trabajo Cross-Model (Claude Code + Codex)](development-workflows/cross-model-workflow/cross-model-workflow.md) [![Implementado](!/tags/implemented.svg)](development-workflows/cross-model-workflow/cross-model-workflow.md)
- [RPI](development-workflows/rpi/rpi-workflow.md) [![Implementado](!/tags/implemented.svg)](development-workflows/rpi/rpi-workflow.md)
- [Bucle Ralph Wiggum](https://www.youtube.com/watch?v=eAtvoGlpeRU) [![Implementado](!/tags/implemented.svg)](https://github.com/dimoni26/novel-llm-26)
- [Flujo de trabajo de Andrej Karpathy (Miembro Fundador, OpenAI)](https://x.com/karpathy/status/2015883857489522876)
- [Flujo de trabajo de Peter Steinberger (Creador de OpenClaw)](https://youtu.be/8lF7HmQ_RgY?t=2582)
- Flujo de trabajo de Boris Cherny (Creador de Claude Code) — [13 Consejos](tips/claude-boris-13-tips-03-jan-26.md) · [10 Consejos](tips/claude-boris-10-tips-01-feb-26.md) · [12 Consejos](tips/claude-boris-12-tips-12-feb-26.md) [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny)

<p align="center">
  <img src="!/claude-jumping.svg" alt="divisor de sección" width="60" height="50">
</p>

## 💡 CONSEJOS Y TRUCOS

🚫👶 = no supervisar constantemente

![Comunidad](!/tags/community.svg)

■ **Prompting (4)**
- desafía a Claude — "cuestióname sobre estos cambios y no hagas un PR hasta que pase tu prueba" o "demuéstrame que esto funciona" y haz que Claude compare entre main y tu rama 🚫👶 [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2017742752566632544)
- después de una solución mediocre — "sabiendo todo lo que sabes ahora, descarta esto e implementa la solución elegante" 🚫👶 [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2017742752566632544)
- Claude soluciona la mayoría de los errores por sí mismo — pega el error, di "solucionar", no microgestiones cómo 🚫👶 [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2017742750473720121)
- di "usa subagentes" para dedicar más computación a un problema — delega tareas para mantener tu contexto principal limpio y enfocado 🚫👶 [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2017742755737555434)

■ **Planificación/Especificaciones (6)**
- comienza siempre con el [modo plan](https://code.claude.com/docs/en/common-workflows) [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2007179845336527000)
- comienza con una especificación o prompt mínimo y pide a Claude que te entreviste usando la herramienta [AskUserQuestion](https://code.claude.com/docs/en/cli-reference), luego crea una nueva sesión para ejecutar la especificación [![Thariq](!/tags/thariq.svg)](https://x.com/trq212/status/2005315275026260309)
- haz siempre un plan por fases con puertas de control, donde cada fase tenga múltiples pruebas (unitarias, de automatización, de integración)
- lanza un segundo Claude para revisar tu plan como un ingeniero de staff, o usa [cross-model](development-workflows/cross-model-workflow/cross-model-workflow.md) para la revisión [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2017742745365057733)
- escribe especificaciones detalladas y reduce la ambigüedad antes de entregar el trabajo — cuanto más específico seas, mejor será el resultado [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2017742752566632544)
- prototipo > PRD — construye 20-30 versiones en lugar de escribir especificaciones, el costo de construir es bajo, así que intenta muchas veces [![Boris](!/tags/boris-cherny.svg)](https://youtu.be/julbw1JuAz0?t=3630) [![Video](!/tags/video.svg)](https://youtu.be/julbw1JuAz0?t=3630)

■ **CLAUDE.md (6)**
- [CLAUDE.md](https://code.claude.com/docs/en/memory) debería apuntar a menos de [200 líneas](https://code.claude.com/docs/en/memory#write-effective-instructions) por archivo. [60 líneas en humanlayer](https://www.humanlayer.dev/blog/writing-a-good-claude-md) ([aún no garantizado al 100%](https://www.reddit.com/r/ClaudeCode/comments/1qn9pb9/claudemd_says_must_use_agent_claude_ignores_it_80/)). [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2007179840848597422) [![Dex](!/tags/dex.svg)](https://www.humanlayer.dev/blog/writing-a-good-claude-md)
- envuelve las reglas de CLAUDE.md específicas del dominio en [etiquetas \<important if="..."\>](https://www.hlyr.dev/blog/stop-claude-from-ignoring-your-claude-md) para evitar que Claude las ignore a medida que los archivos se vuelven más largos [![Dex](!/tags/dex.svg)](https://www.hlyr.dev/blog/stop-claude-from-ignoring-your-claude-md)
- usa [múltiples CLAUDE.md](best-practice/claude-memory.md) para monorepos — carga de ancestros + descendientes
- usa [.claude/rules/](https://code.claude.com/docs/en/memory#organize-rules-with-clauderules) para dividir instrucciones grandes
- [memory.md](https://code.claude.com/docs/en/memory), constitution.md no garantiza nada
- mantén las bases de código limpias y termina las migraciones — los frameworks parcialmente migrados confunden a los modelos que podrían elegir el patrón equivocado [![Boris](!/tags/boris-cherny.svg)](https://youtu.be/julbw1JuAz0?t=1112) [![Video](!/tags/video.svg)](https://youtu.be/julbw1JuAz0?t=1112)

■ <img src="s.svg" height="14"> **Habilidades (Skills) (10)**
- ten [subagentes](https://code.claude.com/docs/en/sub-agents) específicos para cada característica (contexto extra) con [habilidades](https://code.claude.com/docs/en/skills) (divulgación progresiva) en lugar de un qa o ingeniero de backend general. [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2007179850139000872)
- usa [context: fork](https://code.claude.com/docs/en/skills) para ejecutar una habilidad en un subagente aislado — el contexto principal solo ve el resultado final, no las llamadas a herramientas intermedias. El campo agent te permite establecer el tipo de subagente [![Lydia](!/tags/lydia.svg)](https://x.com/lydiahallie/status/2033603164398883042)
- usa [habilidades en subcarpetas](reports/claude-skills-for-larger-mono-repos.md) para monorepos
- las habilidades son carpetas, no archivos — usa subdirectorios references/, scripts/, examples/ para la [divulgación progresiva](https://code.claude.com/docs/en/skills) [![Thariq](!/tags/thariq.svg)](https://x.com/trq212/status/2033949937936085378)
- construye una sección de "Gotchas" (trampas) en cada habilidad — contenido de mayor señal, añade los puntos de fallo de Claude con el tiempo [![Thariq](!/tags/thariq.svg)](https://x.com/trq212/status/2033949937936085378)
- el campo de descripción de la habilidad es un disparador, no un resumen — escríbelo para el modelo ("¿cuándo debería activarme?") [![Thariq](!/tags/thariq.svg)](https://x.com/trq212/status/2033949937936085378)
- no digas lo obvio en las habilidades — enfócate en lo que saca a Claude de su comportamiento por defecto 🚫👶 [![Thariq](!/tags/thariq.svg)](https://x.com/trq212/status/2033949937936085378)
- no encarriles a Claude en las habilidades — da objetivos y restricciones, no instrucciones prescriptivas paso a paso 🚫👶 [![Thariq](!/tags/thariq.svg)](https://x.com/trq212/status/2033949937936085378)
- incluye scripts y librerías en las habilidades para que Claude componga en lugar de reconstruir código repetitivo [![Thariq](!/tags/thariq.svg)](https://x.com/trq212/status/2033949937936085378)
- incrusta `` !`comando` `` en SKILL.md para inyectar salida dinámica de la shell en el prompt — Claude lo ejecuta al invocarlo y el modelo solo ve el resultado [![Lydia](!/tags/lydia.svg)](https://x.com/lydiahallie/status/2034337963820327017)

■ **Flujos de Trabajo (9)**
- usa [comandos](https://code.claude.com/docs/en/slash-commands) para tus flujos de trabajo en lugar de [subagentes](https://code.claude.com/docs/en/sub-agents) [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2007179847949500714)
- evita la zona tonta del agente, haz [/compact](https://code.claude.com/docs/en/interactive-mode) manual al 50% máximo. Usa [/clear](https://code.claude.com/docs/en/cli-reference) para resetear el contexto a mitad de la sesión si cambias a una nueva tarea
- el cc básico es mejor que cualquier flujo de trabajo con tareas más pequeñas
- usa [/model](https://code.claude.com/docs/en/model-config) para seleccionar el modelo y el razonamiento, [/context](https://code.claude.com/docs/en/interactive-mode) para ver el uso del contexto, [/usage](https://code.claude.com/docs/en/costs) para revisar los límites del plan, [/extra-usage](https://code.claude.com/docs/en/interactive-mode) para configurar la facturación por exceso, [/config](https://code.claude.com/docs/en/settings) para configurar los ajustes — usa Opus para el modo plan y Sonnet para el código para obtener lo mejor de ambos [![Cat](!/tags/cat-wu.svg)](https://x.com/_catwu/status/1955694117264261609)
- usa siempre [thinking mode](https://code.claude.com/docs/en/model-config) true (para ver el razonamiento) y [Output Style](https://code.claude.com/docs/en/output-styles) Explanatory (para ver la salida detallada con cajas ★ Insight) en [/config](https://code.claude.com/docs/en/settings) para una mejor comprensión de las decisiones de Claude [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2007179838864666847)
- usa la palabra clave ultrathink en los prompts para un [razonamiento de alto esfuerzo](https://docs.anthropic.com/en/docs/build-with-claude/extended-thinking#tips-and-best-practices)
- [/rename](https://code.claude.com/docs/en/cli-reference) sesiones importantes (ej. [TODO - tarea de refactorización]) y [/resume](https://code.claude.com/docs/en/cli-reference) más tarde — etiqueta cada instancia cuando ejecutes múltiples Claudes simultáneamente [![Cat](!/tags/cat-wu.svg)](https://every.to/podcast/how-to-use-claude-code-like-the-people-who-built-it)
- usa [Esc Esc o /rewind](https://code.claude.com/docs/en/checkpointing) para deshacer cuando Claude se desvíe en lugar de intentar arreglarlo en el mismo contexto
- haz commits a menudo — intenta hacer un commit al menos una vez por hora, tan pronto como se complete la tarea, haz commit.

■ **Flujos de Trabajo Avanzados (10)**
- usa mucho los diagramas ASCII para entender tu arquitectura [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2017742759218794768)
- [equipos de agentes con tmux](https://code.claude.com/docs/en/agent-teams) y [git worktrees](https://x.com/bcherny/status/2025007393290272904) para desarrollo paralelo
- usa [/loop](https://code.claude.com/docs/en/scheduled-tasks) para monitoreo recurrente — sondea despliegues, supervisa PRs, revisa compilaciones (funciona hasta 3 días)
- usa el [plugin Ralph Wiggum](https://github.com/dimoni26/novel-llm-26) para tareas autónomas de larga duración [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2007179858435281082)
- [/permissions](https://code.claude.com/docs/en/permissions) con sintaxis de comodín (Bash(npm run *), Edit(/docs/**)) en lugar de dangerously-skip-permissions [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2007179854077407667)
- [/sandbox](https://code.claude.com/docs/en/sandboxing) para reducir las solicitudes de permisos con aislamiento de archivos y red — reducción del 84% internamente [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2021700506465579443) [![Cat](!/tags/cat-wu.svg)](https://creatoreconomy.so/p/inside-claude-code-how-an-ai-native-actually-works-cat-wu)
- etiqueta a [@claude](https://github.com/apps/claude) en el PR de un compañero para autogenerar reglas de lint para comentarios de revisión recurrentes — automatízate fuera de la revisión de código 🚫👶 [![Boris](!/tags/boris-cherny.svg)](https://youtu.be/julbw1JuAz0?t=2715) [![Video](!/tags/video.svg)](https://youtu.be/julbw1JuAz0?t=2715)
- usa [hooks bajo demanda](https://code.claude.com/docs/en/skills) en las habilidades — /careful bloquea comandos destructivos, /freeze bloquea ediciones fuera de un directorio [![Thariq](!/tags/thariq.svg)](https://x.com/trq212/status/2033949937936085378)
- invierte en habilidades de [verificación de producto](https://code.claude.com/docs/en/skills) (signup-flow-driver, checkout-verifier) — vale la pena pasar una semana perfeccionándolas [![Thariq](!/tags/thariq.svg)](https://x.com/trq212/status/2033949937936085378)
- [mide el uso de habilidades](https://code.claude.com/docs/en/skills) con un hook PreToolUse para encontrar habilidades populares o que no se activan lo suficiente [![Thariq](!/tags/thariq.svg)](https://x.com/trq212/status/2033949937936085378)

■ **Depuración (6)**
- haz que sea un hábito tomar capturas de pantalla y compartirlas con Claude siempre que estés atascado con cualquier problema
- usa mcp ([Claude en Chrome](https://code.claude.com/docs/en/chrome), [Playwright](https://github.com/microsoft/playwright-mcp), [Chrome DevTools](https://developer.chrome.com/blog/chrome-devtools-mcp)) para dejar que Claude vea los logs de la consola de Chrome por su cuenta
- pide siempre a Claude que ejecute la terminal (de la que quieres ver los logs) como una tarea en segundo plano para una mejor depuración
- [/doctor](https://code.claude.com/docs/en/cli-reference) para diagnosticar problemas de instalación, autenticación y configuración
- el error durante la compactación se puede resolver usando [/model](https://code.claude.com/docs/en/model-config) para seleccionar un modelo de 1M de tokens, luego ejecutando [/compact](https://code.claude.com/docs/en/interactive-mode)
- usa un [cross-model](development-workflows/cross-model-workflow/cross-model-workflow.md) para QA — ej. [Codex](https://github.com/dimoni26/codex-cli-best-practice) para la revisión del plan y la implementación
- la búsqueda agéntica (glob + grep) vence a RAG — Claude Code probó y descartó las bases de datos vectoriales porque el código se desincroniza y los permisos son complejos [![Boris](!/tags/boris-cherny.svg)](https://youtu.be/julbw1JuAz0?t=3095) [![Video](!/tags/video.svg)](https://youtu.be/julbw1JuAz0?t=3095)

■ **Utilidades (5)**
- terminales [iTerm](https://iterm2.com/)/[Ghostty](https://ghostty.org/) [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2017742753971769626)/[tmux](https://github.com/tmux/tmux) en lugar de IDE ([VS Code](https://code.visualstudio.com/)/[Cursor](https://www.cursor.com/))
- [Wispr Flow](https://wisprflow.ai) para prompts de voz (10x productividad)
- [claude-code-hooks](https://github.com/dimoni26/claude-code-hooks) para feedback de Claude
- [línea de estado](https://github.com/dimoni26/claude-code-status-line) para conciencia del contexto y compactación rápida [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2021700784019452195)
- explora las características de [settings.json](best-practice/claude-settings.md) como [Directorio de Planes](best-practice/claude-settings.md#plans-directory), [Verbos del Spinner](best-practice/claude-settings.md#display--ux) para una experiencia personalizada [![Boris](!/tags/boris-cherny.svg)](https://x.com/bcherny/status/2021701145023197516)

■ **Diario (3)**
- [actualiza](https://code.claude.com/docs/en/cli-reference) Claude Code diariamente para obtener las últimas características y correcciones de errores
- sigue [r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/), [r/ClaudeCode](https://www.reddit.com/r/ClaudeCode/) ![Reddit](https://img.shields.io/badge/-FF4500?style=flat&logo=reddit&logoColor=white)
- sigue a [Boris](https://x.com/bcherny), [Thariq](https://x.com/trq212), [Cat](https://x.com/_catwu), [Lydia](https://x.com/lydiahallie), [Noah](https://x.com/noahzweben), [Anthony](https://x.com/amorriscode), [Alex](https://x.com/alexalbert__), [Claude](https://x.com/claudeai) ![X](https://img.shields.io/badge/-000?style=flat&logo=x&logoColor=white)

![Boris Cherny + Equipo](!/tags/boris-team.svg)

- [Lecciones de la construcción de Claude Code: Cómo usamos las habilidades (Thariq) | 17/Mar/26](tips/claude-thariq-tips-17-mar-26.md) ● [Artículo](https://x.com/trq212/status/2033949937936085378)
- [Revisión de Código y Cómputo en Tiempo de Prueba (Boris) | 10/Mar/26](tips/claude-boris-2-tips-10-mar-26.md) ● [Tweet](https://x.com/bcherny/status/2031089411820228645)
- /loop — programa tareas recurrentes por hasta 3 días (Boris) | 07 Mar 2026 ● [Tweet](https://x.com/bcherny/status/2030193932404150413)
- AskUserQuestion + ASCII Markdowns (Thariq) | 28 Feb 2026 ● [Tweet](https://x.com/trq212/status/2027543858289250472)
- Viendo como un Agente - lecciones de la construcción de Claude Code (Thariq) | 28 Feb 2026 ● [Artículo](https://x.com/trq212/status/2027463795355095314)
- Git Worktrees - 5 formas en que Boris los está usando | 21 Feb 2026 ● [Tweet](https://x.com/bcherny/status/2025007393290272904)
- Lecciones de la construcción de Claude Code: El almacenamiento en caché de prompts lo es todo (Thariq) | 20 Feb 2026 ● [Artículo](https://x.com/trq212/status/2024574133011673516)
- [12 formas en que la gente está personalizando sus Claudes (Boris) | 12/Feb/26](tips/claude-boris-12-tips-12-feb-26.md) ● [Tweet](https://x.com/bcherny/status/2021699851499798911)
- [10 consejos para usar Claude Code del equipo (Boris) | 01/Feb/26](tips/claude-boris-10-tips-01-feb-26.md) ● [Tweet](https://x.com/bcherny/status/2017742741636321619)
- [Cómo uso Claude Code — 13 consejos de mi configuración sorprendentemente básica (Boris) | 03/Ene/26](tips/claude-boris-13-tips-03-jan-26.md) ● [Tweet](https://x.com/bcherny/status/2007179832300581177)
- Pide a Claude que te entreviste usando la herramienta AskUserQuestion (Thariq) | 28/Dic/25 ● [Tweet](https://x.com/trq212/status/2005315275026260309)
- Usa siempre el modo plan, dale a Claude una forma de verificar, usa /code-review (Boris) | 27/Dic/25 ● [Tweet](https://x.com/bcherny/status/2004711722926616680)

![Videos / Podcasts](!/tags/videos-podcasts.svg)

- Construyendo Claude Code con Boris Cherny (Boris) | 04 Mar 2026 | The Pragmatic Engineer ● [YouTube](https://youtu.be/julbw1JuAz0)
- Jefe de Claude Code: Qué sucede después de que la codificación esté resuelta (Boris) | 19 Feb 2026 | Lenny's Podcast ● [YouTube](https://youtu.be/We7BZVKbCVw)
- Dentro de Claude Code con su creador Boris Cherny (Boris) | 17 Feb 2026 | Y Combinator ● [YouTube](https://youtu.be/PQU9o_5rHC4)
- Boris Cherny (Creador de Claude Code) sobre lo que hizo crecer su carrera (Boris) | 15 Dic 2025 | Ryan Peterman ● [YouTube](https://youtu.be/AmdLVWMdjOk)
- Los secretos de Claude Code de los ingenieros que lo construyeron (Cat) | 29 Oct 2025 | Every ● [YouTube](https://youtu.be/IDSAMqip6ms)

<p align="center">
  <img src="!/claude-jumping.svg" alt="divisor de sección" width="60" height="50">
</p>

## ☠️ STARTUPS / NEGOCIOS

| Claude | Reemplazado |
||-|-|
|[**Revisión de Código**](https://code.claude.com/docs/en/code-review)|[Greptile](https://greptile.com), [CodeRabbit](https://coderabbit.ai), [Devin Review](https://devin.ai), [OpenDiff](https://opendiff.com), [Cursor BugBot](https://bugbot.dev)|
|[**Dictado por Voz**](https://code.claude.com/docs/en/voice-dictation)|[Wispr Flow](https://wisprflow.ai), [SuperWhisper](https://superwhisper.com/)|
|[**Control Remoto**](https://code.claude.com/docs/en/remote-control)|[OpenClaw](https://openclaw.ai/)
|[**Cowork**](https://claude.com/blog/cowork-research-preview)|[OpenAI Operator](https://openai.com/operator), [AgentShadow](https://agentshadow.ai)
|[**Tareas**](https://x.com/trq212/status/2014480496013803643)|[Beads](https://github.com/steveyegge/beads)
|[**Modo Plan**](https://code.claude.com/docs/en/common-workflows)|[Agent OS](https://github.com/buildermethods/agent-os)|
|[**Habilidades / Plugins**](https://code.claude.com/docs/en/plugins)|Startups de envoltorios de IA de YC ([reddit](https://reddit.com/r/ClaudeAI/comments/1r6bh4d/claude_code_skills_are_basically_yc_ai_startup/))|

<p align="center">
  <img src="!/claude-jumping.svg" alt="divisor de sección" width="60" height="50">
</p>

<a id="billion-dollar-questions"></a>
![Preguntas de Mil Millones de Dólares](!/tags/billion-dollar-questions.svg)

*Si tienes respuestas, házmelo saber en dimoni26@example.com*

**Memoria e Instrucciones (4)**

1. ¿Qué deberías poner exactamente dentro de tu CLAUDE.md — y qué deberías dejar fuera?
2. Si ya tienes un CLAUDE.md, ¿es realmente necesario un constitution.md o rules.md por separado?
3. ¿Con qué frecuencia deberías actualizar tu CLAUDE.md y cómo sabes cuándo se ha quedado obsoleto?
4. ¿Por qué Claude sigue ignorando las instrucciones de CLAUDE.md — incluso cuando dicen MUST en mayúsculas? ([reddit](https://reddit.com/r/ClaudeCode/comments/1qn9pb9/claudemd_says_must_use_agent_claude_ignores_it_80/))

**Agentes, Habilidades y Flujos de Trabajo (6)**

1. ¿Cuándo deberías usar un comando vs un agente vs una habilidad — y cuándo es simplemente mejor el Claude Code básico?
2. ¿Con qué frecuencia deberías actualizar tus agentes, comandos y flujos de trabajo a medida que los modelos mejoran?
3. ¿Mejora la calidad darle a tu subagente una persona detallada? ¿Cómo se ve una "persona/prompt perfecto" para un subagente de investigación/QA?
4. ¿Deberías confiar en el modo plan integrado de Claude Code — o construir tu propio comando/agente de planificación que imponga el flujo de trabajo de tu equipo?
5. Si tienes una habilidad personal (ej., /implementar con tu estilo de codificación), ¿cómo incorporas habilidades de la comunidad (ej., /simplificar) sin conflictos — y quién gana cuando no están de acuerdo?
6. ¿Ya llegamos? ¿Podemos convertir una base de código existente en especificaciones, borrar el código y hacer que la IA regenere exactamente el mismo código solo a partir de esas especificaciones?

**Especificaciones y Documentación (3)**

1. ¿Debería cada característica en tu repositorio tener una especificación como un archivo markdown?
2. ¿Con qué frecuencia necesitas actualizar las especificaciones para que no queden obsoletas cuando se implementa una nueva característica?
3. Al implementar una nueva característica, ¿cómo manejas el efecto dominó en las especificaciones de otras características?

<p align="center">
  <img src="!/claude-jumping.svg" alt="divisor de sección" width="60" height="50">
</p>

## INFORMES (REPORTS)

<p align="center">
  <a href="reports/claude-agent-sdk-vs-cli-system-prompts.md"><img src="https://img.shields.io/badge/Agent_SDK_vs_CLI-555?style=for-the-badge" alt="Agent SDK vs CLI"></a>
  <a href="reports/claude-in-chrome-v-chrome-devtools-mcp.md"><img src="https://img.shields.io/badge/Browser_Automation_MCP-555?style=for-the-badge" alt="Browser Automation MCP"></a>
  <a href="reports/claude-global-vs-project-settings.md"><img src="https://img.shields.io/badge/Global_vs_Project_Settings-555?style=for-the-badge" alt="Global vs Project Settings"></a>
  <a href="reports/claude-skills-for-larger-mono-repos.md"><img src="https://img.shields.io/badge/Skills_in_Monorepos-555?style=for-the-badge" alt="Skills in Monorepos"></a>
  <br>
  <a href="reports/claude-agent-memory.md"><img src="https://img.shields.io/badge/Agent_Memory-555?style=for-the-badge" alt="Agent Memory"></a>
  <a href="reports/claude-advanced-tool-use.md"><img src="https://img.shields.io/badge/Advanced_Tool_Use-555?style=for-the-badge" alt="Advanced Tool Use"></a>
  <a href="reports/claude-usage-and-rate-limits.md"><img src="https://img.shields.io/badge/Usage_&_Rate_Limits-555?style=for-the-badge" alt="Usage & Rate Limits"></a>
  <a href="reports/claude-agent-command-skill.md"><img src="https://img.shields.io/badge/Agents_vs_Commands_vs_Skills-555?style=for-the-badge" alt="Agents vs Commands vs Skills"></a>
  <br>
  <a href="reports/llm-day-to-day-degradation.md"><img src="https://img.shields.io/badge/LLM_Degradation-555?style=for-the-badge" alt="LLM Degradation"></a>
</p>

<p align="center">
  <img src="!/claude-jumping.svg" alt="divisor de sección" width="60" height="50">
</p>

![Cómo usar](!/tags/how-to-use.svg)

```
1. Lee el repositorio como un curso, aprende qué son los comandos, agentes, habilidades y hooks antes de intentar usarlos.
2. Clona este repositorio y juega con los ejemplos, prueba /weather-orchestrator, escucha los sonidos de los hooks, ejecuta equipos de agentes, para que puedas ver cómo funcionan las cosas realmente.
3. Ve a tu propio proyecto y pide a Claude que sugiera qué mejores prácticas de este repositorio deberías añadir, dale este repositorio como referencia para que sepa qué es posible.
```

<p align="center">
  <img src="!/claude-jumping.svg" alt="divisor de sección" width="60" height="50">
</p>

<p align="center">
  <a href="https://github.com/trending?since=monthly"><img src="!/root/github-trending.png" alt="GitHub Trending" width="1200"></a><br>
  ✨Tendencias en Github en Marzo 2026✨
</p>

## Otros Repositorios

<a href="https://github.com/dimoni26/claude-code-hooks"><img src="!/claude-speaking.svg" alt="Claude Code Hooks" width="40" height="40" align="center"></a> <a href="https://github.com/dimoni26/claude-code-hooks"><strong>claude-code-hooks</strong></a> · <a href="https://github.com/dimoni26/codex-cli-best-practice"><img src="!/codex-jumping.svg" alt="Codex CLI" width="40" height="40" align="center"></a> <a href="https://github.com/dimoni26/codex-cli-best-practice"><strong>codex-cli-best-practice</strong></a> · <a href="https://github_com/dimoni26/codex-cli-hooks"><img src="!/codex-speaking.svg" alt="Codex CLI Hooks" width="40" height="40" align="center"></a> <a href="https://github_com/dimoni26/codex-cli-hooks"><strong>codex-cli-hooks</strong></a>

## Desarrollado por

![Desarrollado por](!/tags/developed-by.svg)

> | Flujo de Trabajo | Descripción |
> |----------|-------------|
> | /workflows:development-workflows | Actualiza la tabla de FLUJOS DE TRABAJO DE DESARROLLO y el informe de análisis cross-workflow investigando los 9 repositorios de flujos de trabajo en paralelo |
> | /workflows:best-practice:workflow-concepts | Actualiza la sección de CONCEPTOS del README con las últimas características y conceptos de Claude Code |
> | /workflows:best-practice:workflow-claude-settings | Rastrea los cambios en el informe de ajustes de Claude Code y encuentra qué necesita actualización |
> | /workflows:best-practice:workflow-claude-subagents | Rastrea los cambios en el informe de subagentes de Claude Code y encuentra qué necesita actualización |
> | /workflows:best-practice:workflow-claude-commands | Rastrea los cambios en el informe de comandos de Claude Code y encuentra qué necesita actualización |
> | /workflows:best-practice:workflow-claude-skills | Rastrea los cambios en el informe de habilidades de Claude Code y encuentra qué necesita actualización |

[![Claude para OSS](!/tags/claude-for-oss.svg)](https://claude.com/contact-sales/claude-for-oss)
[![Embajador de la Comunidad Claude](!/tags/claude-community-ambassador.svg)](https://claude.com/community/ambassadors)
[![Arquitecto Certificado de Claude](!/tags/claude-certified-architect.svg)](https://anthropic.skilljar.com/claude-certified-architect-foundations-access-request)
[![Academia Anthropic](!/tags/anthropic-academy.svg)](https://anthropic.skilljar.com/)
