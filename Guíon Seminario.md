**Seminario técnico · UTN FRRo · Ortiz · Oliva · Ramirez · ~35 min**

**Cómo leer este guion:** `[CLIC]` = cambio de diapositiva. `⚠ VERIFICAR` = dato que conviene confirmar con la fuente antes de decirlo. `[COMPLETAR]` = falta un dato que tienen que buscar ustedes.

## Mapa de diapositivas (★ = nueva, hay que agregarla)

| #   | Diapositiva                         | Plantilla de la cátedra              | Quién     | Tiempo      |
| --- | ----------------------------------- | ------------------------------------ | --------- | ----------- |
| 1   | Portada                             | Introducción                         | Valentino | 00:00–01:45 |
| 2★  | Objetivos                           | Objetivos                            | Valentino | 01:45–03:00 |
| 3   | Perspectiva histórica               | Introducción                         | Valentino | 03:00–05:30 |
| 4   | Mercado laboral / Data Translator   | Demanda laboral                      | Valentino | 05:30–07:45 |
| 5   | Cuarteto de Anscombe                | Introducción (fundamento)            | Valentino | 07:45–11:00 |
| 6   | Ecosistema analítico                | Comparativa                          | Laureano  | 11:00–12:30 |
| 7   | Arquitectura de Matplotlib          | —                                    | Laureano  | 12:30–15:30 |
| 8   | Motor de Seaborn                    | —                                    | Laureano  | 15:30–17:45 |
| 9   | Paradigma Plotly                    | —                                    | Laureano  | 17:45–19:45 |
| 10  | Principios de diseño                | —                                    | Laureano  | 19:45–21:15 |
| 11★ | Comparativa, ventajas y desventajas | Comparativa + Ventajas y Desventajas | Laureano  | 21:15–23:00 |
| 12  | Live demo "El Viaje del Dato"       | Live Demo                            | Facundo   | 23:00–31:30 |
| 13  | Conclusión y preguntas              | Conclusión                           | Facundo   | 31:30–35:00 |
| 14  | Fuentes                             | —                                    | —         | —           |

---

# BLOQUE 1 (00:00–11:00)

## Slide 1 · Portada e Introducción (00:00–01:45)

"Buenas tardes, profesores y compañeros. Somos Valentino Ortiz, Laureano Oliva y Facundo Ramirez, y hoy presentamos nuestro seminario técnico: **Data Visualization en Python: arquitectura, historia y ecosistema del análisis visual.**

Arranco con una pregunta: ¿cuántas veces escribieron `plt.plot()` al final de un script solo para 'adornar' un informe? Existe la idea de que graficar es una tarea menor, casi estética. Hoy venimos a demostrar exactamente lo contrario. Visualizar datos es una disciplina de ingeniería y de comunicación científica.

La razón es biológica. Es de general conocimiento que al ser humano le resulta mas sencillo visualizar y comprender información desde una perspectiva visual, por sobre una tabla o datos crudos. Por esta razón, un gráfico bien construido nos deja ver en segundos patrones, tendencias y anomalías que en una tabla de miles de números pasan totalmente desapercibidos. La visualización funciona como una interfaz de alto nivel entre los datos y la persona que tiene que decidir.

En los próximos 35 minutos vamos a ver de dónde viene este ecosistema, cómo funciona por dentro, qué lugar ocupa en el mercado laboral, y lo vamos a probar en vivo." `[CLIC]`

## Slide 2 · Objetivos (01:45–03:00)

"Para ordenar la presentación, nos propusimos tres objetivos.

**Primero, vamos a comprender la arquitectura interna.** No vamos a memorizar comandos, si no que vamos a abrir Matplotlib, Seaborn y Plotly para ver cómo organizan sus capas, qué hacen con los datos y cómo terminan dibujando algo en pantalla.

**Segundo, diferenciaremos los paradigmas.** Donde nos encontramos con la programación procedimental con estado global, programación orientada a objetos, agregación estadística automática, y serialización a JSON para la web.

**Tercero, desarrollar criterio de selección.** Que al final puedan responder con fundamento qué herramienta usar según la restricción del proyecto: un PDF para publicar, una exploración rápida, o un tablero interactivo." `[CLIC]`

## Slide 3 · Perspectiva histórica (03:00–05:30)

"Para entender las herramientas de hoy, conviene conocer los problemas que intentaron resolver.

La visualización cuantitativa moderna tiene un referente: **Edward Tufte**, profesor de Yale, que en **1983** publicó _The Visual Display of Quantitative Information_. Su idea central es que un gráfico debe ser honesto, limpio y sin adornos que no aporten información. Más adelante vamos a ver su concepto más famoso, el data-ink ratio.

