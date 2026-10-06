# Práctica: Construir la sesión reutilizable para un boletín semanal

## Metadatos
| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 17 minutos |
| **Complejidad** | Media |
| **Nivel de Bloom** | Aplicar (Apply) |

## Descripción General
En este laboratorio, configurarás una sesión de diseño editorial reutilizable en Microsoft Copilot Notebook (copilot.microsoft.com). Diseñarás un mega-prompt estructurado que defina el rol de redactor de comunicaciones, la audiencia objetivo (departamento de Mercadeo), un tono dinámico pero profesional y tres secciones obligatorias del boletín semanal de comunicaciones internas. Finalmente, realizarás una prueba de adherencia utilizando datos simulados para comprobar que el modelo se ajusta estrictamente a las restricciones de formato, exclusión de información y longitud establecidas.

## Objetivos de Aprendizaje
Al finalizar este laboratorio, serás capaz de:
- [ ] Configurar una sesión de Copilot Notebook estableciendo parámetros estrictos de rol, audiencia, propósito y tono para el departamento de Mercadeo.
- [ ] Diseñar un mega-prompt estructurado y parametrizado con una estructura de salida fija basada en tres secciones obligatorias: Destacados, Campañas en curso, y Fechas clave.
- [ ] Validar la resiliencia del prompt frente a la ausencia de datos simulando condiciones adversas de información incompleta.

## Prerrequisitos
- Comprensión conceptual del diseño de patrones de trabajo reutilizables y la ingeniería de instrucciones (*prompt engineering*).
- Una cuenta corporativa de Microsoft 365 activa con licencia asignada de **Microsoft 365 Copilot Premium (1.0)**.
- Navegador web con acceso a internet sin restricciones de red corporativa para servicios de Microsoft 365.

## Entorno de Laboratorio
Para este laboratorio se requiere la disponibilidad del siguiente software y configuración:

### Hardware Recomendado
- Dispositivo con conexión a Internet (mínimo 10 Mbps de subida y bajada).
- Resolución de pantalla mínima de 1920x1080.

