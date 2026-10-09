**Seminario técnico · UTN FRRo · Ortiz · Oliva · Ramirez · ~35 min**

**Cómo leer este guion:** `[CLIC]` = cambio de diapositiva. `⚠ VERIFICAR` = dato que conviene confirmar con la fuente antes de decirlo.

## Mapa de diapositivas

| #   | Diapositiva                                    | Sección de la presentación            | Quién     | Tiempo      |
| --- | ---------------------------------------------- | ------------------------------------- | --------- | ----------- |
| 1   | Portada                                        | —                                     | Laureano | 00:00–01:45 |
| 2   | Objetivos                                      | ESTRUCTURA Y METAS                    | Laureano | 01:45–03:00 |
| 3   | Perspectiva histórica                          | PERSPECTIVA HISTÓRICA                 | Laureano | 03:00–05:30 |
| 4   | Cuarteto de Anscombe                           | FUNDAMENTO TEÓRICO                    | Laureano | 05:30–08:30 |
| 5   | Datasaurus Dozen                               | FUNDAMENTO TEÓRICO                    | Laureano | 08:30–10:00 |
| 6   | Mercado laboral                                | MERCADO LABORAL                       | Valentino | 10:00–12:00 |
| 7   | La tríada de visualización                     | HERRAMIENTAS DE VISUALIZACIÓN         | Valentino  | 12:00–13:00 |
| 8   | Arquitectura de Matplotlib: tres capas         | INGENIERÍA DE SOFTWARE                | Valentino  | 13:00–15:00 |
| 9   | Artist Layer                                   | INGENIERÍA DE SOFTWARE                | Valentino  | 15:00–16:00 |
| 10  | Scripting Layer: pyplot vs OO                  | INGENIERÍA DE SOFTWARE                | Valentino  | 16:00–17:30 |
| 11  | Matplotlib: tipos de gráficos y sintaxis       | INGENIERÍA DE SOFTWARE                | Valentino  | 17:30–19:00 |
| 12  | Ejemplo código Matplotlib (grilla 2×2)         | INGENIERÍA DE SOFTWARE                | Valentino  | 19:00–19:45 |
| 13  | Seaborn: estadística de alto nivel             | INGENIERÍA ESTADÍSTICA                | Facundo  | 19:45–21:30 |
| 14  | Comparación Matplotlib vs Seaborn (código)     | (código lado a lado)                  | Facundo  | 21:30–22:30 |
| 15  | Plotly: la figura es una especificación JSON   | ARQUITECTURA CLIENTE–SERVIDOR         | Facundo  | 22:30–24:00 |
| 16  | Plotly: un gráfico interactivo en una llamada  | ARQUITECTURA CLIENTE–SERVIDOR         | Facundo  | 24:00–25:00 |
| 17  | Principios de diseño y accesibilidad           | ARQUITECTURA CLIENTE–SERVIDOR         | Facundo  | 25:00–26:30 |
| 18  | Comparativa: ventajas, desventajas             | INGENIERÍA ESTADÍSTICA                | Laureano  | 26:30–28:00 |
| 19  | Live demo (notebook)                           | —                                     | Facundo   | 28:00–33:00 |
| 20  | Conclusión: qué usar y para qué                | RESUMEN Y RECOMENDACIONES             | Laureano   | 33:00–35:00 |
| 21  | Cierre y agradecimiento                        | HERRAMIENTAS DE VISUALIZACIÓN         | -   | 35:00       |

---

# Slide 1 · Portada e Introducción (00:00–01:45)

"Buenas tardes, profesores y compañeros. Somos Valentino Ortiz, Laureano Oliva y Facundo Ramirez, y hoy presentamos nuestro seminario técnico: **Data Visualization en Python: arquitectura, historia y ecosistema del análisis visual.**

Arranco con una pregunta: ¿cuántas veces escribieron `plt.plot()` al final de un script solo para 'adornar' un informe? Existe la idea de que graficar es una tarea menor, casi estética. Hoy venimos a demostrar exactamente lo contrario. Visualizar datos es una disciplina de ingeniería y de comunicación científica.