Ahora, el software. A comienzos de los 2000, **MATLAB** era el estándar para graficar en ciencia e ingeniería: hacía lindos gráficos con muy pocas líneas, aunque es un producto comercial y de código cerrado.

En ese contexto, **John D. Hunter**, un neurobiólogo que hacía una investigación posdoctoral y analizaba señales cerebrales de pacientes con epilepsia, había construido su aplicación de análisis en MATLAB. A medida que la aplicación crecía, MATLAB se le quedó chico como lenguaje de programación y decidió rehacerla en Python. Pero en Python no encontró un paquete de gráficos 2D que cumpliera lo que necesitaba: gráficos de calidad de publicación, salida para documentos científicos, posibilidad de integrarlo en una aplicación, y que fuera fácil de usar.

Entonces hizo lo que haría cualquier programador: lo escribió él mismo. Y decidió imitar los comandos de gráficos de MATLAB, dado que mucha gente ya los conocía, evitando a los usuarios (que provenían de MATLAB) de esta nueva tecnología tener que padecer una curva de aprendizaje. Así nació **Matplotlib, en 2003**: un proyecto personal pensado para resolver un problema médico-científico que terminó volviéndose la base de gran parte del ecosistema científico de Python. Pandas y Seaborn, por ejemplo, dibujan por debajo con Matplotlib."
## Slide 4 · Demanda laboral (05:30–06:30)

_Contenido sugerido para la diapositiva (poco texto):_

- **WEF, Future of Jobs 2025:** big data entre los roles de mayor crecimiento; pensamiento analítico = habilidad más buscada.
- **Avisos en Argentina:** SQL + Python + Power BI/Tableau (a veces Matplotlib y Seaborn).
- _1 o 2 capturas de avisos reales, con fecha._

"Un punto rápido sobre la demanda laboral. Según el Foro Económico Mundial, en su informe _Future of Jobs 2025_, entre los roles de más rápido crecimiento están los especialistas en big data, y el pensamiento analítico es la habilidad central más buscada: siete de cada diez empresas la consideran esencial.

En Argentina, los avisos de Data Analyst suelen pedir SQL, Python y una herramienta de dashboards como Power BI o Tableau, y algunos mencionan directamente Matplotlib y Seaborn. [mostrar captura] En resumen: no alcanza con analizar, hay que saber comunicar visualmente." `[CLIC]`

> **Fuentes de esta slide:** World Economic Forum, _The Future of Jobs Report 2025_ (publicado en enero de 2025; weforum.org). Avisos de ejemplo encontrados en la búsqueda (verificá que sigan activos y sacá captura con fecha): "Data Analyst – SQL / Python / Power BI (Híbrido, CABA)" en Indeed Argentina, que pide Python y Power BI y/o Tableau; y "Data Analyst" de Novo Space en Buenos Aires, que pide Power BI y Python con Pandas, NumPy, Matplotlib y Seaborn (figura como cerrado, usalo igual como ejemplo con la fecha o buscá uno vigente). Se eliminaron "Data Translator", el "70%" y las empresas nombradas (Globant, Mercado Libre, YPF) porque no tenían respaldo.

## Slide 5 · El Cuarteto de Anscombe (06:30–11:00)

_Con la slide de demanda laboral más corta, te sobra tiempo: usalo para mostrar bien los 4 gráficos y hacer una pausa._

"Antes de pasarle la palabra a X, un experimento clásico que demuestra por qué graficar es una etapa obligatoria del análisis.

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

La lección que nos brinda este caso es que **los mismos números pueden esconder realidades opuestas.** Sin el gráfico, tomamos decisiones basadas en ilusiones estadísticas. Y esta idea tiene una versión moderna, mucho más fácil de recordar. En 2016, el especialista en visualización Alberto Cairo creó el **Datasaurus**: un conjunto de puntos que, al graficarse, dibuja un dinosaurio. En 2017, dos investigadores de Autodesk, Justin Matejka y George Fitzmaurice, tomaron ese dinosaurio y generaron otros doce conjuntos con formas muy distintas —una estrella, un círculo, una X— que comparten con él la misma media, la misma desviación estándar y la misma correlación, hasta el segundo decimal. `[mostrar imagen del Datasaurus Dozen]` Es Anscombe, pero con un dinosaurio: **mismos números, dibujos completamente distintos.**

Link al informe de Datasaurus: https://cran.r-project.org/web/packages/datasauRus/vignettes/Datasaurus.html

Ahora X nos cuenta cómo está construido por dentro el software que nos permite ver esto." `[CLIC]`

---

# BLOQUE 2 (11:00–23:00)

## Slide 6 · El ecosistema analítico (11:00–12:30)

