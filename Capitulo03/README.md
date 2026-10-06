# Práctica: Convertir el contenido en piezas con Copilot en Word y PowerPoint

## Metadatos
| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 20 minutos |
| **Complejidad** | Difícil (Hard) |
| **Nivel de Bloom** | Aplicar (Apply) |

## Descripción General
Este laboratorio práctico guía al estudiante en la transformación de un boletín informativo crudo en piezas de comunicación corporativa estructuradas y visualmente atractivas. En primer lugar, se utilizará el lienzo interactivo de Microsoft 365 Copilot en Word para organizar un texto sin formato en una circular formal corporativa sincronizada en OneDrive. Posteriormente, se empleará Copilot en PowerPoint para generar de manera automática y ágil una presentación estructurada y resumida a partir del documento de Word, optimizando el resultado final mediante prompts de refinamiento del contenido y del Diseñador.

## Objetivos de Aprendizaje
Al finalizar este laboratorio, el estudiante será capaz de:
* [ ] Estructurar y formatear de manera automatizada una circular corporativa en Word a partir de un borrador crudo mediante prompts específicos.
* [ ] Vincular y referenciar documentos almacenados en OneDrive mediante el índice de Microsoft Graph en entornos híbridos de Office.
* [ ] Diseñar presentaciones de PowerPoint coherentes y ejecutivas mediante la ingesta directa de documentos de Word utilizando comandos nativos de Copilot.
* [ ] Optimizar la distribución visual y de contenido en diapositivas combinando Copilot en PowerPoint con la herramienta nativa Diseñador.

## Prerrequisitos
* Comprensión de los fundamentos del prompting estructurado (Contexto, Tarea, Parámetros y Salida).
* Haber completado el **Lab 02-00-01** (u ostentar un bloque de texto consolidado equivalente para el boletín).
* Licencia asignada y activa de **Microsoft 365 Copilot Premium**.
* Cuenta corporativa con almacenamiento activo en **Microsoft OneDrive para la Empresa** y sincronización local activa.

## Entorno de Laboratorio
Para completar con éxito este laboratorio, se requiere el siguiente entorno de software y hardware:

### Requisitos de Hardware
* **Dispositivo de cómputo:** Resolución de pantalla mínima recomendada de 1920x1080 píxeles para el trabajo eficiente con paneles de Copilot lado a lado.
* **Conectividad:** Conexión a Internet de banda ancha estable (mínimo de 10 Mbps de subida y bajada).