La razón es biológica. Es de general conocimiento que al ser humano le resulta mas sencillo visualizar y comprender información desde una perspectiva visual, por sobre una tabla o datos crudos. Por esta razón, un gráfico bien construido nos deja ver en segundos patrones, tendencias y anomalías que en una tabla de miles de números pasan totalmente desapercibidos. La visualización funciona como una interfaz de alto nivel entre los datos y la persona que tiene que decidir.

En los próximos 35 minutos vamos a ver de dónde viene este ecosistema, cómo funciona por dentro, qué lugar ocupa en el mercado laboral, y lo vamos a probar en vivo." `[CLIC]`

# Slide 2 · Objetivos (01:45–03:00)

"Para ordenar la presentación, nos propusimos tres objetivos.

**Primero, vamos a comprender la arquitectura interna.** No vamos a memorizar comandos, si no que vamos a abrir Matplotlib, Seaborn y Plotly para ver cómo organizan sus capas, qué hacen con los datos y cómo terminan dibujando algo en pantalla.

**Segundo, diferenciaremos los paradigmas.** Donde nos encontramos con la programación procedimental con estado global, programación orientada a objetos, agregación estadística automática, y serialización a JSON para la web.

**Tercero, desarrollar criterio de selección.** Que al final puedan responder con fundamento qué herramienta usar según la restricción del proyecto: un PDF para publicar, una exploración rápida, o un tablero interactivo." `[CLIC]`

# Slide 3 · Perspectiva histórica (03:00–05:30)

"Para entender las herramientas de hoy, conviene conocer los problemas que intentaron resolver.

La visualización cuantitativa moderna tiene un referente: **Edward Tufte**, profesor de Yale, que en **1983** publicó _The Visual Display of Quantitative Information_. Su idea central es que un gráfico debe ser honesto, limpio y sin adornos que no aporten información. Más adelante vamos a ver su concepto más famoso, el data-ink ratio.

Ahora, el software. A comienzos de los 2000, **MATLAB** era el estándar para graficar en ciencia e ingeniería: hacía lindos gráficos con muy pocas líneas, aunque es un producto comercial y de código cerrado.

En ese contexto, **John D. Hunter**, un neurobiólogo que hacía una investigación posdoctoral y analizaba señales cerebrales de pacientes con epilepsia, había construido su aplicación de análisis en MATLAB. A medida que la aplicación crecía, MATLAB se le quedó chico como lenguaje de programación y decidió rehacerla en Python. Pero en Python no encontró un paquete de gráficos 2D que cumpliera lo que necesitaba: gráficos de calidad de publicación, salida para documentos científicos, posibilidad de integrarlo en una aplicación, y que fuera fácil de usar.

Entonces hizo lo que haría cualquier programador: lo escribió él mismo. Y decidió imitar los comandos de gráficos de MATLAB, dado que mucha gente ya los conocía, evitando a los usuarios (que provenían de MATLAB) de esta nueva tecnología tener que padecer una curva de aprendizaje. Así nació **Matplotlib, en 2003**: un proyecto personal pensado para resolver un problema médico-científico que terminó volviéndose la base de gran parte del ecosistema científico de Python. Pandas y Seaborn, por ejemplo, dibujan por debajo con Matplotlib." `[CLIC]`

# Slide 4 · El Cuarteto de Anscombe (05:30–08:30)

"Para comprender el porque de la importancia de la visualización de datos, vamos a demostrar un clásico experimento, que demuestra por qué graficar es una etapa obligatoria del análisis.

En **1973**, el estadístico británico **Francis Anscombe** construyó cuatro conjuntos de datos de 11 pares (X, Y) cada uno. Si los analizamos solo con estadísticos de resumen, son prácticamente idénticos:
- media de X: 9,0; media de Y: 7,50;
- varianza de X: 11,0; varianza de Y: 4,12;
- recta de regresión: Y = 3,00 + 0,50·X;
- correlación de Pearson: 0,816.

Un informe tabular diría que son cuatro fenómenos indistinguibles. [PAUSA] Ahora miren los gráficos. `[mostrar imagen]`
- **I**: una relación lineal razonable. El único donde la recta tiene sentido.
- **II**: no es una recta, es una curva. Una regresión lineal es un error de modelo.
- **III**: una relación lineal perfecta, pero un único outlier cambia la recta.
- **IV**: todos los puntos tienen X = 8, salvo uno lejano que, por sí solo, fija la pendiente.