"Gracias, X. Buenas tardes a todos.

El ecosistema de visualización en Python es enorme, pero se ordena alrededor de tres librerías que llamamos la **tríada**.

**Matplotlib** es la librería madre: el motor de bajo nivel, con control total sobre cada elemento, a cambio de más código. **Seaborn** es una capa de alto nivel construida sobre Matplotlib, pensada para exploración estadística rápida con DataFrames de Pandas. Y por último, **Plotly** es el estándar para gráficos interactivos y web.

Para elegir entre ellas hay que entender qué pasa por dentro de cada una." `[CLIC]`

## Slide 7 · Arquitectura de Matplotlib (11:30–14:30)

_Contenido sugerido para la diapositiva:_ diagrama de 3 capas (Scripting → Artist → Backend) y, al costado, este mini-código para contrastar los dos estilos:

*Esta diapo la podemos dividir en 2 o 3, representando cada capa con ejemplos concretos*

```python
import matplotlib.pyplot as plt

# Estilo pyplot (estado global)
plt.plot([1, 2, 3], [1, 4, 9])
plt.title("pyplot")
plt.show()

# Estilo orientado a objetos (explícito)
fig, ax = plt.subplots()
ax.plot([1, 2, 3], [1, 4, 9])
ax.set_title("Orientado a objetos")
plt.show()
```

"Matplotlib está organizada en **tres capas**. Las vamos a ver de abajo hacia arriba, porque cada una se apoya en la anterior.

**Backend Layer.** Es la capa más baja y la que sabe producir una salida concreta. Se define con tres clases abstractas: `FigureCanvas`, el área sobre la que se dibuja; `Renderer`, que ejecuta el dibujo; y `Event`, que gestiona la entrada del usuario, como el mouse o el teclado. Hay backends no interactivos, que generan archivos —Agg produce imágenes PNG, y existen backends propios para PDF, SVG y PostScript— y backends interactivos, que muestran la figura en una ventana de escritorio, como Qt o Tk.

**Artist Layer.** Es el núcleo de la librería. Todo lo que se ve en una figura es un objeto `Artist`: líneas, textos, ejes, leyendas. Hay dos tipos: las **primitivas**, como `Line2D`, `Rectangle` o `Text`, y los **contenedores**, como `Figure`, `Axes` y `Axis`, que agrupan a otros artistas y forman una jerarquía. Cada Artist conoce sus coordenadas y sabe dibujarse a sí mismo cuando recibe un Renderer; para eso transforma coordenadas de datos en coordenadas de pantalla.

**Scripting Layer.** Es `pyplot`, una interfaz procedimental que imita a MATLAB. Mantiene un **estado global**: recuerda cuál es la figura y cuáles son los ejes actuales, y por eso `plt.plot()` funciona sin crear nada de forma explícita. Es muy cómodo para scripts cortos, pero en código más grande, con varias figuras, ese estado implícito se vuelve ambiguo.

Por eso, en software mantenible se usa la interfaz **orientada a objetos**: llamamos a `plt.subplots()` solo para crear la `Figure` y los `Axes`, y trabajamos con métodos explícitos como `ax.plot()` o `ax.set_title()`. Una aclaración de terminología: `Axes` es el área de dibujo con su sistema de coordenadas, y cada `Axes` contiene dos objetos `Axis`, el eje X y el eje Y. Una `Figure` puede tener varios `Axes`: son los subplots.

**Para resumir, con una analogía:** pensemos en un taller de impresión. `pyplot` es el pedido que le hacemos al asistente: 'dibujame una línea'. La capa Artist es el diseñador, que sabe qué elementos componen el dibujo y dónde va cada uno. Y el backend es la imprenta, que lo convierte en el producto final: un PNG, un PDF o una ventana en pantalla." `[CLIC]`

> Si vas justo de tiempo, podés omitir la frase de las transformaciones de coordenadas y los nombres de las primitivas (`Line2D`, `Rectangle`, `Text`). Para la diapositiva, cambiá la descripción del Backend, que dice "Habla con el SO local", por algo más preciso: "Renderiza a archivos (PNG, PDF, SVG) y a ventanas (Qt, Tk)". Corrección respecto de v3: Cairo es un backend opcional distinto; PDF y SVG tienen backends propios.

## Slide 8★ · Matplotlib: tipos de gráficos y sintaxis (14:30–17:00)

_Contenido sugerido para la diapositiva:_ la tabla de abajo + el código con su resultado (imagen `imagenes/matplotlib_ejemplo.png`).

*Esta diapo también podriamos divirla en dos: tabla con sintaxis - codigo y salida*


