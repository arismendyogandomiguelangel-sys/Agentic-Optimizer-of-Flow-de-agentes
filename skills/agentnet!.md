# AgentNet Parallel Skill

Usa esta skill (con el comando `/agentnet!`) cuando el proyecto requiera dividir trabajo en paralelo entre múltiples subagentes especializados, optimizando el flujo de trabajo (Agentic Optimizer of Flow).

$ARGUMENTS

---

## Roles y Modelos Recomendados

- **Razonador / Planner / Arquitecto:** Opus (ej. Claude 3.5 Opus).
- **Implementador / Builder / Ejecutor:** Sonnet (ej. Claude 3.5 Sonnet).
- **Escritor / Resumidor / Revisor:** Haiku (ej. Claude 3.5 Haiku).
- **Modo de trabajo:** Paralelo, con subtareas independientes y consolidación final.

## Instrucción Principal de Orquestación

Tú actúas como el **Orquestador**. Antes de ejecutar, descompón el proyecto o la tarea recibida en subtareas claras.
Abre **subagentes en paralelo** para delegar el trabajo. Al instanciar cada subagente, asígnale explícitamente el modelo adecuado según su carga cognitiva. El usuario no debe cambiar de modelo manualmente; tú debes automatizar este enrutamiento.

## Flujo de Trabajo (AgentNet Flow)

1. **Analiza el objetivo general:** Identifica qué componentes, archivos o análisis se requieren.
2. **Divide el trabajo:** Crea un grafo de dependencias de subtareas. Separa lo que debe ser secuencial (ej. definir interfaces) de lo que es paralelizable.
3. **Despliega Subagentes (Enrutamiento Automático):**
   - **Arquitectura y Planificación:** Para tomar decisiones complejas, definir contratos, schemas o interfaces base, lanza un subagente utilizando el modelo **Opus**.
   - **Ejecución y Código:** Para escribir, refactorizar o modificar archivos, lanza múltiples subagentes paralelos usando **Sonnet**. Cada subagente debe enfocarse en un archivo o módulo no superpuesto.
   - **Síntesis y Documentación:** Para resumir salidas, crear borradores rápidos, escribir documentación o revisar ortografía, lanza subagentes usando **Haiku**.
4. **Reúne resultados:** Espera a que los subagentes paralelos reporten sus resultados.
5. **Consolida:** Revisa el trabajo integrado. Si hay errores o conflictos de interfaz, pide correcciones a los subagentes.
6. **Entrega final:** Proporciona una respuesta final corta, clara y accionable al usuario.

## Reglas Clave

- **Enrutamiento Inteligente:** Si una tarea requiere arquitectura, decisiones complejas o planificación, **usa Opus**. Si requiere escribir o refactorizar código, **usa Sonnet**. Si requiere resumir o texto liviano, **usa Haiku**.
- **Contratos antes que Código:** Nunca lances ejecutores en paralelo si no se han definido antes las interfaces o esquemas base.
- **Independencia:** Cada agente ejecutor debe recibir archivos sin superposición para evitar conflictos.
- **No lo hagas tú mismo:** Si una tarea puede dividirse, usa los subagentes. Maximiza la velocidad, calidad y paralelización sin perder coherencia.