La lección que nos brinda este caso es que **los mismos números pueden esconder realidades opuestas.** Sin el gráfico, tomamos decisiones basadas en ilusiones estadísticas." `[CLIC]`

# Slide 5 · El Datasaurus Dozen (08:30–10:00)

"Y esta idea tiene una versión moderna, mucho más fácil de recordar. En 2016, el especialista en visualización Alberto Cairo creó el **Datasaurus**: un conjunto de puntos que, al graficarse, dibuja un dinosaurio. En 2017, dos investigadores de Autodesk, Justin Matejka y George Fitzmaurice, tomaron ese dinosaurio y generaron otros doce conjuntos con formas muy distintas —una estrella, un círculo, una X— que comparten con él la misma media, la misma desviación estándar y la misma correlación, hasta el segundo decimal. `[mostrar imagen del Datasaurus Dozen]` Es Anscombe, pero con un dinosaurio: **mismos números, dibujos completamente distintos.**

Link al informe de Datasaurus: https://cran.r-project.org/web/packages/datasauRus/vignettes/Datasaurus.html

# Slide 6 · Demanda laboral (10:00–12:00)

"Un punto importante sobre la demanda laboral. Según datos de Randstad y la Encuesta de Sueldos de SysArmy 2026, ciencia de datos y analítica **lideran la demanda y ofrecen las mejores remuneraciones** del sector tecnológico argentino. Se buscan especialistas en Business Intelligence y analítica avanzada en empresas de todos los tamaños.

Los perfiles con más tracción son **Data Engineer**, que construye y mantiene los pipelines de datos, y **Data Scientist / AI-ML Engineer**, con demanda que crece a doble dígito.

En cuanto a las competencias más buscadas, los datos son claros: **relevamiento y documentación de requerimientos** encabeza con un 74 %, seguido de **SQL** con un 59 %, **Python** con un 44 % y **alfabetización en IA** con un 35 %. Las más pedidas son las fundacionales, no las más novedosas.

¿Quién contrata? Multinacionales como L'Oréal, Novartis, PedidosYa y Naranja X; GlobalLogic planea incorporar más de 450 profesionales en Argentina durante 2026; y hay ofertas 100 % remotas desde Argentina en empresas como EPAM, Webflow y Newsela.

En resumen: no alcanza con analizar, hay que saber **comunicar visualmente**." `[CLIC]`

# Slide 7 · La tríada de visualización en Python (12:00–13:00)

"El ecosistema de visualización en Python es enorme, pero se ordena alrededor de tres librerías que llamamos la **tríada**.

**Matplotlib** es la librería madre: siendo el motor de bajo nivel, con control total sobre cada elemento, pero a cambio de más código. **Seaborn** es una capa de alto nivel construida sobre Matplotlib, pensada para exploración estadística rápida con DataFrames de Pandas. Y por último, **Plotly** es el estándar para gráficos interactivos y web.

Para elegir entre ellas hay que entender qué pasa por dentro de cada una." `[CLIC]`

# Slide 8 · Arquitectura de Matplotlib: tres capas (13:00–15:00)

"Comenzando con Matplotlib, observamos que se encuentra organizada en **tres capas**. Las vamos a ver de abajo hacia arriba, dado que cada una se apoya en la anterior.

**Backend Layer.** Es la capa más baja y la que sabe producir una salida concreta. Se define con tres clases abstractas: `FigureCanvas`, el área sobre la que se dibuja; `Renderer`, que ejecuta el dibujo; y `Event`, que gestiona la entrada del usuario, como el mouse o el teclado. Hay backends no interactivos, que generan archivos —Agg produce imágenes PNG, y existen backends propios para PDF, SVG y PostScript— y backends interactivos, que muestran la figura en una ventana de escritorio, como Qt o Tk.

**Artist Layer.** Es el núcleo de la librería. Todo lo que se ve en una figura es un objeto `Artist`. Lo vamos a ver en detalle en la próxima diapositiva.

**Scripting Layer.** Es `pyplot`, la interfaz que usamos todos los días. También la vamos a detallar." `[CLIC]`

# Slide 9 · Artist Layer: todo lo que se ve es un Artist (15:00–16:00)

"Profundicemos en la capa Artist. Todo lo que se ve en una figura de Matplotlib es un objeto `Artist`. Hay dos tipos:

Las **primitivas**, como `Line2D`, `Rectangle` o `Text`, que son los elementos de dibujo.

Y los **contenedores**, como `Figure`, `Axes` y `Axis`, que agrupan a otros artistas y forman una jerarquía. En el diagrama pueden ver: la `Figure` contiene un `Axes`, y este a su vez contiene un `Axis X`, un `Axis Y`, objetos `Line2D`, `Text`, etc.

Cada Artist conoce sus coordenadas y sabe dibujarse a sí mismo cuando recibe un Renderer; para eso transforma coordenadas de datos en coordenadas de pantalla.

Una aclaración de terminología importante: `Axes` es el **área de dibujo** con su sistema de coordenadas, y cada `Axes` contiene dos objetos `Axis`, el eje X y el eje Y. Una `Figure` puede tener varios `Axes`: son los subplots." `[CLIC]`

# Slide 10 · Scripting Layer: pyplot y la interfaz orientada a objetos (16:00–17:30)

"La capa de Scripting tiene dos estilos.

El primero es **pyplot**, que mantiene un **estado global**: recuerda cuál es la figura y cuáles son los ejes actuales. Imita a MATLAB, y por eso `plt.plot()` funciona sin crear nada de forma explícita. Es muy cómodo para scripts cortos, pero en código más grande, con varias figuras, ese estado implícito se vuelve ambiguo.

El segundo es la interfaz **orientada a objetos**: llamamos a `plt.subplots()` solo para crear la `Figure` y los `Axes`, y después trabajamos con métodos explícitos como `ax.plot()` o `ax.set_title()`. Es el estilo recomendado en software mantenible.

En la diapositiva pueden ver los dos ejemplos lado a lado. El resultado visual es el mismo, pero la claridad del código es muy distinta.

**Para resumir, con una analogía:** pensemos en un taller de impresión. `pyplot` es el pedido que le hacemos al asistente: 'dibujame una línea'. La capa Artist es el diseñador, que sabe qué elementos componen el dibujo y dónde va cada uno. Y el backend es la imprenta, que lo convierte en el producto final: un PNG, un PDF o una ventana en pantalla." `[CLIC]`

# Slide 11 · Matplotlib: tipos de gráficos y sintaxis (17:30–19:00)

"Ya vimos cómo está construida Matplotlib; veamos qué nos ofrece. Los métodos del objeto `Axes` se agrupan en cuatro familias.

**Tipos de gráficos.** `plot` para líneas; `scatter` para dispersión, donde `s` controla el tamaño de los puntos y `c` el color; `bar` y `barh` para barras verticales y horizontales; `hist` para histogramas, con `bins` para la cantidad de intervalos; `boxplot` para diagramas de caja; e `imshow` para imágenes y mapas de calor.

**Personalización.** Una vez creado el gráfico, lo ajustamos con métodos que empiezan con `set_`: título, etiquetas y límites de los ejes; y con `legend`, `grid` y `annotate` para leyenda, grilla y anotaciones.

**Disposición y salida.** `plt.subplots` crea la `Figure` con una grilla de `Axes`, `tight_layout` acomoda los espacios, y `savefig` exporta: el formato lo define la extensión, `.png`, `.pdf` o `.svg`.

La sintaxis siempre sigue el mismo patrón: `ax.tipo_de_gráfico(datos, parámetros estéticos)`, y después los `set_*` para etiquetar." `[CLIC]`

# Slide 12 · Ejemplo código Matplotlib: grilla 2×2 (19:00–19:45)

"Veámoslo en el ejemplo. `[mostrar código e imagen]` Creamos una `Figure` con cuatro `Axes` en una grilla 2×2. En `axs[0,0]`, dos llamadas a `plot` con `label` y un `legend` dibujan seno y coseno. En `axs[0,1]`, `bar` grafica tres categorías. En `axs[1,0]`, `hist` agrupa 500 valores aleatorios en 20 intervalos. Y en `axs[1,1]`, `scatter` muestra puntos de seno con ruido. Cada `Axes` es independiente: tiene su propio título y sus propias etiquetas. Esto es el paradigma orientado a objetos en acción, y es el control que Matplotlib nos da." `[CLIC]`

# Slide 13 · Seaborn: estadística de alto nivel sobre Matplotlib (19:45–21:30)