| Familia                   | Función                                                                              | Sintaxis básica                                  |
| ------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------ |
| Líneas                    | `ax.plot`                                                                            | `ax.plot(x, y, label="serie", color="tab:blue")` |
| Dispersión                | `ax.scatter`                                                                         | `ax.scatter(x, y, s=tamaños, c=colores)`         |
| Barras                    | `ax.bar` / `ax.barh`                                                                 | `ax.bar(categorias, alturas)`                    |
| Histograma                | `ax.hist`                                                                            | `ax.hist(datos, bins=20)`                        |
| Cajas                     | `ax.boxplot`                                                                         | `ax.boxplot(datos)`                              |
| Imágenes / mapas de calor | `ax.imshow`                                                                          | `ax.imshow(matriz, cmap="viridis")`              |
| Personalización           | `ax.set_title`, `set_xlabel`, `set_ylabel`, `set_xlim`, `legend`, `grid`, `annotate` | `ax.set_title("Título")`                         |
| Disposición y salida      | `plt.subplots`, `fig.tight_layout`, `fig.savefig`                                    | `fig.savefig("grafico.pdf")`                     |

**Código del ejemplo (completo):**

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0, 10, 100)
rng = np.random.default_rng(42)

fig, axs = plt.subplots(1, 3, figsize=(11, 3.4))

axs[0].plot(x, np.sin(x), label="sin(x)")
axs[0].plot(x, np.cos(x), label="cos(x)")
axs[0].set_title("plot: líneas")
axs[0].set_xlabel("x")
axs[0].legend()

axs[1].bar(["A", "B", "C"], [12, 7, 15], color="#4C78A8")
axs[1].set_title("bar: barras")
axs[1].set_ylabel("valor")

axs[2].hist(rng.normal(0, 1, 500), bins=20, color="#F58518")
axs[2].set_title("hist: histograma")
axs[2].set_xlabel("valor")

fig.tight_layout()
fig.savefig("matplotlib_ejemplo.png", dpi=150)
plt.show()
```

"Ya vimos cómo está construida Matplotlib; veamos qué nos ofrece. Los métodos del objeto `Axes` se agrupan en cuatro familias.

**Tipos de gráficos.** `plot` para líneas; `scatter` para dispersión, donde `s` controla el tamaño de los puntos y `c` el color; `bar` y `barh` para barras verticales y horizontales; `hist` para histogramas, con `bins` para la cantidad de intervalos; `boxplot` para diagramas de caja; e `imshow` para imágenes y mapas de calor.

**Personalización.** Una vez creado el gráfico, lo ajustamos con métodos que empiezan con `set_`: título, etiquetas y límites de los ejes; y con `legend`, `grid` y `annotate` para leyenda, grilla y anotaciones.

**Disposición y salida.** `plt.subplots` crea la `Figure` con una grilla de `Axes`, `tight_layout` acomoda los espacios, y `savefig` exporta: el formato lo define la extensión, `.png`, `.pdf` o `.svg`.

La sintaxis siempre sigue el mismo patrón: `ax.tipo_de_gráfico(datos, parámetros estéticos)`, y después los `set_*` para etiquetar. Parámetros como `color`, `label`, `alpha` o `linewidth` funcionan en casi todos.

**Veámoslo en el ejemplo.** `[mostrar código e imagen]` Creamos una `Figure` con tres `Axes` en una fila: `axs[0]`, `axs[1]` y `axs[2]`. En el primero, dos llamadas a `plot` con `label` y un `legend` dibujan seno y coseno. En el segundo, `bar` grafica tres categorías. En el tercero, `hist` agrupa 500 valores aleatorios en 20 intervalos. Cada `Axes` es independiente: tiene su propio título y sus propias etiquetas. Esto es el paradigma orientado a objetos en acción, y es el control que Matplotlib nos da." `[CLIC]`
## Slide 8 · El motor estadístico de Seaborn (15:30–17:45)

"Con Matplotlib, nosotros agrupamos, filtramos y calculamos promedios con Pandas antes de graficar. **Seaborn** trabaja directamente sobre el DataFrame. Cuando ejecutamos algo como `sns.lineplot()` o `sns.barplot()`, internamente:

1. **Agrega** los datos: agrupa por categorías y calcula la medida de resumen, por defecto la media.
2. **Estima la incertidumbre**: por defecto usa _bootstrapping_, un remuestreo repetido, para calcular intervalos de confianza del 95 % y dibujarlos como bandas o barras de error.
3. **Aplica paletas** y estilos pensados para la percepción visual.
4. **Traduce todo a objetos Artist de Matplotlib** y los dibuja.

Seaborn nos da velocidad en la fase exploratoria. A cambio, cedemos control fino y, cuando necesitamos personalizar a fondo, bajamos a Matplotlib; de hecho, los gráficos de Seaborn son objetos de Matplotlib." `[CLIC]`

> ⚠ Se quitó "Millones de filas crudas" de la diapositiva: el bootstrapping sobre datos muy grandes es lento, así que no es un punto fuerte de Seaborn.

## Slide 9 · Seaborn: funcionamiento y ejemplo (17:00–19:30)

_Contenido sugerido para la diapositiva:_ código + resultado (imagen `imagenes/seaborn_ejemplo.png`) y una línea con las familias de funciones.

**Código del ejemplo (completo):**

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.set_theme(style="whitegrid")
tips = sns.load_dataset("tips")      # DataFrame de Pandas: una fila por cuenta

ax = sns.barplot(data=tips, x="day", y="total_bill", hue="sex")
ax.set_title("Cuenta promedio por día y sexo")
ax.set_ylabel("Cuenta total promedio (USD)")
sns.move_legend(ax, "upper left", bbox_to_anchor=(1, 1))

plt.tight_layout()
plt.show()
```

