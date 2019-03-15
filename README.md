# Descripción del proyecto

Este proyecto fue realizadó como caso práctico de la asignatura de Bases de Datos del grado en Ingeniería Informática, de la <a href="https://www.unex.es/conoce-la-uex/centros/epcc">Escuela Politécnica de Cáceres de la Universidad de Extremadura, España</a>, durante el segundo semestre de 2017. El desarrollo del proyecto fue realizado en equipo, por:

* José Ramón Lozano Pinilla
* Isabel Najarro Borrego
* Eduardo Mizar Martínez Alcántara

El enunciado del caso práctico fue proporcionado por la profesora del curso, <a href="https://www.unex.es/conoce-la-uex/centros/epcc/centro/profesores/info/profesor?id_pro=miryam">Miryam Jacinta Salas Sánchez</a>.

# Enunciado

Este curso se ha decidido proponer el diseño y la implementación de una base de datos basada en un caso real, el de las Escuelas Deportivas Municipales, gestionadas por el Instituto Municipal de Deportes (IMD), que depende del Ayuntamiento de Cáceres.
Seguramente algunos de vosotros hace unos años habéis participado en este tipo de actividades en Cáceres o en otra localidad y habéis sufrido (o vuestros padres) el tener que hacer la inscripción en persona perdiendo el tiempo en largas colas o de manera
telefónica.
Desde hace un tiempo (por fin) la inscripción puede realizarse online y posteriormente se realiza un sorteo, si hay más demanda que oferta, para cada grupo de las distintas modalidades deportivas. La información completa del procedimiento de preinscripción, actividades y grupos disponibles, etc., está publicada en la web del ayuntamiento de Cáceres y puede descargarse de la web http://www.ayto-caceres.es/ciudadania/imd/escuelas-deportivas-y-deporte-accesible/. A continuación se ha extraído literalmente de dichos documentos (en cursiva) la información relevante a la parte de la base de datos que se propone diseñar y se comentan, además, algunos aspectos para aclarar o acotar de manera más precisa los datos que deben tenerse en cuenta. También, al final, se añaden nuevos supuestos inventados para hacer más completa la base de datos.
Inicialmente es preciso aclarar que aunque el enunciado se denomina genéricamente Escuelas Deportivas, en realidad se ofertan cuatro programas de actividades deportivas: las escuelas deportivas, deporte accesible, gimnasia para mayores y natación adultos. La información relativa a cada uno de estos programas debe estar estandarizada, al igual que las modalidades deportivas que se integran en cada uno de los programas.

## INFORMACIÓN GENERAL - PROGRAMAS DE ACTIVIDADES

### ESCUELAS DEPORTIVAS

Podrán preinscribirse todas las personas interesadas, que estén debidamente empadronadas en la ciudad de Cáceres, con edades comprendidas entre los 3 y los 18 años. La edad del participante para su preinscripción en cada uno de los grupos de las modalidades deportivas ofertadas, estará determinada exclusivamente por el año de su nacimiento. Las Escuelas Deportivas 2017/18 estarán abiertas para alumnos nacidos entre los años 2014 y 1999 ambos incluidos. Cada alumno podrá preinscribirse en un
máximo de 2 modalidades deportivas.

### DEPORTE ACCESIBLE

Podrán inscribirse todas aquellas personas interesadas que estén debidamente empadronadas en la ciudad de Cáceres, con edades iguales o superiores a 16 años, entendiéndose como nacidos con anterioridad al año 2001, este incluido. Cada alumno/a solamente podrá preinscribirse en un grupo de trabajo.

### GIMNASIA MAYORES

Podrán inscribirse todos aquellas personas interesadas que estén debidamente empadronadas en la ciudad de Cáceres, que sean mayores de 16 años, entendiéndose esta edad como nacidos con anterioridad al año 2001, este incluido. Cada alumno/a
solamente podrá preinscribirse en un grupo de trabajo.

### NATACIÓN PARA ADULTOS

Podrán inscribirse todos aquellas personas interesadas que estén debidamente empadronadas en la ciudad de Cáceres, y nacidos con anterioridad a 1967, este año incluido (mayores de 50 años). Cada alumno/a solamente podrá preinscribirse en un grupo de trabajo, en el nivel elegido, iniciación, intermedio o perfeccionamiento.

## SISTEMA GENERAL DE PREINSCRPCIÓN

