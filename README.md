# Desafio ComoIr

Este es un proyecto que decidi comenzar gracias al desafio propuesto por Guillermo Moncecchi en [Medium][gmoncemedium]. Si bien he de reconocer que no tengo experiencia formal trabajando con ciencia de datos, big data, inteligencia artificial, machine learning, o cualuiera de los nombres que estan de moda, aun asi he tomado varios cursos (algunos mas desafiantes que otros) sobre estas tematicas. Desde cursos introductorios a Python o R, hasta cursos mas avanzados como el de Machine Learning de Andrew Ng en Coursera. De todas formas este desafio era la oportunidad de enfrentarme a un problema en un ambiente no controlado, fuera del ambito academico, donde si bien uno tiene que pelearla en mayor o menor medida, tambien es cierto que en mayor o menor medida le dan el trabajo un poco digerido. Este no era el caso. Aca el unico elemento con el que contaba era, "...estaria bueno hacer un mapa de calor con las estadisticas de uso del comoir...", basicamente eso era todo. 
Creo que eso fue una de las cosas que mas me motivo para enfrentar el desafio. Es un trabajo en progreso ya que falta algun detalle del desafio pero por lo menos pude construir algo más o menos parecido a un mapa de calor.

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

Los datos no estan subidos al repositorio porque son pesados (al menos algunos de ellos) y demoran en subir e incluso algunas veces me dieron error. Asi que decidí poner algunas funciones para descargar todos los archivos necesarios (y alguno que no termine usando tambien). Las funciones para la descarga las tome prestadas de un [MOOC sobre TensorFlow en Udacity][mooctensorflow]. La descarga y extraccion de los datos se hace en el /DesafioComoIr/data (si no existe el folder data dentro del folder DesafioComoIr lo crea). El codigo esta en /DesafioComoIr/source/movilidad_urbana.ipynb.

Las pruebas las hice con los datos del [2010][comoir2010], [2011][comoir2011] y [2013][comoir2013]; el csv del 2010 es el más chico por lo que es más manejable pero el resto va en incremento. Los mapas estan generados con [matplotlib][pltlink] y [bokeh][bokehlink] usando esquemas de colores generados con [ColorBrewer][cbrewerlink].

![alt text][img2010]

[gmoncemedium]: https://medium.com/@gmonce/cinco-desaf%C3%ADos-de-ciencia-de-datos-bad99448b7f7
[mooctensorflow]: https://www.udacity.com/course/deep-learning--ud730
[img2010]: https://raw.githubusercontent.com/avrinan/DesafioComoIr/master/source/comoir2011_bokehplot.png "ComoIr 2011"
[comoir2010]: https://rawgit.com/avrinan/DesafioComoIr/master/source/comoir2010.html
[comoir2011]: https://rawgit.com/avrinan/DesafioComoIr/master/source/comoir2011.html
[comoir2013]: https://rawgit.com/avrinan/DesafioComoIr/master/source/comoir2013.html
[pltlink]: https://matplotlib.org
[bokehlink]: http://bokeh.pydata.org/en/latest/
[cbrewerlink]: http://colorbrewer2.org/#type=sequential&scheme=BuGn&n=3
