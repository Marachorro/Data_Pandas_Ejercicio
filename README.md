# Data_Pandas_Ejercicio
El presente informe tiene como objetivo describir y analizar las características principales del conjunto de datos disponible. Se incluirán tanto visualizaciones del análisis descriptivo como explicaciones de los resultados para poder analizar detalladamente. 

# 2. Descripción y origen de los datos 

Los datos se han integrado a partir de un archivo excel y un archivo csv. Se han generado dos bases de datos separadas para cada uno de los archvivos y, poteriormente, se han integrado los datos en una única base de datos para facilitar el manejo, la limpieza y orden de los datos.
El primer archivo utilizado es el de customer details, que, a su vez está compuesto de tres hojas de excel con información separada. Esto ha supuesto un total 20114  clientes con 6 columnas con información. Por otro lado, se encuentra también el archivo bank additional, con una única hoja donde aparecen datos relativos a los clientes como puede ser la tasa de variación de empleo o el índice de precios al consumidor.   

# 3. Transformación de los datos.
En cuanto a las transformaciones que se han llevado a cabo para poder trabajar con una base de datos limpia y ordenada

*3.1 Carga de archivos*
Se han cargado dos tipos de archivos: 
  - CSV: bank-additional.csv
  - Excel: customer-details, con tres hojas que posteriormente se han unido en un unico data set, para faciltar la visualización y navegación por los datos.

Estos dos archivos ha generado dos data sets independientes, que finalmente se han unido en uno único para obtener la información completa y depurada en un unico espacio, facilitando el manejo de los datos para llevar a cabo los análisis pertinentes. 

*3.2 Eliminación de columnas*

Se han eliminado varias columnas que no aportaban valor y generaban más ruido a la base de datos: 
- date
- unnamed:0
- lattitude
- longitude
- cons.price.idx
- cons.conf.idx
- euribor3m
- nr.employed
- emp.var.rate

Esto ha pasado también con variables como contact, poutcome y marital, ya que son variables que no se iban a utilizar en los análisis,y, por tanto, no aportaban valor. Para hacer el manejo de datos mucho más simple y accesible, se decició eliminar estas columnas. 

*3.3 Valores nulos*
para poder tratar los valores nulos se han llevado a cabo dos estrategias dependiendo del tipo de variable. 
Variable categorica: los valores nulos han sido sustituidos por la mediana para no alterar los resultados. Se ha preferido usar la mediana a la media puesto que la media es muy sensibls a valores extremos, por tanto el resultado podría quedar alterado en caso de usarla para complementar los valores nulos. 
Variable Numerica: los valores nulos han sido sustituidos por la moda -el valor mas frecuente en cada categoría- para no introducir categorías no existentes y alterar los datos 

*3.4 Creación de variables*
a. Year_sheet: con esta variable se ha podido estudiar la diferencia en afiliaciones según años, lo que ha permitido visualizar el incremento en afiliaciones entre 2013 y 2014. 
b. Hijos: una variable que, posteriormente, no se ha utilizado parallevar a cabo análisis, pero se ha generado para conocer y explorar la composición familiar de los clientes.
c. Grupos por igresos y grupos por edad: para pode representar de manera correcta datos tan dispares y diversos, se ha decidido crear varaiables etxra que agrupen estos valores, facilitando la represnetación e interpretación de los datos. 

# 4. Interpretación y visualizaciones. 

Se han llevado a cabo diferentes visualizaciones gracias a matplotlib, a continuación se decriben y analizan cada una e ellas en detalle. 

*4.1 Distribución de clientes por grupos de edad*
La primera de las visualizaciones es la distribución nde clientes por grupo de edad, en la cual podemos apeciar que la mayor parte de los/as clientes se concentra entre  los 30 y 40 años, con 20729 personas, seguido del grupo de entre 50 y 60, con 9650 personas que conforman el grupo. Esto indica que la base de los clientes está compuesta por personas en etapas de adultez consolidada, pudiendo influir, generalmente, en la estabilidad económica de los mismos y en la demanda de productos ofertados por la compañía. 

