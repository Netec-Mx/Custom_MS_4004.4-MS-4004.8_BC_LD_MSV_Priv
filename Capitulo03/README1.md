# Práctica: Planificar seguimiento y distribución con Copilot en Excel y Outlook

## Metadatos

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 20 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Aplicar (Apply) |

## Descripción General

En este laboratorio práctico, aprenderás a utilizar de forma combinada las capacidades de asistencia de inteligencia artificial de Microsoft 365 Copilot en Excel y Outlook. Inicialmente, procesarás una lista de distribución estructurada en Excel con métricas de comportamiento histórico de lectura del equipo de mercadeo. Utilizando Copilot en Excel, segmentarás a los destinatarios que muestran baja interacción con las comunicaciones internas. Posteriormente, te trasladarás a la nueva experiencia de Outlook para estructurar y redactar un correo electrónico persuasivo, personalizado y altamente dirigido, incentivando a este grupo crítico de colaboradores a consumir el boletín informativo corporativo semanal previamente generado en el Lab 2.

## Objetivos de Aprendizaje

Al finalizar este laboratorio, serás capaz de:
- [ ] Analizar y segmentar listas de distribución en Excel utilizando prompts estructurados en lenguaje natural.
- [ ] Filtrar datos críticos de comportamiento (tasas de interacción menores al 40%) sin necesidad de escribir fórmulas complejas o macros de ordenamiento manual.
- [ ] Redactar correos electrónicos profesionales de difusión en Outlook mediante la asistencia interactiva de 'Draft con Copilot'.
- [ ] Ajustar parámetros de tono, longitud y ganchos conversacionales de manera iterativa aplicando supervisión humana antes de la distribución de información.

## Prerrequisitos

Para realizar este laboratorio con éxito, debes contar con:
- Haber completado satisfactoriamente los laboratorios **Lab 02-00-01** y **Lab 03-00-01** (donde se estructuró y almacenó el archivo de boletín en la ruta de OneDrive).
- Una cuenta de Microsoft 365 con una licencia activa de **Microsoft 365 Copilot Premium (1.0)** habilitada en tu tenant corporativo.
- Acceso a OneDrive para la Empresa asociado a tu cuenta de prueba.
- Comprensión de los principios básicos de estructuración de tablas en Microsoft Excel.

## Entorno de Laboratorio

Este laboratorio se ejecuta directamente en tus aplicaciones de productividad de Microsoft 365. Asegúrate de cumplir con el siguiente inventario de hardware y software:

### Especificaciones de Software Recomendadas

