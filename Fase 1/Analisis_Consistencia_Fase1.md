# Análisis de consistencia — Fase 1 (CRM Easy Office)

Revisión cruzada de los 12 documentos de la carpeta "Fase 1" (Informe grupal 1.4, Guía del Estudiante 1.5, Presentación de Proyecto, y las autoevaluaciones/diarios individuales 1.1, 1.2 y 1.3 de Diego Navarrete, Andrés Fernández y Dunkan Hernández).

Como pidieron las instrucciones del proyecto, esto no es una validación de que "todo está bien": es un listado de contradicciones reales entre documentos, para que el equipo decida cuál versión es la correcta y la deje igual en todos lados antes de avanzar a Fase 2.

## 1. Inconsistencias detectadas

### 1.1 El alcance del problema no es el mismo en todos los documentos
El **Informe grupal (1.4)** y la **Guía del Estudiante (1.5)** — que son los documentos formales de definición — describen el problema únicamente como gestión **documental** manual (contratos y autorización de domicilio tributario armados y firmados a mano).

La **Presentación**, en cambio, describe un problema mucho más amplio que no aparece en ningún documento de definición: venta y seguimiento por WhatsApp sin flujo digital único, ausencia total de trazabilidad de ejecutivos, falta de seguridad/control de acceso a los datos, y cobranza manual. La autoevaluación de **Dunkan (1.3)** también menciona de pasada que la gestión hoy es "principalmente por vía WhatsApp", dato que tampoco está en el Informe ni en la Guía.

Esto importa porque el Informe de Inicio de Proyecto es, en teoría, la fuente de verdad del alcance — y ahí el problema de WhatsApp/venta/trazabilidad simplemente no existe. Si el problema real es más amplio que "generar y firmar dos documentos", el documento formal debería decirlo explícitamente.

### 1.2 El objetivo general tiene dos versiones distintas circulando
- **Versión A** (Informe grupal 1.4, Guía 1.5, y la autoevaluación de **Diego** 1.3): *"Digitalizar y automatizar la generación, firma y entrega de documentos de Easy Office con un CRM que reduzca errores, achique los tiempos de gestión..."*
- **Versión B** (Presentación, autoevaluación de **Andrés** 1.3, autoevaluación de **Dunkan** 1.3): *"Diseñar e implementar un ecosistema digital (CRM) que centralice la gestión de clientes... y **automatice la venta**, la generación y firma electrónica de documentos, y el seguimiento operativo."*

Dos de los tres integrantes (Andrés y Dunkan) y la presentación oficial ya están usando una versión ampliada del objetivo (que incluye "automatizar la venta") que el documento formal de definición (firmado por los tres) no contiene, y que el propio líder del proyecto (Diego) no usa en su autoevaluación individual.

### 1.3 Aparece un módulo de venta/pago en línea que no está en el alcance del MVP acordado
El Informe grupal (sección 7, "Alcance del MVP") es explícito: el sistema "permite registrar los datos del cliente, generar ambos documentos... enviarlos a firma... y dejar registro del estado", y aclara que quedan **fuera** de esta primera versión "otros tipos de documentos, la automatización completa de creación de empresas, y un chatbot con IA". No menciona pagos en línea en ningún punto.

Sin embargo:
- La Presentación (slide 7, "Prototipo inicial: flujo de compra") incluye un paso explícito de **"Pagar — Pago en línea seguro"**.
- La autoevaluación de **Andrés** (1.3) describe a Diego desarrollando "la interfaz del CRM **y del e-commerce** de compra/firma de documentos" y a Dunkan desarrollando "el frontend del CRM **y del e-commerce**".

Un módulo de e-commerce/pago en línea es una funcionalidad no menor (pasarela de pago, conciliación, seguridad de transacciones) que **no fue acordada con el cliente según el propio Informe de Inicio**, y contradice directamente el listado de "lo que queda fuera del MVP". Si esto sí se conversó con Easy Office, el Informe de Inicio debería actualizarse; si no se conversó, hay que sacarlo de la Presentación y de las autoevaluaciones antes de que el equipo empiece a construirlo.