El formulario exigirá para los mayores de 14 años la cumplimentación del NIF, y con éste se validará al usuario, que podrá continuar con la preinscripción. Para los menores de 14 años que NO dispongan de NIF, se procederá a rellenar el formulario
pulsando en “SIN NIF”. En cualquier caso para menores de 18 años, será obligatorio incorporar el número del NIF de uno de sus progenitores, que será el que validará al usuario. Además, en todos los casos habrá de rellenarse el resto de los datos
personales que aparecen en el cuestionario .

##

Una vez cumplimentados todos los datos exigidos en la pantalla anterior podrá pulsar el botón para continuar con la siguiente ventana donde se podrá seleccionar la modalidad deportiva elegida, la instalación, los días y la hora de los posibles grupos de
trabajo:

##

Una vez elegidos los campos de la modalidad deportiva se pulsará en “Anotar Reserva” con lo que aparece el reporte de la preinscripción realizada .

## 

## CONSULTA DE INSCRIPCIONES

Todos los participantes tendrán a su disposición un formulario de consulta en la WEB municipal, donde podrán comprobar todos los datos de las inscripciones realizadas en cualquier momento.

##

##

## LISTADO DE GRUPOS DISPONIBLES

En la documentación también se incluye el listado de grupos por programa y modalidad, con los datos relevantes que hay que almacenar para para cada grupo. A continuación se muestra parcialmente dicha información, solo para los programas escuelas deportivas y deporte accesible:

##

Para simplificar podemos considerar que los grupos en todos los programas y modalidades se desarrollan siempre solo dos días a la semana y que esos dos días tienen el mismo horario en ese grupo.

##

## SORTEO

Una vez finalizado el plazo de las preinscripciones se realizará un sorteo de las plazas en aquellos grupos donde haya más solicitantes que plazas, de la siguiente manera:
La adjudicación de plazas se realizará mediante un generador WEB de número aleatorios totalmente externo al Ayuntamiento de Cáceres, y del que se desconoce la fórmula que utiliza para establecer las secuencias aleatorias que proporciona. Este
generador proporcionará un número aleatorio comprendido entre el número 1 y el asignado al último alumno/a preinscrito en cada grupo de trabajo. El número generado designará el primer inscrito y consecutivamente hasta agotar las plazas ofertadas por
cada grupo, el resto quedarán en reserva según ese mismo orden. Es decir, será preciso almacenar el número que ha resultado del sorteo para cada grupo, con el fin de aceptar a los preinscritos a partir de ese número y hasta agotar las plazas del grupo (si se llega al último se comenzará otra vez por el preinscrito número 1 de cada grupo). Los que no sean aceptados quedarán en estado de reserva.

En los grupos donde el número de solicitantes es menor que el número de plazas no se necesitará hacer sorteo y todos los preinscritos serán admitidos.

## 

## PAGO

No contemplaremos en nuestra base de datos la gestión del pago de las actividades. Únicamente recogeremos que cada programa tiene una serie de tarifas específicas (algunas precisan entregar cierta documentación), que se detallan a continuación, y que cada inscrito admitido deberá comunicar la tarifa a la que se acoge y la forma de pago (bimestral, cuatrimestral o anual).

ESCUELAS DEPORTIVAS
* Tarifa General Bimestral: 18,00 €
* Tarifa 2o Hermano Inscrito Bimestral: 13,50 €
* Tarifa Familias Numerosas Bimestral: 9,00 €
* Alumnos Modalidad Deporte Especial: 10,00 €
DEPORTE ACCESIBLE
* Tarifa Bimestral: 18,00 €
GIMNASIA MAYORES
* Tarifa Bimestral: 12,00 €
* Tarifa Bimestral Mayores de 65 años: 6,00 €
NATACIÓN ADULTOS PARA MAYORES 50 AÑOS
* Tarifa Bimestral: 28,00 €GIMNASIA

## BAJA EN LAS ACTIVIDADES

Se podrá solicitar la baja en un programa o actividad en cualquier momento, pero exclusivamente podrá solicitarse la devolución de las cuotas pagadas de aquellos meses pagados y no disfrutados, independientemente del sistema de pago elegido.
A efectos estadísticos, habrá de mantenerse la información de aquellas personas que han estado inscritas en algún grupo durante el curso 2017/2018, aún después de haber causado baja (solo hasta el comienzo del siguiente curso), registrando la fecha efectiva
de baja en la base de datos.

