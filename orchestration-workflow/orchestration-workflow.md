# Flujo de Trabajo de Orquestación

Este documento describe el flujo de orquestación **Comando → Agente (con skill) → Skill**, demostrado a través de un sistema de obtención de datos meteorológicos y renderizado SVG.

<table width="100%">
<tr>
<td><a href="../">← Volver a Claude Code Best Practice</a></td>
<td align="right"><img src="../!/claude-jumping.svg" alt="Claude" width="60" /></td>
</tr>
</table>

## Visión General del Sistema

El sistema meteorológico demuestra dos patrones de skill distintos dentro de un único flujo de orquestación:
- **Skills de Agente** (precargadas): `weather-fetcher` se inyecta en el `weather-agent` al inicio como conocimiento de dominio
- **Skills** (independientes): `weather-svg-creator` es invocada directamente por el comando a través de la herramienta Skill

Esto muestra el patrón de arquitectura **Comando → Agente → Skill**, donde:
- Un comando orquesta el flujo de trabajo y gestiona la interacción con el usuario
- Un agente obtiene datos usando su skill precargada
- Una skill crea la salida visual de forma independiente

## Resumen de Componentes

| Componente | Rol | Ejemplo |
|-----------|------|---------|
| **Comando** | Punto de entrada, interacción con el usuario | [`/weather-orchestrator`](../.claude/commands/weather-orchestrator.md) |
| **Agente** | Obtiene datos con skill precargada (skill de agente) | [`weather-agent`](../.claude/agents/weather-agent.md) con [`weather-fetcher`](../.claude/skills/weather-fetcher/SKILL.md) |
| **Skill** | Crea la salida de forma independiente (skill) | [`weather-svg-creator`](../.claude/skills/weather-svg-creator/SKILL.md) |

## Diagrama de Flujo

```
╔══════════════════════════════════════════════════════════════════╗
║              FLUJO DE ORQUESTACIÓN                               ║
║           Comando  →  Agente  →  Skill                           ║
╚══════════════════════════════════════════════════════════════════╝

                         ┌───────────────────┐
                         │ Interacción Usuario│
                         └─────────┬─────────┘
                                   │
                                   ▼
         ┌─────────────────────────────────────────────────────┐
         │  /weather-orchestrator — Comando (Punto de Entrada) │
         └─────────────────────────┬───────────────────────────┘
                                   │
                              Paso 1
                                   │
                                   ▼
                      ┌────────────────────────┐
                      │  AskUser — ¿C° o F°?   │
                      └────────────┬───────────┘
                                   │
                         Paso 2 — Herramienta Agente
                                   │
                                   ▼
         ┌─────────────────────────────────────────────────────┐
         │  weather-agent — Agente ● skill: weather-fetcher    │
         └─────────────────────────┬───────────────────────────┘
                                   │
                          Devuelve: temp + unidad
                                   │
                         Paso 3 — Herramienta Skill
                                   │
                                   ▼
         ┌─────────────────────────────────────────────────────┐
         │  weather-svg-creator — Skill ● Tarjeta SVG + salida │
         └─────────────────────────┬───────────────────────────┘
                                   │
                          ┌────────┴────────┐
                          │                 │
                          ▼                 ▼
                   ┌────────────┐    ┌────────────┐
                   │weather.svg │    │ output.md  │
                   └────────────┘    └────────────┘
```

## Detalles de los Componentes

### 1. Comando

#### `/weather-orchestrator` (Comando)
- **Ubicación**: `.claude/commands/weather-orchestrator.md`
- **Propósito**: Punto de entrada — orquesta el flujo de trabajo y gestiona la interacción con el usuario
- **Acciones**:
  1. Pregunta al usuario la unidad de temperatura preferida (Celsius/Fahrenheit)
  2. Invoca weather-agent mediante la herramienta Agente
  3. Invoca weather-svg-creator mediante la herramienta Skill
- **Modelo**: haiku

### 2. Agente con Skill Precargada (Skill de Agente)

#### `weather-agent` (Agente)
- **Ubicación**: `.claude/agents/weather-agent.md`
- **Propósito**: Obtener datos meteorológicos usando su skill precargada
- **Skills**: `weather-fetcher` (precargada como conocimiento de dominio)
- **Herramientas Disponibles**: WebFetch, Read
- **Modelo**: sonnet
- **Color**: verde
- **Memoria**: proyecto

El agente tiene `weather-fetcher` precargada en su contexto al inicio. Sigue las instrucciones de la skill para obtener la temperatura y devuelve el valor al comando.

### 3. Skill

