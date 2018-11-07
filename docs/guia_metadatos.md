# Guía para el uso y la publicación de metadatos del Gobierno de la Ciudad Autónoma de Buenos Aires

## Introducción

### Versión

Esta guía busca ayudar a los organismos de la Administración Centralizada y Descentralizada y a las Entidades Autárquicas del Gobierno de la Ciudad Autónoma de Buenos Aires a instrumentar los lineamientos en materia de apertura de datos públicos establecidos en los Decretos N°[156/2012](https://boletinoficial.buenosaires.gob.ar/normativaba/norma/190097) y N° [478/2013](https://boletinoficial.buenosaires.gob.ar/normativaba/norma/234859) y a mejorar la calidad y la gestión de los datos generados por estas entidades. Está basada en la Guía para el uso y la publicación de metadatos elaborada por el equipo de la Dirección Nacional de Datos e Información Pública de la Secretaría de Gobierno de Modernización de la Jefatura de Gabinete de Ministros de la Nación. 

### Objetivo de esta guía

Esta es una **guía de recomendaciones y buenas prácticas, para el uso y la publicación de metadatos** del Gobierno de la Ciudad Autónoma de Buenos Aires (GCABA).

Las recomendaciones se basan en la guía del Gobierno Nacional, en estándares usados a nivel nacional e internacional y en la experiencia de trabajo del equipo de la Dirección General de Calidad Institucional y Gobierno Abierto, de la Subsecretaría de Gestión Estratégica y Calidad Institucional, Secretaría General y Relaciones Institucionales del Gobierno de la Ciudad Autónoma de Buenos Aires.

Esta es **una guía colaborativa y en progreso**. Valoramos, y alentamos, a organizaciones y ciudadanos a plantear ideas, sugerencias, y comentarios que nos ayuden a crear un mejor documento.

Este documento se complementa con la **[Guía para la publicación de datos en formatos abiertos](guia_abiertos.md)** y la **[Guía para la identificación y uso de entidades interoperables del Gobierno de la Ciudad Autónoma de Buenos Aires](guia_interoperables.md)**.

### ¿Qué son los metadatos?

**Los metadatos son los elementos descriptivos que dan contexto** a un conjunto de datos, y acercan al usuario la información necesaria para entenderlos y usarlos.

Un **título** y una breve **descripción** son los metadatos básicos que cualquier conjunto de datos a publicar debería tener. Otros elementos que ayudan al lector a hacer un buen uso de los datos, por ejemplo, pueden ser:

* **Nombre, tipo de datos y descripción de los campos**: ¿qué significa cada campo? ¿qué datos puedo encontrar en esa columna? ¿qué dicen y qué *no* dicen esos datos, cómo debo leerlos?
* **Palabras clave**: clasifican a un dataset como perteneciente a un conjunto de tópicos.
* **Tema**: clasifican a un dataset como perteneciente a un determinado tema, dentro de una jerarquía temática.
* **Fecha de publicación**: ¿cuándo se publicó por primera vez este dataset?
* **Fecha de última modificación**: ¿cuándo se actualizó por última vez este dataset?
* **Frecuencia de actualización**: ¿cada cuánto se actualiza este dataset?
* **URL de descarga**: ¿cómo dispongo de los datos, desde dónde puedo descargarlos?

Una lista curada de campos de metadatos, junto con las instrucciones de cómo deben utilizarse, define un **perfil de metadatos**.

En esta guía describimos el **perfil de metadatos recomendado para los catálogos del Gobierno de la Ciudad Autónoma de Buenos Aires** y cómo publicarlo.

### ¿Cómo se publican los metadatos?

**La publicación de los metadatos puede ser muy diversa** en detalle, calidad y forma. **Una publicación muy elemental es un documento de texto** que ofrece una descripción del dataset y de cada uno de los recursos que lo componen. Es posible ver un ejemplo textual de los metadatos de un catálogo de datos en el Anexo VI - Ejemplo de metadatos como texto.

Sin embargo, **las computadoras no pueden leer fácilmente documentos de texto**. La organización sistemática de colecciones de datasets (es decir, la creación de un **catálogo** de datos) exige un nivel de complejidad mayor para facilitar su descubrimiento, indexación, y reutilización por parte de scripts y aplicaciones de todo tipo.

La potencial reutilización de los conjuntos de datos dependerá de la calidad de sus metadatos. Por lo tanto, la lectura e interpretación de los conjuntos de datos mejora cuando se adoptan y/o desarrollanr estándares y vocabularios controlados.

Para esto, **los catálogos de datos publican sus metadatos en un formato estructurado (JSON)** respetando un determinado perfil estandarizado. Recomendamos ver un ejemplo en JSON de los metadatos de un catálogo de datos en el Anexo III - Ejemplo de data.json.

A continuación se detallan las características de los estándares y vocabularios controlados adoptados para catálogos de datos, datasets y distribuciones.

### Público objetivo de esta guía

Esta guía intenta ayudar a aquellas entidades que publican sus datos directamente en el [portal de datos abiertos del Gobierno de la Ciudad Autónoma de Buenos Aires](https://data.buenosaires.gob.ar/)  o de alguna forma alternativa. Estas entidades deberán publicar su catálogo en un archivo estructurado (JSON) siguiendo las especificaciones del perfil de metadatos de esta guía.

## Perfil de Metadatos

Cada entidad del Gobierno de la Ciudad Autónoma de Buenos Aires tendrá publicados los metadatos de sus conjuntos de datos en un archivo data.json 
Este archivo estará construido respetando los lineamientos establecidos en el Perfil de Metadatos tal como se lo describe más adelante en la sección “Campos del perfil”, tal como se puede ver en el ejemplo del Anexo IV - Ejemplo de data.json

### Estándar usado

**El perfil de metadatos recomendado en esta guía es una adaptación realizada por el equipo de Datos Abiertos del Gobierno Nacional utilizando como base el estándar [DCAT - AP](https://joinup.ec.europa.eu/solution/dcat-application-profile-data-portals-europe)**, usado por los países de la Unión Europea. DCAT es un vocabulario controlado definido por la W3C, ampliamente usado a nivel global para la descripción de catálogos de datos.

Según la W3C: "Mediante la utilización de DCAT para describir datasets en catálogos de datos, quienes publican aumentan la posibilidad de descubrimiento (*discoverability*) y permiten a aplicaciones informáticas consumir metadatos de manera simple desde múltiples catálogos. Además permite la publicación descentralizada de catálogos y favorece la búsqueda *federada* de datasets a través de varios sitios."

El perfil de metadatos propuesto para la Administración Pública Nacional se compone de 3 clases principales (*Catalog, Dataset y Distribution*) y 2 auxiliares (*Field* y *Theme*) que se relacionan según el siguiente esquema:

![](assets/der_perfil_metadatos.png)

A continuación, describimos los metadatos que el *data.json* debe contener, para cada una de estas clases.

### Campos del perfil

#### Catálogo (`catalog`)

El portal del Gobierno de la Ciudad Autónoma de Buenos Aires tendrá un catálogo con ciertos campos de perfil detallados más abajo.

Ejemplos de metadatos de un **catálogo**:

* [Catálogo en texto](https://github.com/datosgobar/paquete-apertura-datos/blob/master/examples/data.md)
* [Catálogo en JSON](https://github.com/datosgobar/paquete-apertura-datos/blob/master/examples/data.json)

Metadatos necesarios para describir el catálogo, que un *data.json* debe contener:

<table id="left-align-col-3-4">
  <tr>
    <th>Nombre</th>
    <th>Requerido</th>
    <th>Descripción</th>
    <th>Ejemplo</th>
    <th>Variable (data.json)</th>
    <th>Tipo (data.json)</th>
  </tr>
  <tr>
    <td>Nombre</td>
    <td>Sí</td>
    <td>Nombre dado al catálogo. Debe ser claro, breve y lo suficientemente abstracto como para abarcar la multiplicidad de datasets que contiene.</td>
    <td>Buenos Aires Data</td>
    <td>title</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Descripción</td>
    <td>Sí</td>
    <td>Descripción del contenido del catálogo.</td>
    <td>Portal de Datos Abiertos del Gobierno de la Ciudad Autónoma de Buenos Aires</td>
    <td>description</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Autor</td>
    <td>Sí</td>
    <td>Responsable de la publicación del catálogo.</td>
    <td>Secretaría General y Relaciones Institucionales - Gobierno de la Ciudad Autónoma de Buenos Aires</td>
    <td>publisher -> name</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Correo electrónico del autor</td>
    <td>Sí</td>
    <td>Correo electrónico de contacto del responsable de la publicación del catálogo.</td>
    <td>gobiernoabierto@buenosaires.gob.ar</td>
    <td>publisher -> mbox</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Datasets</td>
    <td>Sí</td>
    <td>Contiene una lista de los datasets que forman parte del catálogo.</td>
    <td>[{...}, {...}]</td>
    <td>dataset</td>
    <td>Array</td>
  </tr>
  <tr>
    <td>Fecha de creación o publicación</td>
    <td>Recomendado</td>
    <td>Fecha de creación o publicación del catálogo. Se escribe según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.</td>
    <td>"2016-04-14T19:48:05.433640" para especificar fecha y hora<br/>"2016-04-14" para especificar fecha únicamente</td>
    <td>issued</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Fecha de última actualización/ modificación</td>
    <td>Recomendado</td>
    <td>Fecha de última actualización/modificación del catálogo. Se escribe según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.</td>
    <td>"2016-04-19T19:48:05.433640" para especificar fecha y hora<br/>"2016-04-19" para especificar fecha únicamente</td>
    <td>modified</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Versión del perfil de metadatos</td>
    <td>Recomendado</td>
    <td>Es la versión del perfil de metadatos de la red de nodos de datos abiertos de la administración pública nacional de Argentina, utilizada en el catálogo.<br/><br/> Se utiliza para que distintas aplicaciones reconozcan y validen los metadatos del catálogo, y las funcionalidades disponibles para distintos fines.</td>
    <td>1.1</td>
    <td>version</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Idioma(s)</td>
    <td>Recomendado</td>
    <td>Lenguaje para la descripción de los metadatos de los datasets contenidos en el catálogo. Hay 2 estándares ISO que pueden ser utilizados para este campo:<br/>
    (a) ISO 639-1 (2 letras)<br/>
    (b) ISO 639-2/T (3 letras) es el más recomendado.<br/>
    Puede definirse 1 o más lenguajes en una lista. (<a href="https://www.loc.gov/standards/iso639-2/php/code_list.php">Link a los estándares ISO</a>)</td>
    <td>["es"] para un lenguaje ISO 639-1<br/>
    ["spa", "eng"] para dos lenguajes ISO 639-2</td>
    <td>language</td>
    <td>Array</td>
  </tr>
  <tr>
    <td>Licencia</td>
    <td>Recomendado</td>
    <td>Indica la licencia bajo la cual todos los datasets y distribuciones del catálogo están disponibles mediante un enlace a la licencia o documento de la licencia seleccionada, o mediante el título textual de la licencia tal como aparece en la lista de <a href="http://opendefinition.org/licenses/">http://opendefinition.org/licenses/</a> . recomendamos usar la licencia "Open Database License (ODbL) v1.0". Un dataset o distribución que especifique una licencia diferente, sobreescribe a la licencia general del catálogo.</td>
    <td>"http://opendatacommons.org/licenses/dbcl/1-0/" si se utiliza un enlace<br/>"Open Database License (ODbL) v1.0" si se consigna el nombre de la licencia a utilizar</td>
    <td>license</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Página web del catálogo</td>
    <td>Recomendado</td>
    <td>Dirección web de acceso a la página principal del catálogo. Enlace a la página principal del catálogo.</td>
    <td>http://data.buenosaires.gob.ar</td>
    <td>homepage</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Taxonomía temática global</td>
    <td>Sí</td>
    <td>Es el sistema de clasificación temática global del GCBA. Compone una lista de temas globales y está publicada en <a href=" http://data.buenosaires.gob.ar/superThemeTaxonomy.json">http://data.buenosaires.gob.ar/superThemeTaxonomy.json</a>.</td>
    <td>http://data.buenosaires.gob.ar/superThemeTaxonomy.json</td>
    <td>superThemeTaxonomy</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Taxonomía temática específica</td>
    <td>Recomendado</td>
    <td>Es el sistema de clasificación temática específica, creado por la organización responsable del catálogo. Compone una lista de temas específicos a los datasets del catálogo. Si se clasifica algún dataset del catálogo como perteneciente a uno o más temas, este campo es obligatorio ya que se debe explicitar una taxonomía temática para poder usar sus temas.</td>
    <td>[{...}, {...}]</td>
    <td>themeTaxonomy</td>
    <td>Array</td>
  </tr>
  <tr>
    <td>Derechos sobre el catálogo</td>
    <td>No</td>
    <td>Información sobre derechos aplicables al catálogo en el caso que no se hayan especificado en la licencia. Los datasets y sus distribuciones heredan la información sobre derechos aplicables al catálogo, a menos que especifiquen unos derechos distintos.</td>
    <td></td>
    <td>rights</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Cobertura geográfica</td>
    <td>No</td>
    <td>El área geográfica cubierta por el catálogo. Puede tomar valores:<br/>
    a) De comunas, barrios, fracciones censales o radios censales, según las recomendaciones de la Guía para la identificación y uso de entidades interoperables.<br/>
    b) Un área de coordenadas representada por latitud/longitud en el orden: minima longitud, mínima latitud, máxima longitud, máxima latitud.<br/>
    c) Un punto geográfico representado por latitud/longitud.<br/>
    d) Si la referencia geográfico no está identificada en la Guía para la identificación y uso de entidades interoperables indicar la URIs según geonames.org; ej : 
    http://sws.geonames.org/6255146</td>
    <td>"ARG" es el código para la República Argentina.<br/>
    "06007" es el código de un departamento<br/>
    [-58.111111, -35.111111, -57.111111, -33.111111] es un bounding box<br/>
    [-58.111111, -35.111111] es un punto geográfico<br/>"http://sws.geonames.org/6255146"</td>
    <td>spatial</td>
    <td>String or Array</td>
  </tr>
</table>

Dentro de los metadatos necesarios para describir el catálogo en un data.json , hay que poner atención a los dos campos que contienen una lista de objetos: **`dataset`** y **`themeTaxonomy`**.

El **primero** contendrá una lista de objetos que describen (cada uno) los metadatos de los distintos datasets que componen el catálogo (en la próxima sección se describen los metadatos que debe contener cada uno de estos objetos).

El **segundo** también contiene una lista de objetos que, juntos, definen una taxonomía temática para el catálogo. Cada uno de estos objetos contiene los metadatos que describen a cada uno de los temas de esta taxonomía. Más adelante se describen estos metadatos en la sección Tema.

#### Dataset (`dataset`)

A continuación, describimos los metadatos que se deben completar para describir un dataset a la hora de su carga o actualización en el catálogo.

Ejemplos de metadatos de un **dataset**:

* [Dataset en texto](https://github.com/datosgobar/paquete-apertura-datos/blob/master/examples/dataset.md)
* [Dataset en JSON](https://github.com/datosgobar/paquete-apertura-datos/blob/master/examples/dataset.json)

Metadatos que el *data.json* debe contener, para describir a un dataset dentro de la lista contenida en el campo **`dataset`** del catálogo:

<table id="left-align-col-3-4">
  <tr>
    <th>Nombre</th>
    <th>Requerido</th>
    <th>Descripción</th>
    <th>Ejemplo</th>
    <th>Variable (data.json)</th>
    <th>Tipo (data.json)</th>
  </tr>
  <tr>
    <td>Identificador</td>
    <td>Si</td>
    <td>Identificador único del dataset, este identificador debe ser único para todo el catálogo.</td>
    <td>Un identificador único para el dataset. La URI u otro identificador único en el contexto del catálogo, ejemplo:<br/>"dataset-ejemplo-35782”</td>
    <td>identifier</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Título</td>
    <td>Sí</td>
    <td>Nombre asignado al dataset tal como será publicado. Debe ser claro y lo suficientemente abstracto como para abarcar la multiplicidad de distribuciones que contiene. Se recomienda no exceder los 100 caracteres en la mayoría de los casos. En caso de que un título más largo se juzgue necesario o relevante, este no deberá exceder los 200 caracteres.</td>
    <td>Acceso a la información pública</td>
    <td>title</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Descripción</td>
    <td>Sí</td>
    <td>Descripción del contenido del dataset de un modo claro y conciso. Se recomienda no exceder los 500 caracteres en la mayoría de los casos. En caso de que una descripción más larga se juzgue necesaria o relevante, ésta no deberá exceder los 1500 caracteres.</td>
    <td>Datos correspondientes a pedidos de acceso a la información pública solicitados al Gobierno de la Ciudad conforme a la Ley 104</td>
    <td>description</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Autor</td>
    <td>Sí</td>
    <td>Responsable de la publicación del dataset. En el caso de organizaciones, detallar la estructura jerárquica separada por puntos, de manera jerárquicamente descendiente. Si la organización es parte del GCABA y se encuentra en el dataset "Organigrama" (<a href="https://data.buenosaires.gob.ar/dataset/organigrama">https://data.buenosaires.gob.ar/dataset/organigrama</a>), deberá utilizarse la denominación allí documentada.</td>
    <td>Ministerio de Gobierno. Subsecretaría de Reforma Política. Dirección General de Seguimiento de Organismos de Control y Acceso a la Información.</td>
    <td>publisher -> name</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Correo electrónico del autor</td>
    <td>Recomendado</td>
    <td>Correo electrónico de contacto del responsable de la publicación del dataset.</td>
    <td>dgsocai@buenosaires.gob.ar</td>
    <td>publisher -> mbox</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Área/Persona de contacto</td>
    <td>Recomendado</td>
    <td>Área/persona de contacto que puede brindar información relevante sobre el dataset.</td>
    <td>Ministerio de Gobierno. Subsecretaría de Reforma Política. Dirección General de Seguimiento de Organismos de Control y Acceso a la Información.</td>
    <td>contactPoint -> fn</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Correo electrónico del área/persona de contacto</td>
    <td>Recomendado</td>
    <td>Correo electrónico del área/persona de contacto que puede brindar información relevante sobre el dataset.</td>
    <td>dgsocai@buenosaires.gob.ar</td>
    <td>contactPoint -> hasEmail</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Distribuciones</td>
    <td>Sí</td>
    <td>Lista de distribuciones que pertenecen al dataset y sus metadatos. Cada distribución se representa con un objeto ("{}") donde se describen los metadatos especificados para la clase "distribution" de este perfil de metadatos.</td>
    <td>[{...}, {...}]</td>
    <td>distribution</td>
    <td>Array</td>
  </tr>
  <tr>
    <td>Temática(s) globales</td>
    <td>Sí</td>
    <td>Temática/s o categoría/s globales a la/s que se refiere el dataset al ser publicado. Un dataset puede pertenecer a más de una categoría global, de manera que el tipo de valor de este campo es una lista de categorías. La/s categoría/s o temática/s globales deben adoptarse según el campo "Código (authority code)" del Anexo "Taxonomía temática para los datasets", que contiene una lista predefinida de temática/s globales.</td>
    <td>["GOVE"]</td>
    <td>superTheme</td>
    <td>Array</td>
  </tr>
  <tr>
    <td>Temática(s) específicas</td>
    <td>Recomendado</td>
    <td>Temática/s o categoría/s específica/s a la/s que se refiere el dataset al ser publicado. Un dataset puede pertenecer a más de una categoría específica, de manera que el tipo de valor de este campo es una lista de categorías. La taxonomía a utilizar debe ser creada por la autoridad responsable del Catálogo. Se deben usar los ids (ver campo "id" de la clase Theme) de los temas definidos en la taxonomía para componer la lista (no se deben usar las etiquetas ni las descripciones).</td>
    <td>["Normas", "Transparencia"]</td>
    <td>theme</td>
    <td>Array</td>
  </tr>
  <tr>
    <td>Fecha de publicación</td>
    <td>Sí</td>
    <td>Fecha de publicación del dataset. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.</td>
    <td>"2016-04-14T19:48:05.433640" para especificar fecha y hora<br/>"2016-04-14" para especificar fecha únicamente</td>
    <td>issued</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Fecha de última actualización/ modificación</td>
    <td>Recomendado</td>
    <td>Fecha de última actualización/modificación del dataset (ya sea de sus datos o de sus metadatos). Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.</td>
    <td>"2016-04-19T19:48:05.433640" para especificar fecha y hora<br/>"2016-04-19" para especificar fecha únicamente</td>
    <td>modified</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Frecuencia de actualización</td>
    <td>Sí</td>
    <td>Frecuencia con la que se actualiza el dataset. Recomendamos especificar períodos normalizados con formato ISO-8601, agregando el campo “eventual” para datasets que se publican con una frecuencia eventual o no especificada. Anexo "Especificación de frecuencias según ISO-8601".</td>
    <td>“R/P6M” para datasets que se actualizan anualmente</td>
    <td>accrualPeriodicity</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Fuente primaria</td>
    <td>No</td>
    <td>Fuente original o primaria de los datos publicados en el dataset. Se utiliza cuando la entidad responsable de la publicación del dataset, no es la entidad que produce los datos.<br/><br/> Si la organización es parte del GCABA y se encuentra en el dataset "Organigrama" [https://data.buenosaires.gob.ar/dataset/organigrama](https://data.buenosaires.gob.ar/dataset/organigrama), deberá utilizarse la denominación allí documentada</td>
    <td>Ministerio de Gobierno. Subsecretaría de Reforma Política. Dirección General de Seguimiento de Organismos de Control y Acceso a la Información.</td>
    <td>source</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Página de referencias</td>
    <td>No</td>
    <td>URL de una página web a través de la cual se puede acceder al dataset, sus recursos o información adicional sobre el mismo.</td>
    <td>https://data.buenosaires.gob.ar/dataset/acceso-a-la-informacion-publica</td>
    <td>landingPage</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Etiqueta(s)</td>
    <td>Recomendado</td>
    <td>Palabras que describen el título o el contenido del recurso. Es necesario que las etiquetas se encuentren correctamente escritas, en plural y respetando la existencia de tags anteriores. Etiquetas que colaboran en la búsqueda de los usuarios. Cuanto más amplia y uniforme sea la lista de tags mayor será su eficiencia. A tales fines se recomienda ver el Anexo “Pautas para la selección de etiquetas”.</td>
    <td>["pedidos", "normas","transparencia"]</td>
    <td>keyword</td>
    <td>Array</td>
  </tr>
  <tr>
    <td>Cobertura temporal</td>
    <td>Recomendado</td>
    <td>Período de tiempo cubierto por el dataset. El intervalo de tiempo está formado por una fecha de inicio y una de fin separadas por “/”, en formato ISO 8601, con el nivel de especificidad requerido por el dataset.</td>
    <td>2013-01-01/2018-09-12</td>
    <td>temporal</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Licencia</td>
    <td>Recomendado</td>
    <td>Indica la licencia bajo la cual el dataset y todas sus distribuciones están disponibles mediante un enlace a la licencia o documento de la licencia seleccionada, o mediante el título textual de la licencia tal como aparece en la lista de <a href="http://opendefinition.org/licenses/">http://opendefinition.org/licenses/</a>. Recomendamos usar la licencia "Open Database License (ODbL) v1.0". Un dataset hereda por default la licencia general del catálogo salvo que se especifique una licencia diferente en este campo. Las distribuciones del dataset heredan esta licencia salvo que especifiquen una diferente.</td>
    <td>"http://opendatacommons.org/licenses/dbcl/1-0/" si se utiliza un enlace<br/>"Open Database License (ODbL) v1.0" si se consigna el nombre de la licencia a utilizar</td>
    <td>license</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Idioma(s)</td>
    <td>No</td>
    <td>Lenguaje para la descripción de los metadatos del dataset. Hay 2 estándares ISO que pueden ser utilizados para este campo:<br/>
    (a) ISO 639-1 (2 letras)<br/>
    (b) ISO 639-2/T (3 letras) es el más recomendado.<br/>
    Puede definirse 1 o más lenguajes en una lista. Los lenguajes especificados para un dataset, sobreescriben a los del catálogo. Si este campo está vacío el dataset hereda los lenguajes del catálogo. (<a href="https://www.loc.gov/standards/iso639-2/php/code_list.php">Link a los estándares ISO</a>)</td>
    <td>["es"] para un lenguaje ISO 639-1<br/>
    ["spa", ”eng"] para dos lenguajes ISO 639-2</td>
    <td>language</td>
    <td>Array</td>
  </tr>
  <tr>
    <td>Cobertura geográfica</td>
    <td>No</td>
    <td>Una región o lugar determinado al que el dataset haga referencia. Una región o un lugar determinado. Puede tomar valores:<br/>
    a) De comunas, barrios, fracciones censales o radios censales, según las recomendaciones de la Guía para la identificación y uso de entidades interoperables.<br/>
    b) Un área de coordenadas representada por latitud/longitud en el orden: mínima longitud, mínima latitud, máxima longitud, máxima latitud.<br/>
    c) Un punto geográfico representado por latitud/longitud.<br/>
    d) Si la referencia geográfico no está identificada en la Guía para la identificación y uso de entidades interoperables indicar la URIs según geonames.org; ej : http://sws.geonames.org/6255146"</td>
    <td>"ARG" es el código para la República Argentina.<br/>
    "06007" es el código de un departamento<br/>
    [-58.111111, -35.111111, -57.111111, -33.111111] es un bounding box<br/>[-58.111111, -35.111111] es un punto geográfico<br/>
    "http://sws.geonames.org/6255146"</td>
    <td>spatial</td>
    <td>Array or String</td>
  </tr>
</table>

Es importante prestar atención al campo **`distribution`** que contiene una lista de objetos que describen los metadatos de cada una de las distribuciones del daset. En la próxima sección abordaremos estos metadatos.

#### Distribución (`distribution`)

Estos son los metadatos que se deben completar al cargar o actualizar una distribución de un dataset en el catálogo para describirla.

Ejemplos de metadatos de una **distribución**:

* [Distribución en texto](https://github.com/datosgobar/paquete-apertura-datos/blob/master/examples/distribution.md)
* [Distribución en JSON](https://github.com/datosgobar/paquete-apertura-datos/blob/master/examples/distribution.json)

Metadatos que el *data.json* debe contener, para describir a una distribución dentro de la lista contenida en el campo **`distribution`** de un dataset:

<table id="left-align-col-3-4">
  <tr>
    <th>Nombre</th>
    <th>Requerido</th>
    <th>Descripción</th>
    <th>Ejemplo</th>
    <th>Variable (data.json)</th>
    <th>Tipo (data.json)</th>
  </tr>
  <tr>
    <td>Identificador</td>
    <td>Si</td>
    <td>Identificador único de la distribución, este identificador debe ser único para la distribución dentro del catálogo completo.<br/><br/>Debe estar compuesto por letras mayúsculas o minúsculas de la "a" a la "z" sin caracteres especiales (sin tildes y sin la "ñ"), números, guiones bajos "_", guiones medios "-" y puntos ".".</td>
    <td>1.2</td>
    <td>identifier</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Título</td>
    <td>Sí</td>
    <td>Nombre asignado a la distribución.</td>
    <td>Acceso a la Información Pública</td>
    <td>title</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Descripción</td>
    <td>Recomendado</td>
    <td>Breve descripción de la distribución. Recomendamos no escribir más de una línea. Toda información adicional puede ser incluida en la descripción del dataset.</td>
    <td>Pedidos de acceso a la información pública solicitados durante los años 2013-2018. Tema, fecha, dependencia y estado de la solicitud.</td>
    <td>description</td>
    <td>String</td>
  </tr>
  <tr>
    <td>URL de descarga</td>
    <td>Sí</td>
    <td>URL que permite la descarga directa de la distribución del dataset, vincula directamente a un archivo descargable en un formato dado.</td>
    <td>https://data.buenosaires.gob.ar/api/files/acceso-a-la-informacion-publica.csv/download/csv</td>
    <td>downloadURL</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Tipo de distribución</td>
    <td>Recomendado</td>
    <td>Indica el tipo de recurso.<br/><br/>"Archivo de datos" (file): archivo físico de algún formato de datos que se puede descargar.<br/>"API" (api): documentación en línea de un servicio web de datos.<br/>"Código" (code): repositorio o archivo con scripts utilizados para la generación, transformación, limpieza o validación de los datos de todo o parte del dataset.<br/>"Documentación" (documentation): documentación metodológica sobre los datos de todo o parte del dataset.</td>
    <td>file<br/>api<br/>code<br/>documentation</td>
    <td>type</td>
    <td>String</td>
  </tr>
  <tr>
    <td>URL de acceso</td>
    <td>Sí</td>
    <td>URL que permite el acceso a la distribución del dataset. Puede ser una página, feed u otro tipo de recurso que dé acceso indirecto a las distribuciones. Si las distribuciones son solo accesibles a través de la página de referencia del dataset, debe completarse el valor de la URL de acceso a la distribución con el mismo valor de la página de referencia del dataset.</td>
    <td>https://data.buenosaires.gob.ar/api/files/acceso-a-la-informacion-publica.csv/download/csv</td>
    <td>accessURL</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Campos de la distribución</td>
    <td>Recomendado</td>
    <td>Lista de campos que contiene una distribución tabular (no aplica para aquellas distribuciones que no sean tablas) y sus metadatos. Cada campo se representa con un objeto ("{}") donde se describen los metadatos especificados para la clase "field" de este perfil de metadatos (como "nombre", "tipo" y "descripción").</td>
    <td>[{...}, {...}]</td>
    <td>field</td>
    <td>Array</td>
  </tr>
  <tr>
    <td>Fecha de publicación</td>
    <td>Sí</td>
    <td>Fecha de publicación de la distribución. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.</td>
    <td>"2016-04-14T19:48:05.433640" para especificar fecha y hora<br/>"2016-04-14" para especificar fecha únicamente</td>
    <td>issued</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Fecha de última actualización/modificación</td>
    <td>Recomendado</td>
    <td>Fecha de última actualización/modificación de la distribución. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.</td>
    <td>"2016-04-19T19:48:05.433640" para especificar fecha y hora<br/>"2016-04-19" para especificar fecha únicamente</td>
    <td>modified</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Formato del archivo</td>
    <td>Recomendado</td>
    <td>Indica el formato del archivo de la distribución. Si el tipo de la distribución está definido por IANA (http://www.iana.org/assignments/media-types/media-types.xml), debe usarse esa definición. En caso contrario deberán ponerse los caracteres después del punto final del archivo, que determinan el formato (cuando no está definido por IANA).</td>
    <td>"text/csv" definición de IANA "csv" caracteres finales después del punto</td>
    <td>format</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Nombre del archivo</td>
    <td>Recomendado</td>
    <td>Nombre de la distribución bajo el cual se descarga un archivo que contiene los datos, incluyendo la extensión del formato.<br/><br/>Debe estar compuesto por letras minúsculas de la "a" a la "z" sin caracteres especiales (sin tildes y sin la "ñ"), números y guiones medios "-".</td>
    <td>acceso-a-la-informacion-publica.csv</td>
    <td>fileName</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Licencia</td>
    <td>Recomendado</td>
    <td>Indica la licencia bajo la cual la distribución está disponible mediante un enlace a la licencia o documento de la licencia seleccionada, o mediante el título textual de la licencia tal como aparece en la lista de <a href="http://opendefinition.org/licenses/">http://opendefinition.org/licenses/</a>. Recomendamos usar la licencia "Open Database License (ODbL) v1.0". Una distribución hereda por default la licencia del dataset al que pertenece, salvo que se especifique una licencia diferente en este campo.</td>
    <td>"http://opendatacommons.org/licenses/dbcl/1-0/" si se utiliza un enlace<br/> "Open Database License (ODbL) v1.0" si se consigna el nombre de la licencia a utilizar</td>
    <td>license</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Tipo de archivo</td>
    <td>No</td>
    <td>Indica el tipo de archivo de la distribución, sólo si este está definido por IANA (http://www.iana.org/assignments/media-types/media-types.xml). En caso contrario este campo permanece vacío.</td>
    <td>"text/csv" definición de IANA "" cuando el formato no tiene definición en IANA</td>
    <td>mediaType</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Tamaño</td>
    <td>No</td>
    <td>Tamaño de la distribución en bytes. El tamaño puede ser aproximado cuando no se conozca el tamaño exacto.</td>
    <td>Ejemplo para un archivo de 5Kb aproximadamente: "5120”</td>
    <td>byteSize</td>
    <td>Integer</td>
  </tr>
  <tr>
    <td>Derechos sobre la distribución</td>
    <td>No</td>
    <td>Información sobre derechos aplicables a la distribución que no se hayan especificado en la licencia. Si se especifican, estos derechos sobreescriben a los del catálogo. En caso contrario, las distribuciones heredan los derechos especificados para el catálogo.</td>
    <td></td>
    <td>rights</td>
    <td>String</td>
  </tr>
</table>

Recomendamos poner atención al campo **`field`** que contiene una lista de objetos que describen los metadatos de cada uno de los campos de la distribución (en el **caso de distribuciones tabulares, únicamente**). En la próxima sección abordaremos estos metadatos.

#### Campo (`field`)

Recomendamos enfáticamente que las distribuciones tabulares **incluyan metadatos que ayuden a entender la información que contiene cada campo**. Documentarlos adecuadamente facilita enormemente la correcta utilización de los datos por parte de los usuarios.

En un portal Andino, estos metadatos se completan en el mismo formulario que se utiliza para cargar o actualizar una distribución.

Ejemplos de metadatos de un **campo**:

* [Metadatos de un campo de una distribución tabular en JSON](https://github.com/datosgobar/paquete-apertura-datos/blob/master/examples/field.json)

Estos son los metadatos que el *data.json* debe contener para describir a un campo de una distribución tabular dentro de la lista contenida en el campo de metadatos **`field`** de una distribución:

<table id="left-align-col-3-4">
  <tr>
    <th>Nombre</th>
    <th>Requerido</th>
    <th>Descripción</th>
    <th>Ejemplo</th>
    <th>Variable (data.json)</th>
    <th>Tipo (data.json)</th>
  </tr>
  <tr>
    <td>Nombre</td>
    <td>Recomendado</td>
    <td>El nombre del campo tal como se denomina en el encabezado de la distribución. Véase la "Guía para la publicación de datos en formatos abiertos del Gobierno de la Ciudad Autónoma de Buenos Aires" para una adecuada elección del nombre de un campo.<br/><br/>Se recomienda no exceder los 40 caracteres en la mayoría de los casos. En caso de que un título más largo se juzgue necesario o significativamente más claro, este no deberá exceder los 60 caracteres en ningún caso.<br/><br/>Debe estar compuesto por letras minúsculas de la "a" a la "z" sin caracteres especiales (sin tildes y sin la "ñ"), números y guiones bajos "_".</td>
    <td>Ejemplo para el octavo campo del recurso "Acceso a la Información Pública", valor para el nombre: " categoria_tema "</td>
    <td>title</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Tipo</td>
    <td>Recomendado</td>
    <td>El tipo de dato contenido en el campo según la lista utilizada por la librería recline.js (<a href="http://okfnlabs.org/recline/docs/models.html#types">http://okfnlabs.org/recline/docs/models.html#types</a>).
    <br/><br/>Los tipos incluidos en esta lista son:<br/><br/>
    string (text): Valores de texto.<br/>
    number (double, float, numeric): Números que puedan no ser enteros (incluyen decimales).<br/>
    integer (int): Números que siempre son enteros.<br/>
    date: Fecha simple expresada según el estándar ISO 8601 incluyendo únicamente año, mes y día (YYYY-MM-DD) como en "2016-02-01".<br/>
    time: Tiempo expresado según el estándar ISO 8601 incluyendo únicamente horas, minutos y segundos (hh:mm:ss) como en "10:05:00".<br/>
    date-time (datetime, timestamp): Fecha completa expresada según el estándar ISO 8601 incluyendo año, mes, día, horas, minutos y segundos (YYYY-MM-DDThh:mm:ssZ) como en "2016-02-01T10:05:00+03:00"<br/>
    boolean (bool): Valores verdadero/falso.<br/>
    binary: Representación de datos binarios base64.<br/>
    geo_point: Ver estructura en  <a href="https://www.elastic.co/guide/en/elasticsearch/reference/current/geo-point.html">https://www.elastic.co/guide/en/elasticsearch/reference/current/geo-point.html.</a><br/>
    geojson: ver en <a href="http://geojson.org/">http://geojson.org/</a><br/>
    array: Lista de valores.<br/>
    object (json): Objeto de JSON.<br/>
    any: Campo que puede contener valores de cualquier tipo.</td>
    <td>Ejemplo para el campo: " categoria_tema "del recurso "Acceso a la Información Pública", valor para tipo: "string"</td>
    <td>type</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Descripción</td>
    <td>Recomendado</td>
    <td>La descripción de la información que contiene el campo.</td>
    <td>Ejemplo para el campo: " categoria_tema "del recurso "Acceso a la Información Pública"", valor para descripción: "Tema de la categoría según lo establecido por el Ministerio de Gobierno."</td>
    <td>description</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Identificador</td>
    <td>No</td>
    <td>El código identificador del campo. Debe ser único para todo el catálogo. Se utiliza cuando el campo requiere un identificador para ser utilizado en un sistema o aplicación, como en el caso de una base de series de tiempo (donde el identificador ejerce el rol de "nomenclador" del campo y debe ser único para todo el sistema - más allá incluso del presente catálogo).<br/><br/>Debe estar compuesto por letras mayúsculas o minúsculas de la "a" a la "z" sin caracteres especiales (sin tildes y sin la "ñ"), números, guiones bajos "_", guiones medios "-" y puntos ".".</td>
    <td>1.1_OGP_D_1993_A_17</td>
    <td>id</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Unidad de medida</td>
    <td>No</td>
    <td>La descripción de la unidad de medida en la que están expresados los valores del campo. Sólo se utiliza para campos de tipo numérico.</td>
    <td>Millones de pesos a precios de 1993</td>
    <td>units</td>
    <td>String</td>
  </tr>
</table>

Los primeros tres metadatos son útiles para **describir las características de cualquier campo de una distribución tabular**.

Los últimos dos metadatos son opcionales porque sólo cobran sentido al **describir las características de un campo, para casos específicos**. Mientras que no todos los campos de una distribución tabular tienen "**unidad de medida**", la asingación de un **"nomenclador" o "identificador"** suele ser útil para la identificación unívoca de variables en otros sistemas o aplicaciones, pero no en la generalidad de los casos.

#### Tema (`theme`)

Cada catálogo de datos puede tener su propia taxonomía temática que permite clasificar a los datasets como pertenecientes a una o más categorías temáticas. Recomendamos que los temas tengan algunos metadatos que ayuden a un usuario a entenderlos mejor.

Estos son metadatos que el responsable de cargar o actualizar la taxonomía temática de un catálogo debe completar para describir los temas de la misma.

Ejemplos de metadatos de un **tema**:

* [Metadatos de un tema en JSON](https://github.com/datosgobar/paquete-apertura-datos/blob/master/examples/theme.json)

Metadatos que el *data.json* debe contener, para describir a un tema de la taxonomía temática de un catálogo:

<table id="left-align-col-3-4">
  <tr>
    <th>Nombre</th>
    <th>Requerido</th>
    <th>Descripción</th>
    <th>Ejemplo</th>
    <th>Variable (data.json)</th>
    <th>Tipo (data.json)</th>
  </tr>
  <tr>
    <td>Identificador</td>
    <td>Recomendado</td>
    <td>El identificador del tema.</td>
    <td>AGRI</td>
    <td>id</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Etiqueta</td>
    <td>Recomendado</td>
    <td>La etiqueta o título de un tema.</td>
    <td>Gobierno</td>
    <td>label</td>
    <td>String</td>
  </tr>
  <tr>
    <td>Descripción</td>
    <td>Recomendado</td>
    <td>Una breve y concisa descripción del tema.</td>
    <td>Bajo este concepto se incluyen datasets que cubren dominios referidos al Gobierno o al Sector Público.</td>
    <td>description</td>
    <td>String</td>
  </tr>
</table>

## Glosario

Ver [Glosario](glosario.md)

## Anexo I - Taxonomía temática global de la APN para los datasets (tabla)

Siguiendo los lineamientos para la Administración Pública Nacional, se utilizará  la [taxonomía temática definida por la Unión Europea](http://publications.europa.eu/mdr/authority/data-theme/index.html). Los campos de metadatos para definir la taxonomía son:

* **themeTaxonomy**: es un campo de metadatos del catálogo que define una lista de temas que se pueden usar para clasificar los datasets. Refiere al esquema completo de la taxonomía en sí, no a alguna de sus etiquetas en particular.

* **theme**: es un campo de metadatos de un Dataset. Refiere a la/s etiqueta/s en particular bajos la/s cuales un dataset es clasificado temáticamente. Sólo pueden usarse etiquetas que estén definidas en la taxonomía temática de *themeTaxonomy*.

Además del uso de una taxonomía propia de cada catálogo de datos, **recomendamos la clasificación de los datasets según la taxonomía del Portal Nacional de Datos del Gobierno Nacional.** Esta es una *súper taxonomía* a la que cada catálogo hace referencia mediante los siguientes campos de metadatos:

* **superThemeTaxonomy**: es un campo de metadatos del catálogo que apunta a la URL donde el Portal Nacional de Datos documenta la taxonomía temática de la Administración Pública Nacional.

* **superTheme**: es un campo de metadatos de un dataset. Refiere a la/s etiqueta/s en particular bajos la/s cuales un dataset es clasificado temáticamente, según la *súper taxonomía* que es la de la Administración Pública Nacional. Sólo pueden usarse etiquetas que estén definidas en la taxonomía temática de *superThemeTaxonomy*.

**La ventaja de usar una súper taxonomía** temática es que **facilita la clasificación de datasets** por parte de un usuario según un conjunto de categorías temáticas más generales, que son interoperables con las usadas por otros países del mundo.

<table>
      <td>Código (authority code)</td>
      <td>Etiqueta (label)</td>
      <td>Descripción (description)</td>
    </tr>
    <tr>
      <td>AGRI</td>
      <td>Agroganadería, pesca y forestación</td>
      <td>Datos referidos a agroganadería, pesca y forestación. Por ejemplo: 'Lechería: precio pagado al productor' o 'Superficie forestada'.</td>
    </tr>
    <tr>
      <td>ECON</td>
      <td>Economía y finanzas</td>
      <td>Datos referidos a economía y finanzas. Por ejemplo: 'Mapa de oportunidades comerciales'.</td>
    </tr>
    <tr>
      <td>EDUC</td>
      <td>Educación, cultura y deportes</td>
      <td>Datos referidos a educación, cultura y deportes. Por ejemplo: 'Distritos Escolares'.</td>
    </tr>
    <tr>
      <td>ENER</td>
      <td>Energía</td>
      <td>Datos referidos a energía. Por ejemplo: 'Transformadores PCB'.</td>
    </tr>
    <tr>
      <td>ENVI</td>
      <td>Medio ambiente</td>
      <td>Datos referidos a medio ambiente. Por ejemplo: 'Arbolado público lineal'.</td>
    </tr>
    <tr>
      <td>GOVE</td>
      <td>Gobierno y sector público</td>
      <td>Datos referidos a gobierno y sector público. Por ejemplo: 'Acceso a la información pública'.</td>
    </tr>
    <tr>
      <td>HEAL</td>
      <td>Salud</td>
      <td>Datos referidos a salud. Por ejemplo: 'Áreas hospitalarias'.</td>
    </tr>
    <tr>
      <td>INTR</td>
      <td>Asuntos internacionales</td>
      <td>Datos referidos a asuntos internacionales. Por ejemplo: 'Eventos de Turismo de reuniones y Eventos deportivos internacionales'.</td>
    </tr>
    <tr>
      <td>JUST</td>
      <td>Justicia, seguridad y legales</td>
      <td>Datos referidos a justicia, seguridad y legales. Por ejemplo: 'Empresas de Seguridad Privada Habilitadas'.</td>
    </tr>
    <tr>
      <td>REGI</td>
      <td>Regiones y ciudades</td>
      <td>Datos referidos a regiones y ciudades. Por ejemplo: 'Comunas'.</td>
    </tr>
    <tr>
      <td>SOCI</td>
      <td>Población y sociedad</td>
      <td>Datos referidos a población y sociedad. Por ejemplo: 'Registro de Guías de Turismo'.</td>
    </tr>
    <tr>
      <td>TECH</td>
      <td>Ciencia y tecnología</td>
      <td>Datos referidos a ciencia y tecnología. Por ejemplo: 'Recursos humanos en ciencia y tecnología'.</td>
    </tr>
    <tr>
      <td>TRAN</td>
      <td>Transporte</td>
      <td>Datos referidos a transporte. Por ejemplo: 'Bicicletas públicas'.</td>
    </tr>
    </tbody>
</table>

## Anexo II - Pautas para la selección de etiquetas

Elegir buenas etiquetas hace más fácil la búsqueda de datasets para los usuarios. Cuanto más amplia y uniforme sea la lista de etiquetas, mayor será su efectividad.

Estas son pautas para definir etiquetas aplicables a la propiedad *keyword* de la clase dataset:

* Escribir correctamente y en plural.

* Usar mayúsculas sólo donde corresponda.

* Identificar palabras claves.

* Respetar la existencia de etiquetas anteriores.

* Agregar sinónimos y emplear lenguaje natural.

* Usar una sóla palabra. Si es muy necesario, usar más de una. 

* Si la etiqueta tiene más de una palabra, debe estar separada por un espacio, ej: "declaraciones juradas".

Preguntas útiles a la hora de pensar los etiquetas:

* ¿Cuál es el tema?

* ¿Qué aspectos serán de interés para los usuarios?

* ¿De qué otro modo buscaría sobre esta información?

* ¿De qué tipo de información se trata?

* ¿Qué área la provee?

## Anexo III - Especificación de frecuencias (según ISO-8601)

<table>
  <tr>
    <td>Frecuencia</td>
    <td>Valor según ISO-8601</td>
  </tr>
  <tr>
    <td>Cada diez años</td>
    <td>R/P10Y</td>
  </tr>
  <tr>
    <td>Cada cuatro años</td>
    <td>R/P4Y</td>
  </tr>
  <tr>
    <td>Cada tres años</td>
    <td>R/P3Y</td>
  </tr>
  <tr>
    <td>Cada dos años</td>
    <td>R/P2Y</td>
  </tr>
  <tr>
    <td>Anualmente</td>
    <td>R/P1Y</td>
  </tr>
  <tr>
    <td>Cada medio año</td>
    <td>R/P6M</td>
  </tr>
  <tr>
    <td>Cuatrimestralmente</td>
    <td>R/P4M</td>
  </tr>
  <tr>
    <td>Trimestralmente</td>
    <td>R/P3M</td>
  </tr>
  <tr>
    <td>Bimestralmente</td>
    <td>R/P2M</td>
  </tr>
  <tr>
    <td>Mensualmente</td>
    <td>R/P1M</td>
  </tr>
  <tr>
    <td>Cada 15 días</td>
    <td>R/P0.5M</td>
  </tr>
  <tr>
    <td>Tres veces por mes</td>
    <td>R/P0.33M</td>
  </tr>
  <tr>
    <td>Semanalmente</td>
    <td>R/P1W</td>
  </tr>
  <tr>
    <td>Dos veces a la semana</td>
    <td>R/P0.5W</td>
  </tr>
  <tr>
    <td>Tres veces a la semana</td>
    <td>R/P0.33W</td>
  </tr>
  <tr>
    <td>Diariamente</td>
    <td>R/P1D</td>
  </tr>
  <tr>
    <td>Cada hora</td>
    <td>R/PT1H</td>
  </tr>
  <tr>
    <td>Continuamente actualizado</td>
    <td>R/PT1S</td>
  </tr>
  <tr>
    <td>Eventual</td>
    <td>eventual</td>
  </tr>
</table>

## Anexo IV - Ejemplo de data.json

Este es un [ejemplo de data.json](https://github.com/datosgobar/paquete-apertura-datos/blob/master/examples/data.json):

```json
{
  "title": "Datos Argentina",
  "description": "Portal de Datos Abiertos del Gobierno de la República Argentina",
  "publisher": {
    "name": "Ministerio de Modernización",
    "mbox": "datos@modernizacion.gob.ar"
  },
  "issued": "2016-04-14T19:48:05.433640-03:00",
  "modified": "2016-04-19T19:48:05.433640-03:00",
  "language": [
    "spa"
  ],
  "superThemeTaxonomy": "http://datos.gob.ar/superThemeTaxonomy.json",
  "themeTaxonomy": [
    {
      "id": "convocatorias",
      "label": "Convocatorias",
      "description": "Datasets sobre licitaciones en estado de convocatoria."
    },
    {
      "id": "compras",
      "label": "Compras",
      "description": "Datasets sobre compras realizadas."
    },
    {
      "id": "contrataciones",
      "label": "Contrataciones",
      "description": "Datasets sobre contrataciones."
    },
    {
      "id": "adjudicaciones",
      "label": "Adjudicaciones",
      "description": "Datasets sobre licitaciones adjudicadas."
    },
    {
      "id": "normativa",
      "label": "Normativa",
      "description": "Datasets sobre normativa para compras y contrataciones."
    },
    {
      "id": "proveedores",
      "label": "Proveedores",
      "description": "Datasets sobre proveedores del Estado."
    }
  ],
  "license": "Open Data Commons Open Database License 1.0",
  "homepage": "http://datos.gob.ar",
  "rights": "Derechos especificados en la licencia.",
  "spatial": "ARG",
  "dataset": [
    {
      "title": "Sistema de contrataciones electrónicas",
      "description": "Datos correspondientes al Sistema de Contrataciones Electrónicas (Argentina Compra)",
      "publisher": {
        "name": "Ministerio de Modernización. Secretaría de Modernización Administrativa. Oficina Nacional de Contrataciones",
        "mbox": "onc@modernizacion.gob.ar"
      },
      "contactPoint": {
        "fn": "Ministerio de Modernización. Secretaría de Modernización Administrativa. Oficina Nacional de Contrataciones. Dirección de Compras Electrónicas.",
        "hasEmail": "onc-compraselectronicas@modernizacion.gob.ar"
      },
      "superTheme": [
        "ECON"
      ],
      "theme": [
        "contrataciones",
        "compras",
        "convocatorias"
      ],
      "keyword": [
        "bienes",
        "compras",
        "contrataciones"
      ],
      "accrualPeriodicity": "R/P1Y",
      "issued": "2016-04-14T19:48:05.433640-03:00",
      "modified": "2016-04-19T19:48:05.433640-03:00",
      "identifier": "99db6631-d1c9-470b-a73e-c62daa32c420",
      "language": [
        "spa"
      ],
      "spatial": "ARG",
      "temporal": "2015-01-01/2015-12-31",
      "landingPage": "http://datos.gob.ar/dataset/sistema-de-contrataciones-electronicas-argentina-compra",
      "license": "Open Data Commons Open Database License 1.0",
      "distribution": [
        {
          "accessURL": "http://datos.gob.ar/dataset/sistema-de-contrataciones-electronicas-argentina-compra/archivo/fa3603b3-0af7-43cc-9da9-90a512217d8a",
          "description": "Listado de las convocatorias abiertas durante el año 2015 en el sistema de contrataciones electrónicas",
          "format": "CSV",
          "mediaType": "text/csv",
          "downloadURL": "http://186.33.211.253/dataset/99db6631-d1c9-470b-a73e-c62daa32c420/resource/4b7447cb-31ff-4352-96c3-589d212e1cc9/download/convocatorias-abiertas-anio-2015.csv",
          "title": "Convocatorias abiertas durante el año 2015",
          "license": "Open Data Commons Open Database License 1.0",
          "byteSize": "5120",
          "issued": "2016-04-14T19:48:05.433640-03:00",
          "modified": "2016-04-19T19:48:05.433640-03:00",
          "rights": "Derechos especificados en la licencia.",
          "field": [
            {
              "title": "procedimiento_id",
              "type": "integer",
              "description": "Identificador único del procedimiento de contratación"
            },
            {
              "title": "organismo_unidad_operativa_contrataciones_id",
              "type": "integer",
              "description": "Identificador único del organismo que realiza la convocatoria. Organismo de máximo nivel jerárquico al que pertenece la unidad operativa de contrataciones."
            },
            {
              "title": "unidad_operativa_contrataciones_id",
              "type": "integer",
              "description": "Identificador único de la unidad operativa de contrataciones"
            },
            {
              "title": "organismo_unidad_operativa_contrataciones_desc",
              "type": "string",
              "description": "Organismo que realiza la convocatoria. Organismo de máximo nivel jerárquico al que pertenece la unidad operativa de contrataciones."
            },
            {
              "title": "unidad_operativa_contrataciones_desc",
              "type": "string",
              "description": "Unidad operativa de contrataciones."
            },
            {
              "title": "tipo_procedimiento_contratacion",
              "type": "string",
              "description": "Tipo de procedimiento al que se adecua la contratación."
            },
            {
              "title": "ejercicio_procedimiento_anio",
              "type": "date",
              "description": "Año en el que se inició el proceso de la convocatoria."
            },
            {
              "title": "fecha_publicacion_convocatoria",
              "type": "date",
              "description": "Fecha de publicación de la convocatoria en formato AAAA-MM-DD, ISO 8601."
            },
            {
              "title": "modalidad_convocatoria",
              "type": "string",
              "description": "Modalidad bajo la cual se realiza la convocatoria."
            },
            {
              "title": "clase_convocatoria",
              "type": "string",
              "description": "Clase de la convocatoria."
            },
            {
              "title": "objeto_convocatoria",
              "type": "string",
              "description": "Objeto/objetivo de la convocatoria"
            }
          ]
        }
      ]
    }
  ]
}
```

## Anexo V - Taxonomía temática global de la APN para los datasets (JSON)

Esta es la [taxonomía temática global](https://raw.githubusercontent.com/datosgobar/paquete-apertura-datos/master/standards/metadata/superThemeTaxonomy.json):

```json
[
    {
        "id":"AGRI",
        "label":"Agroganadería, pesca y forestación",
        "description":"Datos referidos a agroganadería, pesca y forestación. Por ejemplo: 'Lechería: precio pagado al productor' o 'Superficie forestada'."
    },
    {
        "id":"ECON",
        "label":"Economía y finanzas",
        "description":"Datos referidos a economía y finanzas. Por ejemplo: 'Deuda pública'."
    },
    {
        "id":"EDUC",
        "label":"Educación, cultura y deportes",
        "description":"Datos referidos a educación, cultura y deportes. Por ejemplo: 'Registro de Establecimientos Educativos'."
    },
    {
        "id":"ENER",
        "label":"Energía",
        "description":"Datos referidos a energía. Por ejemplo: 'Productos mineros exportados' o 'Precios del GNC'."
    },
    {
        "id":"ENVI",
        "label":"Medio ambiente",
        "description":"Datos referidos a medio ambiente. Por ejemplo: 'Operadores de residuos peligrosos'."
    },
    {
        "id":"GOVE",
        "label":"Gobierno y sector público",
        "description":"Datos referidos a gobierno y sector público. Por ejemplo: 'Inmuebles del estado Nacional'."
    },
    {
        "id":"HEAL",
        "label":"Salud",
        "description":"Datos referidos a salud. Por ejemplo: 'Estadísticas nacionales de VIH/SIDA'."
    },
    {
        "id":"INTR",
        "label":"Asuntos internacionales",
        "description":"Datos referidos a asuntos internacionales. Por ejemplo: 'Representaciones argentinas en el exterior'."
    },
    {
        "id":"JUST",
        "label":"Justicia, seguridad y legales",
        "description":"Datos referidos a justicia, seguridad y legales. Por ejemplo: 'Censo penitenciario'."
    },
    {
        "id":"REGI",
        "label":"Regiones y ciudades",
        "description":"Datos referidos a regiones y ciudades. Por ejemplo: 'Departamentos de la provincia de Río Negro'."
    },
    {
        "id":"SOCI",
        "label":"Población y sociedad",
        "description":"Datos referidos a población y sociedad. Por ejemplo: 'Turistas residentes que viajan por Argentina'."
    },
    {
        "id":"TECH",
        "label":"Ciencia y tecnología",
        "description":"Datos referidos a ciencia y tecnología. Por ejemplo: 'Recursos humanos en ciencia y tecnología'."
    },
    {
        "id":"TRAN",
        "label":"Transporte",
        "description":"Datos referidos a transporte. Por ejemplo: 'Estadísticas viales'."
    }
]
```

## Anexo VI - Ejemplo de metadatos como texto

Este es un [ejemplo en markdown](https://github.com/datosgobar/paquete-apertura-datos/blob/master/examples/data.md):

**Catálogo: Buenos Aires Data**

Portal de Datos Abiertos del Gobierno de la Ciudad Autónoma de Buenos Aires

* Derechos sobre el catálogo: Derechos especificados en la licencia.

* Correo electrónico del autor: gobiernoabierto@buenosaires.gob.ar

* Autor: Secretaría General y Relaciones Institucionales - Gobierno de la Ciudad Autónoma de Buenos Aires

* Licencia: Creative Commons License 2.5 ARG

* Idioma(s): spa

* Fecha de creación o publicación: 2012-03-22T00:00:00.433640-03:00

* Taxonomía temática global: [http://data.buenosaires.gob.ar/superThemeTaxonomy.json](http://data.buenosaires.gob.ar/superThemeTaxonomy.json)

* Fecha de última actualización/modificación: 2016-04-19T19:48:05.433640-03:00

* Cobertura geográfica: CABA

* Página web del catálogo: [http://data.buenosaires.gob.ar](http://data.buenosaires.gob.ar)

**Taxonomía temática específica**

* Pedidos (pedidos): Dataset sobre pedidos de acceso a la información pública.

* Barrios (barrios): Datasets sobre límites y ubicación geográfica de los barrios de la ciudad.

**Datasets**

**Dataset: Acceso a la información pública**

Datos correspondientes a pedidos de acceso a la información pública solicitados al Gobierno de la Ciudad conforme a la Ley 104

* **Correo electrónico del autor**: dgsocai@buenosaires.gob.ar

* **Autor**: Ministerio de Gobierno. Subsecretaría de Reforma Política. Dirección General de Seguimiento de Organismos de Control y Acceso a la Información.

* **Página de referencias**: [https://data.buenosaires.gob.ar/dataset/acceso-a-la-informacion-publica](https://data.buenosaires.gob.ar/dataset/acceso-a-la-informacion-publica)

* **Temática(s) globales**: GOVE

* **Fecha de publicación**: 2016-08-24T14:58:25.433640-03:00

* **Cobertura temporal**: 2013-01-01/2018-09-12

* **Fecha de última actualización/ modificación**: 2018-11-05T16:51:27.433640-03:00

* **Idioma(s)**: spa

* **Temática(s) específicas**: normas, transparencia

* **Etiqueta(s)**: pedidos, normas, transparencia

* **Frecuencia de actualización**: R/P6M

* **Cobertura geográfica**: CABA

* **Licencia**: Creative Commons License 2.5 ARG

* **Correo electrónico del área/persona de contacto**: dgsocai@buenosaires.gob.ar

* **Área/Persona de contacto**: Ministerio de Gobierno. Subsecretaría de Reforma Política. Dirección General de Seguimiento de Organismos de Control y Acceso a la Información.

* **Identificador**: 99db6631-d1c9-470b-a73e-c62daa32c420

*Distribuciones*

**Distribución: Acceso a la información pública**

Pedidos de acceso a la información pública solicitados durante los años 2013-2018. Tema, fecha, dependencia y estado de la solicitud.

* **URL de acceso**: [https://data.buenosaires.gob.ar/dataset/acceso-a-la-informacion-publica](https://data.buenosaires.gob.ar/dataset/acceso-a-la-informacion-publica)

* **Derechos sobre la distribución**: Derechos especificados en la licencia.

* **Licencia**: Creative Commons License 2.5 ARG

* **Tamaño**: 5120

* **Formato del archivo**: CSV

* **Tipo de archivo**: text/csv

* **Fecha de última actualización/ modificación**: 2018-11-05T16:51:27.433640-03:00

* **URL de descarga**: [ https://data.buenosaires.gob.ar/api/files/acceso-a-la-informacion-publica.csv/download](https://data.buenosaires.gob.ar/api/files/acceso-a-la-informacion-publica.csv/download)

* **Fecha de publicación**: 2016-08-24T14:58:25.433640-03:00

*Campos de la distribución*

* **categoria_tema** (string): Tema de la categoría según lo establecido por el Ministerio de Gobierno.

* **dependencia** (string): Nombre de la dependencia pública donde se realizó el pedido.

* **fecha** (date): Fecha del pedido de acceso a la información.