"**Funcionamiento.** Seaborn es una capa de alto nivel construida sobre Matplotlib que trabaja directamente sobre un DataFrame de Pandas en formato _tidy_: una fila por observación y una columna por variable. En lugar de pasarle listas de números, le indicamos qué columna cumple cada rol visual con tres parámetros: `data`, el DataFrame; `x` e `y`, las columnas de cada eje; y `hue`, la columna que define el color.

Sus funciones se agrupan por el tipo de pregunta que responden: relacionales, como `scatterplot` y `lineplot`; de distribución, como `histplot` y `kdeplot`; categóricas, como `boxplot`, `barplot` y `countplot`; de regresión, como `regplot` y `lmplot`; matrices, como `heatmap`; y grillas de varios gráficos, como `pairplot`.

Y cuando ejecutamos una de ellas, internamente: primero **agrupa** los datos y calcula una medida de resumen, por defecto la media; segundo, **estima la incertidumbre** con _bootstrapping_, un remuestreo repetido, para calcular un intervalo de confianza del 95 %; tercero, aplica una paleta de colores; y cuarto, **traduce todo a objetos de Matplotlib** y los dibuja.

**Veámoslo en el ejemplo.** `[mostrar código e imagen]` Usamos el dataset `tips`: una fila por cuenta de un restaurante. Con una sola línea, `sns.barplot`, le decimos: tomá el DataFrame, poné el día en X, la cuenta total en Y y separá por color según el sexo. Seaborn agrupa por día y sexo, calcula la cuenta promedio de cada grupo y dibuja las barras, con una línea negra que muestra el intervalo de confianza del 95 %. Nosotros no calculamos ninguna media. Fíjense que el viernes tiene intervalos muy anchos: hay pocas observaciones, y el gráfico lo comunica sin que se lo pidamos. Además, la función devuelve un `Axes` de Matplotlib, así que seguimos personalizando con `set_title` y `set_ylabel`.

**En resumen, con una analogía:** con Matplotlib calculamos y dibujamos nosotros, como hacer las cuentas y el gráfico a mano. Seaborn es como tener un analista que ya resumió la tabla y solo nos pide que le digamos qué comparar." `[CLIC]`

## Slide 10 · Plotly: funcionamiento y ejemplo (19:30–22:00)

_Contenido sugerido para la diapositiva:_ código + **captura de la figura abierta en el navegador o en Jupyter, mostrando un tooltip** (no es una imagen que se pueda generar sin navegador: sacala vos corriendo el código). Sumá un esquema mínimo: Python → JSON → Plotly.js.

**Código del ejemplo (completo):**
```python
import plotly.express as px

tips = px.data.tips()     # dataset incluido en Plotly

fig = px.scatter(
    tips,
    x="total_bill", y="tip",
    color="day",
    hover_data=["sex", "size"],
    title="Propina vs. cuenta total"
)

fig.show()
```

"**Funcionamiento.** Plotly ofrece dos interfaces. `plotly.express` es la de alto nivel: una sola llamada crea un gráfico completo, con funciones como `px.scatter`, `px.line`, `px.bar`, `px.histogram` o `px.box`. `plotly.graph_objects` es la de bajo nivel: construimos la figura trazo por trazo con `go.Figure` y `go.Scatter`, con control total.

Las dos producen el mismo objeto: una `Figure`, que en esencia es un diccionario con dos claves: `data`, una lista de **trazas**, donde cada traza es una serie con su tipo de gráfico; y `layout`, que guarda títulos, ejes y márgenes.