#### `weather-svg-creator` (Skill)
- **Ubicación**: `.claude/skills/weather-svg-creator/SKILL.md`
- **Propósito**: Crear una tarjeta SVG meteorológica visual y escribir los archivos de salida
- **Invocación**: Mediante la herramienta Skill desde el comando (no precargada en ningún agente)
- **Salidas**:
  - `orchestration-workflow/weather.svg` — Tarjeta SVG meteorológica
  - `orchestration-workflow/output.md` — Resumen meteorológico

### 4. Skill Precargada

#### `weather-fetcher` (Skill)
- **Ubicación**: `.claude/skills/weather-fetcher/SKILL.md`
- **Propósito**: Instrucciones para obtener datos de temperatura en tiempo real
- **Fuente de Datos**: API Open-Meteo para Dubái, EAU
- **Salida**: Valor de temperatura y unidad (Celsius o Fahrenheit)
- **Nota**: Esta es una skill de agente — precargada en `weather-agent`, no se invoca directamente

## Flujo de Ejecución

1. **Invocación del Usuario**: El usuario ejecuta el comando `/weather-orchestrator`
2. **Pregunta al Usuario**: El comando pregunta la unidad de temperatura preferida (Celsius/Fahrenheit)
3. **Invocación del Agente**: El comando invoca `weather-agent` mediante la herramienta Agente
4. **Ejecución de la Skill** (dentro del contexto del agente):
   - El agente sigue las instrucciones de la skill `weather-fetcher` para obtener la temperatura desde Open-Meteo
   - El agente devuelve el valor de temperatura y la unidad al comando
5. **Creación del SVG**: El comando invoca `weather-svg-creator` mediante la herramienta Skill
   - La skill crea la tarjeta SVG en `orchestration-workflow/weather.svg`
   - La skill escribe el resumen en `orchestration-workflow/output.md`
6. **Visualización del Resultado**: Se muestra un resumen al usuario con:
   - Unidad de temperatura solicitada
   - Temperatura obtenida
   - Ubicación de la tarjeta SVG
   - Ubicación del archivo de salida

## Ejemplo de Ejecución

```
Entrada: /weather-orchestrator
├─ Paso 1: Pregunta: ¿Celsius o Fahrenheit?
│  └─ Usuario: Celsius
├─ Paso 2: Herramienta Agente → weather-agent
│  ├─ Skill Precargada:
│  │  └─ weather-fetcher (conocimiento de dominio)
│  ├─ Obtiene de Open-Meteo → 26°C
│  └─ Devuelve: temperatura=26, unidad=Celsius
├─ Paso 3: Herramienta Skill → /weather-svg-creator
│  ├─ Crea: orchestration-workflow/weather.svg
│  └─ Escribe: orchestration-workflow/output.md
└─ Salida:
   ├─ Unidad: Celsius
   ├─ Temperatura: 26°C
   ├─ SVG: orchestration-workflow/weather.svg
   └─ Resumen: orchestration-workflow/output.md
```

## Principios Clave de Diseño

1. **Dos Patrones de Skill**: Demuestra tanto las skills de agente (precargadas) como las skills (invocadas directamente)
2. **Comando como Orquestador**: El comando gestiona la interacción con el usuario y coordina el flujo de trabajo
3. **Agente para Obtención de Datos**: El agente usa su skill precargada para obtener datos y los devuelve
4. **Skill para la Salida**: El creador de SVG se ejecuta de forma independiente, recibiendo datos del contexto del comando
5. **Separación Clara de Responsabilidades**: Obtención (agente) → Renderizado (skill) — cada componente tiene una única responsabilidad

## Patrones de Arquitectura

### Skill de Agente (Precargada)

```yaml
# En la definición del agente (.claude/agents/weather-agent.md)
---
name: weather-agent
skills:
  - weather-fetcher    # Precargada en el contexto del agente al inicio
---
```

- **Las skills se precargan**: El contenido completo de la skill se inyecta en el contexto del agente al inicio
- **El agente usa el conocimiento de la skill**: El agente sigue las instrucciones de las skills precargadas
- **Sin invocación dinámica**: Las skills son material de referencia, no se invocan por separado

### Skill (Invocación Directa)

```yaml
# En la definición de la skill (.claude/skills/weather-svg-creator/SKILL.md)
---
name: weather-svg-creator
description: Crea una tarjeta SVG meteorológica...
---
```

- **Invocada mediante la herramienta Skill**: El comando llama a `Skill(skill: "weather-svg-creator")`
- **Ejecución independiente**: Se ejecuta en el contexto del comando, no dentro de un agente
- **Recibe datos del contexto**: Usa los datos de temperatura ya disponibles en la conversación
