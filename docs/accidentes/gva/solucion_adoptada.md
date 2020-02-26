# SOLUCI�N ADOPTADA

La soluci�n adoptada en el software gvSIG permite realizar estudios de accidentalidad tal y como se menciona en el p�rrafo anterior y lo realiza mediante la implementaci�n de 3 grandes grupos de procesos.

**Importaci�n de datos de Arena2.** Este apartado permite la obtenci�n de la informaci�n mediante el dise�o de un m�dulo de base de datos acorde a las especificaciones del sistema Arena2, la cual almacena los datos proporcionados gracias a la creaci�n de un importador de datos extensible que permite a parte tambi�n la gesti�n de incidencias.

**Consulta de accidentes (consulta de datos).** Como su propio nombre indica este apartado permite la visualizaci�n de los datos mediante fichas de b�squeda o formularios, los cuales nos proporciona un conjunto de registros o un �nico registro respectivamente. Adem�s este apartado proporciona tambi�n la posibilidad de visualizar los datos en informes as� como exportarlos en diferentes formatos como por ejemplo CSV.

**A�adir a la vista.** Esta �ltima fase de la herramienta no deja de ser otra forma de visualizaci�n pero se enfoca m�s en el aspecto geogr�fico del dato. Con esta nueva funcionalidad se pueden crear diferentes mapas con sus respectivas leyendas y etiquetado que permitan un estudio de manera visual de la informaci�n.

## Situaci�n previa

Previo a la realizaci�n de los trabajos que dan soporte al formato XML de ARENA2, exist�an para gvSIG Desktop complementos utilizados para la gesti�n de carreteras, accidentes y aforos. Estos complementos estaban desarrollados espec�ficamente para ser usados en el entorno de la GVA, ya que depend�an de BBDD con estructuras espec�ficas ubicadas en las instalaciones de esta. Los complementos existentes eran los siguientes:

* Gesti�n de usuarios (org.gvsig.cegesev.roadadmin)
* Gesti�n de carreteras (org.gvsig.cegesev.roadcatalog)
* Gesti�n de accidentes (org.gvsig.cegesev.accidentrate)
* Gesti�n de aforos (org.gvsig.cegesev.capacity)

## Modificaciones solicitadas

Debido al cambio en el formato en como la DGT proporciona a la GVA la informaci�n de los accidentes, se solicita dar soporte a que el complemento de "Gesti�n de accidentes" sea capaz de importar los nuevos ficheros.

## Soluci�n implementada

Tras evaluar el impacto en el complemento de "Gesti�n de accidentes" se decide sobrescribir completamente el complemento, optando por un modelo que reduzca al m�nimo los desarrollos espec�ficos e incluya de base en la aplicaci�n "gvSIG Desktop" gran parte de la funcionalidad que tenia el complementos de "Gesti�n de accidentes" existente. Para esto el desarrollo se divide en cuatro bloques:

* Actualizaciones en el n�cleo de gvSIG Desktop (mejoras o nuevos desarrollos relacionados con Informes, fichas de b�squeda, formularios, exportador,...).
* Desarrollo de un proveedor de datos para XML ARENA2.
* Desarrollo de un importador de datos extensible de ARENA2 a BBDD.
* Desarrollo de extensiones espec�ficas de la GVA para el importador de datos.

En el siguiente gr�fico de bloques podemos observar en que parte de la aplicaci�n encajan cada uno de estos desarrollos.

![Alt text](/solucion_adoptada_files/1000000000000366000001D0756F58124A511242.png)

Los desarrollos coloreados en rojo, son los desarrollos espec�ficos realizados para la GVA.

Los nuevos desarrollos, aunque pueden funcionar de forma independiente de los desarrollos que ya exist�an previamente, mantienen una relaci�n, que no dependencia, con el complemento de gesti�n de usuarios. Esto es, si esta instalado el complemento de gesti�n de usuarios, lo utilizara para comprobar si el usuario tiene permisos para realizar algunas operaciones, como pueden ser:

* Modificaci�n de la fecha de cierre.
* Modificaci�n de los datos de titularidad de un accidente.

De forma que solo los usuarios con permisos podr�n realizar estas operaciones.

Si no esta instalado el complemento de gesti�n de usuario, se podr� utilizar la aplicaci�n y acceder a los datos para su explotaci�n, pero no se podr�n modificar los accidentes importados en la BBDD.

Siempre que el usuario tenga las credenciales de acceso a la BBDD adecuadas no precisara de la herramienta de gesti�n de usuario para realizar operaciones de explotaci�n de los datos.

Vamos a ver con un poco de detalle en que consisten los cuatro bloques comentados.

### Actualizaciones en el n�cleo de gvSIG Desktop