| Aplicación | Edición / Versión Requerida | Enlace Oficial de Referencia |
| :--- | :--- | :--- |
| **Microsoft 365 Apps para Empresas** | Canal Actual - Versión 2408 Build 17928.20156 (64 bits) | [Canal Actual de M365](https://learn.microsoft.com/en-us/officeupdates/current-channel) |
| **Nueva Experiencia de Outlook** | Versión 24215.1002.3044.5203 o superior | [Nuevo Outlook para Windows](https://support.microsoft.com/office/getting-started-with-the-new-outlook-for-windows-656bb037-d3ed-4c2c-94b5-4a2333b81135) |
| **Microsoft Excel** | Versión de Escritorio o Web con autoguardado activo | [Excel con Copilot](https://support.microsoft.com/office/copilot-in-excel-help-and-learning-85b4cd1e-a973-4001-9a70-8e10098f9293) |
| **Navegador Web** | Microsoft Edge (Canal Estable - Versión 128.0.2739.42 o superior) | [Descarga de Edge](https://www.microsoft.com/edge) |

### Requisitos de Conectividad y Hardware
- Conexión estable a Internet con una velocidad de subida/bajada no menor a 10 Mbps para evitar latencias en las llamadas de API hacia el servicio de Microsoft Graph y Copilot Orchestrator.
- Resolución de pantalla recomendada de 1920x1080 píxeles para facilitar la visualización del panel de Copilot en paralelo a las aplicaciones abiertas.

---

## Instrucciones Paso a Paso

### Paso 1: Preparación de los datos de distribución en Excel

**Objetivo:** Crear una tabla de datos simulada en Microsoft Excel que sirva de insumo para el análisis de comportamiento de la audiencia y guardarla en la ubicación requerida de OneDrive para que Copilot se habilite con éxito.

**Instrucciones:**

1. Inicia la aplicación **Microsoft Excel** (Desktop o Web) e inicia sesión con tu cuenta que dispone de la licencia de Copilot Premium.
2. Crea un **Nuevo libro** en blanco.
3. Copia el siguiente conjunto de datos plano de ejemplo (incluyendo la fila de encabezados) y pégalo en la celda **A1**:

```text
ID_Empleado,Nombre,Correo,Departamento,Tasa_Apertura,Ultima_Interaccion,Segmento
E01,Sofia Perez,sofia.perez@contoso.com,Mercadeo,0.25,2024-10-10,Bajo
E02,Juan Gomez,juan.gomez@contoso.com,Ventas,0.85,2024-10-24,Alto
E03,Carlos Ruiz,carlos.ruiz@contoso.com,Mercadeo,0.30,2024-10-12,Bajo
E04,Ana Martinez,ana.martinez@contoso.com,Mercadeo,0.75,2024-10-22,Alto
E05,Luis Rodriguez,luis.rodriguez@contoso.com,Ventas,0.45,2024-10-18,Medio
E06,Elena Vega,elena.vega@contoso.com,Mercadeo,0.15,2024-10-05,Bajo
E07,Pedro Castillo,pedro.castillo@contoso.com,Finanzas,0.90,2024-10-25,Alto
E08,Laura Mendez,laura.mendez@contoso.com,Mercadeo,0.35,2024-10-14,Bajo
```

4. Selecciona cualquier celda que contenga datos dentro del rango copiado (de la celda `A1` a la `G9`).
5. Presiona la combinación de teclas `Ctrl + T` (o dirígete a la pestaña **Inicio** > **Dar formato como tabla**). En la ventana emergente, asegúrate de que la casilla **"La tabla tiene encabezados"** esté marcada y haz clic en **Aceptar**.
6. Con la tabla seleccionada, ve a la pestaña **Diseño de tabla** en la cinta de opciones superior y cambia el nombre predeterminado de la tabla a `ListaDistribucion` en el campo del extremo izquierdo.
7. Selecciona los valores numéricos de la columna **Tasa_Apertura** (rango `E2:E9`), haz clic derecho, selecciona **Formato de celdas**, selecciona la categoría **Porcentaje** con 0 posiciones decimales y haz clic en **Aceptar**.
8. Guarda el archivo con el nombre `Metricas_Distribucion.xlsx` en la carpeta `/OneDrive/Boletin_Semanal/` de tu usuario. Si estás usando la aplicación de escritorio, asegúrate de activar el interruptor de **Autoguardado** en la esquina superior izquierda.

**Resultado esperado:** El archivo debe quedar guardado en la nube con un formato de tabla estructurado. El icono de **Copilot** en la pestaña Inicio debe iluminarse en color, indicando que el archivo cumple las condiciones de procesamiento de IA.

**Verificación:** Confirma que el archivo se almacena en la ruta correcta en OneDrive y que al hacer clic en cualquier celda dentro de la tabla, la pestaña "Diseño de tabla" se muestra de forma activa.

---

### Paso 2: Análisis y Segmentación con Copilot en Excel

**Objetivo:** Utilizar comandos de lenguaje natural (prompts) en Copilot para identificar de forma exclusiva a los destinatarios pertenecientes al departamento de "Mercadeo" que posean bajas tasas de interacción (menos del 40%).

**Instrucciones:**

1. En Excel, haz clic en el botón de **Copilot** ubicado en el extremo derecho de la pestaña **Inicio** para desplegar el panel lateral de chat interactivo.
2. Una vez que el panel haya cargado, introduce la siguiente instrucción detallada (prompt) en el cuadro de texto inferior:

```text
Identifica y resalta en amarillo claro todas las filas de la tabla correspondientes a empleados que pertenezcan al Departamento de "Mercadeo" y tengan una Tasa_Apertura inferior al 40%.
```

3. Presiona **Enviar** (icono de enviar o tecla Enter). Observa cómo Copilot analiza la estructura de la tabla `ListaDistribucion` y ejecuta la acción de marcado visual directamente sobre los registros que corresponden con la regla lógica dada.
4. Ahora, introduce una segunda instrucción para filtrar los resultados de forma destructiva o enfocada únicamente en los datos que te interesan exportar:

```text
Aplica un filtro a la tabla para mostrar únicamente a estos empleados de Mercadeo con baja apertura (Tasa_Apertura menor al 40%) que acabamos de marcar.
```

5. Copia los datos resultantes visibles en pantalla de los empleados que quedaron en la vista filtrada. Específicamente, registra mentalmente o en un archivo de notas los nombres y correos de las personas afectadas (por ejemplo, *Sofia Perez*, *Carlos Ruiz*, *Elena Vega*, *Laura Mendez*).

**Resultado esperado:** La tabla de Excel se actualizará dinámicamente mostrando sombreado amarillo e aplicando un filtro activo en las columnas `Departamento` ("Mercadeo") y `Tasa_Apertura` (< 40%). El panel de Copilot confirmará por chat la ejecución exitosa de los pasos de filtrado.

**Verificación:** Valida manualmente que los empleados visibles en la tabla filtrada correspondan estrictamente a los registros con tasas de apertura de `25%`, `30%`, `15%` y `35%` y que pertenezcan al equipo de Mercadeo.

---

### Paso 3: Redacción del correo de distribución y recuperación en Outlook

**Objetivo:** Diseñar y generar un correo electrónico enfocado en la adopción del boletín utilizando 'Draft con Copilot' en Outlook, dirigiendo el mensaje al equipo de mercadeo segmentado anteriormente.

**Instrucciones:**

1. Abre la aplicación **Nuevo Outlook** (o accede a la versión de Outlook Web en tu navegador Edge).
2. Haz clic en el botón **Correo nuevo** en la esquina superior izquierda de la pantalla.
3. En el campo **Para**, ingresa de manera simulada las direcciones de correo obtenidas en el Paso 2: `sofia.perez@contoso.com`, `carlos.ruiz@contoso.com`, `elena.vega@contoso.com`, `laura.mendez@contoso.com`. (Para propósitos prácticos de entorno de pruebas, puedes poner tu propia dirección si deseas enviar el correo de test de extremo a extremo).
4. En el campo de **Asunto**, escribe: `Seguimiento de innovación: Boletín Semanal de Mercadeo`.
5. Haz clic dentro del cuerpo del mensaje. Verás aparecer el indicador flotante de Copilot. Selecciona el icono azul de Copilot y haz clic en **Borrador con Copilot** (o presiona el atajo de teclado `Alt + I`).
6. En la ventana emergente de redacción de Copilot, escribe el siguiente prompt estructurado que vincula contexto cruzado:

```text
Redacta un correo electrónico persuasivo, entusiasta y directo dirigido al equipo de Mercadeo que ha tenido baja interacción con los correos de boletines anteriores. El objetivo es motivarlos a leer el nuevo "Boletín de Innovación Corporativa" almacenado en la ruta de OneDrive '/OneDrive/Boletin_Semanal/Boletin_Innovacion.docx'. Menciona brevemente que en dicho documento se detallan tres ventajas clave del uso de Copilot que potenciarán sus campañas publicitarias este trimestre. Agrega un llamado a la acción claro invitándolos a hacer clic en el enlace adjunto y finaliza con un marcador de posición visible para que yo pueda insertar el enlace web dinámico del archivo de OneDrive de forma manual.
```

7. Antes de hacer clic en generar, haz clic en el icono de **Opciones de generación** (icono de ajustes en la barra inferior del diálogo de Copilot) y realiza la siguiente configuración de parámetros:
   - **Tono:** Entusiasta (Enthusiastic).
   - **Longitud:** Media (Medium).
8. Haz clic en el botón **Generar**.
9. Revisa detenidamente el borrador del mensaje generado en pantalla por la inteligencia artificial de Microsoft.
10. Si el texto cumple con tus expectativas de tono profesional, impacto y retención de destinatarios, haz clic en el botón **Mantener** (Keep). De lo contrario, puedes hacer clic en **Volver a redactar** (Regenerate) o modificar las instrucciones refinando el prompt en la caja de diálogo.

**Resultado esperado:** Un correo redactado con un saludo profesional para mercadeo, un cuerpo de mensaje entusiasta sobre la innovación corporativa, la justificación de tres ventajas de Copilot enfocadas en campañas de mercadeo y un marcador de posición explícito (como `[Inserta aquí el enlace al Boletín]`) para vincular el archivo de OneDrive.

**Verificación:** Asegúrate de que el texto no contenga errores gramaticales obvios, que use lenguaje motivador libre de regaños por su inactividad histórica y que muestre claramente el marcador de posición para el enlace.

---

## Validación y Pruebas

Para garantizar que el proceso de distribución y análisis haya cumplido con los estándares requeridos de efectividad, realiza las siguientes actividades de control de calidad:

1. **Prueba de Consistencia de Datos (Excel):**
   - Asegúrate de que no se hayan modificado los datos de otros departamentos (como Ventas o Finanzas). Ninguna fila de Ventas o Finanzas debe tener filtros aplicados o sombreado amarillo.
2. **Prueba de Control de Alucinaciones en Outlook (Supervisión Humana):**
   - Valida que Copilot en Outlook no haya "alucinado" o inventado nombres de productos inexistentes o metas de mercadeo que no formaban parte de tus instrucciones originales. El correo debe mantenerse centrado en "tres ventajas clave de Copilot aplicadas a campañas publicitarias".
3. **Caso Adversario (Prueba de Robustez del Prompt):**
   - *Escenario:* ¿Qué ocurre si un estudiante escribe un prompt vago en Outlook, tal como: `"Escribe un correo sobre el boletín anterior"`?
   - *Acción correctiva:* Copilot generará un correo genérico e inútil sin los enlaces correspondientes ni el tono motivacional requerido. El estudiante debe contrastar este resultado insatisfactorio con la precisión obtenida al usar el mega-prompt estructurado provisto en el Paso 3, constatando la diferencia abismal en calidad del output basado en la ingeniería del prompt.

---

## Solución de Problemas

En caso de encontrar fallas técnicas durante el desarrollo del laboratorio, utiliza la siguiente guía de resolución:

### Problema 1: El icono de Copilot en la barra de Excel se encuentra atenuado (gris) y no responde.
- **Síntoma:** No se puede abrir la barra lateral de Copilot para escribir comandos en Excel.
- **Causa:** El archivo de Excel se guardó de forma local en la máquina, no se encuentra en un directorio sincronizado de OneDrive para la Empresa, o el rango de celdas no está definido explícitamente como una Tabla estructurada con nombre.
- **Solución:** 
  1. Verifica que la barra superior de Excel muestre el indicador de **Autoguardado** en posición "Activado".
  2. Si no es así, ve a **Archivo > Guardar como**, selecciona tu cuenta de almacenamiento de OneDrive de pruebas e ingresa a la ruta `/OneDrive/Boletin_Semanal/`.
  3. Selecciona todo el rango `A1:G9`, presiona `Ctrl + T` para asegurarte de que sea una Tabla formal y vuelve a cargar la aplicación.

### Problema 2: El comando 'Borrador con Copilot' en Outlook muestra el error "No pudimos conectarnos al servicio de Copilot en este momento".
- **Síntoma:** El cuadro flotante de IA se queda cargando indefinidamente o devuelve un mensaje de falla de conexión de red o API.
- **Causa:** Pérdida temporal de autenticación en la sesión del "Nuevo Outlook" o restricciones de seguridad en las directivas de acceso del tenant con la red corporativa de internet actual.
- **Solución:**
  1. Guarda el mensaje actual en borradores, cierra por completo la aplicación Outlook.
  2. Abre Microsoft Edge, ingresa a `outlook.office.com` e inicia sesión con las mismas credenciales.
  3. Ubica el correo en tu carpeta de "Borradores", haz clic en él y abre el menú de asistencia flotante de Copilot para ejecutar el prompt en el navegador Web. Copilot en la web cuenta con un tiempo de espera de conexión (timeout) más tolerante.

---

## Limpieza

Para finalizar las actividades del laboratorio, asegúrate de mantener el orden del entorno siguiendo estos pasos de limpieza:

1. Guarda los cambios del archivo `Metricas_Distribucion.xlsx` en Excel y cierra la aplicación para liberar recursos de memoria del equipo.
2. Si realizaste correos de prueba reales, elimina los correos enviados de tu carpeta de **Elementos enviados** y los borradores sin terminar en la carpeta de **Borradores** de Outlook para prevenir el consumo excesivo de la cuota de almacenamiento del buzón de pruebas.
3. Asegúrate de mantener la estructura e integridad de la carpeta `/OneDrive/Boletin_Semanal/` y el archivo `Boletin_Innovacion.docx`, ya que estos recursos servirán de base directa para los módulos de retroalimentación en laboratorios futuros.

---

## Resumen

En este laboratorio práctico, consolidaste una estrategia automatizada de distribución dirigida. Utilizaste **Copilot en Excel** para analizar, filtrar y segmentar datos planos de comportamiento de lectura, separando rápidamente al público objetivo que requería mayor atención (equipo de mercadeo con bajo engagement). Posteriormente, aprovechaste las bondades de generación lingüística de **Copilot en Outlook** mediante una instrucción estructurada que incorporaba contexto de almacenamiento en la nube, metas funcionales de departamento y configuraciones avanzadas de tono entusiasta. Como instructor técnico, recuerda que el pilar principal de este proceso recae en la **supervisión humana**, la cual refina y asegura que la IA actúe como un acelerador de operaciones sin perder la rigurosidad corporativa.
