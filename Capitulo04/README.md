# Laboratorio 4: Investigar, validar y cerrar el ciclo de comunicación

**Duración:** 25 min

## Descripción
Con Investigador contrastarán tendencias, referencias externas o hechos que requieran respaldo adicional antes de incorporarlos al mensaje[cite: 3]. Con Analista revisarán datos disponibles de campañas o comunicaciones para identificar patrones de respuesta, segmentos y oportunidades de mejora[cite: 3]. Regresarán al chat reutilizable o al contexto organizado en Copilot Notebooks para actualizar el boletín con la evidencia y los resultados más recientes[cite: 3]. Aplicarán una revisión final de actualidad, consistencia, trazabilidad, tono, audiencia y diferenciación entre hechos, interpretaciones y elementos pendientes de validación[cite: 3]. Cerrarán la actividad dejando preparada la estructura que se reutilizaría en la siguiente semana y definiendo qué fuentes deben actualizarse en el siguiente ciclo[cite: 3].

## Pasos para ejecutar la práctica

1. **Investigación de tendencias externas con el agente Investigador:**
   * Activa el agente **Investigador (Researcher)** en Microsoft 365 Copilot.
   * Envía el siguiente prompt estructurado:
     ```text
     Escribe un PLAN DE INVESTIGACIÓN de 2 pasos para analizar tendencias recientes en canales de comunicación interna y efectividad de boletines corporativos.

     A continuación, ejecuta el plan realizando una búsqueda directa y entrega un informe sintético de 3 viñetas con mejores prácticas, respaldado por referencias y fechas.
     ```

2. **Análisis de desempeño de campaña con el agente Analista:**
   * Activa el agente **Analista (Analyst)** en Microsoft 365 Copilot.
   * Adjunta el archivo `Plan_Editorial_Seguimiento.xlsx` y envía:
     ```text
     Analiza la tabla de datos del archivo adjunto Plan_Editorial_Seguimiento.xlsx.
     
     Identifica:
     1. Patrones de respuesta o canales con mayor efectividad teórica según los KPIs.
     2. Brechas de distribución por audiencia.
     3. Tres recomendaciones concretas para optimizar el siguiente ciclo de comunicación.
     ```

3. **Consolidación de la versión final en Markdown:**
   * Abre Copilot Chat, vincula el archivo `Boletin_Semanal_Edicion2.docx` y las conclusiones del Analista e Investigador, y envía:
     ```text
     Genera la versión optimizada "Boletín Semanal - Edición Final Consolidada" integrando las tendencias externas y las recomendaciones de desempeño analizadas.
     
     Entrega el resultado estructurado en sintaxis Markdown (.md) incluyendo una nota final sobre las fuentes que deberán actualizarse en el siguiente ciclo semanal.
     ```
   * Guarda el resultado en un archivo llamado: `boletin_final_consolidado.md`.

4. **Validación interactiva con prueba de opción múltiple:**
   * En Copilot Chat, envía la siguiente solicitud para cerrar la sesión:
     ```text
     Con base en el contenido de boletin_final_consolidado.md, actúa como Director de Marca y evalúa mi criterio editorial mediante una prueba de opción múltiple.

     Reglas:
     1. Hazme 3 preguntas consecutivas (con opciones A, B, C, D) sobre trazabilidad de fuentes, tono adecuado y priorización de mensajes.
     2. Realiza una pregunta a la vez y espera a que responda únicamente con la letra seleccionada.
     3. Entrega retroalimentación inmediata sobre la elección realizada antes de formular la siguiente pregunta.
     ```

## Resultado esperado
Un informe final consolidado guardado como `boletin_final_consolidado.md` respaldado por investigación externa y analítica de desempeño, junto con la evaluación interactiva de opción múltiple completada en Copilot Chat.