"Con Matplotlib, nosotros agrupamos, filtramos y calculamos promedios con Pandas antes de graficar. En cambio, **Seaborn** trabaja directamente sobre el DataFrame.

**Cómo se usa.** La entrada es un DataFrame de Pandas en formato _tidy_: una fila por observación y una columna por variable. En lugar de pasarle listas de números, le indicamos qué columna cumple cada rol visual con tres parámetros: `data`, el DataFrame; `x` e `y`, las columnas de cada eje; y `hue`, la columna que define el color.

Sus funciones se agrupan por el tipo de pregunta que responden: **relacionales**, como `scatterplot` y `lineplot`; de **distribución**, como `histplot` y `kdeplot`; **categóricas**, como `boxplot`, `barplot` y `countplot`; de **regresión**, como `regplot` y `lmplot`; **matrices**, como `heatmap`; y **grillas** de varios gráficos, como `pairplot`.

Y cuando ejecutamos una de ellas, internamente pasa por cuatro pasos:
1. **Agrega** los datos: agrupa por categorías y calcula la medida de resumen, por defecto la media.
2. **Estima la incertidumbre**: por defecto usa _bootstrapping_, un remuestreo repetido, para calcular intervalos de confianza del 95 % y dibujarlos como bandas o barras de error.
3. **Aplica paletas** y estilos pensados para la percepción visual.
4. **Traduce todo a objetos Artist de Matplotlib** y los dibuja.

Seaborn nos da velocidad en la fase exploratoria. A cambio, cedemos control fino y, cuando necesitamos personalizar a fondo, bajamos a Matplotlib; de hecho, los gráficos de Seaborn son objetos de Matplotlib." `[CLIC]`

# Slide 14 · Comparación Matplotlib vs Seaborn: código lado a lado (21:30–22:30)

"Para ver la diferencia en la práctica, comparamos cómo se hace el **mismo gráfico** —propina promedio por día— con ambas librerías.

A la izquierda, **Matplotlib**: primero tenemos que agrupar manualmente con Pandas (`tips.groupby('day')['tip'].mean()`), después crear la figura, dibujar las barras con `ax.bar`, agregar las etiquetas con `ax.bar_label`, setear título y label del eje Y, y desactivar la grilla del eje X. Son varias líneas de código.

A la derecha, **Seaborn**: una sola llamada a `sns.barplot` con `data=tips, x='day', y='tip', estimator='mean'`. Seaborn agrupa, calcula la media y dibuja, todo internamente. Después solo seteamos título y label con `ax.set()`.

El resultado visual es muy similar, pero la diferencia en código es notable. Eso sí, fíjense que en la versión de Seaborn podrían aparecer barras de error con intervalo de confianza; acá las desactivamos con `errorbar=None` para que sean comparables. Esa es justamente la estadística que Seaborn agrega por defecto." `[CLIC]`

# Slide 15 · Plotly: la figura es una especificación JSON (22:30–24:00)

"Plotly ofrece dos interfaces. `plotly.express` es la de alto nivel: una sola llamada crea un gráfico completo, con funciones como `px.scatter`, `px.line`, `px.bar`, `px.histogram` o `px.box`. `plotly.graph_objects` es la de bajo nivel: construimos la figura trazo por trazo con `go.Figure` y `go.Scatter`, con control total.

Las dos producen el mismo objeto: una `Figure`, que en esencia es un diccionario con dos claves: `data`, una lista de **trazas**, donde cada traza es una serie con su tipo de gráfico; y `layout`, que guarda títulos, ejes y márgenes.

Cuando llamamos a `fig.show()`, Python no dibuja nada: **serializa** esa figura a JSON y se la entrega al navegador, o a la celda de Jupyter. Ahí, la librería JavaScript **Plotly.js** la renderiza, por defecto como SVG, y con WebGL cuando hay muchísimos puntos. Por eso el zoom, el desplazamiento, el filtrado desde la leyenda y los tooltips los procesa el navegador, no el kernel de Python." `[CLIC]`

# Slide 16 · Plotly: un gráfico interactivo en una llamada (24:00–25:00)

"Veámoslo con un ejemplo concreto. Acá usamos `px.bar` para graficar la propina promedio por día, el mismo gráfico que hicimos con Matplotlib y Seaborn.