### 1.4 Los roles del equipo se contradicen entre documentos
| Documento | Diego | Andrés | Dunkan |
|---|---|---|---|
| Informe grupal (1.4) / Guía (1.5) | Líder, contacto con cliente, levantamiento | Documentación formal | Apoya en pruebas y desarrollo |
| Presentación (slide 8) | Líder + Desarrollo Backend + interfaz del e-commerce | Levantamiento documental, valida criterios de aceptación | QA – Desarrollo Frontend |
| Autoeval. Andrés (1.3) | Backend, contacto con cliente | **"Mi rol es QA y levantamiento documental"**: coordina levantamiento, **define y ejecuta el plan de pruebas**, valida criterios de aceptación | Frontend + e-commerce, apoya en pruebas |
| Autoeval. Dunkan (1.3) | Lidera, contacto con cliente, backend | Documentación formal y evidencias | **"Mi rol principal es desarrollo, QA y DBA"**: mantiene las pruebas del proyecto y el modelo de datos |

Hay dos problemas concretos aquí:
- **Andrés y Dunkan se atribuyen el mismo rol de QA** ("definir y ejecutar el plan de pruebas") en sus respectivos documentos individuales, mientras el Informe grupal solo asigna pruebas a Dunkan.
- Nadie en el Informe grupal ni en la Guía asigna "frontend" a Dunkan ni "e-commerce" a nadie; ese lenguaje solo aparece en la Presentación y en el documento de Andrés.

### 1.5 El Informe grupal quedó con texto de plantilla sin completar
En la sección 4.4 ("Relación con los intereses profesionales") del Informe grupal (1.4), las entradas de Andrés y Dunkan siguen siendo el placeholder original sin rellenar:
> *"Andrés Fernández: [Andrés Fernández: completar con su propio interés profesional y cómo se relaciona con su rol de documentación en el proyecto]"*
> *"Dunkan Hernández: completar con su propio interés profesional y cómo se relaciona con su rol de pruebas y desarrollo en el proyecto]"*

La información sí existe y está bien desarrollada en los documentos individuales 1.2 y 1.3 de cada uno — simplemente no se copió de vuelta al informe grupal antes de entregarlo. Esto es un error de entrega, no de contenido: el documento que debería ser el más completo del grupo es el que quedó incompleto.

### 1.6 Tres cronogramas de sprint distintos para la misma Fase 2
- **Informe grupal (1.4) / Guía (1.5) / autoeval. Diego y Dunkan (1.3)**: diseño de arquitectura y mockups en semanas 5-6, "Desarrollo de sprints" como bloque único en semanas 6-14, pruebas en paralelo, integración y despliegue en semanas 15-16, cierre en 17-18. No se definen sprints individuales con fechas propias.
- **Presentación (slide 9)**: define explícitamente **4 sprints de 3 semanas** cada uno dentro de S5–S16 (Sprint 1: S5-S7 con mockups + clientes + backend; Sprint 2: S8-S10 contrato + firma; Sprint 3: S11-S13 trazabilidad + roles; Sprint 4: S14-S16 pruebas + Docker + manual).
- **Autoevaluación de Andrés (1.3)**: propone una tercera distribución — Sprint 1 en semanas 5-6, Sprint 2 en 7-8, Sprint 3 en 9-10, Sprint 4 en 11-12, y luego "Consolidación de evidencias y ajustes finales" en semanas 13-16.

Ninguna de las tres coincide exactamente con las otras dos en cuántas semanas dura cada sprint ni en cuándo termina el despliegue con Docker.

### 1.7 El líder da por "pendiente" algo que el propio informe grupal ya resolvió
Diego, en su autoevaluación individual (1.3), dice en la tabla de Plan de Trabajo que todos los responsables quedan "Por definir", y en su conclusión escribe: *"el mayor pendiente ahora es terminar de repartir responsabilidades dentro del equipo."* Sin embargo, el Informe grupal (1.4) — que el propio Diego firma como líder — ya trae una tabla de responsables asignados por actividad (él mismo, Andrés y Dunkan con tareas específicas). No queda claro si la repartición del informe grupal es definitiva o si de verdad sigue "por definir" como dice Diego.

### 1.8 Ortografía inconsistente del nombre de un integrante
El nombre real registrado es **"Dunkan"** (así figura en su propia autoevaluación de competencias 1.1: "Dunkan Andre Hernandez Reyes", y así se usa en la mayoría de los documentos). Sin embargo, tanto la Presentación (slide 2: "Duncan: Me interesa...") como la autoevaluación de Andrés (1.3, dos veces: "Duncan Hernández desarrolla el frontend...") lo escriben como **"Duncan"**. Es un detalle menor pero vale corregirlo por prolijidad, sobre todo si estos documentos se entregan formalmente.