Cuando llamamos a `fig.show()`, Python no dibuja nada: **serializa** esa figura a JSON y se la entrega al navegador, o a la celda de Jupyter. Ahí, la librería JavaScript **Plotly.js** la renderiza, por defecto como SVG, y con WebGL cuando hay muchísimos puntos. Por eso el zoom, el desplazamiento, el filtrado desde la leyenda y los tooltips los procesa el navegador, no el kernel de Python.

**Veámoslo en el ejemplo.** `[mostrar código y captura]` Con el mismo dataset `tips`, una sola llamada a `px.scatter` arma un gráfico de dispersión con la cuenta total en X y la propina en Y, un color distinto por cada día, y con `hover_data` agregamos al tooltip el sexo y el tamaño del grupo. Lo que ven no es una imagen estática: si paso el cursor sobre un punto, aparece su información; si hago clic en un día de la leyenda, lo oculto; y si hago zoom, el gráfico se reencuadra.

**En resumen, con una analogía:** Python escribe la receta, el JSON, y el navegador cocina el plato." `[CLIC]`

## Slide 11 · Principios de diseño (22:00–23:30)

"Que el código funcione no alcanza. Para seguir los principios del diseño debemos aplicar las siguientes reglas prácticas:
* **Maximizar el data-ink ratio de Tufte.** La mayor parte de la tinta debe representar datos: fuera bordes pesados, fondos oscuros y grillas recargadas.
* **Evitar el chartjunk.** Los gráficos 3D de torta o de barras se desaconsejan dado la perspectiva distorsiona la percepción del área.
* **Color con intención.** El color es una codificación de datos, no decoración: paletas categóricas para variables cualitativas, secuenciales o divergentes para cuantitativas.
* **Accesibilidad.** Cuidamos el contraste, siguiendo criterios como los de WCAG, y usamos paletas perceptualmente uniformes como Viridis o Cividis, que se leen bien también con daltonismo." `[CLIC]`

## Slide 12★ · Comparativa, ventajas y desventajas (21:15–23:00)

_Contenido sugerido para la diapositiva (tabla):_

|Herramienta|Ventajas|Desventajas|Cuándo usarla|
|---|---|---|---|
|**Matplotlib**|Control total; salida vectorial (PDF/SVG); base del ecosistema|Verboso; curva de aprendizaje alta; estética por defecto básica|Publicaciones y reportes estáticos|
|**Seaborn**|Rápido; estadística integrada; buena estética|Menos control fino; depende de Matplotlib|EDA (exploración inicial)|
|**Plotly**|Interactivo; despliegue web; integra con Dash/Streamlit|HTML pesado con muchos datos; menos control para impresión|Dashboards y apps|
|**Otras**|Altair/Bokeh (declarativo / interactivo), ggplot2 (R), Power BI/Tableau (BI sin código)|Menos flexibles, otro ecosistema o licencias|Según equipo y contexto|

"Sintetizamos en una matriz.

**Matplotlib**: cuenta con control total y salida de calidad de publicación, a cambio de más código y una curva alta. **Seaborn**: rapidez y estadística lista, a cambio de menos control fino. **Plotly**: interactividad y despliegue web, pero con muchísimos puntos el HTML se vuelve pesado y no es ideal para imprimir.

Y existen alternativas: **Altair**, declarativo, y **Bokeh**, también interactivo; **ggplot2** en R; y herramientas de BI como **Power BI** o **Tableau**, que no requieren programar pero ofrecen menos flexibilidad y suelen estar sujetas a licencias. Para nichos: **Missingno** para datos faltantes, y **Folium** y **GeoPandas** para mapas.

La conclusión: no hay una mejor herramienta, hay una mejor herramienta **para cada restricción**. Y eso es lo que X va a mostrar en vivo." `[CLIC]`

---

# BLOQUE 3 (23:00–35:00)

## Slide 12 · Live Demo "El Viaje del Dato" (23:00–31:30)

**Intro (23:00–24:30)**

"Gracias, Laureano. En vez de hacer el mismo gráfico en tres librerías, armamos un flujo de trabajo real, **'El Viaje del Dato'**. Tomamos un dataset de siniestralidad vial y lo hacemos pasar por tres etapas:

1. **Exploración rápida** (Missingno y Seaborn): ¿los datos están completos?, ¿qué relaciones hay?
2. **Refinamiento estático** (Matplotlib orientado a objetos): una figura lista para un informe.
3. **Interactivo** (Plotly Express): el mismo hallazgo, ahora explorable en el navegador.

Comparto pantalla."

**Notebook completo (para copiar y ejecutar)**

```python
# ───────────── Paso 0: entorno ─────────────
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
import missingno as msno

plt.style.use('seaborn-v0_8-whitegrid')

# Dataset incluido en Seaborn (requiere internet la primera vez)
df = sns.load_dataset('car_crashes')
df.to_csv('car_crashes.csv', index=False)   # respaldo por si falla la conexión en la demo
df.head()
```