Con una sola llamada configuramos todo: el DataFrame, los ejes, los colores, las etiquetas, el template visual y hasta el formato de los números con `text_auto`. Después ajustamos el ancho de las barras y la posición del texto con `fig.update_traces`.

Lo que ven no es una imagen estática: si paso el cursor sobre una barra, aparece su valor exacto; puedo hacer zoom, y puedo descargar un PNG con el ícono de la cámara. Todo eso lo resuelve el navegador, no Python.

Ese es el paradigma de Plotly: **Python escribe la receta —el JSON— y el navegador cocina el plato.**" `[CLIC]`

# Slide 17 · Principios de diseño y accesibilidad (25:00–26:30)

"Que el código funcione no alcanza. Para seguir los principios del diseño debemos aplicar las siguientes reglas prácticas:
* **Maximizar el data-ink ratio de Tufte.** La mayor parte de la tinta debe representar datos: fuera bordes pesados, fondos oscuros y grillas recargadas.
* **Evitar el chartjunk.** Los gráficos 3D de torta o de barras se desaconsejan dado la perspectiva distorsiona la percepción del área.
* **Color con intención.** El color es una codificación de datos, no decoración: paletas categóricas para variables cualitativas, secuenciales o divergentes para cuantitativas.
* **Accesibilidad.** Cuidamos el contraste, siguiendo criterios como los de WCAG, y usamos paletas perceptualmente uniformes como Viridis o Cividis, que se leen bien también con daltonismo." `[CLIC]`

# Slide 18 · Comparativa: ventajas, desventajas y cuándo usar cada una (26:30–28:00)

"Sintetizamos en una matriz.

**Matplotlib**: cuenta con control total y salida de calidad de publicación (PDF/SVG), y es la base del ecosistema. A cambio: es verboso, tiene una curva de aprendizaje alta y su estética por defecto es básica. **Usarla para:** publicaciones y reportes estáticos.

**Seaborn**: rápido, estadística integrada y buena estética por defecto. A cambio: menos control fino y depende de Matplotlib. **Usarla para:** EDA (exploración inicial).

**Plotly**: interactivo, despliegue web, e integra con Dash y Streamlit. A cambio: el HTML se vuelve pesado con muchos datos y tiene menos control para impresión. **Usarla para:** dashboards y apps.

Y existen alternativas: **Altair**, declarativo, y **Bokeh**, también interactivo; **ggplot2** en R; y herramientas de BI como **Power BI** o **Tableau**, que no requieren programar pero ofrecen menos flexibilidad y suelen estar sujetas a licencias.

La conclusión: **no hay una mejor herramienta, hay una mejor herramienta para cada restricción.**.

# Slide 19 · Live Demo: notebook de Datos Climáticos (28:00–33:00) (ESTA NO ESTA EN LA DIAPO ORIGINAL PERO PODEMOS USARLA COMO GUÍA PARA LA DEMO REAL)

**Intro (28:00–29:00)**

"En vez de hacer el mismo gráfico en tres librerías, armamos un flujo de trabajo real con un dataset de **emisiones de CO₂ y anomalías de temperatura global** de 10 países (1960–2023). La idea es que cada librería muestre su fortaleza:

| Librería | Fortaleza | Gráfico |
|---|---|---|
| **Matplotlib** | Control total, anotaciones precisas | Línea temporal con hitos históricos y doble eje Y |
| **Seaborn** | Estadística automática | Regresión por continente, heatmap de correlación, violinplot |
| **Plotly** | Interactividad y animación | Mapa coroplético animado, burbujas estilo Gapminder |

Comparto pantalla."

**Paso 1 — Preparación y limpieza (29:00–30:00)**

"Generamos un dataset sintético basado en patrones reales de Our World in Data: 640 filas, 10 países, 8 columnas. Al ser sintético, no hace falta internet. Introducimos nulos realistas —Nigeria sin datos de CO₂ antes de 1971, India con gaps en los 60s— porque los datos climáticos reales siempre tienen huecos. Los tratamos con interpolación lineal por país para las columnas de CO₂."

**Paso 2 — Matplotlib: control total (30:00–31:00)**

