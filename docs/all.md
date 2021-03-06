{% comment %} encoding: utf-8 {% endcomment %}

{% include accidentes/gva/introduccion.md %}

{{pagebreak /}}

{% include accidentes/gva/solucion_adoptada.md %}

{{pagebreak /}}

{% include accidentes/gva/importacion_datos.md %}

# Consulta de datos

## Ficha de Búsqueda

Tras realizar la conexión con la base de datos de Arena2 ya se pueden realizar 
consultas y búsquedas sobre sus datos. Para realizar lo anterior el programa gvSIG 
dispone de la ficha de búsqueda.

{% include herramientas/ficha_de_busqueda/introduccion.md %}

En la ficha de búsqueda podemos encontrar tres paneles que nos permiten realizar
busuqedas con mas o menos funcionalidades. Estos son:

* El panel de "búsqueda simplificada".
* El panel de "búsqueda avanzada".
* El panel de "búsqueda especifica de accidentes".

### Busqueda simplificada

{% include herramientas/ficha_de_busqueda/simplificada.md %}

### búsqueda avanzada

{% include herramientas/ficha_de_busqueda/avanzada.md %}

### búsqueda especifica de accidentes

{% include accidentes/gva/consulta_datos/ficha_de_busqueda/ficha_accidentes.md %}

### Ejemplos

Para facilitar la comprensión de las fichas de búsqueda a continuación 
se muestran una serie de casos o ejemplos de cómo se realizan las 
consultas. Los ejemplos propuestos son:

* Localización de accidentes mortales.
* Localización de vehículos implicados en accidentes mortales.
* Localización de peatones involucrados en accidentes mortales.

#### Localizacion de accidentes mortales

{% include accidentes/gva/consulta_datos/ficha_de_busqueda/ejemplos/accidentes_mortales.md %}

#### Localizacion de peatones implicados accidentes mortales

{% include accidentes/gva/consulta_datos/ficha_de_busqueda/ejemplos/peatones_en_accidentes_mortales.md %}

#### Localizacion de vehiculos implicados accidentes mortales

{% include accidentes/gva/consulta_datos/ficha_de_busqueda/ejemplos/peatones_en_accidentes_mortales.md %}


## Formularios

{% include accidentes/gva/consulta_datos/formularios.md %}

## Informes

{% include accidentes/gva/consulta_datos/informes.md %}

## Exportacion

{% include accidentes/gva/consulta_datos/exportacion.md %}

### Exportacion a fichero CSV

{% include accidentes/gva/consulta_datos/exportacion_a_csv.md %}

# Añadir informacion a la vista

{% include accidentes/gva/anadir_a_la_vista/introduccion.md %}

## Leyenda

{% include accidentes/gva/anadir_a_la_vista/leyenda.md %}

## Etiquetado

{% include accidentes/gva/anadir_a_la_vista/etiquetado.md %}

# Anexos

## Creador de expresiones

{% include herramientas/constructor_expresiones/constructor_expresiones.md %}

### Funciones y operadores disponibles

{% include herramientas/constructor_expresiones/funciones_y_operadores.md %}

#### Operadores

{% include herramientas/constructor_expresiones/operadores.md %}

#### Funciones

{% include herramientas/constructor_expresiones/fn_numericas.md %}

{% include herramientas/constructor_expresiones/fn_carpetas.md %}

{% include herramientas/constructor_expresiones/fn_ogc.md %}

{% include herramientas/constructor_expresiones/fn_cadena.md %}

{% include herramientas/constructor_expresiones/fn_imagenes.md %}

{% include herramientas/constructor_expresiones/fn_accesodatos.md %}

{% include herramientas/constructor_expresiones/fn_logicas.md %}

{% include herramientas/constructor_expresiones/fn_conversion.md %}

{% include herramientas/constructor_expresiones/fn_fechas.md %}

## Informes de usuario

{% include herramientas/informes_usuario/informes_usuario.md %}

