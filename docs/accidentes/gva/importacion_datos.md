# IMPORTACI�N DE DATOS ARENA2

gvSIG Desktop es un software con soporte para cargar los XML de Arena2, proceso que puede realizarse de dos formas. Una primera forma directa o m�s primitiva que nos permite su visualizaci�n pero un deficiente tratamiento de los datos. La segunda forma resulta m�s acertada tanto para su visualizaci�n como para el tratamiento y consiste en cargar la informaci�n en un base de datos local optimizando la explotaci�n de recursos.

## Creaci�n de tablas

Este es el paso inicial y necesario para trabajar con los datos de Arena2 y consiste en crear e inicializar las tablas base y diccionarios necesarios para poder trabajar con dichos datos.

El proceso comienza al pulsar dentro de la *pesta�a Herramientas*, dentro de *Arena2*, el comando *Crear tablas*.

![Alt text](/importacion_datos_files/100002010000029B000001684F8F16A7522999AA.png)

Una vez realizado lo anterior se despliega una ventana siguiente.

![Alt text](/importacion_datos_files/10000000000001F300000136F71F30ECB72B49A1.png)

Dicha ventana permite definir los par�metros de la creaci�n de tablas, de modo que todas las pesta�as tiene que estar marcadas. Especial menci�n es que en este caso se crea el *Espacio de trabajo*, elemento necesario y definido en mayor medida en el apartado de *Conexi�n a espacio de trabajo*.

La conexi�n se realiza pulsando el icono de la esquina superior derecha, ![Alt text](/importacion_datos_files/100002010000002C0000002B806BCA7455134A82.png) y rellenando la siguiente ventana emergente que permite especificar todo lo referente a la base de datos a conectar y su situaci�n en el equipo.

![Alt text](/importacion_datos_files/100002010000010900000187F24F4043F34C110D.png)

### Descripci�n de los datos

Las tablas que forman parte de la base de datos Arena2 se muestran a continuaci�n con informaci�n de su contenido.