## LISTA DE RESERVA

1. Las listas quedarán por el orden que se corresponde de manera correlativa a la numeración otorgada para cada grupo de trabajo para el sorteo, al final de este listado se incorporarán las personas que realicen la reserva a partir del mes de octubre, en
este caso el orden de prelación quedará determinado por el día hora de esta reserva, pero siempre a partir del último alumno que participó en el sorteo.
2. Una vez que exista plaza vacante, desde el IMD o la entidad colaboradora avisará al número de teléfono consignado en la preinscripción de la plaza vacante, en caso que con esta llamada no sea posible contactar con el alumno, se realizará otra llamada en horario distinto y en caso de no ser posible su localización, se dará de baja al
alumno/a.
Habrán de conocerse los preinscritos que están en reserva en un grupo y el orden que ocupan en dicha lista de reserva.

## GESTIÓN DEL PERSONAL

La base de datos debe también completarse con los datos del personal que estará encargado de impartir las actividades a los diferentes grupos, a los que se denomina monitores. De cada monitor debemos tener los mismos datos personales que tenemos para los inscritos y, además, el número de la seguridad social y la fecha del contrato. Debemos tener en cuenta que un monitor podría también inscribirse como alumno en alguno de los grupos del mismo o distinto programa (por ejemplo, una monitora de tenis
podría estar inscrita en un grupo de pilates).
Para un mejor control de las actividades este curso, el IMD ha decidido nombrar a cuatro monitores como responsables de cada uno de los programas (uno por programa). También, para todos los monitores, y dependiendo de las acreditaciones y títulos que
haya aportado cada uno, se quieren almacenar en la base de datos aquellas modalidades deportivas en las que se le considera especialista (pueden ser varias). Lo más importante, sin embargo, es llevar un control exhaustivo de la asignación de monitores a los distintos grupos, tanto de su asignación actual (cada grupo solo tiene asignado un monitor pero un monitor podría dar clase a varios grupos) como a lo largo de todo el curso, porque es frecuente que los monitores roten por distintos grupos durante el curso, bien por necesidades del IMD, bajas de compañeros o con motivo de sus estudios (muchos son estudiantes del Grado en Ciencias del Deporte). Así pues, es preciso mantener información de a qué grupos imparte clase un monitor y desde cuándo,
así como a qué grupos ha dado clase durante otros periodos de tiempo en el curso, almacenando información de dichos periodos. Es bastante probable, además, que un monitor esté asignado varias veces al mismo grupo en diferentes periodos de tiempo.

# Desarrollo de la base de datos

En base al enunciado del caso práctico, se realizó el diagrama entidad/relación de la base de datos:

##

Posteriormente se desarrolló un diagrama de relacional:

##

Se determinaron las dependencias funcionales y formas normales:

##

Se implemento el esquema de la base de datos en SQL:

```sql
CREATE TABLE PERSONA (
  COD_PERSONA NUMBER (5),
  NOMBRE VARCHAR2 (20) NOT NULL,
  APELLIDO1 VARCHAR2 (20) NOT NULL,
  APELLIDO2 VARCHAR2 (20) NOT NULL,
  FECHA_NAC DATE CHECK (FECHA_NAC BETWEEN '01/JAN/1900' AND '01/JAN/2017'),
  CORREO_ELEC VARCHAR2 (30) NOT NULL,
  TELEF NUMBER (9),
  DNI VARCHAR2 (9) UNIQUE,
  TIPO_PERSONA CHAR(1) NOT NULL CHECK(TIPO_PERSONA IN ('A', 'B', 'R', 'E')),
  CONSTRAINT PERSONA_PK
  PRIMARY KEY (COD_PERSONA)
);

CREATE TABLE ALUMNO (
  COD_PERSONA NUMBER (5),
  DNI_PROGENITOR VARCHAR2 (9),
  CONSTRAINT ALUMNO_PK
  PRIMARY KEY (COD_PERSONA),
  CONSTRAINT ALUMNO_COD_PERSONA_FK
  FOREIGN KEY (COD_PERSONA)
  REFERENCES PERSONA (COD_PERSONA) ON DELETE CASCADE
);

CREATE TABLE MONITOR (
  COD_PERSONA NUMBER (5),
  NUM_SS NUMBER (12) UNIQUE,
  FECHA_CONTRATO DATE,
  CONSTRAINT MONITOR_PK
  PRIMARY KEY (COD_PERSONA),
  CONSTRAINT MONITOR_COD_PERSONA_FK
  FOREIGN KEY (COD_PERSONA)
  REFERENCES PERSONA(COD_PERSONA) ON DELETE CASCADE
);

CREATE TABLE PROGRAMA (
  COD_PROGRAMA NUMBER (3),
  NOM_PROGRAMA VARCHAR2 (25) NOT NULL,
  ANIO_INICIO DATE NOT NULL,
  ANIO_FIN DATE,
  MONITOR NUMBER (5) UNIQUE NOT NULL,
  CONSTRAINT PROGRAMA_PK
  PRIMARY KEY (COD_PROGRAMA),
  CONSTRAINT PROGRAMA_MONITOR_FK
  FOREIGN KEY (MONITOR)
  REFERENCES MONITOR(COD_PERSONA)
);

CREATE TABLE MODALIDAD (
  COD_MODALIDAD NUMBER (3),
  NOM_MODALIDAD VARCHAR2 (25) NOT NULL,
  PROGRAMA NUMBER (3) NOT NULL,
  CONSTRAINT MODALIDAD_PK
  PRIMARY KEY (COD_MODALIDAD),
  CONSTRAINT MODALIDAD_PROGRAMA_FK
  FOREIGN KEY (PROGRAMA)
  REFERENCES PROGRAMA(COD_PROGRAMA) ON DELETE CASCADE
);

CREATE TABLE INSTALACION (
  COD_INSTALACION NUMBER (2),
  NOM_INSTALACION VARCHAR2 (25) NOT NULL,
  CONSTRAINT INSTALACION_PK
  PRIMARY KEY (COD_INSTALACION)
);

CREATE TABLE GRUPO (
  COD_GRUPO NUMBER (4) PRIMARY KEY,
  NIVEL NUMBER (1) CHECK (NIVEL >= 0),
  ANIO_INICIO_EDAD NUMBER (2) NOT NULL,
  ANIO_FIN_EDAD NUMBER (2),
  HORA_INICIO CHAR (5) NOT NULL,
  HORA_FIN CHAR (5) NOT NULL,
  DIA_1 VARCHAR2 (9) NOT NULL,
  DIA_2 VARCHAR2 (9) NOT NULL,
  NUM_MAX_PLAZAS NUMBER (2) NOT NULL CHECK (NUM_MAX_PLAZAS >= 1),
  NUM_SORTEO NUMBER (2),
  MODALIDAD NUMBER (3) NOT NULL REFERENCES MODALIDAD (COD_MODALIDAD) ON DELETE CASCADE,
  MONITOR NUMBER (5) UNIQUE REFERENCES MONITOR (COD_PERSONA),
  FECHA_INICIO DATE NOT NULL,
  INSTALACION NUMBER (2) NOT NULL REFERENCES INSTALACION (COD_INSTALACION)
);

CREATE TABLE TARIFA (
  COD_TARIFA NUMBER (2),
  NOM_TARIFA VARCHAR2 (25) NOT NULL,
  PRECIO NUMBER (5, 2) NOT NULL CHECK (PRECIO > 0),
  PROGRAMA NUMBER (3) NOT NULL,
  CONSTRAINT TARIFA_PK
  PRIMARY KEY (COD_TARIFA),
  CONSTRAINT TARIFA_PROGRAMA_FK
  FOREIGN KEY (PROGRAMA)
  REFERENCES PROGRAMA(COD_PROGRAMA)
);

CREATE TABLE ESPECIALISTA (
  COD_PERSONA NUMBER (5),
  COD_MODALIDAD NUMBER (3),
  CONSTRAINT ESPECIALISTA_PK
  PRIMARY KEY (COD_PERSONA, COD_MODALIDAD),
  CONSTRAINT ESPECIALISTA_PERSONA_FK
  FOREIGN KEY (COD_PERSONA)
  REFERENCES PERSONA(COD_PERSONA) ON DELETE CASCADE,
  CONSTRAINT ESPECIALISTA_MODALIDAD_FK
  FOREIGN KEY (COD_MODALIDAD)
  REFERENCES MODALIDAD(COD_MODALIDAD)
);

CREATE TABLE PREINSCRIPCION (
  COD_PREINSCRIPCION NUMBER (5),
  ESTADO CHAR (1) NOT NULL CHECK (ESTADO IN ('A', 'B', 'R', 'E')),
  FECHA_PREINSCRIPCION DATE NOT NULL,
  GRUPO NUMBER (4) NOT NULL,
  ALUMNO NUMBER (5) NOT NULL,
  CONSTRAINT PREINSCRIPCION_PK
  PRIMARY KEY (COD_PREINSCRIPCION),
  CONSTRAINT PREINSCRIPCION_GRUPO_FK
  FOREIGN KEY (GRUPO)
  REFERENCES GRUPO(COD_GRUPO),
  CONSTRAINT PREINSCRIPCION_ALUMNO_FK
  FOREIGN KEY (ALUMNO)
  REFERENCES ALUMNO(COD_PERSONA) ON DELETE CASCADE
);

CREATE TABLE PREINSCRIPCION (
  COD_PREINSCRIPCION NUMBER (5),
  ESTADO CHAR (1) NOT NULL CHECK (ESTADO IN ('A', 'B', 'R', 'E')),
  FECHA_PREINSCRIPCION DATE NOT NULL,
  GRUPO NUMBER (4) NOT NULL,
  ALUMNO NUMBER (5) NOT NULL,
  CONSTRAINT PREINSCRIPCION_PK
  PRIMARY KEY (COD_PREINSCRIPCION),
  CONSTRAINT PREINSCRIPCION_GRUPO_FK
  FOREIGN KEY (GRUPO)
  REFERENCES GRUPO(COD_GRUPO),
  CONSTRAINT PREINSCRIPCION_ALUMNO_FK
  FOREIGN KEY (ALUMNO)
  REFERENCES ALUMNO(COD_PERSONA) ON DELETE CASCADE
);

CREATE TABLE INSCRITO (
  COD_PREINSCRIPCION NUMBER (5),
  FORMA_PAGO VARCHAR2 (20) NOT NULL,
  TARIFA NUMBER (2),
  CONSTRAINT INSCRITO_PK
  PRIMARY KEY (COD_PREINSCRIPCION),
  CONSTRAINT INSCRITO_PREINSCRIPCION_FK
  FOREIGN KEY (COD_PREINSCRIPCION)
  REFERENCES PREINSCRIPCION(COD_PREINSCRIPCION),
  CONSTRAINT INSCRITO_TARIFA_FK
  FOREIGN KEY (TARIFA)
  REFERENCES TARIFA(COD_TARIFA)
);

CREATE TABLE RESERVA (
  COD_PREINSCRIPCION NUMBER (5),
  NUM_RESERVA NUMBER (5) NOT NULL,
  CONSTRAINT RESERVA_PK
  PRIMARY KEY (COD_PREINSCRIPCION),
  CONSTRAINT RESERVA_PREINSCRIPCION_FK
  FOREIGN KEY (COD_PREINSCRIPCION)
  REFERENCES PREINSCRIPCION(COD_PREINSCRIPCION) ON DELETE CASCADE
);

CREATE TABLE HIST_MONITOR (
  COD_GRUPO NUMBER (4),
  FECHA_INICIO_MONITOR DATE,
  FECHA_FIN_MONITOR DATE NOT NULL,
  COD_PERSONA NUMBER (5),
  CONSTRAINT HIST_MONITOR_PK
  PRIMARY KEY (COD_GRUPO, FECHA_INICIO_MONITOR),
  CONSTRAINT HIST_MONITOR_GRUPO_FK
  FOREIGN KEY (COD_GRUPO)
  REFERENCES GRUPO(COD_GRUPO),
  CONSTRAINT HIST_MONITOR_PERSONA_FK
  FOREIGN KEY (COD_PERSONA)
  REFERENCES MONITOR(COD_PERSONA)
);
```
# Enunciado y resolución de todas las consultas:

Una vez diseñada e implementada la base de datos, se debían realizar algunas consultas a la base de datos:

1. Obtener la información de las preinscripciones que ha realizado la persona con DNI 01234567X, mostrando para cada preinscripción el número de solicitud que se le otorgó, la fecha y hora en que la realizó, el nombre del programa y de la modalidad deportiva en que se inscribió y el estado en que se encuentra dicha preinscripción. Téngase en cuenta que esta persona puede haber realizado preinscripciones para ella misma o para sus hijos. Ordenar por la fecha y hora.

```sql
SELECT cod_preinscripcion, hora_preinscripcion, fecha_preinscripcion, nom_programa, nom_modalidad, estado
FROM persona INNER JOIN 
     alumno USING (cod_persona) INNER JOIN 
     preinscripcion ON (alumno = cod_persona) INNER JOIN 
     grupo ON (grupo = cod_grupo) INNER JOIN 
     modalidad ON (modalidad = cod_modalidad) INNER JOIN 
     programa ON (programa = cod_programa)
WHERE dni = '01234567X' OR dni_progenitor = '01234567X'
ORDER BY fecha_preinscripcion;
```

2. Para cada modalidad deportiva dentro del programa de “Escuelas Deportivas”, obtener su nombre, el número de grupos que se han ofertado y el número total de plazas ofertadas de dicha modalidad.

