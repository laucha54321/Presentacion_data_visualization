---
area: UTN
tipo: tp
materia: Seminario de Soporte
tags:
  - python
  - data-visualization
  - matplotlib
  - seaborn
  - plotly
  - demo
---

# Guion de Exposición — Demostración Práctica (`demo.ipynb`)

**Referencia cruzada:** [[Guíon Seminario]] · **Notebook:** `demo.ipynb`  
**Tiempo estimado total:** ~5 a 6 minutos

---

## 1. Introducción y Enfoque de la Demostración

> **Indicación en escena:** *Compartir pantalla en Jupyter Notebook, situarse en el encabezado del notebook y mirar a la audiencia antes de ejecutar las celdas.*

"Para poner a prueba los conceptos arquitectónicos que explicamos en la teoría, preparamos esta demostración práctica en vivo. 

Cuando se comparan herramientas de visualización, con frecuencia se comete el error pedagógico de graficar exactamente lo mismo —por ejemplo, un gráfico de barras elemental— en las tres librerías. Ese enfoque desaprovecha el potencial de cada una. En este análisis planteamos un flujo de trabajo real sobre una problemática climática, donde cada herramienta entra en acción para hacer aquello en lo que realmente brilla:

* **Matplotlib** lo empleamos para lograr control milimétrico sobre el lienzo y una salida de calidad editorial.
* **Seaborn** lo utilizamos como laboratorio de agregación y modelado estadístico automatizado.
* **Plotly** lo reservamos para la dimensión interactiva y la exploración espacio-temporal en el navegador."

---

## 2. Los Datos: Origen, Naturaleza y Tratamiento de la Información

> **Indicación en escena:** *Avanzar y ejecutar las celdas 1 a 7 (Sección 1 y 2 del notebook).*

"Antes de tocar cualquier gráfico, el primer paso de ingeniería consiste en auditar nuestra materia prima: los datos. En este notebook utilizamos un **dataset climático sintético**, generado algorítmicamente mediante NumPy y Pandas.

Conviene despejar de entrada una duda fundamental: ¿por qué es sintético y qué tan representativo resulta? 

Por un lado, el motivo de diseño es la robustez y la reproducibilidad: al crearse dentro del propio código, la demostración es completamente autocontenida. No dependemos de conectividad externa ni de descargar archivos pesados que puedan fallar en vivo. 

Por otro lado, es crucial destacar que **no son datos ficticios inventados al azar**. El generador numérico sigue con estricta fidelidad las órdenes de magnitud, tendencias históricas y escalas reales documentadas por organismos de referencia como *Our World in Data*. Cubre el período que va desde **1960 hasta 2023** para diez países representativos de todos los continentes, entre ellos Argentina, Brasil, Estados Unidos, China, Alemania, India y Nigeria.

El dataset registra para cada país y año su población, sus emisiones de dióxido de carbono totales y per cápita, y la anomalía de temperatura global. Además, modela deliberadamente fenómenos históricos reales, como la abrupta caída de emisiones provocada por las restricciones sanitarias de 2020. 

Asimismo, incorporamos una dificultad clásica de las series temporales climáticas: la presencia de **valores nulos o huecos de registro**. Esto refleja la realidad de países que recién comenzaron a medir de forma sistemática en los años setenta. Para tratarlos, aplicamos una interpolación lineal por país sobre las columnas de dióxido de carbono, partiendo de la premisa física de que las emisiones de una nación evolucionan gradualmente entre años conocidos y no a saltos discretos."

---

## 3. Matplotlib — Control Total: Doble Eje y Precisión Editorial

> **Indicación en escena:** *Ejecutar las celdas 10 a 12 (Sección 3 del notebook).*

"Iniciamos el recorrido visual con la biblioteca fundacional: **Matplotlib**. 

Si pensamos en una analogía cotidiana, Matplotlib funciona como el taller de un pintor o una imprenta de precisión: nos exige trabajar artesanalmente línea por línea (acá escribimos cerca de cuarenta líneas de código), pero a cambio nos otorga un control absoluto sobre cada milímetro y píxel del lienzo.

Para evidenciar esta fortaleza, construimos un gráfico histórico global que combina dos variables de magnitudes completamente distintas mediante un **doble eje Y** utilizando el método `twinx()`. Sobre el eje izquierdo representamos el volumen global de emisiones de CO₂ en megatoneladas, y sobre el eje derecho, la anomalía de temperatura media del planeta.

La ventaja de este enfoque radica en la precisión editorial:
* Trazamos **anotaciones personalizadas con flechas** apuntando con exactitud matemática a hitos geopolíticos clave: la firma del Protocolo de Kyoto en 1997, el Acuerdo de París en 2015 y la caída por el confinamiento de 2020.
* Integramos un sombreado semitransparente para delimitar el área de calentamiento global más pronunciado.
* Consolidamos las leyendas de ambos ejes en un único bloque visual limpio.

Construir este nivel de detalle gráfico con herramientas de mayor abstracción suele resultar sumamente complejo. Matplotlib es la herramienta indicada cuando el destino de la figura es un informe institucional, una tesis o un artículo científico donde ningún elemento puede quedar librado al azar."

---

## 4. Seaborn — El Laboratorio Estadístico Automatizado

> **Indicación en escena:** *Ejecutar las celdas 13 a 20 (Sección 4 del notebook).*

"Pasamos a la segunda herramienta: **Seaborn**. 

Siguiendo nuestra analogía, si Matplotlib es el pincel fino, Seaborn es un asistente de laboratorio estadístico de alto nivel. Su paradigma consiste en operar directamente sobre DataFrames en formato tabular limpio, asumiendo por su cuenta los cálculos matemáticos que de otro modo tendríamos que programar a mano.

