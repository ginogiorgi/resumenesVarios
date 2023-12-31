# Determinar el problema a solucionar, la finalidad y los requerimientos.

Antes de comenzar un proyecto de Base de datos, es importante, determinar el eje a seguir para el diseño, ya que estas nos marcarán las pautas para tener un buen resultado.

# Modelado de Entidades

La idea es que se identifiquen los objetos de la base de datos, llamadas entidades. Para el modelado de la base de datos se propone utilizar el “modelado de objetos”, ya que, la técnica propone una forma abstracta de pensamiento acerca de problemas a resolver, empleando conceptos del mundo real, y no conceptos técnicos informáticos. En el proyecto se pueden identificar varios objetos que se relacionan y establecen un flujo de información, estos objetos se llegaran a transformar en tablas bidimensionales, las cuales son el fundamento de este tipo de base de datos relacional.

### Definir entidades.

Recordemos que las Entidades, son objetos o cosas que existen en nuestro alrededor, pensando en el proyecto ¿qué objetos intervienen en el proceso del proyecto? Estos objetos surgen identificando todos los actores que tienen el proceso, posteriormente identifique las relaciones que tiene cada uno, sus responsabilidades, y el papel que tiene en el proceso.

### Definir los atributos

Recordemos que los objetos tienen apartados que son: identificador, atributos y métodos. Productos Toda entidad tiene atributos que la describen, siendo el atributo las características de la Entidad. . 3.- Modelado Relacional. Prototipo de BD sin normalizar. Ahora bien, para el modelado ER, vamos a retomar las entidades, con sus respectivos atributos. En este paso hacemos énfasis en las relaciones de las entidades, mediante la cardinalidad, entendida por la cantidad de relaciones que tienen los objetos. Para comprender la necesidad del proyecto se debe leer detenidamente y ver cómo interactúan los objetos y relaciones de conjuntos, delimitando la asociación. Además, en el modelo ER, se utilizan figuras de relación y se hace uso de las claves principales y las claves foráneas.

- **Diagrama E/R:** Diagrama de entidad- interrelación (E/R) perite representar gráficamente la estructura lógica de una base de datos. Para poder guiarnos y entender de mejor forma la base de datos a realizar. Figuras: • Rectángulos: entidades • Elipsis: Atributos • Rombos: Interrelaciones • Líneas: enlazan los atributos a entidades, atributos a interrelaciones y entidades a interrelaciones.

- **Cardinalidades:** La razón de cardinalidad, expresa el numero de entidades a las que otra entidad puede estar asociada por medio de una interrelación. Existen los siguientes tipos:
  1. Uno a uno (1:1).
  2. Uno a varios (1:N).
  3. Varios a uno (N:1) o la simétrica de la anterior.
  4. Varios a varios o muchos a muchos (N:M).

# Base de datos Normalizada

Continuamos con el paso de normalizar, ¿pero ¿qué es normalizar? Para mejorar el desempeño de una base de datos, así como evitar redundancia en la información que contiene y en consecuencia, generar condiciones para un mejor diseño, se debe conocer las formas de normalización. La normalización de datos es el proceso que permite refinar la construcción de modelos relacional con el objetivo de minimizar la redundancia de datos mediante ciertas normas y restricciones con el fin de evitar futuros problemas cuando nuestra base de datos sea mayor. Su principal objetivo es reducir la redundancia de datos y simplificar las dependencias entre columnas, aplicándose de manera acumulativa.

## Aplicación de Normalización

- **Convertirlas en Tablas:** El modelado relacional, se deberá convertir en tablas, la siguiente imagen muestra las partes que la integran.

  ![Tablas de Normalizacion](./imagenes/tablas-4a2fb4a4-3d82-457b-b49e-cb35f0750eb8.webp)

- **Realizar algunos registros:** Para ayudarse a visualizar mejor los casos en los que estamos cayendo en redundancias, sirve hacer ejemplos de los registros, de esta manera nos podemos percatar en las situaciones donde tendremos problemas con la estructura de nuestra base de datos.

- **Aplicaremos las reglas de Normalización:**

  - 1FN: El valor de una columna debe ser una entidad atómica, indivisible, excluyendo así las dificultades que podría conllevar el tratamiento de un dato formado de varias partes.

  - 2FN: Una tabla se encuentra en 2FN cuando está en 1FN y no contiene dependencias parciales. Por consiguiente, una tabla 1FN automáticamente está en 2FN si su clave primaria está basada solamente en un atributo simple. Una tabla en 2FN aún puede contener dependencias transitivas.

  - 3FN: Cumple con la 1FN y 2FN y los campos que NO son clave, NO deben tener dependencias. Se debe seguir analizando la estructura de las tablas, para evitar que no haya registros con campos no dependientes.

  - 4FN: Cumple 1FN, 2FN, 3FN y los campos multivaluados se identifican por una clave única.

# RDB (relational database)

RDBMS (Relational DataBase Magement System) Sistema Manejador de Bases de datos relacionales.

La diferencia entre ambos es que las BBDD son un conjunto de datos pertenecientes ( o al menos en teoría) a un mismo tipo de contexto, que guarda los datos de forma persistente para un posterior uso, y el Sistema de gestión de BBDD o sistema manejador, es el que nos permite acceder a ella, es un software, herramienta que sirve de conexión entre las BBDD y el usuario (nos presenta una interfaz para poder gestionarla, manejarla).

### RDBMS:

- MySQL
- PostgreSQL
- Etc

Todas toman un lenguaje base, pero cada uno lo apropia, imponiéndole diferentes reglas y características.

# SQL

SQL significa Structured Query Language y tiene una estructura clara y fija. Su objetivo es hacer un solo lenguaje para consultar cualquier manejador de bases de datos volviéndose un gran estándar.

SQL tiene dos grandes sublenguajes:

## DDL

O Data Definition Language que nos ayuda a crear la estructura de una base de datos. Existen 3 grandes comandos:

- Create: Nos ayuda a crear bases de datos, tablas, vistas, índices, etc.

- Alter: Ayuda a alterar o modificar entidades.

- Drop: Nos ayuda a borrar. Hay que tener cuidado al utilizarlo.

3 objetos que manipularemos con el lenguaje DDL:

- Database o bases de datos
- Table o tablas. Son la traducción a SQL de las entidades
- View o vistas: Se ofrece la proyección de los datos de la base de datos de forma entendible.

Nota: las herramientas del DDL se utilizan mayormente en la fase de construcción y mantenimiento de las bases de datos, la manipulación u operación se hace con DML.

## DML

Trata del contenido de la base de datos. Son las siglas de Data Manipulation Language y sus comandos son:

- Insert: Inserta o agrega nuevos registros a la tabla
- Update: Actualiza o modifica los datos que ya existen
- Delete: Esta sentencia es riesgosa porque puede borrar el contenido de una tabla
- Select: Trae información de la base de datos

## Creando las tablas en My SQL

- Una buena práctica es comenzar creando las entidades que no tienen una llave foránea.
- Generalmente en los nombres de bases de datos se evita usar eñes o acentos para evitar problemas en los manejadores de las bases de datos.
- Cuando creamos las tablas dependientes, el comando **CASCADE** sirve para que cada que se haga un update en la tabla principal, se refleje también en la tabla en la que estamos creando la relación.