```sql
SELECT nom_modalidad, COUNT(cod_grupo) AS numero_grupos, SUM(num_max_plazas) AS total_plazas
FROM modalidad INNER JOIN
     grupo ON (cod_modalidad = modalidad)
WHERE modalidad.programa IN ( SELECT cod_programa
                              FROM programa
                              WHERE nom_programa = 'Escuelas Deportivas')
GROUP BY nom_modalidad;
```

3. Mostrar los nombres de los programas y modalidades deportivas de los grupos a los que da clase la monitora cuyo nombre es Susana Moreno Recio.


```sql
SELECT DISTINCT nom_programa, nom_modalidad
FROM programa INNER JOIN 
     modalidad ON (cod_programa = programa) INNER JOIN 
     grupo ON (modalidad = cod_modalidad) INNER JOIN 
     persona ON (monitor = cod_persona)
WHERE nombre = 'Susana' AND apellido1 = 'Moreno' AND apellido2 = 'Recio';
```

4. Mostrar los nombres completos y edades de los niños que han sido admitidos en algún grupo de la modalidad deportiva “Tenis” y que también han sido admitidos en algún grupo de la modalidad deportiva “Fútbol” (el niño que se obtenga debe estar admitido en los dos deportes). Ordenar por la edad de los niños, de menor a mayor, y a igual edad, alfabéticamente, por los apellidos y el nombre.


```sql
SELECT nombre||' '||apellido1||' '||apellido2 AS nombre_completo, trunc((SYSDATE - fecha_nacimiento)/365) AS edad
FROM persona INNER JOIN 
     alumno USING(cod_persona)
WHERE cod_persona IN (SELECT alumno
                      FROM preinscripcion
                      WHERE estado = 'A' AND
                      cod_grupo IN (SELECT cod_grupo
                                    FROM grupo
                                    WHERE modalidad IN (SELECT cod_modalidad
                                                        FROM modalidad
                                                        WHERE nom_modalidad = 'Tenis'))
                                                        INTERSECT
                                                        SELECT alumno
                                                        FROM preinscripcion
                                                        WHERE estado = 'A' AND
                                                        cod_grupo IN (SELECT cod_grupo
                                                                      FROM grupo
                                                                      WHERE modalidad IN (SELECT cod_modalidad
                                                                                          FROM modalidad
                                                                                          WHERE nom_modalidad = 'Futbol'
                                                                                          )))
      AND trunc((SYSDATE - fecha_nacimiento)/365) < 18
ORDER BY edad, apellido1, apellido2, nombre;
```

5. Para todos los grupos de modalidad deportiva “Aerobic” dentro del programa de “Deporte accesible” mostrar el número de grupo y el número de preinscritos por grupo, así como el número que se generó en el sorteo. Si hay grupos que no tienen ninguna persona preinscrita, deben salir también en el resultado con un total de 0 personas (obviamente estos grupos no tendrán asignado un número de sorteo). Ordenar por el número de preinscritos de mayor a menor y a igual número de preinscritos, por el número de grupo.


```sql
SELECT cod_grupo, COUNT (cod_preinscripcion) AS "Numero de preinscritos", num_sorteo
FROM grupo LEFT OUTER JOIN 
     preinscripcion ON (cod_grupo = grupo)
WHERE modalidad = (SELECT nom_modalidad
                   FROM modalidad INNER JOIN programa ON (programa = cod_programa)
                   WHERE nom_modalidad = 'Aerobic' AND nom_programa = 'Deporte accesible')
ORDER BY "Numero de preinscritos" DESC, cod_grupo;
```

