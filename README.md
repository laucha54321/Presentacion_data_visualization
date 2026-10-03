# Visualización de datos en Python: Matplotlib vs. Seaborn vs. Plotly

Trabajo práctico que compara las tres librerías de gráficos más usadas en Python
graficando **el mismo dataset** con cada una.

## Contenido del repositorio

| Archivo | Para qué sirve |
|---|---|
| `demo.ipynb` | Notebook con los gráficos y la comparación |
| `requirements.txt` | Lista de librerías necesarias |
| `.gitignore` | Archivos que git no debe guardar |

## El dataset

Usamos `tips`, un dataset de ejemplo que viene con Seaborn: 244 mesas de un
restaurante, con el total de la cuenta, la propina, el día, si fue almuerzo o cena
y la cantidad de personas.

## Qué se compara

El notebook hace cuatro tipos de gráfico, cada uno con las tres librerías:

1. **Dispersión**: propina vs. cuenta total, por almuerzo/cena
2. **Barras**: propina promedio por día
3. **Histograma**: distribución del monto de las cuentas
4. **Boxplot**: cuenta total por día

Los tres usan los mismos colores, títulos y etiquetas, así las diferencias se deben
a la librería y no a decisiones de diseño. Al final hay una tabla con las conclusiones.

## Cómo ejecutarlo (Windows)

### 1. Instalar Python (una sola vez)

Descargá Python 3.12 o superior desde <https://www.python.org/downloads/>.
En el instalador, **tildá "Add python.exe to PATH"** antes de hacer clic en *Install*.

Para comprobar que quedó instalado, abrí una terminal nueva y escribí:

```powershell
python --version
```

### 2. Crear un entorno virtual

Un entorno virtual es una carpeta (`.venv`) con una copia de Python solo para este
proyecto, para que sus librerías no se mezclen con las de otros. Desde la carpeta
del proyecto:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

Si PowerShell avisa que la ejecución de scripts está deshabilitada, ejecutá esto
una sola vez y volvé a intentar:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

Cuando el entorno está activo, la terminal muestra `(.venv)` al principio de la línea.

### 3. Instalar las librerías

```powershell
pip install -r requirements.txt
```

### 4. Abrir el notebook

- **En VS Code:** abrí `demo.ipynb`, hacé clic en *Select Kernel* (arriba a la derecha) y elegí `.venv`.
- **En el navegador:** ejecutá `jupyter notebook demo.ipynb`.

Después ejecutá las celdas en orden con `Shift + Enter`. La primera vez hace falta
internet, porque `sns.load_dataset("tips")` descarga el dataset.

## Nota sobre los gráficos de Plotly

Los gráficos de Plotly son interactivos y se ven al ejecutar el notebook en VS Code
o Jupyter. GitHub muestra los notebooks como imagen estática, así que **en la
página de GitHub los gráficos de Plotly no aparecen**; los de Matplotlib y Seaborn sí.
