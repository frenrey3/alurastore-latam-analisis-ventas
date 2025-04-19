# AluraStore LATAM: Análisis de Ventas y Recomendación de Tienda

## Descripción General del Proyecto

Este proyecto analiza datos de ventas de cuatro tiendas diferentes de AluraStore LATAM (Tienda_1, Tienda_2, Tienda_3, Tienda_4). El objetivo principal es evaluar el desempeño de cada tienda basándose en diversas métricas y proporcionar una recomendación fundamentada en datos al "Sr. Juan" sobre la tienda más conveniente para vender sus productos.

El análisis implica la carga, limpieza, procesamiento y visualización de datos de ventas para comparar las tiendas según ingresos, popularidad de categorías de producto, satisfacción del cliente (calificaciones) y costos de envío.

## Tabla de Contenidos

1.  [Objetivo](#objetivo)
2.  [Conjunto de Datos](#conjunto-de-datos)
3.  [Metodología](#metodología)
4.  [Resultados Clave](#resultados-clave)
5.  [Recomendación](#recomendación)
6.  [Visualizaciones](#visualizaciones)
7.  [Tecnologías Utilizadas](#tecnologías-utilizadas)
8.  [Configuración y Uso](#configuración-y-uso)
9.  [Trabajo Futuro](#trabajo-futuro)
10. [Autor](#autor)

## Objetivo

Analizar los datos de ventas de cuatro tiendas de AluraStore LATAM para comprender su desempeño y recomendar la tienda más conveniente para que el Sr. Juan venda sus productos.

## Conjunto de Datos

Los datos consisten en cuatro archivos CSV separados, uno para cada tienda, alojados en GitHub:

*   **Repositorio Fuente:** [alura-es-cursos/challenge1-data-science-latam](https://github.com/alura-es-cursos/challenge1-data-science-latam/tree/main/base-de-datos-challenge1-latam)
*   **Archivos:** `tienda_1 .csv`, `tienda_2.csv`, `tienda_3.csv`, `tienda_4.csv`

Cada archivo contiene datos transaccionales de ventas que incluyen:
*   Nombre del Producto (`Producto`)
*   Categoría del Producto (`Categoría del Producto`)
*   Precio (`Precio`)
*   Costo de envío (`Costo de envío`)
*   Fecha de Compra (`Fecha de Compra`)
*   Vendedor (`Vendedor`)
*   Lugar de Compra (`Lugar de Compra`)
*   Calificación del Cliente (`Calificación`)
*   Método de pago (`Método de pago`)
*   Cantidad de cuotas (`Cantidad de cuotas`)
*   Coordenadas Geográficas (`lat`, `lon`)

El notebook carga estos archivos directamente desde sus URL de GitHub sin procesar.

## Metodología

El análisis sigue estos pasos dentro del notebook `AluraStoreLatam.ipynb`:

1.  **Carga y Combinación de Datos:** Importar las bibliotecas necesarias (`pandas`, `matplotlib`, `seaborn`) y cargar los cuatro archivos CSV desde las URLs. Se añade una columna 'Tienda' para identificar la fuente antes de concatenarlos en un único DataFrame.
2.  **Limpieza y Preprocesamiento de Datos:**
    *   Inspección inicial de tipos de datos y valores faltantes.
    *   Manejo de valores nulos en columnas críticas (`Precio`, `Calificación`, etc.).
    *   Conversión de tipos de datos (numéricos, datetime, categóricos). Las fechas se procesan con manejo de errores.
    *   Eliminación de filas duplicadas.
    *   Optimización del uso de memoria convirtiendo columnas relevantes al tipo 'category'.
3.  **Análisis Exploratorio de Datos (EDA):** Calcular y comparar métricas clave entre las cuatro tiendas:
    *   Ingresos Totales por Tienda.
    *   Cantidad Total de Ventas por Categoría de Producto.
    *   Calificación Promedio del Cliente por Tienda.
    *   Productos Más y Menos Vendidos (General).
    *   Costo de Envío Promedio por Tienda.
4.  **Visualización:** Generar gráficos utilizando Matplotlib y Seaborn para representar visualmente los hallazgos del EDA, incluyendo:
    *   Gráfico de barras comparando ingresos totales.
    *   Gráfico de barras mostrando la distribución de ventas por categoría.
    *   Gráfico de barras comparando las calificaciones promedio de los clientes.
    *   Gráfico de barras comparando los costos de envío promedio.
    *   (Opcional) Gráfico de dispersión mostrando la distribución geográfica de las compras.
5.  **Elaboración de Informe y Recomendación:** Consolidar los hallazgos en un informe final y proporcionar una recomendación para el Sr. Juan.

## Resultados Clave

*   **Ingresos:** **Tienda_1** generó los ingresos totales más altos ($1,150.9M COP), seguida de cerca por Tienda_2 ($1,116.3M COP) y Tienda_3 ($1,098.0M COP). Tienda_4 tuvo los ingresos más bajos ($1,038.4M COP). Los ingresos totales combinados fueron aproximadamente $4,403.6M COP.
*   **Categorías Populares:** En todas las tiendas, **Muebles** y **Electrónicos** fueron las categorías con el mayor número de transacciones de venta. Artículos para el hogar, Libros e Instrumentos musicales tuvieron el menor volumen.
*   **Satisfacción del Cliente:** Las cuatro tiendas tienen calificaciones promedio de clientes muy similares y positivas, agrupadas alrededor de **4.0 sobre 5**. Tienda_3 y Tienda_2 tuvieron promedios ligeramente más altos (4.05 y 4.04) que Tienda_4 (4.00) y Tienda_1 (3.98), pero las diferencias son mínimas.
*   **Productos Populares:** El producto más vendido en general fue **Mesa de noche** con 210 unidades. El producto menos vendido fue **Celular ABXY** con 157 unidades.
*   **Costos de Envío:** El costo de envío promedio pagado por los clientes varió:
    *   Tienda_1: ~$26,019 COP (El más alto)
    *   Tienda_2: ~$25,216 COP
    *   Tienda_3: ~$24,806 COP
    *   Tienda_4: ~$23,459 COP (El más bajo)
    *(Nota: El informe final del notebook contiene una discrepancia, indicando que T4 era el más alto y T1/T2 los más bajos. El hallazgo anterior se basa en la salida directa del código y la visualización.)*

## Recomendación

Basado en el análisis presentado *dentro del notebook*:

**Se recomienda Tienda_1 como la opción más sólida para el Sr. Juan.**

*Justificación (según se indica en la conclusión del notebook):* Aunque la satisfacción del cliente es similarmente alta en todas las tiendas, Tienda_1 lidera en ingresos totales. La conclusión del notebook también citó los menores costos de envío promedio para Tienda_1 y Tienda_2 como un factor positivo (potencialmente en relación con T3/T4 o considerando otros factores no declarados explícitamente, a pesar de que T1 tiene el costo promedio nominal más alto). Tienda_2 es un segundo lugar muy cercano en ingresos con costos de envío comparables. Tienda_3, a pesar de tener buenos ingresos, tiene un costo de envío promedio más alto (comparado con T4, según la salida del código). Tienda_4 presenta tanto los ingresos más bajos como los costos de envío más bajos, haciéndola menos atractiva en general según los criterios principales del notebook.

## Visualizaciones

El proyecto incluye las siguientes visualizaciones:

*   **Gráfico 1:** Gráfico de barras comparando los Ingresos Totales por Tienda.
*   **Gráfico 2:** Gráfico de barras horizontal mostrando el Número de Ventas por Categoría de Producto.
*   **Gráfico 3:** Gráfico de barras comparando la Calificación Promedio del Cliente por Tienda.
*   **Gráfico 4:** Gráfico de barras comparando el Costo de Envío Promedio por Tienda.
*   **(Opcional):** Gráfico de dispersión visualizando la distribución geográfica de las coordenadas de venta, coloreado por tienda.

## Tecnologías Utilizadas

*   **Lenguaje:** Python 3
*   **Bibliotecas:**
    *   Pandas: Manipulación y análisis de datos.
    *   Matplotlib: Visualización de datos.
    *   Seaborn: Visualización de datos mejorada.
    *   Tabulate: Formateo de tablas para el informe.
*   **Entorno:** Jupyter Notebook

## Configuración y Uso

1.  **Prerrequisitos:**
    *   Python 3 instalado.
    *   `pip` (instalador de paquetes de Python).

2.  **Instalación:**
    Instale las bibliotecas requeridas usando pip:
    ```bash
    pip install pandas matplotlib seaborn tabulate jupyterlab
    ```
    *(Reemplace `jupyterlab` con `notebook` si prefiere la interfaz clásica de Jupyter Notebook).*

3.  **Ejecución del Notebook:**
    *   Clone o descargue este repositorio/archivos del proyecto.
    *   Navegue al directorio del proyecto en su terminal.
    *   Inicie Jupyter Lab o Notebook:
        ```bash
        jupyter lab
        # o
        jupyter notebook
        ```
    *   Abra el archivo `AluraStoreLatam.ipynb` en la interfaz de Jupyter.
    *   Ejecute las celdas secuencialmente (p. ej., usando "Ejecutar Todo" o ejecutando cada celda individualmente).

    *Nota:* El notebook obtiene los datos directamente de las URLs de GitHub, por lo que no se requiere la descarga manual de archivos CSV siempre que haya acceso a Internet.

## Trabajo Futuro

*   Realizar análisis de series temporales para identificar tendencias de ventas a lo largo del tiempo.
*   Analizar el desempeño de los vendedores dentro de cada tienda.
*   Llevar a cabo segmentación de clientes basada en el comportamiento de compra o la ubicación.
*   Utilizar herramientas de visualización geográfica más avanzadas (p. ej., Folium) para mapas interactivos.
*   Investigar la discrepancia observada en el resumen de costos de envío vs. el cálculo bruto y refinar la lógica de recomendación si es necesario.
*   Realizar un análisis más profundo de la rentabilidad del producto (requiere datos de costos no presentes).

## Autor

Este proyecto fue desarrollado por:

*   **Nelson Enrique Reyes**
*   **GitHub:** [frenrey3](https://github.com/frenrey3)