6. Obtener los números de los grupos de la modalidad deportiva “Patinaje” que tienen clase los martes y se imparten en la instalación “Cuidad Deportiva”, indicando el horario que tienen ese día y el nombre completo del monitor que está actualmente
dando clase en ese grupo.


```sql
SELECT cod_grupo, hora_inicio || ' - ' || hora_fin AS horario, nombre||' '||apellido1||' '||apellido2 AS nombre_monitor
FROM persona INNER JOIN 
     grupo ON (cod_persona = monitor) INNER JOIN 
     instalacion ON (instalacion = cod_instalacion)
WHERE modalidad IN (SELECT cod_modalidad
                    FROM modalidad
                    WHERE nom_modalidad = 'Patinaje') 
      AND nom_instalacion = 'Ciudad Deportiva' 
      AND (dia_1 = 'Martes' OR dia_2 = 'Martes');
```

7. Mostrar los nombres de las modalidades deportivas, junto con el nombre del programa al que pertenecen, de aquellas modalidades deportivas que tienen más de dos grupos que no han cubierto a día de hoy las plazas ofertadas. Ordenar por programa y
modalidad deportiva.

```sql
SELECT nom_modalidad, nom_programa
FROM modalidad INNER JOIN 
     programa ON (programa = cod_programa) INNER JOIN 
     grupo ON (cod_modalidad = modalidad)
WHERE cod_grupo IN (SELECT g2.cod_grupo
                    FROM grupo g2 INNER JOIN preinscripcion ON (g2.cod_grupo = grupo)
                    WHERE g2.num_max_plazas < (SELECT COUNT (*)
                                               FROM preinscripcion INNER JOIN grupo g3 ON (g3.cod_grupo = grupo)
                                               WHERE fecha_preinscripcion <= SYSDATE AND (g2.cod_grupo = g3.cod_grupo)
                                               GROUP BY g3.cod_grupo)
                    )
GROUP BY nom_modalidad, nom_programa
HAVING COUNT (*) >= 2
ORDER BY nom_programa, nom_modalidad;
```

8. Mostrar la edad media y el número de personas admitidas en la modalidad deportiva de “Pilates”.

```sql
SELECT AVG trunc((SYSDATE - fecha_nacimiento)/365)) AS edad_media, COUNT (*) AS num_admitidos
FROM persona INNER JOIN 
     preinscripcion ON (alumno = cod_persona) INNER JOIN 
     grupo ON (grupo = cod_grupo)
WHERE modalidad IN (SELECT cod_modalidad
                    FROM modalidad
                    WHERE nom_modalidad = 'Pilates')
      AND estado = 'A';
```

9. Para cada monitor que da clase a grupos del programa “Gimnasia para mayores”, mostrar su dni y nombre completo, así como el número total de grupos que imparte. Mostrar solo los monitores que dan clase a más de dos grupos.

```sql
SELECT dni, nombre||' '||apellido1||' '||apellido2 AS nombre_monitor, COUNT(cod_grupo) AS total_grupos
FROM persona INNER JOIN 
     grupo ON (cod_persona = monitor) INNER JOIN 
     modalidad ON (modalidad = cod_modalidad)
WHERE programa IN (SELECT cod_programa
                   FROM programa
                   WHERE nom_programa = 'Gimnasia para mayores')
GROUP BY cod_persona, nombre, apellido1, apellido2
HAVING COUNT(cod_grupo) > 2;
```

10. Obtener el nombre de la/s modalidad/es deportiva/s dentro del programa de “Deporte Accesible” que cuenta/n con el mayor número de plazas ofertadas, mostrando además, dicho número de plazas.

```sql
SELECT cod_modalidad, nom_modalidad, SUM(num_max_plazas) AS total_plazas
FROM modalidad INNER JOIN grupo ON (cod_modalidad = modalidad)
WHERE programa IN (SELECT cod_programa
                   FROM programa
                   WHERE nom_programa = 'Deporte Accesible')
GROUP BY cod_modalidad, nom_modalidad
HAVING SUM(num_max_plazas) >= ALL (SELECT SUM(num_max_plazas) AS total_plazas
                                   FROM modalidad INNER JOIN
                                        grupo ON (cod_modalidad = modalidad)
                                   WHERE programa IN (SELECT cod_programa
                                                      FROM programa
                                                      WHERE nom_programa = 'Deporte Accesible')
                                   GROUP BY cod_modalidad, nom_modalidad);
```