En el notebook resolvemos tres interrogantes analíticos en tan solo unas quince líneas de código cada uno:

1. **Regresión y facetado regional con `lmplot`**: dividimos el comportamiento temporal por continentes. Mediante un único parámetro (`col='continent'`), la librería subdivide la figura en paneles independientes, ajusta una recta de regresión lineal para cada región y calcula de forma automática bandas sombreadas de incertidumbre al 95 % de confianza mediante remuestreo estadístico (*bootstrapping*).
2. **Matriz de correlación con `heatmap`**: evaluamos cómo se relacionan entre sí las variables del problema. Con una única llamada obtenemos un mapa térmico con escala cromática divergente, centrada en cero, donde cada celda incluye su valor numérico exacto para identificar correlaciones fuertes entre emisiones y temperatura en una fracción de segundo.
3. **Distribución completa mediante `violinplot`**: en lugar de recurrir a un diagrama de caja tradicional que solo resume cuartiles, el gráfico de violín grafica la función de densidad de probabilidad continua de las emisiones per cápita, permitiendo comparar la dispersión y asimetría de cada continente.

Seaborn nos permite acelerar la etapa exploratoria, produciendo análisis estadísticamente sólidos con una economía de código notable."

---

## 5. Plotly — Interactividad, Animación y la Web

> **Indicación en escena:** *Ejecutar las celdas 21 a 26 (Sección 5 del notebook). Interactuar con el mouse: pasar el cursor para mostrar tooltips y accionar el botón de Play del slider.*

"Finalmente, abordamos la tercera pieza: **Plotly**.

Hasta este punto, todas las visualizaciones eran estáticas: imágenes fijas ideales para imprimir. Sin embargo, en entornos corporativos o plataformas web interactivas, los usuarios necesitan manipular la información de forma autónoma.

Aquí entra en juego la arquitectura cliente-servidor de Plotly: el kernel de Python no dibuja los píxeles, sino que elabora una especificación estructurada en formato JSON y se la entrega al navegador. Es el motor JavaScript de Plotly.js el que procesa la interacción en tiempo real.

Con apenas diez a doce líneas de código desarrollamos dos visualizaciones de alto impacto:

1. **Mapa coroplético animado (`px.choropleth`)**: utilizando los códigos internacionales ISO de cada nación, proyectamos las emisiones geográficamente. Al presionar el botón de reproducción (*Play*) en el control deslizante, vemos cómo los países transicionan de tonalidad año tras año. Al posicionar el cursor sobre cualquier territorio, el navegador despliega de inmediato una ventana emergente con el valor exacto de toneladas per cápita.
2. **Gráfico de burbujas animado estilo Hans Rosling (`px.scatter`)**: esta visualización alcanza la máxima densidad de información multidimensional, integrando simultáneamente cinco variables:
   * En el eje horizontal, las emisiones de CO₂ per cápita.
   * En el eje vertical, la anomalía térmica.
   * En el tamaño relativo de cada burbuja, la población de cada país.
   * En la paleta de color, la pertenencia continental.
   * En la animación temporal interactiva, la evolución cronológica entre 1960 y 2023.

El usuario puede pausar, hacer zoom sobre un cuadrante específico, aislar continentes haciendo clic en la leyenda o rastrear la trayectoria de un país individual."

---

## 6. Cierre Integrador: Criterio de Selección de Herramientas

> **Indicación en escena:** *Mostrar la tabla comparativa final en la celda 27 y volver la mirada al auditorio.*

"Para concluir la demostración y conectar la práctica con los objetivos de nuestra materia, la lección central es que **no existe una librería intrínsecamente superior a las demás**. El criterio profesional radica en elegir la herramienta adecuada en función de las restricciones del proyecto:

* Optamos por **Seaborn** cuando recibimos un volumen de datos crudo y requerimos exploración estadística rápida y fiable.
* Seleccionamos **Matplotlib** cuando el producto final es un documento estático, una memoria técnica o una publicación académica que exige precisión artesanal.
* Implementamos **Plotly** cuando la comunicación se orienta a paneles de control interactivos, aplicaciones web o toma de decisiones ejecutiva.

El flujo de trabajo óptimo en ingeniería de datos no es excluyente sino complementario: exploramos con Seaborn, refinamos con Matplotlib y publicamos con Plotly."

---

## Guía Rápida para Preguntas de la Cátedra

| Pregunta probable | Respuesta técnica fundamentada |
| :--- | :--- |
| **¿Por qué usaron datos sintéticos y no una descarga directa en vivo?** | *Por reproducibilidad e higiene en la demo: evitamos dependencias de red o caídas de servidores externos en la presentación. Los datos replican con exactitud las escalas y tendencias de Our World in Data e incorporan problemáticas reales como vacíos muestrales.* |
| **¿Por qué no resolvieron el gráfico de dos ejes con Seaborn?** | *Porque Seaborn está optimizado para relaciones estadísticas sobre ejes compartidos. Superponer un segundo eje con escala independiente (`twinx`) y trazar flechas vectoriales pixel a pixel requiere descender directamente a la capa Artist de Matplotlib.* |
| **¿Qué costo tiene la interactividad de Plotly?** | *El peso del documento. Dado que la figura transporta los datos en formato JSON para que el navegador los renderice, un conjunto con cientos de miles de puntos generaría archivos HTML sumamente pesados, escenario donde las imágenes rasterizadas o vectoriales de Matplotlib resultan más eficientes.* |
