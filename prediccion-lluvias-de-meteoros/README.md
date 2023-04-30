# Predicción de lluvias de meteoros mediante Python y Visual Studio Code 🔭☄️

Obtenga información sobre cómo usar conceptos de aprendizaje automático para predecir la aparición de lluvias de meteoros.

🔗 [Microsoft Learn](https://learn.microsoft.com/es-es/training/modules/predict-meteor-showers-using-python/) <br/>
🔗 [Learn with Dr G](https://www.youtube.com/watch?v=Aln9p6farRg&list=PLlrxD0HtieHgJdiA08EVViP8D6hfDRXx8&index=4)

### Objetivos de aprendizaje:

* Los aspectos básicos de las lluvias de meteoros: qué son y por qué se ven.
* Cómo elegir y recopilar los datos adecuados.
* Estrategias para limpiar y manipular los datos.

<hr/>

## Introducción

Este módulo se centra en un fenómeno del mundo real, las lluvias de meteoros. Se le guiará por el uso de la ciencia de datos a fin de predecir el mejor día para observar una lluvia de meteoros desde una ubicación general. Al igual que Fei Fei, perfeccionará nuevas aptitudes, desarrollará la persistencia y se inspirará en la historia para crear algo que le acerque más al universo.

<hr/>

### ¿Qué son las lluvias de meteoros?

Los *meteoroides* son objetos en el espacio que normalmente están formados por polvo, rocas o metal. Pueden ser desde pequeñas motas de polvo hasta pequeños asteroides. Básicamente son rocas espaciales que flotan en el espacio.

Cuando los meteoroides se encuentra cerca de la Tierra, la gravedad los atrae a la atmósfera, donde entran en combustión. Esa combustión es la luz que se ve en el cielo. En este estado, los meteoroides se denominan *meteoros*. Si un meteoro atraviesa la atmósfera sin quemarse completamente y aterriza en algún lugar de la Tierra, se conoce como *meteorito*.

La NASA estima que cada día caen a la Tierra 48,5 toneladas de material meteórico. La mayoría de los meteoros se consumen completamente en la atmósfera. El mejor lugar para encontrar los que llegan a la superficie terrestre es el desierto o un lugar helado como la Antártida. Resultan más fáciles de localizar en estos lugares porque, cuando llegan a la Tierra, los meteoritos se parecen a cualquier otra roca convencional. Es difícil distinguirlos de las rocas que se producen de forma natural en la Tierra.

Los meteoroides puede provenir de cometas, asteroides, lunas o planetas. El origen más común de las lluvias de meteoros son los cometas. Este módulo se centra en los cometas.

Puede obtener más información sobre los meteoros y las lluvias de meteoros en el [sitio web de exploración del sistema solar de la NASA](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/meteors-and-meteorites/overview).

### Meteoros procedentes de cometas

Los cometas están formados básicamente de hielo. Están formados por polvo, roca y metales. Los cometas describen órbitas elípticas alrededor del Sol. Por tanto, algunas veces están más cerca del Sol que otras. Cuando un cometa está cerca del Sol, a menudo comienza a derretirse. Mientras se derrite, parte del polvo, las rocas y el metal se desprende del cometa y permanece en el espacio.

Cuando la Tierra está cerca de una ubicación en la que un cometa ha desprendido residuos, pueden entrar en la atmósfera y provocar lluvias de meteoros. Como en algunas ubicaciones de la órbita terrestre la probabilidad de la presencia de residuos de cometas es mayor, las lluvias de meteoros son más comunes en esas ubicaciones.

**Dato curioso**: Es probable que los océanos de la Tierra se originaran por el impacto de cometas sobre el planeta durante su formación, y que se fundieran en agua.

<hr/>

## Ejercicio: Aspectos básicos de la ciencia de datos y configuración del entorno

Los meteoros se pueden observar cada noche desde la Tierra. Pero las mejores lluvias de meteoros son las que se originan a partir de uno de los cometas que orbitan alrededor del Sol. Para verlas, además de conocer la trayectoria de los cometas, también hay que tener en cuenta el lado de la Tierra por donde los meteoros atravesarán la atmósfera. Y también hay que tener en cuenta si el cielo nocturno será lo suficientemente oscuro como para optimizar la visión de las colas de los meteoros.

### Revisión del ciclo de vida de la ciencia de datos

Antes de describir el código, es necesario revisar el [ciclo de vida de la ciencia de datos](https://learn.microsoft.com/es-es/azure/machine-learning/team-data-science-process/overview). La *ciencia de datos* es un campo que admite la detección de nuevas formas de ver y entender el mundo mediante el uso de datos.

Un proyecto típico de ciencia de datos itera por cuatro pasos principales:

1. Conocimiento del negocio
2. Adquisición y comprensión de los datos
3. Modelado
4. Implementación

Un proyecto *iterará* por estos pasos. Por tanto, en cada paso, puede volver a visitar cualquiera de los otros para comprobar si ha cambiado algo, o bien si lo que ahora sabe proporciona conclusiones que permitirían cambiar uno de los otros pasos.

Aunque no sea un experto en la exploración espacial, puede usar lo que aprenda de los expertos como guía en este módulo. En un escenario en el que lo que cree y descubra afecte a algo real, siempre debe consultar a un experto en la materia.

Este módulo se centra en el nodo "Adquisición y descripción de los datos" del ciclo de vida de la ciencia de datos.

### Configurado su entorno de desarrollo

Este módulo le ayuda a crear un modelo para predecir la mejor fecha para ver una lluvia de meteoros. Para crear el modelo, necesita algún tipo de entorno de desarrollo de cuadernos de Python.

1. Cree una carpeta llamada *over-the-moon*.
2. Cree una carpeta dentro de la carpeta *over-the-moon*. Asígnele el nombre *meteor-showers*.
3. Cree un archivo con el nombre *meteor-showers.ipynb.*
4. Cree una carpeta dentro de la carpeta *meteor-showers*. Asígnele el nombre *data*.
5. Abra el archivo *meteor-showers.ipynb*.

<hr/>

## Ejercicio: Recopilación de datos relacionados con las lluvias de meteoritos

Ahora es el momento de preparar los datos para crear el modelo de predicción. Recuerde que, idealmente, un experto en meteoros tendría que guiar este paso. Pero incluso sin un experto, puede intentar adivinar qué datos ayudarían a identificar la mejor fecha para ver una lluvia de meteoros.

Antes de recopilar los datos, es importante identificar el tipo de datos que se quiere encontrar. Sabe algunas cosas:

* Los meteoroides que se desprenden de los cometas suelen provocar lluvias de meteoros.
* Los cometas describen una órbita alrededor del Sol, que se puede observar y predecir.
* Una Luna muy brillante dificulta la posibilidad de ver una lluvia de meteoros.
* La órbita y el giro de la Tierra afectan a la posición desde la que se puede ver una lluvia de meteoros.

### Selección de los cometas concretos

Aunque los meteoroides pueden provenir de cometas, asteroides, lunas y planetas, este módulo se centra en los que provienen de cometas conocidos. A menudo se usan cuatro cometas para predecir cuándo y dónde serán visibles las lluvias de meteoros. En las secciones siguientes se describen estos cometas.

#### Cometa Thatcher

El [cometa Thatcher](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/comets/c-1861-g1-thatcher/in-depth/) se descubrió por primera vez en 1861. Tarda 415,5 años en orbitar alrededor del Sol.

Los residuos de este cometa crean la [lluvia de meteoros de las Líridas](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/meteors-and-meteorites/lyrids/in-depth/) cada mes de abril. La primera observación registrada de las Líridas se remonta al año 687 a.C.

La lluvia de meteoros de las Líridas parece provenir de la dirección de la constelación Lira. Pero el cometa y la lluvia de meteoros realmente no se originan en esta constelación.

#### Cometa Halley

El [cometa Halley](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/comets/1p-halley/in-depth/) se descubrió por primera vez en 1531. Pero no fue hasta 1705 que se descubrió que el cometa avistado en 1531, 1607 y 1682 era el mismo.

El cometa Halley tarda 76 años en orbitar alrededor del Sol. Los residuos de este cometa crean la [lluvia de meteoros Eta Acuáridas](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/meteors-and-meteorites/eta-aquarids/in-depth/) en el mes de mayo y las [Oriónidas](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/meteors-and-meteorites/orionids/in-depth/) en octubre.

La lluvia de meteoros de las Eta Acuáridas parece provenir de la dirección de la constelación Acuario. La lluvia de meteoros de las Oriónidas parece provenir de la dirección de la constelación Orión.

#### Cometa Swift-Tuttle

El [cometa Swift-Tuttle](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/comets/109p-swift-tuttle/in-depth/) se descubrió en 1862 por primera vez. Tarda 133 años en orbitar alrededor del Sol. Los residuos de este cometa crean la [lluvia de meteoros de las Perseidas](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/meteors-and-meteorites/perseids/in-depth/) cada mes de agosto.

En 1865 se descubrió que esta lluvia de meteoros se originaba en el cometa Swift-Tuttle. La lluvia de meteoros de las Perseidas parece provenir de la dirección de la constelación Perseo.

#### Cometa Tempel-Tuttle

El [cometa Tempel-Tuttle](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/comets/55p-tempel-tuttle/in-depth/) se descubrió de forma independiente dos veces, en 1865 y 1866. Tarda 33 años en orbitar alrededor del Sol. Los residuos de este cometa crean la lluvia de meteoros de las Leónidas cada mes de noviembre.

Cada 33 años, la [lluvia de las Leónidas](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/meteors-and-meteorites/leonids/in-depth/) se convierte en una *tormenta de meteoros*. Una tormenta de meteoros es cuando hay al menos 1000 meteoros por hora. La lluvia de meteoros de las Leónidas parece provenir de la dirección de la constelación Leo.

### Fases de la luna

Como la Luna gira alrededor de la Tierra y la Tierra alrededor del Sol, desde la Luna se reflejan distintas cantidades de luz solar sobre la Tierra. Cada mes, la Luna recorre diferentes fases. Las fases son básicamente los nombres que se aplican a la cantidad de luz solar que se refleja sobre ciertas partes de la Luna.

Las fases de la Luna son:

* Luna nueva 🌑: aproximadamente el día 15 de cada mes 
* Creciente menguante 🌘
* Cuarto creciente 🌓: aproximadamente el día 23 de cada mes
* Luna gibosa creciente 🌘
* Luna llena 🌕: aproximadamente el día 1 de cada mes
* Luna gibosa menguante 🌖
* Cuarto menguante 🌗: aproximadamente el día 10 de cada mes
* Creciente menguante 🌘

Las fases de las que se realiza el seguimiento más frecuente son luna nueva, cuarto creciente, luna llena y cuarto menguante. El ciclo de las fases dura 29 días, por lo que las fechas exactas dependen del número de días del mes.

### Archivos de datos

Ha empezado a recopilar algunos datos para el ejemplo de este módulo. Por su cuenta, intente encontrar otros datos que le ayuden a explorar las predicciones de lluvias de meteoros. Por ejemplo, puede crear nuevos archivos de datos que contengan datos del año actual o los años futuros.

Estos son los datos que ya se han recopilado:

* [moonphases.csv](https://github.com/drguthals/learnwithdrg/blob/main/OverTheMoon/meteor-showers/data/moonphases.csv): este archivo contiene las fases de la luna para cada día de 2020. Los datos que faltan se agregarán en la unidad siguiente. (Datos obtenidos de [timeanddate.com](https://www.timeanddate.com/moon/phases/))
* [meteorshowers.csv](https://github.com/drguthals/learnwithdrg/blob/main/OverTheMoon/meteor-showers/data/meteorshowers.csv): este archivo contiene datos para cada una de las cinco lluvias de meteoros que se han descrito antes. Los datos incluyen el mes preferido para verlas, los meses durante los que son visibles y el hemisferio preferido para verlas. (Datos obtenidos de [NASA](https://solarsystem.nasa.gov/asteroids-comets-and-meteors/meteors-and-meteorites/in-depth/))
* [constellations.csv](https://github.com/drguthals/learnwithdrg/blob/main/OverTheMoon/meteor-showers/data/constellations.csv): este archivo contiene datos de las cuatro constelaciones en las que se originan las cinco lluvias de meteoros. Los datos incluyen las latitudes en las que son visibles y el mes para la mejor visualización. (Datos obtenidos de [Wikipedia](https://en.wikipedia.org/wiki/IAU_designated_constellations)).
* [cities.csv](https://github.com/drguthals/learnwithdrg/blob/main/OverTheMoon/meteor-showers/data/cities.csv): este archivo contiene una lista de capitales/ciudades de países o regiones y sus latitudes correspondientes. (Datos obtenidos de [Wikipedia](https://en.wikipedia.org/wiki/List_of_national_capitals_by_latitude))

Copie el contenido de estos archivos y guárdelos en archivos CSV en la carpeta *over-the-moon/meteor-showers/data*:

![data-downloaded](https://learn.microsoft.com/es-es/training/modules/predict-meteor-showers-using-python/media/data-downloaded.png)

> [!TIP]
> Para descargar un archivo .csv en GitHub, haga lo siguiente:
> 1. En la lista de archivos del repositorio de GitHub, seleccione el archivo.
> 2. En la esquina superior derecha, seleccione **Raw** (Sin formato). El archivo se abre como un archivo .csv sin formato en el explorador.
> 3. Haga clic con el botón derecho en cualquier parte de la ventana del explorador y, después, seleccione **Guardar como**.
> 4. En el cuadro de diálogo **Guardar archivo como**, puede elegir el nombre de archivo (*rocksamples*), el tipo de archivo (.csv) y la ubicación de descarga del archivo (la carpeta de datos del proyecto).

### Otros datos que se deben tener en cuenta

Este módulo se centra en los cuatro archivos de datos. Pero también puede recopilar otros tipos de datos que es posible que afecten a la probabilidad de ver una lluvia de meteoros:

* Tiempo
* Otros tipos de cometas o meteoros conocidos
* Contaminación lumínica de las ciudades

<hr/>

## Ejercicio: Limpieza de datos sobre meteoritos

Recuerde que en el ciclo de vida del proyecto de ciencia de datos, después de tener los datos de las predicciones, debe prepararlos para su análisis. En esta unidad, explorará los datos y se asegurará de que estén listos para usarse en el modelo de Machine Learning.

### Ejercicio: Importar datos

En primer lugar, importe NumPy y pandas:

```python
import numpy as np 
import pandas as pd
```

Ahora importe los cuatro archivos `.csv`:

```python
meteor_showers = pd.read_csv('data/meteorshowers.csv')
moon_phases = pd.read_csv('data/moonphases.csv')
constellations = pd.read_csv('data/constellations.csv')
cities = pd.read_csv('data/cities.csv')
```

### Ejercicio: Exploración de datos

Examine los datos. Por cada variable creada, imprima los elementos `head` e `info` de esos dataframes.`head` permite ver las cinco primeras líneas de los archivos `.csv`. `info` proporciona información general sobre los datos que pueden faltar. Asegúrese de ejecutar cada uno de estos comandos en su propia celda para que ver la salida.

```python
meteor_showers.head()
```

```python
meteor_showers.info()
```

```python
moon_phases.head()
```

```python
moon_phases.info()
```

```python
constellations.head()
```

```python
constellations.info()
```

```python
cities.head()
```

```python
cities.info()
```

### Conversión en números

En las llamadas a `head()` se puede ver que una gran cantidad de información se escribe en palabras (cadenas) en lugar de números (enteros). Algunos datos tienen sentido como cadenas, como los nombres de ciudades o los de las lluvias de meteoros. Pero otros tienen más sentido como enteros, como los meses o las fases de la Luna.

Puede convertir rápidamente las columnas de mes en números:

1. Cree una asignación de meses a números. En la salida de `head()` se puede apreciar que los meses se escriben en minúsculas.
2. Asigne el mapa de los meses a las columnas que tienen meses.
3. Guarde el resultado en el dataframe.

```python
months = {'january':1, 'february':2, 'march':3, 'april':4, 'may':5, 'june':6, 'july':7, 'august':8, 'september':9, 'october':10, 'november':11, 'december':12}
meteor_showers.bestmonth = meteor_showers.bestmonth.map(months)
meteor_showers.startmonth = meteor_showers.startmonth.map(months)
meteor_showers.endmonth = meteor_showers.endmonth.map(months)
moon_phases.month = moon_phases.month.map(months)
constellations.bestmonth = constellations.bestmonth.map(months)
```

Para confirmar los cambios, agregue llamadas a `head()` e `info()` a cada uno de los tres dataframes que ha modificado. Por ejemplo:

```python
meteor_showers.head()
```

```python
meteor_showers.info()
```

Antes de continuar, convierta los meses y los días del dataframe `meteor_showers` en un tipo denominado `datetime`, que realiza el seguimiento de las fechas.

Cree dos columnas: `startdate` y `enddate`. Estas columnas contendrán un mes y un día de 2020:

```python
meteor_showers['startdate'] = pd.to_datetime(2020*10000+meteor_showers.startmonth*100+meteor_showers.startday,format='%Y%m%d')
meteor_showers['enddate'] = pd.to_datetime(2020*10000+meteor_showers.endmonth*100+meteor_showers.endday,format='%Y%m%d')
```

Siga el mismo patrón para `moon_phases`:

```python
moon_phases['date'] = pd.to_datetime(2020*10000+moon_phases.month*100+moon_phases.day,format='%Y%m%d')
```

Después, convierta los datos de los hemisferios en números mediante el proceso de asignación:

```python
hemispheres = {'northern':0, 'southern':1, 'northern, southern':3}
meteor_showers.hemisphere = meteor_showers.hemisphere.map(hemispheres)
constellations.hemisphere = constellations.hemisphere.map(hemispheres)
```

Por último, convierta las fases de la Luna en números que representen el porcentaje de visibilidad de la Luna. En esta ocasión, agregue una columna nueva para representar los datos:

1. Cree la asignación de fases a números.
2. Agregue una columna nueva denominada `percentage` y establézcala en la columna `moonphase`, asignada a los números.
3. Muestre las primeras cinco filas.

```python
phases = {'new moon':0,'third quarter':0.5, 'first quarter':0.5,'full moon':1.0}
moon_phases['percentage'] = moon_phases.moonphase.map(phases)
moon_phases.head()
```

Ahora ha convertido todos los datos que tienen más sentido como números. Pero faltan algunos valores.

### Eliminación de datos innecesarios

Algunos de los datos de estos archivos .csv no son útiles. Puede eliminar los datos siguientes:

> meteor_showers -> `startmonth`, `startday`, `endmonth`, `endday`, `hemisphere` -> La información del mes y el día se captura en las columnas startdate y enddate. La columna preferredhemisphere es el valor óptimo.

> moon_phases -> `month`, `day`, `moonphase`, `specialevent` -> La columna date ya contiene month y day. La columna percentage cubre moonphase. La columna specialevent no es pertinente para el caso.

> constellations -> `besttime` ->Cada fila es 21:00.

Aquí se muestra cómo quitar esas columnas:

```python
meteor_showers = meteor_showers.drop(['startmonth', 'startday', 'endmonth', 'endday', 'hemisphere'], axis=1)
moon_phases = moon_phases.drop(['month','day','moonphase','specialevent'], axis=1)
constellations = constellations.drop(['besttime'], axis=1)
```

Ahora es el momento de rellenar los datos que faltan.

### Datos que faltan

Uno de los archivos `.csv` es interesante. La salida de moon_phases.info() muestra la información siguiente:

```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 366 entries, 0 to 365
Data columns (total 2 columns):
 #   Column      Non-Null Count  Dtype         
---  ------      --------------  -----         
 0   date        366 non-null    datetime64[ns]
 1   percentage  50 non-null     float64       
dtypes: datetime64[ns](1), float64(1)
memory usage: 5.8 KB
```

Verá que el ciclo de las fases de la Luna pasa de 0 a 0,5, a 1, a 0,5 y después vuelve a 0. Por tanto, podría hacer que todos los valores entre 0 y 0,5 sean 0,25. Y que todos los valores entre 0,5 y 1 sean 0,75.

Podría conseguir más detalle si determina un porcentaje propio más preciso:

1. Cree una variable para guardar la última fase que ha visto.
2. Recorra en bucle cada fila y columna del dataframe `moon_phases`.
3. Si el valor de la columna `percentage` de una fila es `NaN`(null), reemplácelo por la última fase que ha visto.
4. Si el valor no es `NaN`, guarde el valor como la última fase que ha visto.
5. Muestre la información del dataframe `moon_phases`:

    ```python
    lastPhase = 0

    for index, row in moon_phases.iterrows():
        if pd.isnull(row['percentage']):
            moon_phases.at[index,'percentage'] = lastPhase
        else:
            lastPhase = row['percentage']

    moon_phases.info()
    ```

    ```
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 366 entries, 0 to 365
    Data columns (total 2 columns):
    #   Column      Non-Null Count  Dtype         
    ---  ------      --------------  -----         
    0   date        366 non-null    datetime64[ns]
    1   percentage  366 non-null    float64       
    dtypes: datetime64[ns](1), float64(1)
    memory usage: 5.8 KB
    ```

Ahora los datos están limpios y listos para su análisis.

<hr/>

## Ejercicio: Escritura de una función de predicción, parte 1

Ahora que ha limpiado los conjuntos de datos, puede empezar a crear una función que usará para realizar la predicción.

Pero en primer lugar, asegúrese de que sabe exactamente lo que quiere predecir: En una ciudad concreta, ¿en qué fecha es más probable que vea lluvias de meteoros?

En este módulo se presenta una manera simplificada de examinar los datos. Sin usar muchas predicciones, el método es muy similar a una tabla de búsqueda compleja. Más adelante podrá expandir el modelo con datos como los meteorológicos para que se parezca más a un modelo de Machine Learning clásico.

### Escritura de la función de predicción

Revisemos ahora los cuatro conjuntos de datos:

```python
meteor_showers.info()
moon_phases.info()
cities.info()
constellations.info()
```

La función que va a escribir debe hacer lo siguiente:

1. Determinar la *latitud* de una ciudad.
2. Usar esa latitud para determinar qué *constelaciones* se ven en esa ciudad.
3. Usar las constelaciones para determinar qué *lluvias de meteoros* se ven en esa ciudad.
4. Usar las lluvias de meteoros para determinar las *fechas* en las que son visibles.
5. Usar las fechas para buscar la *fecha óptima* en la que se perciba la menor cantidad de luz de la Luna.

Siga estos pasos para crear la función.

### Determinación de la latitud

Cree una función llamada `predict_best_meteor_shower_viewing` que tome una ciudad como parámetro:

```python
def predict_best_meteor_shower_viewing(city):
```

Aquí encontrará una operación de Python compleja. Si le parece complicado, no se preocupe. En este ejercicio es la primera vez que trabaja con este tipo de funcionalidad de ciencia de datos. Se necesita tiempo para acostumbrarse, por lo que puede considerarlo como una práctica.

```python
def predict_best_meteor_shower_viewing(city):
    # Get the latitude of the city from the cities DataFrame
    latitude = cities.loc[cities['city'] == city, 'latitude'].iloc[0]
```

Ahora se desglosará el código.

#### `cities['city'] == city`

La línea de código `cities['city'] == city` crea una lista de valores true y false. `True` estará en la fila donde la ciudad es igual a la ciudad que se ha pasado como parámetro.

Considere este ejemplo:

```python
print(cities['city'] == 'Abu Dhabi')
```

Este código obtiene la salida siguiente:

```
0       True
1      False
2      False
3      False
4      False
       ...  
251    False
252    False
253    False
254    False
255    False
Name: city, Length: 256, dtype: bool
```

#### `cities.loc[cities['city'] == city]`

La línea de código `cities.loc[cities['city'] == city]` devuelve las filas en las que el valor true o false anterior es `True`. En este caso solo se devuelve una fila, porque el dataframe de ciudades tiene una fila por cada ciudad.

Por ejemplo, podría escribir el código siguiente:

```python
print(cities.loc[cities['city'] == 'Abu Dhabi'])
```

Esta es la salida:

|   | city     | latitude | País o región          |
| - | -------- | -------- | ---------------------- |
| 0 | Abu Dabi | 24.47 	  | Emiratos Árabes Unidos |

#### `cities.loc[cities['city'] == city, 'latitude']`

La línea de código `cities.loc[cities['city'] == city, 'latitude']` solo devuelve la columna de latitud. No devuelve toda la fila.

Por ejemplo, podría imprimir el código siguiente:

```python
print(cities.loc[cities['city'] == 'Abu Dhabi', 'latitude'])
```

Esta es la salida:

```
0    24.47
Name: latitude, dtype: float64
```

#### `latitude = cities.loc[cities['city'] == city, 'latitude'].iloc[0]`

Por último, toda la línea de código devuelve el valor específico de esa columna en la fila 0:

```python
print(cities.loc[cities['city'] == 'Abu Dhabi', 'latitude'].iloc[0])
```

En este caso, el valor devuelto es 24.47:

```
24.47
```

### Llamada a la función

Ahora que tiene un valor, pruebe la función para asegurarse de que funciona de la forma esperada. Devuelva el valor actual y, después, llame a la función:

```python
def predict_best_meteor_shower_viewing(city):
    # Get the latitude of the city from the cities DataFrame
    latitude = cities.loc[cities['city'] == city, 'latitude'].iloc[0]

    return latitude
```

```python
print(predict_best_meteor_shower_viewing('Abu Dhabi'))
```

```
24.47
```

<hr/>

## Ejercicio: Escritura de una función de predicción, parte 2

### Uso de la latitud para determinar la constelación

Ahora que tiene la latitud de una ciudad, el paso siguiente consiste en usarla para determinar qué constelaciones se pueden ver en la ciudad.

```python
# Get the list of constellations that are viewable from that latitude
constellation_list = constellations.loc[(constellations['latitudestart'] >= latitude) & (constellations['latitudeend'] <= latitude), 'constellation'].tolist()
```

Esta línea se puede desglosar de esta forma:

* `(constellations['latitudestart'] >= latitude) & (constellations['latitudeend'] <= latitude)`
    - Marque una fila como `True` solo si la latitud identificada en la línea anterior se encuentra dentro de los valores `latitudestart` y `latitudeend` de esa fila.
* `constellations.loc[(constellations['latitudestart'] >= latitude) & (constellations['latitudeend'] <= latitude)`
    - Obtenga todas las filas en las que la latitud está dentro del rango de esa constelación.
* `constellations.loc[(constellations['latitudestart'] >= latitude) & (constellations['latitudeend'] <= latitude), 'constellation']`
    - Obtenga solo la columna de constelación de esas filas.
* `constellations.loc[(constellations['latitudestart'] >= latitude) & (constellations['latitudeend'] <= latitude), 'constellation'].tolist()`
    - Convierta la serie devuelta de la función `.loc` en una lista.

### Impresión de la lista de constelaciones

Recuerde que siempre debe imprimir mientras avanza para asegurarse de que obtiene los datos esperados.

```python
def predict_best_meteor_shower_viewing(city):
    # Get the latitude of the city from the cities DataFrame
    latitude = cities.loc[cities['city'] == city, 'latitude'].iloc[0]

    # Get the list of constellations that are viewable from that latitude
    constellation_list = constellations.loc[(constellations['latitudestart'] >= latitude) & (constellations['latitudeend'] <= latitude), 'constellation'].tolist()
    
    return constellation_list
```

```python
print(predict_best_meteor_shower_viewing('Abu Dhabi'))
```

```
['Lyra', 'Aquarius', 'Orion', 'Perseus']
```

### Creación de una cadena de salida

Antes de continuar con el análisis de los datos, cree una cadena que contendrá todas las lluvias de meteoros visibles desde esa ciudad. Incluya las mejores fechas para ver las lluvias de meteoros.

En este momento, también puede tener en cuenta el hecho de que no se representan todas las ciudades ni todas las constelaciones. Por tanto, algunas entradas de usuario podrían producir errores. En la parte superior de la función, agregue la siguiente instrucción condicional:

```python
# Create an empty string to return the message back to the user
meteor_shower_string = ""

if city not in cities.values:
    meteor_shower_string = "Unfortunately, " + city + " isn't available for a prediction at this time."
    return meteor_shower_string
```

Esta cadena devolverá antes de que se produzca cualquier otra cosa en el código, asegurándose de que no se produce un error. Este código se prueba de esta forma:

```python
print(predict_best_meteor_shower_viewing('San Diego'))
```

```
Unfortunately, San Diego isn't available for a prediction at this time.
```

También puede agregar una comprobación para ver si un constelación es visible desde la ciudad especificada. Este es el código escrito hasta ahora:

```python
def predict_best_meteor_shower_viewing(city):
    # Create an empty string to return the message back to the user
    meteor_shower_string = ""

    if city not in cities.values:
        meteor_shower_string = "Unfortunately, " + city + " isn't available for a prediction at this time."
        return meteor_shower_string

    # Get the latitude of the city from the cities DataFrame
    latitude = cities.loc[cities['city'] == city, 'latitude'].iloc[0]

    # Get the list of constellations that are viewable from that latitude
    constellation_list = constellations.loc[(constellations['latitudestart'] >= latitude) & (constellations['latitudeend'] <= latitude), 'constellation'].tolist()

    # If no constellations are viewable, let the user know
    if not constellation_list:
        meteor_shower_string = "Unfortunately, there are no meteor showers viewable from "+ city + "."

        return meteor_shower_string
```

Ahora, al principio de la cadena que se va a devolver, agregue una frase de inicio:

```python
meteor_shower_string = "In " + city + " you can see the following meteor showers:\n"
```

### Determinación de las lluvias de meteoros visibles

Por lo general, las lluvias de meteoros están asociadas a un constelación que se usa para indicar a qué punto del cielo se debe mirar para localizarlas. Por tanto, estas constelaciones se pueden usar para determinar qué lluvias de meteoros son visibles.

En una ciudad cualquiera, es probable que vea varias constelaciones. Por tanto, para esta parte siguiente, recorra cada una de las constelaciones identificadas en el paso anterior.

El código debería resultarle familiar:

```python
# Iterate through each constellation that is viewable from the city
    for constellation in constellation_list:
        # Find the meteor shower that is nearest to that constellation
        meteor_shower = meteor_showers.loc[meteor_showers['radiant'] == constellation, 'name'].iloc[0]
        # Find the start and end dates for that meteor shower
        meteor_shower_startdate = meteor_showers.loc[meteor_showers['radiant'] == constellation, 'startdate'].iloc[0]
        meteor_shower_enddate = meteor_showers.loc[meteor_showers['radiant'] == constellation, 'enddate'].iloc[0]

        # Find the Moon phases for each date within the viewable time frame of that meteor shower
        moon_phases_list = moon_phases.loc[(moon_phases['date'] >= meteor_shower_startdate) & (moon_phases['date'] <= meteor_shower_enddate)]
```

No olvide probarlo. Puede agregar una instrucción print al final. Simplemente asegúrese de aplicarle sangría para que se imprima cada vez que itere el bucle `for`.

```python
print(moon_phases_list)
```

### Búsqueda de la fecha óptima en función de las fases de la Luna

Por último, se puede encontrar el valor mínimo de la fase lunar (la menor cantidad de luz que refleja la Luna). Para esta función de predicción, solo se toma la primera fecha.

```python
# Find the first date where the Moon is the least visible
best_moon_date = moon_phases_list.loc[moon_phases_list['percentage'].idxmin()]['date']
```

Después, agregue esa información a la cadena que se va a devolver:

```python
# Add that date to the string to report back to the user
meteor_shower_string += meteor_shower + " is best seen if you look towards the " + constellation + " constellation on " +  best_moon_date.to_pydatetime().strftime("%B %d, %Y") + ".\n"
```

Una parte complicada de este código la conversión de la fecha en un objeto `pydatetime` y, después, en una cadena mediante `strftime`. Si intenta omitir esta parte, se producirá un error.

### Código final

Este es el código final de esta función predictiva:

```python
def predict_best_meteor_shower_viewing(city):
    # Create an empty string to return the message back to the user
    meteor_shower_string = ""

    if city not in cities.values:
        meteor_shower_string = "Unfortunately, " + city + " isn't available for a prediction at this time."
        return meteor_shower_string

    # Get the latitude of the city from the cities DataFrame
    latitude = cities.loc[cities['city'] == city, 'latitude'].iloc[0]

    # Get the list of constellations that are viewable from that latitude
    constellation_list = constellations.loc[(constellations['latitudestart'] >= latitude) & (constellations['latitudeend'] <= latitude), 'constellation'].tolist()

    # If no constellations are viewable, let the user know
    if not constellation_list:
        meteor_shower_string = "Unfortunately, there are no meteor showers viewable from "+ city + "."

        return meteor_shower_string

    meteor_shower_string = "In " + city + " you can see the following meteor showers:\n"
    
    # Iterate through each constellation that is viewable from the city
    for constellation in constellation_list:
        # Find the meteor shower that is nearest to that constellation
        meteor_shower = meteor_showers.loc[meteor_showers['radiant'] == constellation, 'name'].iloc[0]

        # Find the start and end dates for that meteor shower
        meteor_shower_startdate = meteor_showers.loc[meteor_showers['radiant'] == constellation, 'startdate'].iloc[0]
        meteor_shower_enddate = meteor_showers.loc[meteor_showers['radiant'] == constellation, 'enddate'].iloc[0]

        # Find the Moon phases for each date within the viewable time frame of that meteor shower
        moon_phases_list = moon_phases.loc[(moon_phases['date'] >= meteor_shower_startdate) & (moon_phases['date'] <= meteor_shower_enddate)]

        # Find the first date where the Moon is the least visible
        best_moon_date = moon_phases_list.loc[moon_phases_list['percentage'].idxmin()]['date']

        # Add that date to the string to report back to the user
        meteor_shower_string += meteor_shower + " is best seen if you look towards the " + constellation + " constellation on " +  best_moon_date.to_pydatetime().strftime("%B %d, %Y") + ".\n"
    
    return meteor_shower_string
```

Asegúrese de aplicar la sangría con atención.

Llame a la función de esta forma:

```python
print(predict_best_meteor_shower_viewing('Abu Dhabi'))
```

Este es el resultado:

```
In Abu Dhabi you can see the following meteor showers:
Lyrids is best seen if you look towards the Lyra constellation on April 22, 2020.
Eta Aquarids is best seen if you look towards the Aquarius constellation on April 22, 2020.
Orionids is best seen if you look towards the Orion constellation on October 16, 2020.
Perseids is best seen if you look towards the Perseus constellation on July 20, 2020.
```