### 1.9 Formato del RUT de Andrés
Informe grupal (1.4): **"15.417.074-K"** (dígito verificador en mayúscula). Autoevaluación de Andrés (1.3): **"RUN:15.417.074-k"** (minúscula). Mismo RUT, formato distinto — sin impacto real, pero conviene unificar el estilo en todos los documentos formales.

### 1.10 Ubicación de Easy Office
La Guía del Estudiante (1.5) sitúa el proyecto "en la Región Metropolitana". La Presentación (slide 3) dice: **"Casa Matriz: Región de Valparaíso · Sucursal: Región Metropolitana"**. No es necesariamente una contradicción (podría ser correcto que la casa matriz esté en Valparaíso y la sucursal con la que trabajan en la RM), pero el Informe/Guía nunca mencionan Valparaíso, así que conviene que quede explícito en el documento de definición para no dar la impresión de que se agregó un dato nuevo sin verificar.

### 1.11 Cifras de la empresa sin respaldo en los documentos de definición
La Presentación (slide 3) incluye cifras concretas — "5.000+ emprendimientos exitosos", "15+ años de experiencia", sitio web, y un servicio adicional ("rebaja tributaria") — que no figuran en el Informe de Inicio ni en la Guía, y no se indica de dónde salen (¿reunión con el cliente? ¿sitio web de la empresa?). **No puedo verificar estos datos** porque no están documentados en las fuentes de Fase 1 ni se me pidió contrastarlos externamente; si vienen de una fuente real conviene citarla en el Informe, y si son solo para la presentación, aclarar que son referenciales.

### 1.12 Cantidad total de documentos de Easy Office, poco clara
En las conclusiones del Informe grupal, Diego menciona evitar "los cuarenta y tantos documentos que maneja la empresa". La Presentación, en cambio, habla de una futura "ampliación a 10 documentos" en los próximos sprints. No se aclara en ningún documento si esos 10 son un subconjunto priorizado de los 40+ o si hay una discrepancia real en el número total. **Infiero** que probablemente los "10" sean una priorización posterior dentro de los 40+ totales, pero como no está explicado en ningún documento, lo dejo como punto abierto en vez de asumirlo como hecho.

### 1.13 Año de ingreso de Diego a la carrera
En su autoevaluación de competencias (1.1), Diego registra **"Año de ingreso: 2026"** — el mismo año en curso. Esto llama la atención porque Capstone suele ser la asignatura de cierre de carrera, después de varios años de estudio, y el resto de sus propios documentos (PalletScan como proyecto personal ya desarrollado, experiencia freelance) sugieren una trayectoria más larga. **Infiero que probablemente sea un error de tipeo** (quizás debería decir un año anterior), pero no tengo forma de confirmarlo — vale la pena que Diego lo revise y corrija si corresponde.

### 1.14 El nombre de la carpeta del repositorio ya no refleja el proyecto
La carpeta raíz se llama **"APT-Capstone_PirqueSpA"**, pero según el diario de reflexión de Diego (1.2) y su autoevaluación (1.3), la empresa **Pirque SpA fue el proyecto original que se cayó** tras la reunión con las empresas, y el docente confirmó que el proyecto definitivo sería **Easy Office**. Todo el contenido de Fase 1 (informe, guía, presentación, autoevaluaciones) es sobre Easy Office — Pirque SpA no vuelve a aparecer en ningún otro documento. Vale la pena que el equipo evalúe renombrar el repositorio (o al menos dejar una nota clara en el README) para que no genere confusión a futuro sobre cuál es el proyecto real.

## 2. Resumen de la problemática

Reconciliando las distintas versiones (y dejando explícito dónde tuve que decidir cuál tomar como base), el problema del proyecto es:

Easy Office es una empresa dedicada a formalizar emprendimientos (domicilio tributario, contabilidad, firma electrónica, creación de empresas). Su documento de definición formal (Informe 1.4 y Guía 1.5) acota el problema a que **los procesos documentales de mayor volumen se gestionan hoy de forma manual**: un agente rellena cada contrato o autorización, lo sube a la plataforma de firma electrónica, lo descarga firmado y lo reenvía al cliente, todo dependiente de la disponibilidad de ese agente. Esto le pone un techo al crecimiento de la empresa sin sumar más personal.