*4.2 Número de clientes por año*
La segunda visualización que se ha llevado a cabo es "Número de clientes por año". Esta visualización nos facilitará información respecto al año en el que la persona comienza a consumir los servicios ofrecidos. La mayor parte de los clientes comenzaron en 2012 (20115 personas), seguido de 2014 (14090) y, por último, 2013. Esto implica que en el año 2014 hubo un crecimiento aproximado de un 57% en las ventas. Esto nos lleva a cuestionarnos cuáles fueron los cambios llevados a cabo entre 2013 y 2014 que hayan podido suponer un incremento en las afiliaciones. 

*4.3 Distribución de clientes según trabajo*
La tercera visualización que se encuentra es la división de clientes según el tipo de trabajo. Los datos muestran que el grupo más numeroso es el de "Admin" (11218) seguido de "Blue collar" (11218). Esto nos indica que una gran parte de los clientes provienen de sectores administrativos y de industrias de trabajo manual o técnico, demostrando capacidad económica y adquisitiva diversas. 

*4.4 Distribución de clientes según educación*

La siguiente visualización muestra cómo se distribuyen los/as clientes/as según su nivel educativo. Los datos indican que el 33.8% posee un grado universitario, constituyendo el grupo más numeroso. En segundo lugar, un 30.3% se concentra en los niveles de educación básica (4, 6 o 9 años). Además, un 23.1% de los/as clientes/as cuenta con estudios equivalentes a la ESO o high school, mientras que el 12.7% restante ha completado cursos especializados como formación principal. Esta distribución revela que, aunque los trabajos administrativos son los más frecuentes dentro de la muestra, no requieren necesariamente estudios universitarios, ya que solo alrededor del 34% de los/as clientes/as ha cursado un grado. Esto sugiere que la base de clientes es diversa en términos educativos y que los puestos predominantes pueden estar asociados a requisitos formativos más flexibles.

*4.5 Porcentaje de clientes segun préstamos*
Solo el 15.2% de los/as clientes/as actuales tiene algún otro tipo de préstamo distinto del hipotecario. Este porcentaje relativamente bajo indica que la mayoría de la clientela no mantiene deudas adicionales más allá de las habituales.

Por otro lado, es relevante mencionar que el 54.7% de los/as clientes/as sí dispone de un prestamo hipotecario. Esto sugiere que más de la mitad de los clienes están vinculados a deudas a largo plazo, que podrían influir en la estabilidad económica de los/as mismos/as.

*4.6 boxplot Salarios*

El boxplot de salarios muestra que los cuartiles 2 y 3 abarcan un rango aproximado entre 50k € y 135k €, con una mediana cercana a los 90 000 €. Esto significa que el 50% central de la plantilla se sitúa dentro de ese intervalo salarial. Esto implica que el 25% de los/as clientes tienen salarios inferiores a los 50K, que conformarían el cuartil 1, y, también el 25% restante que percibe salarios superiores a los 135K, que conformarían el cuartil 4. 
Esto indica que los salarios que perciben los/as clientes/as son bastante diversos, reflejando una distribución salarial amplia 
En cuanto a salarios no encontramos outliers.

*4.7 Boxplot Edad*
El boxpot de edad muestra que los cuartiles 2 y 3 están conformados por clientes/as entre las edades de 30- 32 y 48-50 años, con una mediana cercana a los 49 años. En este caso sí se aprecian numerosos outliers, ya que el cuartil 4 abarca edades desde los 50 hasta los 65, pero  existen clientes con edades superiores a este rango, todo esto indica que existe un grupo minoritario de edades significativamente superiores que amplía la variabilidad del conjunto. Por último, es importante mencionar que el cuartil 1 lo conforman las personas entre 20 y 32 años, suponiendo un 25% de la población, con las edades más bajas del conjunto de datos. 

# 5. Hipótesis 

a. El crecimiento del 57% mencionado previamente podría estar relacionado con cambios en la estrategia comercial, las campañas de captación o cambios en el poder adquisitivo de las entre los años 2012 y 2013. 
b. El banco atrae a personas principalemente en etapas de la adultez consolidadas, con perfiles educativos y laborales diversos, lo cual puede indicar una amplia gama de productos que se ajustan a diferenes sectores de la población.