```python
# ───────────── Paso 1: auditoría y EDA ─────────────
# 1.1 Auditoría visual de datos faltantes
ax = msno.matrix(df, sparkline=False, figsize=(6, 2))
ax.set_title("Auditoría visual de integridad de datos", fontsize=10)
plt.show()

# (Opcional, para que la matriz muestre algo) simular faltantes en una copia:
# df_sucio = df.copy()
# df_sucio.loc[[3, 10, 25], 'alcohol'] = None
# msno.matrix(df_sucio, sparkline=False, figsize=(6, 2)); plt.show()

# 1.2 Relaciones entre variables con Seaborn
g = sns.pairplot(df, vars=['total', 'speeding', 'alcohol'],
                 corner=True, diag_kind='kde')
g.figure.suptitle("EDA rápido: accidentes totales vs. alcohol y velocidad", y=1.02)
plt.show()

# 1.3 El número detrás del gráfico
df[['total', 'speeding', 'alcohol']].corr().round(2)
```

```python
# ───────────── Paso 2: figura estática (Matplotlib OO) ─────────────
fig, ax = plt.subplots(figsize=(9, 4.5), dpi=100)

scatter = ax.scatter(
    df['alcohol'], df['total'],
    c=df['speeding'], cmap='viridis',
    s=(df['not_distracted'] - df['not_distracted'].min() + 5) * 4,  # tamaño legible
    alpha=0.85, edgecolors='white', linewidths=0.5
)

# Data-ink ratio: quitar bordes que no aportan
for side in ['top', 'right']:
    ax.spines[side].set_visible(False)
for side in ['left', 'bottom']:
    ax.spines[side].set_color('#cccccc')

ax.grid(axis='x', visible=False)
ax.grid(axis='y', linestyle='--', alpha=0.4)

ax.set_title("Alcohol y siniestralidad vial fatal por estado (EE. UU.)",
             fontsize=12, fontweight='bold', pad=12)
ax.set_xlabel("Conductores en choques fatales con alcohol (por mil millones de millas)\n"
              "Tamaño del punto: % de conductores no distraídos", fontsize=10)
ax.set_ylabel("Conductores en choques fatales (por mil millones de millas)", fontsize=10)

cbar = fig.colorbar(scatter, ax=ax)
cbar.set_label('Exceso de velocidad', fontsize=9)
cbar.outline.set_visible(False)

fig.tight_layout()
fig.savefig('siniestralidad.pdf', bbox_inches='tight')   # backend vectorial PDF
plt.show()
```

```python
# ───────────── Paso 3: versión interactiva (Plotly Express) ─────────────
fig_plotly = px.scatter(
    df,
    x='alcohol', y='total',
    color='speeding', size='not_distracted', size_max=18,
    hover_name='abbrev',
    color_continuous_scale='Viridis',
    title="<b>Siniestralidad vial por estado (interactivo)</b>",
    labels={
        'alcohol': 'Choques fatales con alcohol (por mil millones de millas)',
        'total': 'Choques fatales totales (por mil millones de millas)',
        'speeding': 'Exceso de velocidad',
        'not_distracted': '% no distraídos'
    },
    template='plotly_white'
)

fig_plotly.show()

# Mostrar la "receta": la especificación JSON que viaja al navegador
print(fig_plotly.to_json()[:400])

# Exportar una página web independiente
fig_plotly.write_html('siniestralidad_interactivo.html')
```

> ⚠ Cambios en el código respecto de v3: (1) faltaba cargar `df`; (2) varias instrucciones estaban pegadas en una sola línea (error de sintaxis); (3) `s=not_distracted*10` generaba burbujas enormes y casi iguales (el rango es angosto); (4) Plotly ahora usa **la misma codificación** que Matplotlib (color = velocidad, tamaño = no distraídos) para que sea realmente "el mismo hallazgo"; (5) se agrega `to_json()` y `write_html()` para mostrar en vivo lo que se explicó en la slide de Plotly; (6) las unidades de `car_crashes` son _conductores involucrados en choques fatales por mil millones de millas_, no "siniestros por cada 10.000 habitantes"; (7) se quitó `numpy` por no usarse.

**Narración**

**Paso 0 (24:30–25:00).** "Importamos Pandas y las tres librerías de la tríada, más Missingno. Cargamos `car_crashes`, un dataset de choques fatales por estado de EE. UU. Guardamos un CSV por si falla internet."

**Paso 1 (25:00–27:00).** "Primero, ¿están completos los datos? `msno.matrix` dibuja una fila por registro y deja en blanco lo faltante. Acá todo es negro: el dataset está completo, que es una conclusión válida de la auditoría; en datos reales verían franjas blancas. [Opcional: mostrar la copia con faltantes.]