**Infiero**, a partir de la Presentación y de la autoevaluación de Dunkan (que no forman parte del documento formal de definición), que el problema real que el cliente describió podría ser más amplio: la gestión completa de venta y seguimiento de servicios ocurre hoy por WhatsApp, sin trazabilidad de qué ejecutivo hizo qué gestión ni con qué cliente, y sin una base de datos centralizada ni control de acceso a la información. Si esto es efectivamente lo que Easy Office planteó en la reunión de levantamiento, el Informe de Inicio (que es el documento oficial) debería decirlo explícitamente — tal como está redactado hoy, subestima el alcance del problema real frente a lo que ya se está comunicando en la Presentación.

## 3. Solución propuesta

Según el documento formal de definición (Informe 1.4, sección 4.2 y objetivos): un **CRM** que registre los datos de cada cliente, automatice la **generación, firma electrónica y entrega** de los dos documentos de mayor flujo (contrato de prestación de servicios y autorización de domicilio tributario), integrándose con la plataforma de firma electrónica que Easy Office ya contrata, y que deje registro del estado de cada trámite con perfiles de acceso diferenciados para agentes y administradores.

La Presentación amplía esta solución a un "ecosistema digital" que también centraliza la venta (incluyendo pago en línea) y da trazabilidad por ejecutivo — como se señaló en el punto 1.3, esa ampliación **no está respaldada todavía por el Informe de Inicio**, así que la trato aquí como una extensión propuesta por el equipo, no como parte confirmada del alcance oficial, hasta que el Informe se actualice o el equipo decida descartarla.

## 4. Alcances y limitantes

**Dentro del alcance del MVP** (según el Informe 1.4, sección 7 — la fuente más específica sobre esto):
- Registro de datos del cliente.
- Generación automática de: contrato de prestación de servicios y autorización de uso de domicilio tributario.
- Envío a la plataforma de firma electrónica ya contratada por Easy Office.
- Registro del estado de cada trámite.
- Perfiles de acceso diferenciados (agente / administrador).
- Despliegue en un entorno local (vía Docker).

**Fuera del alcance del MVP** (explícito en el Informe 1.4):
- Otros tipos de documentos más allá de los dos priorizados (la empresa maneja "cuarenta y tantos" según las conclusiones de Diego).
- Automatización completa de la creación de empresas.
- Chatbot de atención con inteligencia artificial.
- Migración a infraestructura en la nube (queda para una fase futura, según la Presentación).

**Punto abierto que el equipo debería resolver antes de Fase 2**, dado lo detectado en este análisis: si el módulo de venta/pago en línea (e-commerce) y la ampliación del problema a "gestión completa por WhatsApp sin trazabilidad" están realmente dentro del alcance acordado con el cliente, deberían incorporarse formalmente al Informe de Inicio; si no lo están, deberían retirarse de la Presentación y de las autoevaluaciones individuales para no generar expectativas con el cliente ni confusión interna sobre qué se va a construir.

**Restricciones** (consistentes en todos los documentos): el cliente no tiene conocimientos técnicos avanzados (interfaz debe ser simple), el despliegue inicial es local (no en la nube), debe integrarse con el proveedor de firma electrónica ya contratado (sin reemplazarlo), y el plazo está acotado por el calendario académico (18 semanas, cierre estimado entre septiembre y octubre).

## 5. Recomendación para mantener consistencia hacia adelante

Antes de avanzar a Fase 2, sugiero que el equipo:
1. Decida una única versión del objetivo general y del alcance (¿incluye venta/pago o no?) y la replique igual en el Informe, la Guía, la Presentación y las tres autoevaluaciones.
2. Complete los dos placeholders sin rellenar en el Informe grupal (sección 4.4).
3. Defina un único cronograma de sprints y lo use en todos los documentos que lo mencionen.
4. Aclare por escrito quién hace QA (Andrés, Dunkan, o ambos en distintas partes) para que no se dupliquen responsabilidades ni queden vacíos.
5. Unifique la ortografía del nombre "Dunkan" y el formato del RUT de Andrés.