| Nombre de la tabla | Campos | Contenido |
|:---|:---:|:---|
| ARENA2_AC_VE_CO_PA | 308 | Informaci�n sobre veh�culo, conductor y pasajeros de un accidente. |
| ARENA2_AC_VE_CO_PA_PE | 348 | Informaci�n sobre veh�culo, conductor,  pasajeros y peatones de un accidente. |
| ARENA2_ACCIDENTES | 176 | Informaci�n general de accidentes. |
| ARENA2_CONDUCTORES | 61 | Informaci�n sobre el conductor de un accidente. |
| ARENA2_CROQUIS | 2 | Croquis de los accidentes. |
| ARENA2_DIC_ACC_SEG_CASCO | 2 | Informaci�n sobre el uso de casco en un accidente. |
| ARENA2_DIC_ACC_SEG_COND | 2 | Informaci�n sobre uso de accesorios de seguridad por el conductor en un accidente. |
| ARENA2_DIC_ACC_SEG_PAS | 2 | Informaci�n sobre uso de accesorios de seguridad por los pasajeros en un accidente. |
| ARENA2_DIC_ACC_SEG_PEA | 2 | Informaci�n sobre uso de accesorios de seguridad por los peatones en un accidente. |
| ARENA2_DIC_ACCION_CONDUCTOR | 2 | Informaci�n sobre las acciones especiales del conductor si las hay. |
| ARENA2_DIC_ACCION_PAS | 2 | Informaci�n sobre las acciones especiales de los pasajeros si las hay. |
| ARENA2_DIC_ACCION_PEA | 2 | Informaci�n sobre las acciones especiales de los peatones si las hay. |
| ARENA2_DIC_ACERA | 2 | Informaci�n sobre la acera en un accidente. |
| ARENA2_DIC_ANCHURA_ARCEN | 2 | Informaci�n sobre la anchura del arc�n en un accidente. |
| ARENA2_DIC_ANCHURA_CALZADA | 2 | Informaci�n sobre la anchura de la calzada en un accidente. |
| ARENA2_DIC_ANCHURA_CARRIL | 2 | Informaci�n sobre la anchura del carril en un accidente. |
| ARENA2_DIC_ASISTENCIA_SANITARIA | 2 | Informaci�n sobre la asistencia sanitaria dada a cualquier persona implicada en un accidente. |
| ARENA2_DIC_CARACT_FUNCIONAL_VIA | 2 | Informaci�n sobre la caracter�stica funcional de la v�a. |
| ARENA2_DIC_CARACTERISTICAS_PERMISO | 2 | Informaci�n sobre el estado del permiso de circulaci�n del conductor en un accidente. |
| ARENA2_DIC_CLASE_PERMISO | 2 | Informaci�n sobre el tipo de permiso de circulaci�n del conductor. |
| ARENA2_DIC_CONDICION_FIRME | 2 | Informaci�n del estado del firme en un accidente. |
| ARENA2_DIC_DANYOS | 2 | Informaci�n sobre el �rea  m�s da�ada del veh�culo. |
| ARENA2_DIC_DESPLAZAMIENTO_PREVISTO | 2 | Informaci�n sobre el tipo de desplazamiento previsto antes del accidente. |
| ARENA2_DIC_ERRORES_COND | 2 | Informaci�n sobre los presuntos errores cometido por el conductor en el accidente. |
| ARENA2_DIC_ERRORES_PEA | 2 | Informaci�n sobre los presuntos errores cometido por los peatones en el accidente. |
| ARENA2_DIC_ESTADO_INFORME | 2 | Informaci�n sobre el estado del informe de un accidente. |
| ARENA2_DIC_FACTORES_ATENCION_COND | 2 | Informaci�n sobre los factores que puedan afectar a la atenci�n del conductor. |
| ARENA2_DIC_FACTORES_ATENCION_PEA | 2 | Informaci�n sobre los factores que puedan afectar a la atenci�n de los peatones. |
| ARENA2_DIC_GENERICO2 | 2 | Informaci�n gen�rica (Si/No/Se desconoce). |
| ARENA2_DIC_ILUMINACION | 2 | Informaci�n sobre la iluminaci�n en el instante de un accidente. |
| ARENA2_DIC_INFORME_JUDICIAL | 2 | Informaci�n sobre la causa del fallecimiento o lesi�n seg�n informe judicial. |
| ARENA2_DIC_INFRACCIONES_CODUCTOR | 2 | Informaci�n sobre presuntas infracciones del conductor en un accidente |
| ARENA2_DIC_INFRACCIONES_OTRAS | 2 | Informaci�n sobre otras presuntas infracciones del conductor en un accidente. |
| ARENA2_DIC_INFRACCIONES_PEATON | 2 | Informaci�n sobre presuntas infracciones de los peatones en un accidente |
| ARENA2_DIC_INFRACCIONES_VELOCIDAD | 2 | Informaci�n sobre presuntas infracciones de velocidad del conductor en un accidente. |
| ARENA2_DIC_ITV | 2 | Informaci�n sobre el estado de la ITV del veh�culo. |
| ARENA2_DIC_LUGAR_CIRCULA | 2 | Informaci�n del lugar por el que circulaba el veh�culo. |
| ARENA2_DIC_MARCAS_VIALES | 2 | Informaci�n sobre las marcas viales existentes en la zona de un accidente. |
| ARENA2_DIC_METEO | 2 | Informaci�n sobre la meteorolog�a en el instante de un accidente. |
| ARENA2_DIC_MMA | 2 | Informaci�n sobre la masa m�xima autorizada del veh�culo. |
| ARENA2_DIC_MOTIVO_DESPLAZA_COND | 2 | Informaci�n sobre el motivo de desplazamiento del conductor implicado en un accidente. |
| ARENA2_DIC_MOTIVO_DESPLAZA_PEA | 2 | Informaci�n sobre el motivo de desplazamiento del peat�n implicado en un accidente. |
| ARENA2_DIC_NIEBLA | 2 | Informaci�n sobre el tipo de niebla existente en el momento del accidente. |
| ARENA2_DIC_NIVEL_CIRCULACION | 2 | Informaci�n sobre el nivel de circulaci�n existente en el momento de un accidente. |
| ARENA2_DIC_NUDO | 2 | Informaci�n que indica si un accidente ha ocurrido en zona de influencia de nudo o intersecci�n. |
| ARENA2_DIC_NUDO_APROX | 2 | Informaci�n que indica si el veh�culo se encontraba justo, en el nudo o intersecci�n, aproxim�ndose o alej�ndose del mismo. |
| ARENA2_DIC_NUDO_INFORMACION | 2 | Informaci�n a cumplimentar cuando el accidente ha ocurrido en zona de influencia de intersecci�n o nudo. |
| ARENA2_DIC_NUMERO_CALZADAS | 2 | Informaci�n sobre el n�mero de calzadas existentes en un accidente. |
| ARENA2_DIC_ONU | 3 | Informaci�n sobre el transporte de mercanc�as peligrosas por parte del veh�culo, as� como el peligro que representa y la naturaleza de la materia transportada. |
| ARENA2_DIC_POSICION_VEHICULO | 2 | Informaci�n de la posici�n en el veh�culo de cualquier persona implicada en un accidente. |
| ARENA2_DIC_POSICION_VIA | 2 | Informaci�n de la posici�n del veh�culo en la v�a. |
| ARENA2_DIC_PRUEBA_ALCOHOLEMIA | 2 | Informaci�n sobre la prueba de alcohol realizada. |
| ARENA2_DIC_PRUEBA_DROGAS | 2 | Informaci�n sobre la prueba de drogas realizada. |
| ARENA2_DIC_SENTIDO | 3 | Informaci�n sobre el sentido en el que ocurre el accidente, considerando los puntos kilom�tricos en carretera. |
| ARENA2_DIC_SENTIDO_CIRCULA | 2 | Informaci�n sobre el sentido de circulaci�n del veh�culo antes de producirse el accidente. |
| ARENA2_DIC_SENTIDOS_VIA | 2 | Informaci�n de los sentidos de v�a presentes en un accidente |
| ARENA2_DIC_SEXO | 2 | Informaci�n sobre el sexo de las personas. |
| ARENA2_DIC_TIPO_ACCIDENTE_ANIMAL | 2 | Informaci�n sobre el tipo animal implicado en un accidente. |
| ARENA2_DIC_TIPO_ACCIDENTE_COLISION | 2 | Informaci�n sobre el tipo de accidente seg�n primeros indicios. |
| ARENA2_DIC_TIPO_ACCIDENTE_SALIDA | 2 | Informaci�n sobre el tipo de salida de v�a provocado en un accidente |
| ARENA2_DIC_TIPO_BARRERA | 2 | Informaci�n sobre el tipo de barrera existente. |
| ARENA2_DIC_TIPO_VEHICULO | 2 | Informaci�n sobre el tipo de veh�culo implicado en un accidente. |
| ARENA2_DIC_TIPO_VIA | 2 | Informaci�n del tipo de v�a donde se ha producido un accidente. |
| ARENA2_DIC_TITULARIDAD_VIA | 2 | Informaci�n sobre la titularidad de la v�a donde se ha producido un accidente. |
| ARENA2_DIC_TRAZADO_ALZADO | 2 | Informaci�n sobre el trazado geom�trico vertical de la infraestructura donde se da el accidente. |
| ARENA2_DIC_TRAZADO_PLANTA | 2 | Informaci�n sobre el trazado geom�trico horizontal de la infraestructura donde se da el accidente. |
| ARENA2_DIC_VEL_GENERICA | 2 | Informaci�n sobre si la velocidad de la v�a donde tiene lugar el accidente es la velocidad gen�rica o est� indicada por se�alizaci�n espec�fica. |
| ARENA2_DIC_VIENTO | 2 | Informaci�n sobre la existencia de viento fuerte en el momento del accidente. |
| ARENA2_DIC_VISIBILIDAD_RESTRINGIDA_POR | 2 | Informaci�n sobre la visibilidad de la zona en el momento de un accidente. |
| ARENA2_DIC_ZONA | 2 | Informaci�n que indica si un accidente se ha producido en zona urbana o interurbana. |
| ARENA2_PASAJEROS | 23 | Informaci�n sobre los pasajeros de un accidente. |
| ARENA2_PEATONES | 42 | Informaci�n sobre los peatones de un accidente. |
| ARENA2_VEHICULOS | 60 | Informaci�n sobre el veh�culo implicado en un accidente. |