"Arrancamos con Matplotlib, la fortaleza: control pixel a pixel. Creamos un gráfico de líneas con **doble eje Y** usando `twinx`: CO₂ total de todos los países a la izquierda, anomalía de temperatura a la derecha. Agregamos anotaciones con flechas en los hitos históricos: Protocolo de Kyoto (1997), Acuerdo de París (2015) y la caída del COVID-19 (2020). Sombreamos los períodos clave. Son ~40 líneas de código, pero el resultado es un gráfico de **calidad publicación** que no se puede hacer con Seaborn ni con Plotly."

**Paso 3 — Seaborn: estadística automática (31:00–32:00)**

"Ahora Seaborn. Hacemos tres gráficos estadísticos en ~15 líneas cada uno:
- `lmplot` para **regresión con facetado por continente**: ajusta una recta de regresión automáticamente con banda de confianza al 95 % y crea un panel por cada continente.
- `heatmap` para una **matriz de correlación** con un solo llamado.
- `violinplot` para ver la **distribución completa** del CO₂ per cápita por continente, no solo los cuartiles como un boxplot.

Seaborn calculó regresiones, bandas de confianza, correlaciones y densidades. En Matplotlib, cada uno de esos cálculos habría que programarlo a mano."

**Paso 4 — Plotly: interactividad y animación (32:00–33:00)**

"Por último, Plotly. Hacemos dos gráficos que son casi imposibles con las otras librerías:
- Un **mapa coroplético animado** con `px.choropleth`: un mapa mundial donde se puede reproducir la animación para ver cómo cambian las emisiones por país año a año. Se puede pausar, avanzar con el slider, pasar el mouse para ver valores exactos.
- Un **gráfico de burbujas animado** estilo Hans Rosling / Gapminder: cada burbuja es un país, el tamaño representa la población, el color el continente, y la animación avanza por año.

~12 líneas de código por gráfico para obtener mapas animados e interactivos. Plotly genera HTML/JavaScript por detrás, lo que permite interactividad que es imposible con librerías estáticas."

## Slide 20 · Conclusión: qué usar y para qué (33:00–35:00)

"Para cerrar, volvamos a los tres objetivos.

**Arquitectura:** vimos que Matplotlib son tres capas, Seaborn agrega estadística sobre Matplotlib, y Plotly serializa a JSON y delega en el navegador. **Paradigmas:** procedimental, orientado a objetos, agregación automática y especificación declarativa. **Criterio de selección:** Seaborn para explorar; Matplotlib cuando necesitamos control absoluto o salida de publicación; Plotly para interactividad y web.

La diapositiva resume las recomendaciones en una tabla:

| Situación | Herramienta | Por qué |
|---|---|---|
| Explorar un dataset nuevo | Seaborn | Estadística integrada, una línea por gráfico |
| Figura para paper, tesis o informe | Matplotlib | Control total y salida vectorial |
| Tablero interactivo para gerencia o web | Plotly (Dash/Streamlit) | Interactividad en el navegador |
| Auditar datos faltantes o mapear datos geográficos | Missingno / Folium… | Herramientas de nicho |

Y los tres mensajes finales:
1. No hay una mejor librería: hay una mejor **para cada restricción**.
2. El flujo ideal es **híbrido**: explorar con Seaborn, refinar con Matplotlib, publicar con Plotly.
3. **Grafiquen siempre** los datos antes de concluir (Anscombe, Datasaurus).

El notebook y el código quedan a disposición de la cátedra. Muchas gracias; quedamos abiertos a sus preguntas."

# Slide 21 · Cierre y agradecimiento (35:00)

"¡Muchas gracias!"

# Anexo B — Checklist antes de ensayar

- [ ] Correr el notebook `demo.ipynb` completo en la máquina de la demo, sin internet (el dataset es autocontenido).
- [ ] Verificar que los gráficos de Plotly (mapa y burbujas) se renderizan bien en Jupyter/VS Code.
- [ ] Cronometrar cada bloque en voz alta; apuntar a 12 / 16 / 7 minutos.
- [ ] Slide de mercado laboral: confirmar que las fuentes (Randstad, SysArmy 2026) siguen vigentes.
- [ ] Slide de fuentes: confirmar bibliografía (Tufte 1983, Anscombe 1973, Hunter 2007, Matejka & Fitzmaurice 2017, documentación oficial de las tres librerías).