### Software Requerido
| Software / Servicio | Edición / Versión Exacta | Enlace de Origen / Descarga |
| :--- | :--- | :--- |
| **Microsoft Edge** | Canal Estable (Versión 128.0.2739.42, x64) | [Microsoft Edge Enterprise](https://www.microsoft.com/edge/business/download) |
| **Microsoft 365 Copilot Premium** | Licencia Premium Corporativa (Versión 1.0) | [Microsoft Copilot Portal](https://copilot.microsoft.com) |

> **Nota de Configuración**: Para este laboratorio de diseño de prompts, no se requieren archivos físicos externos cargados en OneDrive, ya que utilizaremos datos de control embebidos directamente en la sesión de pruebas.

## Instrucciones Paso a Paso

### Paso 1: Configurar el entorno de Copilot Notebook
**Objetivo**: Acceder a la interfaz de Microsoft Copilot Notebook para habilitar el espacio de trabajo persistente y con mayor capacidad de caracteres en comparación con el chat estándar.

1. Abre tu navegador web **Microsoft Edge** (Versión 128.0.2739.42 o superior).
2. Dirígete a la dirección oficial: [https://copilot.microsoft.com](https://copilot.microsoft.com).
3. Asegúrate de iniciar sesión utilizando tu cuenta corporativa de Microsoft 365. Verifica que en la esquina superior derecha aparezca el logotipo de tu organización y el indicador de protección de datos comerciales (icono de escudo verde/azul).
4. En el menú superior o lateral de la página de inicio de Copilot, selecciona la pestaña **Notebook** (o Bloc de notas). 

   *Nota: A diferencia del chat estándar que fomenta el diálogo inmediato, la interfaz de Notebook de Copilot te permite escribir prompts más largos de hasta 18,000 caracteres a la izquierda y ver el resultado regenerado a la derecha.*

**Resultado esperado**: La interfaz de la pantalla se dividirá en dos paneles principales: a la izquierda, una gran caja de edición de texto editable; a la derecha, un área de visualización de respuestas inicialmente vacía.

**Verificación**: Confirma que en la esquina inferior izquierda del panel de escritura de Notebook se muestre el indicador de conteo de caracteres con un límite máximo extendido (ej. `0 / 18,000`).

---

### Paso 2: Diseñar y estructurar el mega-prompt maestro
**Objetivo**: Redactar de forma estructurada las instrucciones del mega-prompt de diseño editorial, estableciendo el rol del redactor, los límites temáticos de la audiencia de Mercadeo y el formato rígido del boletín.

1. Copia exactamente el siguiente bloque de texto diseñado con arquitectura de instrucción estructurada:

```text
## ROL Y CONTEXTO
Actúa como un Redactor Senior de Comunicaciones Internas para el departamento de Mercadeo. Tu labor consiste en consolidar la información cruda entregada y adaptarla para que los empleados consuman novedades clave rápidamente.

## VARIABLES DE CONFIGURACIÓN
- AUDIENCIA: Empleados, colaboradores y directores del departamento de Mercadeo Corporativo.
- TONO: Profesional, dinámico, moderno y orientado a la acción (evita el uso de voz pasiva y clichés corporativos excesivos).
- CANAL: Formato optimizado para cuerpo de correo electrónico interno de Outlook.

## ESTRUCTURA DE SALIDA REQUERIDA
Produce la salida final utilizando estrictamente el siguiente formato de Markdown estructurado:

## 🌟 Destacados de la Semana
- [Resumen ejecutivo en un máximo de 2 oraciones del hito o noticia principal de la semana]

## 📢 Campañas en Curso
- **[Nombre de Campaña 1]**: [Descripción resumida de estado o logro en una frase, máximo 15 palabras]
- **[Nombre de Campaña 2]**: [Descripción resumida de estado o logro en una frase, máximo 15 palabras]
- **[Nombre de Campaña 3]**: [Descripción resumida de estado o logro en una frase, máximo 15 palabras]

## 📅 Fechas Clave y Próximos Pasos
1. **[Acción 1]** - Responsable: [Nombre o Rol] - Fecha límite: [Fecha exacta o rango temporal]
2. **[Acción 2]** - Responsable: [Nombre o Rol] - Fecha límite: [Fecha exacta o rango temporal]

---
## CRITERIOS DE VALIDACIÓN Y CONTROL DE CALIDAD (RESTRICCIONES):
- Si las fuentes no suministran información suficiente para rellenar alguna de las subsecciones indicadas en "ESTRUCTURA DE SALIDA REQUERIDA", no debes inventar datos bajo ninguna circunstancia. En su lugar, escribe textualmente "[Información no disponible en las fuentes]".
- Mantén la extensión total de la respuesta por debajo de las 200 palabras.
- No incluyas nombres de clientes externos o información financiera confidencial.
```

2. Pega este texto en el panel izquierdo de **Copilot Notebook**. No presiones "Enviar" (*Submit*) todavía.

**Resultado esperado**: El mega-prompt completo con su configuración de rol, variables de control, plantilla de estructura de salida en Markdown y reglas rígidas de validación queda visible en la zona de edición izquierda.

**Verificación**: Comprueba visualmente que el prompt incluya los tres encabezados H2 específicos de salida (`## 🌟 Destacados de la Semana`, `## 📢 Campañas en Curso` y `## 📅 Fechas Clave y Próximos Pasos`).

---

### Paso 3: Probar el prompt con datos simulados
**Objetivo**: Validar el comportamiento de la plantilla de instrucciones alimentándolo con datos de entrada específicos sin salir del contexto de Notebook.

1. En el mismo panel de edición izquierdo, baja un par de líneas después de la palabra final del mega-prompt y escribe una línea divisoria `---`.
2. Justo debajo de la línea divisoria, pega el siguiente bloque de datos de entrada simulados (con información dispersa y desordenada):

```text
DATOS DE ENTRADA PROPORCIONADOS PARA EL BOLETÍN:
- La campaña "Rebajas de Otoño" cerró con un incremento de conversiones del 12% con respecto al año anterior. Todo el equipo de diseño está muy feliz por el resultado.
- Juan Pérez del equipo de analítica necesita que todos aprueben los KPIs del Q4 antes del viernes 10 de noviembre.
- Para la campaña "Lanzamiento Eco-Moda", ya se entregó el borrador del copy publicitario para redes sociales, pero aún estamos esperando la aprobación final de presupuesto por parte del corporativo.
- Se ha programado la reunión de alineación con la agencia de relaciones públicas el miércoles 8 de noviembre a las 3:00 PM. Estará liderada por la Gerente de Marketing Comercial.
```

3. Presiona el botón **Enviar** (icono de flecha o botón de ejecución) ubicado en la esquina inferior derecha del panel izquierdo del Notebook.
4. Observa cómo Copilot procesa los datos en tiempo real y despliega la respuesta en el panel de resultados de la derecha.

**Resultado esperado**: Un boletín perfectamente estructurado en Markdown que consolida los datos crudos en las tres secciones de la plantilla, respetando el tono dinámico corporativo de mercadeo.

**Verificación**: Asegúrate de que en el panel derecho se muestre una estructura similar a la siguiente:
* Un primer apartado destacando el éxito de la campaña "Rebajas de Otoño" (12% más de conversión).
* Una sección con dos viñetas destacando las campañas "Rebajas de Otoño" y "Lanzamiento Eco-Moda".
* Una sección numerada para fechas clave que relacione la aprobación de KPIs por Juan Pérez (vence el 10 de noviembre) y la reunión con la agencia de PR (liderada por la Gerente el 8 de noviembre).

---

## Validación y Pruebas
Para confirmar que tu plantilla/prompt de sesión reutilizable cumple con los estrictos criterios de calidad requeridos antes de aplicarla a información corporativa real, debes realizar una prueba adversaria para verificar el comportamiento ante datos incompletos.

### Ejecución de Prueba Adversaria (Límite de la IA)
1. Modifica la sección de datos en el panel izquierdo del Notebook, eliminando por completo cualquier mención a fechas, tareas asignadas y responsables. Reemplaza el bloque final de datos por este texto:

```text
DATOS DE ENTRADA PROPORCIONADOS PARA EL BOLETÍN:
- Se reporta que la campaña "Branding 2025" ha iniciado su fase de investigación de mercado de manera exitosa.
- El equipo técnico finalizó la migración del panel de control web interno, mejorando la velocidad de carga de reportes.
```

2. Presiona de nuevo el botón **Enviar**.
3. Revisa la salida generada en el panel derecho.

### Criterio de Aceptación Medible
La prueba se considera **Aprobada** si el boletín resultante cumple estrictamente con el siguiente comportamiento:
- La sección `## 📅 Fechas Clave y Próximos Pasos` debe mostrar de forma explícita e inequívoca el texto **`[Información no disponible en las fuentes]`** o un equivalente directo, en lugar de alucinar fechas futuras o inventar reuniones de migración.
- El boletín mantiene la separación de las tres secciones definidas con sus iconos de Markdown originales.
- La extensión total de la respuesta no excede las 200 palabras.

---

## Solución de Problemas

### Problema 1: El texto se genera mezclando idiomas (Inglés / Español)
* **Síntoma**: Los títulos estructurados cambian de "Destacados de la Semana" a "Weekly Highlights", o el resumen ejecutivo incluye términos y transiciones no solicitadas en inglés.
* **Causa**: Al procesar fragmentos o código estructurado de Markdown, el modelo de Copilot puede verse influenciado por la configuración de idioma local de tu sistema operativo o del explorador de Edge.
* **Solución**: Añade una instrucción explícita al final de la sección `# VARIABLES DE CONFIGURACIÓN` del prompt maestro en el panel izquierdo: 
  `- IDIOMA OBLIGATORIO: Redacta la salida final exclusivamente en Español Neutro.`

### Problema 2: El diseño de doble panel "Notebook" no aparece disponible
* **Síntoma**: Solo se visualiza la clásica interfaz de conversación de Copilot con la limitación tradicional de caracteres, y sin el espacio de edición persistente.
* **Causa**: No se ha iniciado sesión con la cuenta de Microsoft 365 que contiene la licencia Premium asignada, o tu organización tiene deshabilitada temporalmente la interfaz de Notebook mediante políticas de inquilino (*tenant*).
* **Solución**: 
  1. Haz clic en tu foto de perfil en la esquina superior derecha de la web de Copilot y confirma que estás usando tu cuenta corporativa.
  2. Si el enlace superior no se muestra, introduce manualmente la URL directa en el navegador: [https://copilot.microsoft.com/?dp=notebook](https://copilot.microsoft.com/?dp=notebook).
  3. Si la URL te redirige al chat tradicional, contacta al administrador de TI para confirmar el estado de tu licencia de **Microsoft 365 Copilot Premium (1.0)**.

---

## Limpieza
Para preparar el entorno de cara a los siguientes laboratorios de integración:

1. Selecciona todo el texto de tu mega-prompt refinado en el panel izquierdo del Notebook, cópialo y pégalo en un documento local de bloc de notas (`boletin_maestro_prompt.txt`) o una nota de OneNote corporativa. Lo requerirás para cruzar fuentes de datos en los siguientes módulos.
2. Haz clic en el botón **Nuevo tema** (o icono de papelera / escoba de limpieza en la parte inferior del panel) para borrar el historial de la sesión del Notebook y restaurar el contador de caracteres a `0`.

---

## Resumen
En este laboratorio has configurado un patrón de trabajo estructurado y reutilizable de nivel profesional utilizando Microsoft Copilot Notebook. 

### Conceptos Clave Consolidados:
- **Patrón Reutilizable vs. Chat Improvisado**: El uso del Notebook permite que definas un marco conceptual (rol, audiencia de mercadeo, exclusiones y formato) que sirve de plantilla repetible reduciendo el tiempo de preparación semanal.
- **Formateo mediante Markdown**: Forzar al modelo a estructurar salidas con títulos predefinidos disminuye drásticamente el retrabajo de edición manual de texto en aplicaciones de destino como Outlook o Word.
- **Mitigación Activa de Alucinaciones**: El uso de instrucciones negativas explícitas (Negative Prompting), como inyectar la regla de "Información no disponible", previene que la IA invente plazos, responsables o datos de mercadeo críticos cuando las fuentes son incompletas.