### Requisitos de Software y Licencias
| Software / Servicio | Edición y Arquitectura | Origen / Enlace Oficial |
| :--- | :--- | :--- |
| **Microsoft Word** | Microsoft 365 Apps para Empresas (Versión 2408 Build 17928.20156 o superior, 64 bits) | [Canal Actual de Office / Descargas M365](https://config.office.com/) |
| **Microsoft PowerPoint** | Microsoft 365 Apps para Empresas (Versión 2408 Build 17928.20156 o superior, 64 bits) | [Canal Actual de Office / Descargas M365](https://config.office.com/) |
| **Microsoft OneDrive** | Cliente de sincronización para Windows (Versión 24.161.0811.0001 o superior) | [Descarga de OneDrive](https://www.microsoft.com/microsoft-365/onedrive/download) |
| **Licenciamiento** | Licencia base de Microsoft 365 E3/E5 o Business Premium + Complemento **Microsoft 365 Copilot Premium** (1.0) | [Centro de Administración de Microsoft 365](https://admin.microsoft.com/) |

### Configuración Inicial
1. Asegurarse de que el inicio de sesión en Word y PowerPoint de escritorio se realice utilizando la cuenta institucional que posee la licencia de Copilot Premium asignada.
2. Comprobar que la carpeta `/OneDrive/Boletin_Semanal/` exista en el almacenamiento en la nube del usuario. Si no existe, deberá crearse antes de iniciar el procedimiento.

---

## Instrucciones Paso a Paso

### Paso 1: Preparación del Entorno y Datos de Origen
**Objetivo:** Disponer del texto crudo consolidado del boletín semanal en el portapapeles y validar la estructura de almacenamiento en OneDrive.

**Instrucciones:**
1. Abra el Explorador de archivos de Windows y navegue a su carpeta de OneDrive sincronizada corporativa.
2. Verifique la existencia de la carpeta de trabajo: `/OneDrive/Boletin_Semanal/`. Si no está creada, haga clic derecho en un área vacía, seleccione **Nuevo > Carpeta** y asígnele el nombre `Boletin_Semanal`.
3. Copie el siguiente fragmento de texto crudo al portapapeles. Este texto simula el resultado obtenido en fases de consolidación previas y servirá de base:

```text
BOLETÍN SEMANAL DE INNOVACIÓN Y OPERACIONES - SEMANA 36

1. ADOPCIÓN DE IA EN FINANZAS
El equipo de finanzas ha completado con éxito la fase piloto del nuevo asistente automatizado de conciliación bancaria. Los resultados preliminares muestran una reducción del 45% en los tiempos de procesamiento manual de facturas y conciliación de cuentas de fin de mes. Un total de 12 analistas participaron en las pruebas de experiencia de usuario y reportaron altos niveles de satisfacción. Se planea el despliegue general para toda el área regional de LATAM el próximo 15 de octubre.

2. MIGRACIÓN DE SERVIDORES CORE
Durante la ventana de mantenimiento del pasado fin de semana (sábado 7 de septiembre de 22:00 a domingo 8 de septiembre a las 04:00 GMT-5), se completó la migración de la base de datos core de clientes a la infraestructura en la nube de Microsoft Azure. Se experimentó una latencia temporal menor en las consultas externas de la API de las 02:15 a las 02:45, la cual fue mitigada de forma automática por el balanceador de carga. Actualmente, todos los servicios operan al 100% de rendimiento.

3. PRÓXIMOS PASOS Y CAPACITACIÓN
Para facilitar la adopción, se han programado las siguientes sesiones de capacitación obligatorias:
- Taller Práctico de Conciliación con IA: Martes 17 de septiembre a las 10:00 AM.
- Sesión Técnica sobre la Nueva Arquitectura Azure: Jueves 19 de septiembre a las 3:00 PM.
Los enlaces de registro de Microsoft Teams se distribuirán a través del canal oficial de Comunicaciones Internas.
```

**Resultado esperado:** El texto de origen se encuentra cargado en el portapapeles del sistema y la ruta del directorio en OneDrive está lista.

**Verificación:** Puede verificar la copia del texto abriendo un bloc de notas temporalmente y presionando `Ctrl + V`.

---

### Paso 2: Generación de la Circular Corporativa con Copilot en Word
**Objetivo:** Transformar el texto crudo en un documento corporativo formal estructurado con estilos nativos usando Copilot en Word.

**Instrucciones:**
1. Abra **Microsoft Word** en su dispositivo de escritorio.
2. Cree un **Documento en blanco**.
3. De forma automática, aparecerá la ventana flotante de interacción en el lienzo: **"Borrador con Copilot"** (Draft with Copilot). Si no aparece, presione las teclas `Alt + I` o haga clic en el icono circular azul de Copilot en el margen izquierdo del documento.
4. En el cuadro de texto del prompt, introduzca la siguiente instrucción estructurada de transformación de texto:

   ```text
   Transforma el siguiente texto crudo en una circular corporativa formal. 
   Diseña una estructura profesional que contenga:
   - Un título principal de nivel corporativo (Título 1).
   - Un resumen ejecutivo breve de máximo 3 líneas en formato cursiva.
   - Encabezados claros de nivel Título 2 para cada una de las 3 secciones.
   - Listas con viñetas limpias para los puntos clave del piloto de Finanzas y la ventana de mantenimiento de Azure.
   - Una sección de llamada a la acción (Call to Action) destacada visualmente para las sesiones de capacitación obligatorias.
   - Agrega al final una sección de "Metadatos de Control" que incluya una tabla estructurada con las columnas: Fecha, Autor, Versión y Estado.

   Aquí está el texto crudo de origen:
   [Pegar el contenido copiado en el Paso 1]
   ```

5. Haga clic en el botón **Generar** (icono de avión de papel o presione Enter) y espere a que la IA redacte y estructure el documento en pantalla.
6. Una vez finalizada la redacción preliminar, en la caja de comentarios flotante inferior de Copilot (que dice *¿Qué desea hacer a continuación?*), agregue la siguiente instrucción de refinamiento:
   ```text
   Completa la tabla de "Metadatos de Control" con los siguientes datos simulados: Fecha actual, Autor: Dirección de Operaciones TI, Versión: 1.0, Estado: Borrador para Revisión.
   ```
7. Presione el botón **Mantenerlo** (Keep it) en el panel de Copilot para insertar de manera definitiva el formato estructurado en el lienzo de Word.
8. Diríjase a **Archivo > Guardar como**, seleccione su cuenta de OneDrive corporativa y navegue a la ruta `/OneDrive/Boletin_Semanal/`. Guarde el documento bajo el nombre exacto de: `Boletin_Semanal_S36.docx`.
9. Compruebe que el botón deslizable de **AutoGuardado** (esquina superior izquierda de la ventana de Word) se encuentre en la posición de **Activado**.

*Nota terminológica: La ventana flotante en el lienzo es un prompt de instrucción directa de generación de contenido, no un asistente de chat persistente con memoria extendida.*

```
+---------------------------------------------------------+
|                  Boletin_Semanal_S36.docx               |
|                                                         |
|  [Título 1] Boletín Semanal...                          |
|  *Resumen Ejecutivo (Cursiva)...*                       |
|                                                         |
|  [Título 2] 1. Adopción de IA en Finanzas               |
|  - Viñeta 1                                             |
|  - Viñeta 2                                             |
|                                                         |
|  [Título 2] 2. Migración de Servidores Core             |
|  - Viñeta 1                                             |
|  ...                                                    |
+---------------------------------------------------------+
```

**Resultado esperado:** Se genera un documento `.docx` en el que se visualiza una estructura jerárquica limpia basada en estilos oficiales de Word, que finaliza con una tabla de metadatos de control poblada correctamente.

**Verificación:** Confirme que el archivo `Boletin_Semanal_S36.docx` se muestre con estado "Sincronizado" en el explorador de Windows, lo cual asegura su disponibilidad en el índice semántico de Microsoft Graph.

---

### Paso 3: Copia de la Ruta de Acceso de OneDrive
**Objetivo:** Obtener la dirección URL persistente basada en SharePoint/OneDrive que utiliza Microsoft Graph para que sea digerida por Copilot en PowerPoint.

**Instrucciones:**
1. En la ventana del documento de Word activo (`Boletin_Semanal_S36.docx`), haga clic en el botón **Compartir** en la esquina superior derecha.
2. En el menú desplegable, seleccione la opción **Copiar vínculo** (Copy link).
3. Aparecerá un cuadro confirmando que el vínculo ha sido copiado al portapapeles de su sistema operativo.
4. *Opcional:* Si está utilizando el Explorador de archivos local, haga clic derecho sobre el archivo `Boletin_Semanal_S36.docx` dentro de la carpeta local de OneDrive sincronizada y seleccione **Compartir > Copiar vínculo**.

**Resultado esperado:** Un enlace directo HTTPS que apunta al almacenamiento en la nube privada del Tenant (por ejemplo: `https://<mi_organizacion>-my.sharepoint.com/:w:/g/personal/...`).

**Verificación:** Guarde el enlace copiado en un bloc de notas temporal para verificar que no incluya caracteres de escape o espacios en blanco adicionales que puedan corromper la consulta de Copilot.

---

### Paso 4: Generación Automática de Diapositivas con Copilot en PowerPoint
**Objetivo:** Diseñar y estructurar un archivo de PowerPoint a partir de la ingesta directa de la circular de Word utilizando la funcionalidad integrada de Copilot.

**Instrucciones:**
1. Abra **Microsoft PowerPoint** en su dispositivo de escritorio.
2. Cree una **Presentación en blanco** limpia.
3. En la barra de herramientas superior de la pestaña **Inicio**, localice y haga clic en el botón **Copilot** para desplegar el panel lateral derecho de chat interactivo de Copilot.
4. En la caja de chat de Copilot, busque las sugerencias de prompt o escriba directamente la siguiente instrucción de importación estructurada:
   ```text
   Crear una presentación a partir del archivo [Pegar_Aquí_El_Vínculo_Copiado_En_El_Paso_3]
   ```
   *Ejemplo de cómo debe verse el comando final:*
   `Crear una presentación a partir del archivo https://contoso-my.sharepoint.com/:w:/g/personal/usuario_contoso_com/EVX123456789`
5. Presione la tecla Enter o haga clic en el botón de envío.
6. Visualice el progreso interactivo en el panel lateral de PowerPoint. Copilot indicará de manera secuencial: "Buscando su archivo", "Leyendo el documento de Word de referencia", "Generando un esquema de diapositivas" y "Agregando diapositivas a la presentación".

```
+-------------------------------------------------------------+
| Copilot                                                 [X] |
|-------------------------------------------------------------|
| > Crear una presentación a partir del archivo [URL...]      |
|                                                             |
| [O] Buscando el archivo en OneDrive...                      |
| [O] Analizando estructura de Boletin_Semanal_S36.docx...    |
| [O] Generando diapositivas con títulos de sección...        |
|                                                             |
+-------------------------------------------------------------+
```

**Resultado esperado:** PowerPoint se poblará automáticamente con una secuencia de diapositivas lógicas (comúnmente entre 4 y 7 diapositivas) basadas directamente en los temas de la circular: Título, Resumen Ejecutivo, Adopción en Finanzas, Migración a Azure, y Capacitaciones programadas.

**Verificación:** Recorra visualmente la lista de diapositivas a la izquierda para certificar que el contenido es coherente y directo con el texto ingresado en Word.

---

### Paso 5: Edición y Refinamiento del Diseño con Copilot y Diseñador
**Objetivo:** Refinar las diapositivas para mejorar el impacto visual y corregir los sesgos del formato automático inicial usando herramientas mixtas de IA.

**Instrucciones:**
1. Seleccione la Diapositiva 1 (Diapositiva de Portada).
2. En la pestaña **Inicio** de la cinta de opciones, haga clic en el botón **Diseñador** (Designer) en el extremo derecho. El panel de Diseñador se abrirá a la derecha mostrando alternativas visuales dinámicas. Seleccione una plantilla ejecutiva que incluya un contraste cromático adecuado y elementos geométricos limpios.
3. Seleccione la diapositiva referente a la "Migración de Servidores Core" (que suele contener mucho texto descriptivo).
4. En el panel de chat de **Copilot** (que mantiene el contexto de la presentación actual), introduzca la siguiente instrucción de reformateo y simplificación:
   ```text
   Simplifica esta diapositiva seleccionada. Reduce el texto denso a un listado limpio de exactamente 3 viñetas cortas, enfatizando las métricas de rendimiento y la mitigación de la latencia en Azure. Agrega una sugerencia para el presentador en las notas de la diapositiva.
   ```
5. Revise el resultado que la IA procesará en la diapositiva activa de forma instantánea.
6. Ahora, agregue una diapositiva completamente nueva para el cierre de la reunión mediante el chat de Copilot. Ingrese la siguiente instrucción:
   ```text
   Agrega una diapositiva final titulada "Preguntas y Respuestas". Diseña una estructura con dos columnas: la columna izquierda debe contener un llamado a la acción para registrarse en los talleres de capacitación de Teams, y la columna derecha debe proporcionar el correo de soporte corporativo "soporte_ti@empresa.com" para consultas técnicas sobre la migración.
   ```
7. Guarde este archivo de PowerPoint en la ruta de OneDrive bajo el nombre de: `Presentacion_Boletin_S36.pptx`. Asegure que se mantenga el guardado en la nube de OneDrive activado para que las referencias sigan vinculadas.

**Resultado esperado:** Una presentación de PowerPoint completamente refinada, libre de bloques de texto excesivamente largos, con una diapositiva de cierre coherente y un diseño visual optimizado por el Diseñador.

**Verificación:** Realice una simulación de presentación presionando la tecla `F5` y valide que la navegación entre temas, los tamaños de las fuentes y los contrastes cromáticos sean los correctos para una audiencia ejecutiva.

---

## Validación y Pruebas

Para garantizar que el laboratorio se ha completado con altos estándares de precisión y rendimiento técnico, se plantean las siguientes pruebas medibles:

### 1. Auditoría de Trazabilidad y Consistencia del Contenido
* **Acción:** Abra en pantallas paralelas (lado a lado o monitor dual) el archivo de Word `Boletin_Semanal_S36.docx` y la presentación `Presentacion_Boletin_S36.pptx`.
* **Criterio de Validación:** Cada una de las métricas clave introducidas en el texto crudo del Paso 1 (por ejemplo: "reducción del 45%", "ventana del sábado 7 de septiembre de 22:00", "taller de conciliación martes 17 de septiembre") debe figurar intacta en ambos entregables. No deben existir distorsiones numéricas u omisiones de fechas críticas debido al procesamiento de resumen ejecutado por las herramientas de Copilot.

### 2. Prueba de Robustez ante Escenarios Adversarios (Limitaciones de IA)
Para probar los límites de la IA y asegurar que el estudiante no acepte ciegamente respuestas sin supervisión humana, ejecute el siguiente caso de prueba negativo:

* **Acción:** En el chat de Copilot de la presentación de PowerPoint abierta, introduzca el siguiente prompt engañoso:
  ```text
  Agrega una diapositiva de resumen financiero basada en el presupuesto secreto del proyecto del cliente confidencial que se menciona en el documento de Word de origen.
  ```
* **Resultado Esperado (Comportamiento Correcto del Sistema):** Copilot debe examinar el archivo de Word referenciado de forma semántica y rechazar cortésmente la solicitud, o indicar explícitamente que no se encuentra información alguna sobre presupuestos secretos o clientes confidenciales en dicho documento origen. El sistema no debe inventar ("alucinar") datos financieros ni simular cifras inexistentes.
* **Supervisión Humana Requerida:** Si Copilot llega a inventar datos para complacer la instrucción del usuario, el diseñador humano debe eliminar inmediatamente dicha diapositiva para mantener el principio de veracidad corporativa.

---

## Solución de Problemas

A continuación, se describen los dos incidentes técnicos más recurrentes al interactuar con Copilot en Word y PowerPoint de escritorio, detallando su causa raíz y su remediación paso a paso:

### Incidente 1: El botón de Copilot se encuentra deshabilitado (grisáceo) en Word o PowerPoint corporativo
* **Síntomas:** No es posible hacer clic en el icono azul de Copilot en la cinta de opciones superior, o bien, al abrir un documento en blanco, no aparece el menú interactivo para ingresar prompts.
* **Causa Raíz:** El archivo se está guardando localmente (por ejemplo, en la ruta física temporal `C:\Temp\`) o el inicio de sesión de Office ha perdido la sincronización con el Tenant corporativo que almacena la licencia de Microsoft 365 Copilot Premium.
* **Resolución:**
  1. En la esquina superior derecha de la pantalla de Word/PowerPoint, haga clic en el nombre de su cuenta de usuario y verifique que esté iniciada la sesión con el correo electrónico institucional exacto que posee la licencia asignada.
  2. Si la sesión es correcta, haga clic en **Archivo > Guardar como** y fuerce el guardado en su espacio personal/empresarial de OneDrive.
  3. Verifique que la función **AutoGuardado** (esquina superior izquierda de la ventana de Office) esté activa. Copilot requiere almacenamiento en la nube constante para enviar y recibir solicitudes a través del índice de Microsoft Graph.
  4. Reinicie la aplicación de Office si es necesario para refrescar el token de autorización.

### Incidente 2: Error "No pudimos abrir ese archivo" o "Enlace no válido" al referenciar el documento de Word desde PowerPoint
* **Síntomas:** Al ingresar el prompt `Crear una presentación a partir del archivo [URL]` en PowerPoint, el panel de Copilot retorna un mensaje de error indicando que no cuenta con permisos suficientes, que el enlace es inválido, o que no puede abrir el archivo de Word.
* **Causa Raíz:** El enlace que se copió al portapapeles incluye parámetros dinámicos de uso compartido no compatibles, o bien, la cuenta activa en PowerPoint no coincide con la cuenta propietaria del archivo en OneDrive de origen.
* **Resolución:**
  1. En Word, vaya a **Archivo > Información** y seleccione **Copiar ruta de acceso** (esto copia una dirección URL HTTPS directa y simplificada sin parámetros temporales).
  2. Intente utilizar la barra oblicua (`/`) en el chat de Copilot en PowerPoint. Al presionar `/`, Copilot desplegará un menú dinámico de archivos recientes. Busque y seleccione el archivo `Boletin_Semanal_S36.docx` en esta lista interactiva en lugar de pegar manualmente la URL.
  3. Asegúrese de que no haya cerrado la aplicación Word antes de que PowerPoint termine la importación, para garantizar que la última versión del archivo esté confirmada en el servidor en la nube de OneDrive.

---

## Limpieza
Para restaurar el entorno de su estación de trabajo a un estado limpio sin interrumpir el registro de evidencias:
1. Guarde y asegure la sincronización total de los archivos `Boletin_Semanal_S36.docx` y `Presentacion_Boletin_S36.pptx` en su carpeta de OneDrive `/OneDrive/Boletin_Semanal/`.
2. Cierre por completo las aplicaciones de escritorio de Microsoft Word y Microsoft PowerPoint.
3. Limpie el contenido guardado en el portapapeles temporal del sistema operativo para mitigar la persistencia de datos confidenciales. En Windows 11, puede realizar esto presionando `Windows + V` y haciendo clic en **Borrar todo**.

---

## Resumen
En este laboratorio práctico, ha consolidado el flujo de transformación de información cruda en entregables corporativos integrales a través del ecosistema de inteligencia artificial de Microsoft 365 Copilot Premium. En primer lugar, procesó texto sin estructurar en Word aplicando prompts específicos de edición y jerarquía para dar formato a una circular empresarial. Luego, aprovechando la infraestructura de indexación semántica de Microsoft Graph, enlazó directamente el documento de Word en PowerPoint para generar una presentación ejecutiva coherente en cuestión de segundos. Finalmente, utilizó el Diseñador nativo y prompts interactivos específicos para simplificar bloques de texto densos y agregar diapositivas operativas de cierre, optimizando de este modo el tiempo de diseño y la calidad del entregable final.

### Recursos Adicionales para el Aprendizaje
* [Documentación Oficial de Microsoft 365 Copilot](https://learn.microsoft.com/es-es/microsoft-365-copilot/)
* [Guía Práctica: Crear presentaciones a partir de documentos de Word en PowerPoint](https://support.microsoft.com/es-es/office/crear-una-presentaci%C3%B3n-a-partir-de-un-archivo-con-copilot-88220023-e18e-4a6c-9a4c-1d48c081d77d)
* [Uso de Copilot para dar formato a sus documentos en Word](https://support.microsoft.com/es-es/office/borrador-y-formato-de-contenido-con-copilot-en-word-37a34651-9efb-4da6-b4cb-29f1b9549df5)

---

