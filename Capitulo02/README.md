# Laboratorio 2: Construir y actualizar el contexto con fuentes de Microsoft 365

**Duración:** 20 min

## Descripción
Partirán de la edición anterior e incorporarán nuevas fuentes de la semana, evitando la recopilación manual de notas cuando la información ya esté disponible en Microsoft 365[cite: 3]. Reutilizarán la misma sesión de chat para solicitar una nueva versión del boletín con los acontecimientos recientes y las mismas reglas editoriales[cite: 3]. Organizarán en Copilot Notebooks las referencias disponibles que deban mantenerse como contexto estable para futuras ediciones[cite: 3]. Solicitarán a Copilot diferenciar información nueva, cambios respecto de la edición anterior, datos potencialmente obsoletos, contradicciones y elementos que requieren validación[cite: 3]. Revisarán la trazabilidad de las afirmaciones principales antes de aceptar el contenido generado[cite: 3].

## Pasos para ejecutar la práctica

1. **Organización del contexto en Copilot Notebooks:**
   * Abre **Copilot Notebooks** (Bloc de notas de Copilot).
   * Adjunta el archivo `Boletin_Semanal_Edicion1.docx` creado en el laboratorio anterior.
   * En el panel de instrucciones de Notebooks, envía el siguiente prompt:
     ```text
     Analiza el documento adjunto Boletin_Semanal_Edicion1.docx y consolídalo como nuestro contexto de referencia estable para el boletín semanal.
     
     Identifica y resume:
     1. Temas clave tratados en la edición anterior.
     2. Supuestos que requerían validación adicional.
     ```

2. **Actualización de la versión con deltas e información nueva:**
   * En el mismo Copilot Notebook, envía la siguiente instrucción para generar la Edición 2:
     ```text
     Genera la Edición 2 del "Boletín Semanal de Innovación y Estrategia" manteniendo exactamente la misma estructura y tono de la Edición 1.
     
     Incorpora los siguientes hechos recientes:
     - Cierre exitoso del piloto de canales digitales con 15% de incremento en adopción.
     - Ajustes en el cronograma de despliegue de soluciones de analítica para el próximo trimestre.
     
     Añade una sección final llamada "Análisis de Cambios y Trazabilidad" que especifique:
     - Información nueva respecto a la edición anterior.
     - Datos actualizados o corregidos.
     - Puntos pendientes de validación.
     ```

3. **Exportación de la Edición 2 a Word:**
   * Copia o exporta la respuesta del cuaderno a un archivo de Microsoft Word con el nombre exacto: `Boletin_Semanal_Edicion2.docx`.

## Resultado esperado
Un documento de Word guardado como `Boletin_Semanal_Edicion2.docx` que actualiza la versión previa del boletín mediante Copilot Notebooks, incluyendo el análisis explícito de cambios y trazabilidad.
