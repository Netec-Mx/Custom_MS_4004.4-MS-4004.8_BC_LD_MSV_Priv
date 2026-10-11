# Laboratorio 3: Convertir el contexto en entregables con Copilot en Microsoft 365

**Duración:** 40 min

## Descripción
Práctica 3.1: Usarán la edición validada del boletín como fuente común para evitar recrear el contexto en cada aplicación[cite: 3]. En Word desarrollarán una versión ampliada del contenido o un brief editorial, manteniendo audiencia, tono, mensajes clave y evidencia[cite: 3]. En PowerPoint convertirán los mismos hallazgos en una síntesis visual para responsables de campaña, comunicaciones o liderazgo[cite: 3]. Validarán que las piezas mantengan coherencia entre sí y que las adaptaciones por formato no cambien el significado del mensaje[cite: 3].

Práctica 3.2: En Excel estructurarán un plan editorial con pieza, audiencia, canal, responsable, fecha, estado, KPI y objetivo de cada comunicación[cite: 3]. Utilizarán Copilot para detectar vacíos de cobertura, mensajes duplicados, concentraciones de publicaciones y oportunidades de ajuste en el plan[cite: 3]. En Outlook prepararán una comunicación basada en la versión aprobada, adaptando el mensaje al destinatario sin perder los elementos esenciales definidos en el prompt reutilizable[cite: 3].

## Pasos para ejecutar la práctica

1. **Desarrollo del Brief Editorial en Microsoft Word:**
   * Abre **Microsoft Word** y activa Copilot.
   * Adjunta el archivo `Boletin_Semanal_Edicion2.docx` y envía el siguiente prompt:
     ```text
     Con base en el archivo adjunto Boletin_Semanal_Edicion2.docx, elabora un Brief Editorial Extendido para la campaña de comunicación interna.
     
     Incluye: Objetivo de comunicación, Mensajes clave por audiencia, Evidencia de soporte, Tono de voz y Canales de distribución recomendados.
     ```
   * Guarda el documento en Word con el nombre exacto: `Brief_Editorial_Campaña.docx`.

2. **Creación de la Presentación Ejecutiva en PowerPoint:**
   * Abre **Microsoft PowerPoint** y activa Copilot.
   * Adjunta el archivo `Brief_Editorial_Campaña.docx` y envía:
     ```text
     Crea una presentación ejecutiva de 4 diapositivas basada en el archivo adjunto Brief_Editorial_Campaña.docx:
     - Diapositiva 1: Resumen de Comunicaciones e Hitos de la Semana
     - Diapositiva 2: Mensajes Clave y Audiencias
     - Diapositiva 3: Avances de Campaña e Impacto
     - Diapositiva 4: Próximos Pasos y Plan de Publicaciones
     ```
   * Guarda la presentación con el nombre: `Sintesis_Ejecutiva_Comunicaciones.pptx`.

3. **Construcción del Plan Editorial en Microsoft Excel:**
   * Abre un libro nuevo en **Microsoft Excel** y guárdalo como `Plan_Editorial_Seguimiento.xlsx`.
   * En Copilot en Excel (modo **Plan**), envía:
     ```text
     Estructura una tabla de Plan Editorial con las columnas: Id_Pieza, Pieza_Comunicación, Audiencia_Objetivo, Canal, Responsable, Fecha_Publicación, Estado, KPI_Esperado y Objetivo_Estratégico. Genera 6 filas de contenido basadas en la campaña actual.
     ```
   * Cambia al modo **Permitir la edición** (Edición) en Copilot en Excel y envía:
     ```text
     Aplica un formato condicional a las piezas en estado "Pendiente de Aprobación" y genera un análisis rápido indicando si existen vacíos de cobertura o concentración de publicaciones en un mismo canal.
     ```

4. **Preparación del borrador de distribución en Microsoft Outlook:**
   * Abre **Microsoft Outlook** o Copilot Chat, adjunta el documento `Brief_Editorial_Campaña.docx` y envía:
     ```text
     Con base en el archivo adjunto Brief_Editorial_Campaña.docx, redacta un correo de distribución ejecutiva dirigido a la red de líderes. Adaptar el texto para formato de correo breve, directo y enfocado en la acción.
     ```

## Resultado esperado
Un Brief Editorial en Word (`Brief_Editorial_Campaña.docx`), una presentación sintética en PowerPoint (`Sintesis_Ejecutiva_Comunicaciones.pptx`), un modelo de gestión en Excel (`Plan_Editorial_Seguimiento.xlsx`) y un correo de distribución listo en Outlook.
