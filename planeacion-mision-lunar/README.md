# Planeación de una misión lunar mediante pandas de Python 🐼🌕

Use datos para planear su propia misión a la Luna. Asegúrese de que el cohete no solo pueda llegar al destino, sino que también regresa de forma segura a la Tierra junto con las rocas lunares.

🔗 [Microsoft Learn](https://learn.microsoft.com/es-es/training/modules/plan-moon-mission-using-python-pandas/) <br/>
🔗 [Learn with Dr G](https://www.youtube.com/watch?v=jyFHnO7-4Gc&list=PLlrxD0HtieHgJdiA08EVViP8D6hfDRXx8&index=3)

### Objetivos de aprendizaje:

* Crear una representación clara de los datos a partir de muchos orígenes.
* Usar Python y pandas para explorar los datos.
* Usar técnicas de limpieza de datos para obtener una representación clara de los datos.
* Teorizar sobre la cantidad de muestras de rocas que los astronautas pueden traer durante las misiones Artemis.

<hr/>

## Introducción

Este módulo se inspirará en [Más allá de la Luna](https://www.youtube.com/watch?v=26DIABx44Tw%3Fazure-portal%3Dtrue) y en los científicos de la NASA para explorar datos relacionados con las misiones Apolo y las muestras de rocas que trajeron a la Tierra. Aprenderá técnicas de limpieza y manipulación de datos que son fundamentales para desarrollar los modelos de Machine Learning e inteligencia artificial que nos ayudan a preparar la exploración espacial.

<hr/>

## Descripción de la importancia de las rocas lunares

Las rocas lunares constituyen una parte importante del descubrimiento científico y el conocimiento del universo y del planeta. Pueden contar cómo se han formado los planetas y las lunas, y servir de guía para preparar la exploración espacial.

Aunque la [Oficina de protección y adquisición de astromateriales de la NASA](https://curator.jsc.nasa.gov/) tiene una lista de todas las muestras extraterrestres obtenidas en la Luna y otros lugares, este módulo se centra en las recogidas en la Luna. Entre las seis misiones del programa Apolo que llevaron humanos a la Luna, y las tres misiones lunares que llevaron sondas robóticas, se han conseguido 383 kilogramos de rocas, tierra y muestras del núcleo. Todas estas muestras se han categorizado y fotografiado, y están disponibles para verlas en el [catálogo de fotografías y muestras lunares de la NASA](https://curator.jsc.nasa.gov/lunar/samplecatalog/index.cfm).

Además de ser interesante para el entusiasta ocasional del espacio, el catálogo es un recurso esencial para investigadores activos e instituciones educativas que podrían ser la inspiración de la próxima generación de científicos de rocas espaciales. De hecho, se pueden solicitar muestras con fines de [investigación](https://curator.jsc.nasa.gov/lunar/sampreq/requests.cfm), [educativos](https://curator.jsc.nasa.gov/education/index.cfm) o para [exposiciones públicas](https://curator.jsc.nasa.gov/education/public_display.cfm). El reto de la oficina es asegurarse de que haya muestras suficientes de diferentes tipos de materia lunar para continuar con la comprensión colectiva del universo y el planeta.

Este desafío es especialmente complejo por dos motivos:

* No se puede enviar a un astronauta hasta la Luna para que tome una muestra más de un tipo de roca concreta sin más.
* Cuando los astronautas vuelvan a aterrizar en la Luna, deben saber qué tipos de muestras de roca y cuántas deben recoger para reabastecer la colección en la Tierra.

Los expertos en la Tierra someten a las muestras de rocas lunares a un exhaustivo proceso de análisis y limpieza, y los responsables se encargan de desarrollar la descripción de las muestras que tienen, cuáles se solicitan y cuál es la parte más difícil de garantizar la continuidad de la investigación.

Este módulo explora cómo puede usar los datos y algo de codificación de Python para comprender lo que existe en este momento. A partir de este análisis, puede hacer recomendaciones dirigidas a los astronautas sobre qué es lo que deben buscar cuando lleguen a la Luna, como parte del programa Artemisa en 2025.

Antes de continuar, asegúrese de dedicar tiempo a examinar el [catálogo de fotografías y muestras lunares](https://curator.jsc.nasa.gov/lunar/samplecatalog/index.cfm). Aunque este módulo se centra en los pesos, los tipos y el número de muestras de cada misión de Apolo, puede fijarse en otros detalles que puede usar para ampliar el análisis y ayudarle a desarrollar recomendaciones aún mejores para el siguiente equipo de astronautas.

<hr/>

## Ejercicio: Transferencia de los datos de muestras de rocas a Visual Studio Code

Ha llegado el momento de transferir a Visual Studio Code los datos del [catálogo de fotografía y muestras lunares](https://curator.jsc.nasa.gov/lunar/samplecatalog/index.cfm). Al hacerlo, puede usar Python para obtener conclusiones de las miles de muestras obtenidas en las seis misiones Apolo que han llegado a la Luna.

### Configuración de un entorno local

En este módulo verá cómo limpiar y manipular los datos relacionados con las muestras de rocas lunares. Para llevar a cabo los ejercicios siguientes, necesita algún tipo de entorno de desarrollo de cuadernos de Python. Si aún no ha preparado el entorno, se recomienda seguir los pasos que se presentan aquí. La forma más fácil de instalar y configurar el entorno de desarrollo es seguir la [documentación de configuración de ciencia de datos de Visual Studio Code](https://code.visualstudio.com/docs/python/data-science-tutorial).

Los tres primeros elementos que debe configurar son los siguientes:

* Visual Studio Code
* Python
* Miniconda

Después de haber instalado los tres elementos enumerados antes, siga estos pasos para preparar el entorno:

1. Cree una carpeta llamada *over-the-moon*.
2. Abra la carpeta en Visual Studio Code.
3. Dentro de esa carpeta, cree otra con el nombre *sample-return*.
4. Dentro de esa carpeta, cree otra con el nombre *data*.
5. Cree un archivo llamado *sample-return.ipynb* en la carpeta *sample-return*.
6. Abra el archivo s*ample-return.ipynb* en Visual Studio Code.

El entorno debe ser similar al siguiente:

![vscode-sample-return](https://learn.microsoft.com/es-es/training/modules/plan-moon-mission-using-python-pandas/media/vscode-sample-return.png)

### Recopilación e importación de datos

Los datos que explorará durante este módulo son un archivo completo de todas las muestras recopiladas en las seis misiones Apolo que han llegado a la Luna. El archivo [rocksamples.csv](https://aka.ms/LearnWithDrG/OverTheMoon/Data2) se ha creado con información del [catálogo de fotografía y muestras lunares](https://curator.jsc.nasa.gov/lunar/samplecatalog/index.cfm).

Descargue el archivo [rocksamples.csv](https://aka.ms/LearnWithDrG/OverTheMoon/Data2) y guárdelo en la carpeta de datos.

> [!TIP]
> Para descargar un archivo .csv en GitHub, haga lo siguiente:
> 1. En la lista de archivos del repositorio de GitHub, seleccione el archivo.
> 2. En la esquina superior derecha, seleccione **Raw** (Sin formato). El archivo se abre como un archivo .csv sin formato en el explorador.
> 3. Haga clic con el botón derecho en cualquier parte de la ventana del explorador y, después, seleccione **Guardar como**.
> 4. En el cuadro de diálogo **Guardar archivo como**, puede elegir el nombre de archivo (*rocksamples*), el tipo de archivo (.csv) y la ubicación de descarga del archivo (la carpeta de datos del proyecto).

Después de descargar el archivo .csv y guardarlo en la carpeta de datos, el entorno de Visual Studio Code debería tener el aspecto siguiente:

![vscode-data](https://learn.microsoft.com/es-es/training/modules/plan-moon-mission-using-python-pandas/media/vscode-data.png)

En la primera celda de Python del archivo *sample-return.ipynb*, importe pandas y lea el archivo de datos que contiene como un elemento dataframe de pandas:

```python
import pandas as pd 

rock_samples = pd.read_csv('data/rocksamples.csv')
```

Para asegurarse de que todo se carga correctamente, imprima las cinco primeras líneas del nuevo elemento dataframe mediante `head()` y el resumen de información mediante `info()`:

```python
rock_samples.head()
```

| Row   | id    | Mission | Type    | Subtype     | Peso (kg) | Pureza (%) |
| ----- | ----- | ------- | ------- | ----------- | -------- | ----------  |
| 0	    | 10001 | Apolo11 |	Tierra  | Sin tamizar |	125,8	 | 88,36       |
| 1	    | 10002 | Apolo11 |	Tierra  | Sin tamizar | 5629,0	 | 93,73       |
| 2	    | 10003 | Apolo11 |	Basalto | Ilmenita	  | 213,0	 | 65,56       |
| 3	    | 10004 | Apolo11 |	Core	| Sin tamizar |	44.8	 | 71,76       |
| 4	    | 10005 | Apolo11 |	Core	| Sin tamizar |	53,4	 | 40,31       |

```python
rock_samples.info()
```

```
#   Column       Non-Null Count  Dtype  
---  ------       --------------  -----  
0   ID           2229 non-null   int64  
1   Mission      2229 non-null   object 
2   Type         2229 non-null   object 
3   Subtype      2226 non-null   object 
4   Weight(g)    2229 non-null   float64
5   Pristine(%)  2229 non-null   float64
```

A partir de esta salida, se ve que durante las misiones Apolo se han obtenido 2229 muestras. Si examina una muestra de los datos, verá que cada fila contiene lo siguiente:

* *ID*: el identificador único que la NASA usa para realizar el seguimiento de la muestra.
* *Misión*: la misión responsable de recuperar la muestra.
* *Tipo*: el tipo de muestra (tipo de roca u otra clasificación).
* *Subtipo*: una clasificación de tipo más específica.
* *Peso (g)*: peso original de la muestra en gramos.
* *Pureza (%)*: porcentaje que queda de la muestra (parte de la muestra se usa durante la investigación).

<hr/>

## Ejercicio: Determinación de la pregunta que se debe formular para informar a la limpieza de datos

Antes de continuar, es importante establecer qué información quiere usar para realizar una recomendación a los astronautas. En este caso, puede usar información pública disponible sobre los tipos de nave espacial utilizados en misiones lunares anteriores y el peso de las muestras de rocas recogidas en cada misión.

### Conversión del peso de la muestra

Aunque los detalles de diseño de cohetes son privados, hay información pública disponible. Por ejemplo, puede recopilar datos como el peso de los módulos de la nave espacial que llevó las muestras de vuelta a la Tierra y el peso total que cada cohete puede transportar. Estos valores se pueden usar para calcular el peso máximo de las muestras de rocas que se pueden recopilar y llevar a la Tierra.

Para preparar los datos de muestra de rocas para cálculos posteriores, es necesario comprender que el peso del cohete se mide a menudo en kilogramos, no en gramos. Por lo tanto, debemos convertir los pesos originales de muestra de roca de gramos a kilogramos para facilitar el análisis de datos más adelante.

```python
rock_samples['Weight (g)'] = rock_samples['Weight (g)'].apply(lambda x : x * 0.001)
rock_samples.rename(columns={'Weight (g)':'Weight (kg)'}, inplace=True)
rock_samples.head()
```

| Row   | id    | Mission | Type    | Subtype     | Peso (kg) | Pureza (%) |
| ----- | ----- | ------- | ------- | ----------- | --------  | ---------- |
| 0	    | 10001 | Apolo11 |	Tierra  | Sin tamizar |	0.1258	  | 88,36      |
| 1	    | 10002 | Apolo11 |	Tierra  | Sin tamizar | 5,6290	  | 93,73      | 
| 2	    | 10003 | Apolo11 |	Basalto | Ilmenita	  | 0,2130	  | 65,56      |
| 3	    | 10004 | Apolo11 |	Core	| Sin tamizar |	0,0448	  | 71,76      |
| 4	    | 10005 | Apolo11 |	Core	| Sin tamizar |	0,0534	  | 40,31      |

Aquí primero se han modificado los valores de la columna **Peso (g)** para que tengan el mismo valor multiplicado por 0,001. Después, se ha cambiado el nombre de la columna por **Peso (kg)** para que sea más preciso.

### Creación de un elemento dataframe

Pandas, la biblioteca de Python que se va a usar para realizar el análisis de datos, tiene una estructura conocida como "dataframe", la cual resulta realmente eficaz para representar datos bidimensionales. Es posible que haya reconocido que, al ejecutar el código de `rock_samples.head()`, lo que se imprime es muy similar a una hoja de cálculo de Excel, una excelente manera de describir los elementos dataframe en pandas.

El elemento dataframe `rock_samples` tiene una fila para cada muestra que se ha obtenido. A pesar de esto, tal como se ha mencionado antes, el objetivo es comprender las muestras de rocas en su totalidad en relación a los cohetes concretos en los que se han transportado.

Cree un elemento dataframe con el nombre `missions`; será un resumen de los datos de cada una de las seis misiones Apolo en las que se han traído muestras. En este elemento dataframe, cree una columna con el nombre Mission, con una fila para cada misión.

```python
missions = pd.DataFrame()
missions['Mission'] = rock_samples['Mission'].unique()
missions.head()
```

| índice | Mission  |
| ------ | -------  | 
| 0	     | Apolo11  |
| 1	     | Apolo12  |
| 2	     | Apolo14  |
| 3	     | Apolo15  |
| 4	     | Apolo16  |

```python
missions.info()
```

```
#   Column   Non-Null Count  Dtype 
---  ------   --------------  ----- 
0   Mission  6 non-null      object
```

### Suma total del peso de las muestras por misión

Ahora puede agregar una columna nueva a `missions` para representar la suma de todas las muestras obtenidas durante esa misión.

```python
sample_total_weight = rock_samples.groupby('Mission')['Weight (kg)'].sum()
missions = pd.merge(missions, sample_total_weight, on='Mission')
missions.rename(columns={'Weight (kg)':'Sample weight (kg)'}, inplace=True)
missions
```

| índice | Mission  | Peso de la muestra (kg) |
| ------ | -------  | ----------------------- |
| 0	     | Apolo11  | 21,55424                |
| 1	     | Apolo12  | 34,34238                |
| 2	     | Apolo14  | 41,83363                |
| 3	     | Apolo15  | 75,39910                |
| 4	     | Apolo16  | 92,46262                |
| 5	     | Apolo17	| 109,44402               |

Ahora se desglosará este código. La primera línea es `sample_total_weight = rock_samples.groupby('Mission')['Weight (kg)'].sum()`, que se puede dividir de esta forma:

* `rock_samples.groupby('Mission')`: agrupa todas las filas por los valores de la columna Mission.
* `rock_samples.groupby('Mission')['Weight (kg)']`: toma todos los valores de la columna Peso (kg), pero los agrupa por valores únicos de la columna Misión.
* `rock_samples.groupby('Mission')['Weight (kg)'].sum()`: suma todos los valores de la columna Peso (kg) para cada valor único de la columna Misión.

Si imprimiera esa línea, obtendría una serie de pandas, que básicamente es un tipo de datos unidimensional o una lista. En la lista, el índice sería el valor único de la columna Mission, en lugar de un número:

```python
sample_total_weight = rock_samples.groupby('Mission')['Weight (kg)'].sum()
sample_total_weight
```

```
Mission
Apollo11     21.55424
Apollo12     34.34238
Apollo14     41.83363
Apollo15     75.39910
Apollo16     92.46262
Apollo17    109.44402
Name: Weight (kg), dtype: float64
```

La línea siguiente, `pd.merge(missions, sample_total_weight, on='Mission')`, se puede describir de esta forma:

Combine el elemento dataframe `missions` con la serie `sample_total_weight` y use la columna **Mission** como el índice sobre el que realizar la combinación. El equipo básicamente hará lo siguiente: para cada valor de la columna **Mission** del elemento dataframe `missions`, se buscará el mismo valor en la serie `sample_total_weight` y se agregará el valor de la serie a la fila como una nueva columna en el elemento dataframe.

Este ejemplo es bastante sencillo, ya que solo hay seis filas. Por tanto, se puede confirmar que el número 21,55424, por ejemplo, se ha agregado a la fila Apolo 11 en el elemento dataframe `missions`.

La siguiente línea simplemente cambia el nombre de la columna, como antes, para asegurarse de que los datos son específicos.

La última línea imprime el elemento dataframe `missions` completo. Como solo hay seis misiones, se puede imprimir el elemento dataframe completo y seguir entendiendo lo que se examina. No es necesario usar head() para imprimir solo las cinco primeras filas.

### Obtención de la diferencia de pesos entre misiones

Como no es un experto en cohetes, es importante examinar una gran cantidad de secciones diferentes de los datos disponibles. En este caso, se ve que el peso total de las muestras ha aumentado en cada misión, pero es difícil ver cuánto a simple vista. Se puede agregar una columna más al elemento dataframe `missions` que simplemente obtenga la diferencia entre la fila actual y la anterior:

```python
missions['Weight diff'] = missions['Sample weight (kg)'].diff()
missions
```

| índice | Mission  | Peso de la muestra (kg) | Diferencia de peso |
| ------ | -------  | ----------------------- | ------------------ |
| 0	     | Apolo11  | 21,55424                | NaN                |
| 1	     | Apolo12  | 34,34238                | 12,78814           |
| 2	     | Apolo14  | 41,83363                | 7,49125            |
| 3	     | Apolo15  | 75,39910                | 33,56547           |
| 4	     | Apolo16  | 92,46262                | 17,06352           |
| 5	     | Apolo17	| 109,44402               | 16,98140           |

Observe que en la primera fila, para Apolo 11, el valor de la columna Diferencia de peso es `NaN`. Esto se denomina valor *NULL*. Como Apolo11 fue la primera misión, no hay ninguna diferencia entre el peso de la roca obtenida durante Apolo11 y el de la misión anterior. Este valor `NaN` se puede rellenar con 0:

```python
missions['Weight diff'] = missions['Weight diff'].fillna(value=0)
missions
```

| índice | Mission  | Peso de la muestra (kg) | Diferencia de peso |
| ------ | -------  | ----------------------- | ------------------ |
| 0	     | Apolo11  | 21,55424                | 0,00000            |
| 1	     | Apolo12  | 34,34238                | 12,78814           |
| 2	     | Apolo14  | 41,83363                | 7,49125            |
| 3	     | Apolo15  | 75,39910                | 33,56547           |
| 4	     | Apolo16  | 92,46262                | 17,06352           |
| 5	     | Apolo17	| 109,44402               | 16,98140           |

Este código de Python ha hecho lo siguiente:

* Solo ha examinado la columna **Diferencia de peso** del elemento dataframe `missions`
T* odos los valores `NaN` (o NULL) se han rellenado con un valor concreto
* El valor para rellenar los valores `NaN` es 0
* Se ha vuelto a guardar en la columna la lista de valores modificada de esa columna

Este último paso es importante. Pandas es una biblioteca que se ha diseñado para la exploración de datos, lo que significa que algunas de las funciones proporcionarán conclusiones sobre los datos, pero no los modificarán directamente. En caso de duda, lea la documentación y pruebe.

<hr/>

## Ejercicio: Adición de datos de peso del cohete al análisis de las misiones

Como se ha mencionado en una unidad anterior, no hay mucha información pública sobre cómo se construyen los cohetes *exactamente*. Dado que no somos expertos, solo podemos hacer suposiciones mediante el uso de datos públicos disponibles.

Un aspecto *esencial* de la ciencia de los datos es garantizar que las suposiciones que se hacen representan con precisión los datos y el impacto que tienen. Por lo tanto, este módulo de entrenamiento concreto no es algo que deba usar para aconsejar a los astronautas. Aunque aquí esto pueda parecer obvio, es fundamental comprender su importancia a medida que aplica el aprendizaje de este módulo a otros conjuntos de datos y problemas para resolverlos.

### Revisión del programa Apolo

El programa Apolo se centró en el cohete [Saturno V](https://www.nasa.gov/centers/johnson/rocketpark/saturn_v.html) para enviar humanos al espacio y a la Luna. El cohete Saturno V que se usó en el programa Apolo se conoce como un cohete de tres fases. *De tres fases* significa que tiene tres partes, y cada una se desprende en un momento concreto para lograr un objetivo diferente.

La **primera fase** es el elemento de propulsión principal que eleva el cohete a aproximadamente 68 kilómetros de altura y que, después, cae a la Tierra, lo que hace que el cohete sea más ligero. La **segunda fase** quema los motores hasta que el cohete alcanza prácticamente la órbita de la Tierra y, después también se desprende. La **fase final** coloca al vehículo espacial en la órbita de la Tierra y lo impulsa hacia la Luna.

Como se ve en la película *Más allá de la Luna*, saber con exactitud cuánto peso se puede tener en cada fase afecta significativamente al resultado de la misión. También se sabe que, en el espacio, los astronautas necesitan muchos materiales, como alimentos, agua, oxígeno, herramientas e instrumentos. Cuando Fei Fe volvió a buscar a Gobi al punto de aterrizaje de emergencia se pudieron ver los suministros que llevaba.

El último dato importante sobre el programa Apolo y Saturno V es que, para los alunizajes hay dos módulos de nave espacial importantes:

* **Módulo de mando**: el módulo en el que se encuentran los astronautas. Cuando dos astronautas están sobre la superficie de la Luna, el tercero permanece en el módulo de mando. Este módulo es el que vuelve a la Tierra.
* **Módulo lunar**: el módulo que se separa del módulo de mando una vez que ha llegado a la órbita alrededor de la Luna. Este módulo aterriza sobre la superficie de la Luna y puede transportar dos astronautas. Cuando el módulo lunar regresa de la superficie al de mando, deja parte de la base (el engranaje de aterrizaje) en la superficie de la Luna.

Los módulos son partes críticas de la nave. La NASA los diseñó precisamente para garantizar que los astronautas pudieran entrar en la órbita de la Luna, orbitar, alunizar, despegar desde la Luna y regresar a la Tierra de forma segura. La cantidad de espacio y el peso de cada uno de estos módulos es preciso para garantizar la seguridad y el éxito de la misión. Por lo tanto, las especificaciones de estos módulos afectan a la cantidad de muestras minerales que se pueden recoger. Dado que los astronautas transportan las muestras en cada uno de estos módulos antes de volver a la Tierra, deben asegurarse de que las muestras no superen la capacidad de peso de cada módulo.

### Adición de datos de los módulos de mando y lunar

Con ayuda del Archivo coordinado de datos de ciencia espacial de la NASA, se ha obtenido información sobre cada uno de los módulos que se usa en cada misión. Como ha hecho al crear las tablas de las muestras, cree seis columnas, tres para los módulos lunares y tres para los módulos de mandos:

* Nombre del módulo
* Masa del módulo
* Diferencia de la masa del módulo

Rellene todos los valores `NaN` con 0:

```python
missions['Lunar module (LM)'] = ['Eagle (LM-5)', 'Intrepid (LM-6)', 'Antares (LM-8)', 'Falcon (LM-10)', 'Orion (LM-11)', 'Challenger (LM-12)']
missions['LM mass (kg)'] = [15103, 15235, 15264, 16430, 16445, 16456]
missions['LM mass diff'] = missions['LM mass (kg)'].diff()
missions['LM mass diff'] = missions['LM mass diff'].fillna(value=0)

missions['Command module (CM)'] = ['Columbia (CSM-107)', 'Yankee Clipper (CM-108)', 'Kitty Hawk (CM-110)', 'Endeavor (CM-112)', 'Casper (CM-113)', 'America (CM-114)']
missions['CM mass (kg)'] = [5560, 5609, 5758, 5875, 5840, 5960]
missions['CM mass diff'] = missions['CM mass (kg)'].diff()
missions['CM mass diff'] = missions['CM mass diff'].fillna(value=0)

missions
```

Se pueden agregar algunos totales para cada misión en los módulos lunares y de mando:

```python
missions['Total weight (kg)'] = missions['LM mass (kg)'] + missions['CM mass (kg)']
missions['Total weight diff'] = missions['LM mass diff'] + missions['CM mass diff']
missions
```

<hr/>

## Ejercicio: Descripción de los datos del elemento dataframe de las misiones

Ahora tiene una idea de cada una de las seis misiones Apolo que han llegado a la Luna. Contiene información sobre las muestras obtenidas durante cada misión y los pesos de cada módulo lunar y de mando.

Pero, ¿qué significa?

### Comparación de los datos

Lo interesante sobre la predicción de la cantidad de muestras que puede traer cada una de las misiones Artemisa es que todavía no se conocen las especificaciones completas de la nave espacial que tienen pensado usar. Con ayuda de la [hoja informativa de la NASA sobre el Sistema de lanzamiento espacial (SLS) y los módulos Orion](https://www.nasa.gov/sites/default/files/atoms/files/0080_sls_fact_sheet_sept2020_09082020_final_0.pdf), se obtienen datos sobre los pesos y las cargas.

Una *carga* es básicamente la cantidad total de peso que un cohete puede transportar a través de la atmósfera hacia el espacio. Por tanto, la probabilidad de que el número de carga sea más preciso que los pesos exactos de cada módulo es alta, ya que la decisión de la carga probablemente afectará a las demás decisiones de diseño.

Se sabe que la carga del Saturno V era 43 500 kg y que los pesos de los módulos han variado de una misión a otra. Por tanto, para determinar las proporciones que permitirán realizar predicciones sobre las misiones Artemis, se puede usar lo siguiente:

* Carga de Saturno V
* Peso de las muestras de la misión
* Peso de los módulos de la misión

```python
# Sample-to-weight ratio
saturnVPayload = 43500
missions['Crewed area : Payload'] = missions['Total weight (kg)'] / saturnVPayload
missions['Sample : Crewed area'] = missions['Sample weight (kg)'] / missions['Total weight (kg)']
missions['Sample : Payload'] = missions['Sample weight (kg)'] / saturnVPayload
missions
```

### Guardado de las proporciones

Después, se puede usar la función `mean()` para tomar el promedio de todas esas proporciones entre todas las misiones.

```python
crewedArea_payload_ratio = missions['Crewed area : Payload'].mean()
sample_crewedArea_ratio = missions['Sample : Crewed area'].mean()
sample_payload_ratio = missions['Sample : Payload'].mean()
print(crewedArea_payload_ratio)
print(sample_crewedArea_ratio)
print(sample_payload_ratio)
```

<hr/>

## Ejercicio: Predicción de la capacidad de transportar muestras de Artemis

Como se ha mencionado en la unidad anterior, se puede usar la [hoja informativa de la NASA sobre el Sistema de lanzamiento espacial (SLS) y los módulos Orion](https://www.nasa.gov/sites/default/files/atoms/files/0080_sls_fact_sheet_sept2020_09082020_final_0.pdf) para recopilar datos estimados sobre los cohetes y los módulos que se usarán en el programa Artemis.

Como recordatorio, el [programa Artemis](https://www.nasa.gov/specials/artemis/) es el segundo conjunto de misiones de la NASA para transportar humanos hasta la superficie de la Luna. El programa se iniciará en 2025 y no solo enviará a los dos siguientes humanos, sino también a la primera mujer que pondrá pie en la Luna. La preparación de esta misión es incluso más importante que centrarse en un alunizaje. También proporcionará espacio para una carga comercial en la nave y es el primer paso del [programa De la Luna a Marte](https://www.nasa.gov/topics/moon-to-mars). Por tanto, aunque es probable que en las misiones Artemis se obtengan muestras adicionales, existen otros objetivos que podrían afectar a la cantidad de capacidad necesaria para hacerlo.

### Creación de un elemento dataframe para la misión Artemis

No se tienen todos los detalles sobre la misión Artemis, pero se sabe que, actualmente, en cada misión el cohete realizará ciclos de tres iteraciones. Cada cohete tendrá una versión tripulada y otra para transporte de mercancías. Para los fines de este módulo, solo se centrará en los tres cohetes diseñados para albergar a la tripulación, y alinearlos más con las misiones Apolo. También se sabe que la carga prevista del Sistema de lanzamiento espacial (SLS) crecerá en cada iteración, pero que el peso actual de Orion (la combinación de los módulos de mando y lunar) tiene un peso estimado en la actualidad.

Una vez más, los módulos de mando y lunar se denominarán *Área de la tripulación*, y se puede crear un elemento dataframe con la información disponible sobre las tres misiones tripuladas:

```python
artemis_crewedArea = 26520
artemis_mission = pd.DataFrame({'Mission':['artemis1','artemis1b','artemis2'],
                                 'Total weight (kg)':[artemis_crewedArea,artemis_crewedArea,artemis_crewedArea],
                                 'Payload (kg)':[26988, 37965, 42955]})
artemis_mission
```

| índice | Mission   | Peso total (kg) | Carga (kg) |
| ------ | --------- | ----------------| ---------- |
| 0	     | artemis1  | 26520           | 26988      |
| 1	     | artemis1b | 26520           | 37965      |
| 2	     | artemis2  | 26520           | 42955      |

Y se puede calcular el peso de las muestras en función de las proporciones determinadas a partir de las misiones Apolo:

```python
artemis_mission['Sample weight from total (kg)'] = artemis_mission['Total weight (kg)'] * sample_crewedArea_ratio
artemis_mission['Sample weight from payload (kg)'] = artemis_mission['Payload (kg)'] * sample_payload_ratio
artemis_mission
```

| índice | Mission   | Peso total (kg) | Carga (kg) | Peso de la muestra del total (kg)	| Peso de la muestra de la carga (kg) |
| ------ | --------- | --------------- | ---------- | --------------------------------- | ----------------------------------- |
| 0	     | artemis1  | 26520           | 26988      | 75.549232                         | 38,779584                           | 
| 1	     | artemis1b | 26520           | 37965      | 75.549232                         | 54,552649                           |
| 2	     | artemis2  | 26520           | 42955      | 75.549232                         | 61,722877                           |


Por último, se puede obtener el promedio de las dos predicciones:

```python
artemis_mission['Estimated sample weight (kg)'] = (artemis_mission['Sample weight from payload (kg)'] + artemis_mission['Sample weight from total (kg)'])/2
artemis_mission
```

| Mission   | Peso total (kg) | Carga (kg) | Peso de la muestra del total (kg) | Peso de la muestra de la carga (kg) | Peso estimado de la muestra (kg) |
| --------- | --------------- | ---------- | --------------------------------- | ----------------------------------- | -------------------------------- |
| artemis1  | 26520           | 26988      | 75.549232                         | 38,779584                           | 57.164408                        |
| artemis1b | 26520           | 37965      | 75.549232                         | 54,552649                           | 65.050940                        |
| artemis2  | 26520           | 42955      | 75.549232                         | 61,722877                           | 68.636054                        |

Ahora se aprecia que las tres misiones Artemisa pueden traer 57,16 kg, 65,05 kg y 68,64 kg, respectivamente.

La pregunta es, ¿qué tipos de rocas deben priorizar?

<hr/>

## Ejercicio: Prioridad de la obtención de muestras de rocas lunares en función de los datos

Para determinar los tipos de muestras que se van a obtener en la Luna se necesita experiencia, pero se pueden formular algunas suposiciones con el fin de aprender a limpiar y manipular los datos.

En primer lugar, se puede determinar cuánto queda de cada muestra obtenida por las misiones Apolo, al multiplicar el peso de la muestra que se obtuvo originalmente por el porcentaje de la muestra original restante.

```python
rock_samples['Remaining (kg)'] = rock_samples['Weight (kg)'] * (rock_samples['Pristine (%)'] * .01)
rock_samples.head()
```

Examinar el `head()` o el `info()` del DataFrame `rock_samples` no es útil para examinar más de 2000 muestras. Para comprender mejor lo que contiene el conjunto de datos, puede usar la función `describe()`:

```python
rock_samples.describe()
```

Esta información ayuda a ver que, de media, cada muestra pesa aproximadamente 0,16 kg y queda aproximadamente un 84 % de la cantidad original. Este conocimiento se puede usar para determinar las muestras con pocas existencias, lo que significa que los investigadores las han utilizado mucho.

```python
low_samples = rock_samples.loc[(rock_samples['Weight (kg)'] >= .16) & (rock_samples['Pristine (%)'] <= 50)]
low_samples.head()
```

```python
low_samples.info()
```

```
#   Column         Non-Null Count  Dtype  
---  ------         --------------  -----  
 0   ID             27 non-null     int64  
 1   Mission        27 non-null     object 
 2   Type           27 non-null     object 
 3   Subtype        27 non-null     object 
 4   Weight (kg)     27 non-null     float64
 5   Pristine (%)    27 non-null     float64
 6   Remaining (kg)  27 non-null     float64
```

27 muestras parecen una cantidad pequeña en la que basar una recomendación. Probablemente encontrará otras muestras necesarias para proseguir con la investigación aquí en la Tierra. A fin de descubrirlas, puede usar la función unique() para ver cuántos tipos únicos hay en los elementos dataframe `low_samples` y `rock_samples`.

```python
low_samples.info()
```

```
array(['Basalt', 'Breccia', 'Soil', 'Core'], dtype=object)
```

```python
rock_samples.Type.unique()
```

```
array(['Soil', 'Basalt', 'Core', 'Breccia', 'Special', 'Crustal'], dtype=object)
```

Se puede ver que, aunque entre todas las muestras se han obtenido seis tipos únicos, aquellas de las que hay menos cantidad solo se corresponden a cuatro tipos únicos. Pero estos datos no lo indican todo sobre las muestras en las que se podría centrar. Por ejemplo, en el DataFrame `low_samples`, ¿de cuántos de cada uno de los tipos se considera que la cantidad es baja?

```python
low_samples.groupby('Type')['Weight (kg)'].count()
```

```
Type
Basalt     14
Breccia     8
Core        1
Soil        4
Name: Weight (kg), dtype: int64
```

Observe que hay más rocas de tipo basalto y brecha con un nivel bajo de muestras que de núcleo y tierra. Además, debido a la elevada probabilidad de que en cada misión haya que obtener muestras de núcleo y tierra, se puede centrar en los tipos de basalto y brecha para las que es necesario recoger:

```python
needed_samples = low_samples[low_samples['Type'].isin(['Basalt', 'Breccia'])]
needed_samples.info()
```

```
#   Column         Non-Null Count  Dtype  
---  ------         --------------  -----  
 0   ID             22 non-null     int64  
 1   Mission        22 non-null     object 
 2   Type           22 non-null     object 
 3   Subtype        22 non-null     object 
 4   Weight (kg)     22 non-null     float64
 5   Pristine (%)    22 non-null     float64
 6   Remaining (kg)  22 non-null     float64
```

<hr/>

## Ejercicio: Desarrollo de una recomendación de las muestras de rocas lunares que se deben recoger

Vamos a dar un paso atrás y comparar las muestras que se están agotando con todas las muestras recopiladas en las misiones del programa Apolo. Se puede comparar el peso total del elemento dataframe `needed_samples` con el de `rock_samples`.

```python
needed_samples.groupby('Type')['Weight (kg)'].sum()
```

```
Type
Basalt     17.4234
Breccia    10.1185
Name: Weight (kg), dtype: float64
```

```python
rock_samples.groupby('Type')['Weight (kg)'].sum()
```

```
Type
Basalt      93.14077
Breccia    168.88075
Core        19.93587
Crustal      4.74469
Soil        87.58981
Special      0.74410
Name: Weight (kg), dtype: float64
```

Hay un dato que destaca especialmente: nunca ha habido una gran cantidad de rocas corticales.

Se pueden agregar rocas corticales al conjunto de muestras necesarias:

```python
needed_samples = pd.concat([needed_samples,rock_samples.loc[rock_samples['Type'] == 'Crustal']])
needed_samples.info()
```

```
#   Column          Non-Null Count  Dtype  
---  ------         --------------  -----  
0   ID              68 non-null     int64  
1   Mission         68 non-null     object 
2   Type            68 non-null     object 
3   Subtype         68 non-null     object 
4   Weight (kg)     68 non-null     float64
5   Pristine (%)    68 non-null     float64
6   Remaining (kg)  68 non-null     float64
```

### Resumen de las muestras necesarias

El paso final consiste en consolidar todo el conocimiento en una tabla que se pueda compartir con los astronautas. En primer lugar, se necesita una columna para cada tipo de roca del que se quieren obtener más muestras:

```python
needed_samples_overview = pd.DataFrame()
needed_samples_overview['Type'] = needed_samples.Type.unique()
needed_samples_overview
```

A continuación, necesita el peso total de cada tipo de roca obtenida originalmente:

```python
needed_sample_weights = needed_samples.groupby('Type')['Weight (kg)'].sum().reset_index()
needed_samples_overview = pd.merge(needed_samples_overview, needed_sample_weights, on='Type')
needed_samples_overview.rename(columns={'Weight (kg)':'Total weight (kg)'}, inplace=True)
needed_samples_overview
```

Cuando los astronautas estén en la Luna, una forma de identificar las rocas es por su tamaño. Si se les puede indicar el tamaño estimado de cada tipo de roca, se podría facilitar el proceso de obtención.

```python
needed_sample_ave_weights = needed_samples.groupby('Type')['Weight (kg)'].mean().reset_index()
needed_samples_overview = pd.merge(needed_samples_overview, needed_sample_ave_weights, on='Type')
needed_samples_overview.rename(columns={'Weight (kg)':'Average weight (kg)'}, inplace=True)
needed_samples_overview
```

Las rocas corticales son pequeñas. Probablemente son más difíciles de detectar, motivo de que sean tan escasas.

Seguramente quiera indicarles a los astronautas qué cantidad de cada tipo quiere que consigan. Por tanto, para los tres tipos que busca, debería tomar el número total de cada tipo y obtener el porcentaje restante de cada tipo de roca.

```python
total_rock_count = rock_samples.groupby('Type')['ID'].count().reset_index()
needed_samples_overview = pd.merge(needed_samples_overview, total_rock_count, on='Type')
needed_samples_overview.rename(columns={'ID':'Number of samples'}, inplace=True)
total_rocks = needed_samples_overview['Number of samples'].sum()
needed_samples_overview['Percentage of rocks'] = needed_samples_overview['Number of samples'] / total_rocks
needed_samples_overview
```

Por último, para asociarlo todo a una recomendación para el programa Artemis, se puede determinar el peso medio de las muestras que se han estimado en la unidad anterior.

```python
artemis_ave_weight = artemis_mission['Estimated sample weight (kg)'].mean()
artemis_ave_weight
```

```
63.61713411579792
```

Este número se puede usar para determinar qué cantidad de cada roca deben intentar conseguir los astronautas:

```python
needed_samples_overview['Weight to collect'] = needed_samples_overview['Percentage of rocks'] * artemis_ave_weight
needed_samples_overview['Rocks to collect'] = needed_samples_overview['Weight to collect'] / needed_samples_overview['Average weight (kg)']
needed_samples_overview
```

| Tipo	    | Peso total (kg) | Peso promedio (kg) | Número de ejemplos | Porcentaje de rocas | Peso que recolectar | Rocas que recolectar |
| --------- | --------------- | ------------------ | ------------------ | ------------------- | ------------------- | -------------------- |
| Basalto   | 17,42340	      | 1,244529	       | 351	            | 0,258850	          |  16.467267	        | 13.231731            |
| Brecha	| 10,11850	      | 1.264813	       | 959	            | 0,707227	          | 44.991764  	        | 35.571884            |
| Cortical	| 4,74469	      | 0,103145	       | 46	                | 0,033923 	          | 2.158103	        | 20.922917            |

Por tanto, es posible que se le indique a los astronautas de la misión Artemisa que intenten conseguir 13 rocas de basalto, 35 de brecha y 20 corticales.