## Importador de datos

### Conexi�n a espacio de trabajo

Un espacio de trabajo asociado a una base de datos en gvSIG es un modelo de datos para gvSIG Desktop en el que se define las tablas que intervienen, especificando las relaciones entre estas y como deben cargarse dichas tablas.

Una idea importante es que estos elementos permiten acceder a las tablas/capas sin estar cargadas en el proyecto.

La conexi�n al espacio de trabajo en gvSIG Desktop se puede realizar de dos maneras;

**Conexi�n al espacio de trabajo de manera directa.** Para iniciar la conexi�n al espacio de trabajo de manera directa se tiene que ejecutar el comando *Connect to database workspace* dentro de la pesta�a *Archivo* en la ventana principal.

![Alt text](/importacion_datos_files/10000000000003B8000001D79761ED6EB3094C5E.png)

Tras la ejecuci�n aparece una nueva ventana con celdas vac�as que nos permite realizar la conexi�n.

![Alt text](/importacion_datos_files/1000020100000289000001AF76753AF27D089CA8.png)

Para rellenar los campos de dicha ventana se tiene que pulsar el bot�n con los puntos suspensivos (...) adyacente a la celda de conexi�n, apareciendo una nueva ventana que permite especificar todo lo referente a la base de datos a conectar y su situaci�n en el equipo.

