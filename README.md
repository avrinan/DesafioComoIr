# Desafio ComoIr

Este es un proyecto que decidi comenzar gracias al desafio propuesto por Guillermo Moncecchi en [Medium][gmoncemedium]. Si bien he de reconocer que no tengo experiencia formal trabajando con ciencia de datos, big data, inteligencia artificial, machine learning, o cualuiera de los nombres que estan de moda, aun asi he tomado varios cursos (algunos mas desafiantes que otros) sobre estas tematicas. Desde cursos introductorios a Python o R, hasta cursos mas avanzados como el de Machine Learning de Andrew Ng en Coursera. De todas formas este desafio era la oportunidad de enfrentarme a un problema en un ambiente no controlado, fuera del ambito academico, donde si bien uno tiene que pelearla en mayor o menor medida, tambien es cierto que en mayor o menor medida le dan el trabajo un poco digerido. Este no era el caso. Aca el unico elemento con el que contaba era, "...estaria bueno hacer un mapa de calor con las estadisticas de uso del comoir...", basicamente eso era todo.
Creo que eso fue una de las cosas que mas me motivo para enfrentar el desafio. Es un trabajo en progreso ya que falta algun detalle del desafio pero por lo menos pude construir algo más o menos parecido a un mapa de calor.

## Lo nuevo
En esta nueva versión simplifique un poco las cosas; al menos esa era la idea. Originalmente tomaba las consultas y joineba con cada codiguera para poder obtener las coordenadas en el mapa, luego joinear con los barrios y contar cuantos puntos caian dentro de cada barrio. Esto tiene la contra que es bastante demoron por lo que cambie el enfoque. Ahora las consultas se reducen a los diferentes destinos y la frecuencia de busqueda de cada uno de ellos. Ahora el notebook descarga y realiza la limpieza y reduccion de los datos para los años del 2010 al 2014. Luego agrega una columna por año a la información de los barrios y genera el mapa de calor para cada año. Después, para un año especifico, hace un juego con los clasificadores Fisher Jenks y Quintiles pero usando solamente dos esquemas de colores: YrOrBr y Reds. Finalmente genera un mapa de colores con Bokeh el cual es interactivo y permite hacer zoom, paneo y al pasar el mouse sobre un barrio indica el nombre del mismo y la cantidad de consultas realizadas para ese año que cayeron dentro del barrio.

## Los Resultados
En la carpeta *source* estan generados los mapas con [bokeh][bokehlink] en un html por cada año; de todas formas dejo la lista de links para cada uno de los html. Al final de este Readme esta la imagen del mapa para el 2011. En el notebook hay otros mapas de calor generados con [matplotlib][pltlink].

- [Mapa de calor Como Ir 2010][comoir2010]
- [Mapa de calor Como Ir 2011][comoir2011]
- [Mapa de calor Como Ir 2012][comoir2012]
- [Mapa de calor Como Ir 2013][comoir2013]
- [Mapa de calor Como Ir 2014][comoir2014]

Asi se ve el mapa generado para el 2011. Las zonas mas rojas (o más calientes) son las que tienen mayor cantidad de destinos y las mas azules (o frías) son las que tienen menor cantidad de destinos buscados. En principio no parece muy loco que barrios como *Ciudad Vieja*, *Centro*, *Cordon*, *Parque Batlle*, *Pocitos* y *Punta Carretas* concentren el mayor "flujo de pasajeros" ya que en dichos barrios estarian concentradas las zonas comerciales, laborales, universidades, etc.

![alt text][img2011]

## Configuración
El notebook esta desarrollado y probado en una Mac con 8 Gb de RAM utilizando las siguientes herramientas/librerias:

- Anaconda 4.3.21
- python 3.6.0
- seaborn 0.7.1
- matplotlib 2.0.0
- numpy 1.11.3
- pandas 0.19.2
- pysal 1.13.0
- geopandas 0.2.1
- shapely 1.5.17
- bokeh 0.12.4

## Los Datos
Los datos no estan subidos al repositorio porque son pesados (al menos algunos de ellos) y demoran en subir e incluso algunas veces me dieron error. Asi que decidí poner algunas funciones para descargar todos los archivos necesarios (y alguno que no termine usando tambien). Las funciones para la descarga las tome prestadas de un [MOOC sobre TensorFlow en Udacity][mooctensorflow]. La descarga y extraccion de los datos se hace en el /DesafioComoIr/data (si no existe el folder data dentro del folder DesafioComoIr lo crea). El codigo esta en /DesafioComoIr/source/movilidad_urbana.ipynb.

[gmoncemedium]: https://medium.com/@gmonce/cinco-desaf%C3%ADos-de-ciencia-de-datos-bad99448b7f7
[mooctensorflow]: https://www.udacity.com/course/deep-learning--ud730
[img2011]: https://raw.githubusercontent.com/avrinan/DesafioComoIr/master/source/comoir2011_bokehplot.png "ComoIr 2011"
[comoir2010]: https://rawgit.com/avrinan/DesafioComoIr/master/source/comoir2010.html
[comoir2011]: https://rawgit.com/avrinan/DesafioComoIr/master/source/comoir2011.html
[comoir2012]: https://rawgit.com/avrinan/DesafioComoIr/master/source/comoir2012.html
[comoir2013]: https://rawgit.com/avrinan/DesafioComoIr/master/source/comoir2013.html
[comoir2014]: https://rawgit.com/avrinan/DesafioComoIr/master/source/comoir2014.html
[pltlink]: https://matplotlib.org
[bokehlink]: http://bokeh.pydata.org/en/latest/
[cbrewerlink]: http://colorbrewer2.org/#type=sequential&scheme=BuGn&n=3