Después, una sola línea de Seaborn, `pairplot`: densidades en la diagonal y dispersogramas en las esquinas. A simple vista, el alcohol muestra una relación positiva fuerte con el total. Y `.corr()` nos da el número exacto: el gráfico sugiere, la estadística confirma."

**Paso 2 (27:00–29:30).** "Ahora preparamos una figura para un informe, con Matplotlib orientado a objetos. Creamos `fig` y `ax` de forma explícita, sin depender del estado global. Quitamos los bordes superior y derecho —data-ink ratio—, suavizamos la grilla y usamos Viridis. Codificamos **cuatro variables en un plano**: eje X, eje Y, color y tamaño. Y exportamos a PDF: ahí actúa el backend vectorial del que habló Laureano.

Una aclaración de rigor: esto muestra **asociación, no causalidad**, y como 'total' ya incluye a los conductores con alcohol, parte de la relación es esperable por construcción."

**Paso 3 (29:30–31:30).** "Por último, el mismo hallazgo en Plotly Express. Pasamos el mismo DataFrame y casi la misma codificación. `show()` abre el gráfico: paso el cursor y el `hover_name` me dice qué estado es; hago zoom, oculto categorías, y con el ícono de cámara descargo un PNG. Y esto es lo que viaja al navegador: [mostrar `to_json()`] la especificación JSON, la receta. Con `write_html` queda un archivo web independiente que se puede compartir." `[CLIC]`

## Slide 13 · Conclusión y preguntas (31:30–35:00)

"Para cerrar, volvamos a los tres objetivos.

**Arquitectura:** vimos que Matplotlib son tres capas, Seaborn agrega estadística sobre Matplotlib, y Plotly serializa a JSON y delega en el navegador. **Paradigmas:** procedimental, orientado a objetos, agregación automática y especificación declarativa. **Criterio de selección:** Seaborn y Missingno para explorar; Matplotlib cuando necesitamos control absoluto o salida de publicación; Plotly para interactividad y web.

No hay que casarse con una librería: la excelencia es un **flujo híbrido**. Y, como mostró Anscombe, ninguna decisión debería apoyarse solo en una tabla de números sin haber mirado el gráfico.

El notebook y el código quedan a disposición de la cátedra [COMPLETAR: link o QR]. Muchas gracias; quedamos abiertos a sus preguntas."

---

# Anexo A — Preguntas probables

1. **¿Por qué no usar solo Plotly, si es interactivo?** Porque para publicaciones impresas o PDF se necesita control fino y salida vectorial, y Matplotlib lo ofrece; además, con muchos puntos los HTML de Plotly se vuelven pesados.
2. **¿Matplotlib está obsoleto?** No: es la base de Seaborn y de `DataFrame.plot()` de Pandas. Lo que cambió es que hoy se usa más a través de capas de mayor nivel.
3. **¿Por qué la correlación alcohol–total no prueba que el alcohol cause más accidentes?** Es asociación entre estados; hay variables no incluidas, y además "total" contiene a los conductores con alcohol, así que parte de la relación es mecánica. Para causalidad se necesita otro diseño de análisis.
4. **¿Y las herramientas de BI (Power BI, Tableau)?** Son una alternativa válida cuando no se requiere programar o el equipo ya las usa; Python ofrece más flexibilidad y se integra con pipelines de datos y automatización.
5. **¿Por qué importa Anscombe si ya existen tests estadísticos?** Porque los resúmenes numéricos pueden coincidir en datasets muy distintos; el gráfico es una verificación complementaria de los supuestos del modelo.

# Anexo B — Checklist antes de ensayar

- [ ] Slide 2★ (Objetivos) y slide 11★ (Comparativa) agregadas.
- [ ] Slide 3 de la presentación original ("historia"): Tufte → **1983**.
- [ ] Slide de mercado laboral: reemplazar "70%" por dato propio verificable.
- [ ] Slide de Seaborn: quitar "Millones de filas crudas".
- [ ] Slide de principios de diseño: "Prohibición…" → "Evitar…"; "Contrastes WCAG certificados" → "Contraste accesible (WCAG)".
- [ ] Slide de fuentes: sumar bibliografía (Tufte 1983, Anscombe 1973, Hunter 2007, documentación oficial de las tres librerías).
- [ ] Correr el notebook completo en la máquina de la demo, con y sin internet.
- [ ] Cronometrar cada bloque en voz alta; apuntar a 11 / 12 / 12 minutos.
- [ ] Reemplazar los `[COMPLETAR]` y confirmar los `⚠ VERIFICAR`.