Se trata de una serie de mejoras destinadas a aportar a gvSIG Desktop la funcionalidad que inclu�a el complemento de "Gesti�n de accidentes" de forma que estas est�n disponibles en la base de la aplicaci�n. Las principales son:

* Creaci�n de una ficha de b�squeda. Se a�ade una nueva ficha de b�squeda en la que se pueda especificar una condici�n de b�squeda y se presente los resultados en forma de tabla. La ficha de b�squeda dispone de un modo de b�squeda simple y otro avanzada. Dispone de las siguientes funcionalidades:

  * Favoritos e hist�rico de b�squedas
  * Campos de b�squeda preferidos
  * Campos de b�squeda mas usados
  * B�squeda en tablas relacionadas
  * Enlace a tablas con lista de valores
  * Previsualizaci�n de valores asociados a un campo
  * Formulario asociado a los datos
  * Exportaci�n resultados de b�squeda
  * Informes sobre los resultados de b�squeda

* Mejoras en el exportador de gvSIG. Se a�ade la funcionalidad relacionada con:

  * Exportaci�n a CSV
  * Selecci�n de campos a exportar y posibilidad de cambiar el nombre de estos.
  * Favoritos e hist�rico de exportaciones

* Mejoras en la gesti�n de formularios.
* Mejoras en los informes, entre otras se a�ade la posibilidad de asociar informes a una tabla o capa.

### Nuevo proveedor de datos para XML ARENA2

La aplicaci�n "gvSIG Desktop" dispone de una capa de abstracci�n para acceso a los datos. Esta capa de abstracci�n expone el concepto de "almac�n de datos", ofreciendo una serie de funcionalidades hacia la aplicaci�n independientes del formato de datos al que se quiere acceder (como puede ser, la obtenci�n de "cursores", su recorrido, filtros sobre ellos, localizaci�n de registro, ...). En las partes de la aplicaci�n que precisan acceder a los datos, se utiliza esta capa de abstracci�n, de forma que el desarrollo de la funcionalidad no esta ligado a un formato de datos especifico.

As� mismo la capa de abstracci�n define el concepto de proveedor de datos, y a que operaciones debe responder este, de forma que existe un proveedor de datos para cada formato especifico que soporta la aplicaci�n. Por ejemplo, existe un proveedor de datos para acceder a ficheros CSV, otro para DBFs, otro para SHPs, otro para BBDD PostgreSQL o para BBDD H2 Spatial. Este modelo permite desacoplar los entresijos del formato, de la l�gica de la aplicaci�n, de forma que una actualizaci�n en el formato implica la modificaci�n del proveedor de datos, reduciendo al m�nimo la adaptaci�n o modificaci�n del resto de la aplicaci�n a los cambios en este.

Adem�s, el modelo de proveedores de datos de gvSIG Desktop, no es un modelo est�tico. No existen 3 o 5 proveedores de datos. Estos se pueden cargar din�micamente en el arranque de la aplicaci�n. El n�cleo de gvSIG Desktop lleva con sigo los proveedores de:

* Ficheros CSV.
* Fichero dBASE (DBFs)
* Ficheros Shape (SHPs)
* Bases de datos H2 Spatial.

Luego existen una serie de complementos que aportan otros proveedores de datos y que no forman parte del n�cleo de gvSIG Desktop aportando soporte para:

* Bases de datos PostgreSQL/PostGIS
* Ficheros DXFs
* Fichero DWG
* Fichero MS Excel (XSL)
* Fichero ODS
* Bases de datos Oracle
* Bases de datos MS SQLServer

Y algunos m�s adem�s de los propios para acceder a datos raster que tienen su propio modelo de datos distinto del de los datos tabulares y vectoriales.

Algunos proveedores est�n desarrollados en Java, pero existen tambi�n proveedores desarrollados a trav�s de la herramienta de scripting en Python. El uso de estos por parte de la capa de abstracci�n de datos es independiente del entorno o lenguaje usado para su desarrollo siempre que el proveedor cumpla con las especificaciones de la capa de abstracci�n.

Con este concepto en mente, lo que se se ha hecho es desarrollar un proveedor de datos, utilizando la herramienta de scripting, que sea capaz de leer un fichero XML ARENA2, de forma que la aplicaci�n pueda acceder a los datos de este como si de cualquier otro "almac�n de datos" de gvSIG Desktop se tratase. Este proveedor de datos se despliega en la aplicaci�n en forma de un complemento independiente, de forma similar a como lo hace el de BBDD postgreSQL, DXF o ODS.

Dado que el proveedor de datos de XML ARENA2, se trata de un proveedor muy especifico, es decir, no lee datos de cualquier XML, sino solo de los datos de ARENA2, que define un modelo de datos en concreto, no solo esta en condiciones de aportar c�mo acceder a los datos, si no tambi�n otro tipo de informaci�n como:

