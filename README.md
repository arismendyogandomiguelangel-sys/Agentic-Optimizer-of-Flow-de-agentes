# Agentic Optimizer of Flow de agentes

Este repositorio contiene la habilidad **AgentNet Parallel Flow**, diseñada para estandarizar y optimizar la forma en que los modelos (como Claude) despliegan subagentes con tareas paralelas.

La premisa principal de este proyecto es que el modelo base asume el rol de **Orquestador** e invoca subagentes de manera automática utilizando los modelos más eficientes para cada tipo de tarea:

- **Claude 3.5 Opus:** Para razonamiento, planificación y diseño de arquitectura.
- **Claude 3.5 Sonnet:** Para ejecución, programación e implementación rápida.
- **Claude 3.5 Haiku:** Para síntesis, revisión rápida de textos y resúmenes.

## Instalación en tu entorno local

Para integrar esta habilidad en tu flujo de trabajo con Claude Code o sistemas similares de agentes CLI:

```bash
# Copia la skill a tu directorio de comandos de Claude
mkdir -p ~/.claude/commands
cp skills/*.md ~/.claude/commands/
```

## Uso

Una vez instalada, simplemente llama a la skill pasando el objetivo de tu proyecto o tarea:

```bash
/agentnet! Crea una nueva aplicación web React conectada a Firebase con autenticación.
```

El modelo principal analizará tu petición, la descompondrá y desplegará automáticamente a los subagentes especializados, optimizando velocidad y calidad sin requerir intervención manual para seleccionar los modelos en cada paso.