![Alt text](/importacion_datos_files/100002010000027200000224AB2A2C69C23C7BFE.png)

Especial menci�n a la pesta�a *Conector* que nos permite establecer varios conectores seg�n el origen de nuestra base de datos.

![Alt text](/importacion_datos_files/100000000000026B000001F245F0DEC134418295.png)

Una vez detallada toda la informaci�n se pulsa el bot�n *Aceptar* y se est� en disposici�n de iniciar la conexi�n de manera directa mediante el bot�n *Connect*.

![Alt text](/importacion_datos_files/1000020100000249000001F764ED817C3CB7ECDE.png)

Una vez realizada la conexi�n al espacio de trabajo, para comprobar que se ha realizado la conexi�n y acceder a los datos disponibles se debe de ir al Cat�logo que aparece en la Vista.

Esta pesta�a se encuentra bajo la zona donde se enuncia los diferentes archivos cargados en el proyecto actual.

![Alt text](/importacion_datos_files/10000201000003C900000157F811C158A925907B.png)

Tras pulsar en el icono se muestra la siguiente estructura de carpetas.

![Alt text](/importacion_datos_files/100000000000018D000000C2B7D8D4737814C33B.png)

Accederemos a la opci�n de *Repositorios*, que tras haber realizado correctamente la conexi�n al espacio de trabajo, aparecer� con las conexiones de las que dispone este espacio.

Una vez accedemos a las tablas del repositorio de Arena2, tras pulsar bot�n derecho sobre alguna de ellas se pueden ver las opciones disponibles para estas tablas.

![Alt text](/importacion_datos_files/10000000000002BA000001ECADECFA0F6896E52D.png)

Si por ejemplo presionamos sobre *Abrir como tabla* se podr� visualizar la tabla de atributos.

![Alt text](/importacion_datos_files/100000000000039F000001E3B8E0705B5D75499E.png)

### Importador

El Importador es una herramienta que permite a gvSIG Desktop cargar los ficheros de la base de datos Arena2 en formato XML. Destacar que  la informaci�n de dichos archivos no siempre se encuentra en perfecta forma, presentando errores,  por ejemplo, en sus geometr�as o en la titularidad. Para corregir lo anterior la Asociaci�n gvSIG ha desarrollado para la GVA una herramienta que permite mediante extensiones de geocodificaci�n y reglas de validaci�n de accidentes corregir o detectar estos errores.

Para visualizar esta herramienta hay que pulsar la pesta�a *Herramientas*, dentro de *Arena2*, el comando *Importador*.

![Alt text](/importacion_datos_files/100002010000029B000001684F8F16A7522999AA.png)

A continuaci�n se muestra la interfaz de este.

![Alt text](/importacion_datos_files/10000201000002B900000218D0B55CBCDB94FCEA.png)

Las partes que lo componen son las siguientes.

![Alt text](/importacion_datos_files/10000201000002B90000021856E2D6867A3F7FAD.png)