* Etiquetas y descripciones para los campos.
* Relaciones entra las distintas tablas que hay en el fichero XML.
* Personalizaci�n de los formularios asociados a las distintas tablas del modelo de ARENA2.
* Personalizaci�n de los informes asociados a las tablas del modelo de ARENA2.
* Diccionarios de datos espec�ficos del modelo de ARENA2.

Con lo que se trata de un proveedor de datos que ademas de los datos aporta mucha informaci�n sobre como se deben visualizar estos.

### Importador de datos de ARENA2 a BBDD

Aunque la existencia de un proveedor de datos de XML ARENA2 para gvSIG Desktop permite ya la carga de los fichero XML de ARENA2 en la aplicaci�n, la funcionalidad que tenemos con esto es limitada. Por ejemplo, los datos del XML se cargan en memoria. O solo podemos acceder a los datos de un fichero XML a la vez. No se dispone de indices que permitan optimizar el acceso a los datos.

� Esto que quiere decir ? Pues que si tenemos dos ficheros XML de dos quincenas de datos de accidentes, no podr�amos cargarlos y realizar una b�squeda que arrojase datos de las dos quincenas ya que cada quincena estar�a en una tabla separada. Ademas, aunque pudi�semos unir en un solo XML los datos, estos se cargan en memoria para acceder a ellos, con lo que no podr�amos cargar ficheros muy grandes. Y cuando quisi�semos realizar una b�squeda sobre ellos, esta seria secuencial, es decir, tendr� que recorrerse todos los datos para localizar los que cumpliesen el criterio indicado.

As� que, aunque parezca atractivo trabajar directamente con los ficheros XML, no es optimo, y por ello se opto por implementar un importador de estos sobre una BBDD. Se desarroll� un importador espec�fico para ese tipo de fichero ya que deber�a realizar algunas tareas espec�ficas. Se precisaba poder realizar:

* Una georeferenciaci�n de los accidentes en funci�n de la carretera y el pk.
* Realizar comprobaciones sobre la titularidad de la carretera.
* Realizar comprobaciones sobre si una actualizaci�n de un accidente entraba en conflicto con modificaciones hechas en los datos de "nuestra" BBDD.

Y en funci�n de las comprobaciones realizadas sobre los datos de los accidentes, poder realizar una gesti�n de las incidencias producidas.

Para su desarrollo se decidi� preparar un importador sobre el que se pudiesen registrar "reglas de comprobaci�n" y "transformaciones de datos", y este se encargase de invocar a las reglas y transformaciones sobre los datos de entrada, realizar la gesti�n de incidencias e importar los datos en la BBDD de destino.

Se dejo fuera del importador la implementaci�n de las reglas y transformaciones, de forma que cada organismo que lo precisase pudiese aportar las suyas. Se trata pues de un importador "gen�rico" que se puede usar para cargar los datos de los XML de ARENA2 en una BBDD para luego poder realizar tareas de explotaci�n sobre el conjunto de datos y no sobre XML independientes.

### Extensiones espec�ficas de la GVA para el importador de datos.

Debido a las necesidades de la GVA, importar los datos de los XML en bruto no era suficiente. Al menos hab�a dos operaciones que hab�a que realizar con los datos antes de cargarlos en la BBDD, y que ademas, eran dependientes de informaci�n que tenia la GVA en otras tablas de BBDD propias.

Esto llevo al desarrollo de reglas de comprobaci�n y transformaciones espec�ficas para la GVA a la hora de importar los datos, que se aportan en un complemento independiente del importador. Este complemento aporta, entre otras cosas:

* Una transformaci�n, que a�ade a los datos del XML informaci�n de la posici�n del accidente sobre una carretera a partir de la identificaci�n de la carretera y el punto kilom�trico en el que se produce el accidente. Para esto se usa la base de datos de carreteras de la GVA, aportando una precisi�n mucho mayor que la que viene en los datos del accidente, ya que en este no siempre se dispone de esa informaci�n y en bastantes ocasiones, aunque se disponga no es precisa o fiable.
* Comprobaci�n de titularidad de la carretera. Se trata de comprobar si la titularidad de la carretera que figura en el accidente coincide con la que tiene la GVA en su BBDD de carreteras, generando la correspondiente incidencia en caso de ser necesario.
* Comprobaci�n de conflictos. En ocasiones, la GVA precisa alterar los datos de la carretera, kil�metro o titularidad que figuran en el accidente. Esta regla se encarga de comprobar si llega una actualizaci�n de un accidente que entra en conflicto con las modificaciones que ha realizado la GVA en estos datos.