1. Ventana con la ruta y archivo a a�adir.
2. Icono que permite a�adir ficheros.
3. Icono que permite a�adir una carpeta contenedora de ficheros.
4. Icono que permite eliminar o suprimir un fichero de los a�adidos en la ventana.
5. Desplegable donde se identifica la base de datos donde se van a integrar los ficheros.
6. Ventana con dos pesta�as. La pesta�a *Incidencias* muestra los casos donde el proceso indique una falta de integridad, mientras que la pesta�a *Opciones* muestra si la herramienta de geocodificaci�n est� activa, as� como otras reglas de validaci�n.
7. Icono que permite modificar por ventana una determinada caracter�stica de un n�mero de muestras.
8. Icono que permite eliminar las incidencias.
9. Icono que permite exportar las incidencias en diferentes archivos gracias al *Exportador*.
10. Icono que inicia el proceso de geocodificaci�n y utilizaci�n de las reglas de validaci�n para comprobar la integridad de los datos. Si un dato presenta alg�n error este se muestra en la ventana n�mero 6.
11. Icono que importa los datos.
12. Icono que cierra el *Importador*.

Una vez seleccionados los ficheros se puede proceder al proceso de importaci�n.

La herramienta tiene la posibilidad de registrar extensiones las cuales realizar�n validaciones o transformaciones de los datos durante el proceso de importaci�n. En este caso las extensiones se han personalizado para la GVA, pero se pueden desarrollar otras extensiones que se adapten a otra tipolog�a de datos o que tenga otras necesidades de validaci�n.

Las extensiones desarrolladas para la GVA son tres, una para el procesamiento de los datos y dos para la validaci�n de integridad. En el men� de opciones se pueden comprobar las extensiones registradas y activar o desactivar las que se deseen utilizar en este momento.

![Alt text](/importacion_datos_files/10000000000002E3000002B1D96D09039F2D6AEB.png)

* La geocodificaci�n. Permite geocodificar en base a segmentaci�n din�mica sobre la base de datos de carreteras de la GVA.
* Dos reglas de validaci�n.
  1. Regla de validaci�n que comprueba si la titularidad de la carretera donde se produce el accidente coincide con la titularidad de dicha carretera  en la base de datos de carreteras de la GVA.
  2. Regla de validaci�n que comprueba la existencia de conflicto en los campos *Tipo de v�a*, *Titularidad de la v�a*, *Nombre de la carretera* y *Kil�metro* entre lo especificado por la DGT y la base de datos de carreteras de la GVA. Si hay conflicto el importador permite su modificaci�n.

El primer paso ser�a realizar una comprobaci�n de integridad. Esta comprobaci�n lanzar�a las reglas de validaci�n y las incidencias encontradas aparecer�an en el panel. En el caso de no tener reglas de validaci�n registradas, la Comprobaci�n de Integridad no har� ninguna funci�n.

![Alt text](/importacion_datos_files/100002010000036C0000027484356C85DC619237.png)

#### Gesti�n de incidencias y exportaci�n

Una vez producida una incidencia esta puede tratarse de dos maneras.

* Ajustar el campo mediante la pesta�a de manera directa pesta�a de manera directa.
* Utilizando el bot�n *Modificar*.

A continuaci�n se muestra un ejemplo de c�mo realizar el cambio en la pesta�a de manera directa en el campo *Titularidad*.

![Alt text](/importacion_datos_files/100002010000036800000272C752AA9A8AAF02BF.png)

Tal y como se aprecia en la imagen anterior aparece una ventana desplegable con las opciones disponibles para dicho campo. Esta opci�n es �til si el n�mero de incidencias es reducido puesto que la modificaci�n se realiza caso a caso.

La otra opci�n de cambio se realiza al pulsar el bot�n *Modificar*, el cual crea una ventana emergente. Ver imagen siguiente.

![Alt text](/importacion_datos_files/100002010000036900000287EBA6FCB92B0700A4.png)

En dicha ventana emergente aparece el campo, en este caso *Titularidad*, y un desplegable con las diferentes opciones de igual manera que en el caso anterior, pero como diferencia, la modificaci�n mediante esta forma permite realizar cambios a multitud de casos. Este proceso se realiza seleccionando dichos casos o el campo concreto y pulsando dicho icono.

Otro aspecto destacable en este apartado es la exportaci�n de las incidencias. Para realizar dicha exportaci�n estas tiene que estar marcadas en la pesta�a *Importar* dentro del cuadro de incidencias y se tiene que pulsar el bot�n *Exportar*. Tras realizar lo anterior se ejecuta el *Exportador* que permite realizar ese proceso en multitud de formatos.

Una vez completada la gesti�n de incidencias, se podr�a pasar a la importaci�n de datos. Durante esta importaci�n se ejecutar�an las extensiones de transformaci�n en el caso de disponer de ellas.