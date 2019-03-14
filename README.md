# Descripción del proyecto

Este proyecto fue realizadó como caso práctico de la asignatura de Bases de Datos del grado en Ingeniería Informática, de la <a href="https://www.unex.es/conoce-la-uex/centros/epcc">Escuela Politécnica de Cáceres de la Universidad de Extremadura, España</a>, durante el segundo semestre de 2017. El desarrollo del proyecto fue realizado en equipo, por:

* José Ramón Lozano Pinilla
* Isabel Najarro Borrego
* Eduardo Mizar Martínez Alcántara

El enunciado del caso práctico fue proporcionado por la profesora del curso, <a href="https://www.unex.es/conoce-la-uex/centros/epcc/centro/profesores/info/profesor?id_pro=miryam">Miryam Jacinta Salas Sánchez</a>.

# Enunciado

Este curso se ha decidido proponer el diseño y la implementación de una base de datos
basada en un caso real, el de las Escuelas Deportivas Municipales, gestionadas por el
Instituto Municipal de Deportes (IMD), que depende del Ayuntamiento de Cáceres.
Seguramente algunos de vosotros hace unos años habéis participado en este tipo de
actividades en Cáceres o en otra localidad y habéis sufrido (o vuestros padres) el tener
que hacer la inscripción en persona perdiendo el tiempo en largas colas o de manera
telefónica.
Desde hace un tiempo (por fin) la inscripción puede realizarse online y
posteriormente se realiza un sorteo, si hay más demanda que oferta, para cada grupo de
las distintas modalidades deportivas.
La información completa del procedimiento de preinscripción, actividades y
grupos disponibles, etc., está publicada en la web del ayuntamiento de Cáceres y puede
descargarse de la web http://www.ayto-caceres.es/ciudadania/imd/escuelas-deportivas-
y-deporte-accesible/.
A continuación se ha extraído literalmente de dichos documentos (en cursiva) la
información relevante a la parte de la base de datos que se propone diseñar y se
comentan, además, algunos aspectos para aclarar o acotar de manera más precisa los
datos que deben tenerse en cuenta. También, al final, se añaden nuevos supuestos
inventados para hacer más completa la base de datos.
Inicialmente es preciso aclarar que aunque el enunciado se denomina
genéricamente Escuelas Deportivas, en realidad se ofertan cuatro programas de
actividades deportivas: las escuelas deportivas, deporte accesible, gimnasia para
mayores y natación adultos. La información relativa a cada uno de estos programas debe
estar estandarizada, al igual que las modalidades deportivas que se integran en cada
uno de los programas.

## INFORMACIÓN GENERAL - PROGRAMAS DE ACTIVIDADES

### ESCUELAS DEPORTIVAS

Podrán preinscribirse todas las personas interesadas, que estén debidamente
empadronadas en la ciudad de Cáceres, con edades comprendidas entre los 3 y los 18
años. La edad del participante para su preinscripción en cada uno de los grupos de las
modalidades deportivas ofertadas, estará determinada exclusivamente por el año de su
nacimiento. Las Escuelas Deportivas 2017/18 estarán abiertas para alumnos nacidos
entre los años 2014 y 1999 ambos incluidos. Cada alumno podrá preinscribirse en un
máximo de 2 modalidades deportivas.

### DEPORTE ACCESIBLE

Podrán inscribirse todas aquellas personas interesadas que estén debidamente
empadronadas en la ciudad de Cáceres, con edades iguales o superiores a 16 años,
entendiéndose como nacidos con anterioridad al año 2001, este incluido. Cada
alumno/a solamente podrá preinscribirse en un grupo de trabajo.

### GIMNASIA MAYORES

Podrán inscribirse todos aquellas personas interesadas que estén debidamente
empadronadas en la ciudad de Cáceres, que sean mayores de 16 años, entendiéndose
esta edad como nacidos con anterioridad al año 2001, este incluido. Cada alumno/a
solamente podrá preinscribirse en un grupo de trabajo.

### NATACIÓN PARA ADULTOS

Podrán inscribirse todos aquellas personas interesadas que estén debidamente
empadronadas en la ciudad de Cáceres, y nacidos con anterioridad a 1967, este año
incluido (mayores de 50 años). Cada alumno/a solamente podrá preinscribirse en un
grupo de trabajo, en el nivel elegido, iniciación, intermedio o perfeccionamiento.

## SISTEMA GENERAL DE PREINSCRPCIÓN

El formulario exigirá para los mayores de 14 años la cumplimentación del NIF, y con
éste se validará al usuario, que podrá continuar con la preinscripción. Para los
menores de 14 años que NO dispongan de NIF, se procederá a rellenar el formulario
pulsando en “SIN NIF”. En cualquier caso para menores de 18 años, será obligatorio
incorporar el número del NIF de uno de sus progenitores, que será el que validará al
usuario. Además, en todos los casos habrá de rellenarse el resto de los datos
personales que aparecen en el cuestionario .

##

Una vez cumplimentados todos los datos exigidos en la pantalla anterior podrá pulsar
el botón para continuar con la siguiente ventana donde se podrá seleccionar la
modalidad deportiva elegida, la instalación, los días y la hora de los posibles grupos de
trabajo:

##

Una vez elegidos los campos de la modalidad deportiva se pulsará en “Anotar
Reserva” con lo que aparece el reporte de la preinscripción realizada .

## 

## CONSULTA DE INSCRIPCIONES

Todos los participantes tendrán a su disposición un formulario de consulta en la WEB
municipal, donde podrán comprobar todos los datos de las inscripciones realizadas en
cualquier momento.

##

##

## LISTADO DE GRUPOS DISPONIBLES

En la documentación también se incluye el listado de grupos por programa y modalidad,
con los datos relevantes que hay que almacenar para para cada grupo. A continuación se
muestra parcialmente dicha información, solo para los programas escuelas deportivas y
deporte accesible:

##

Para simplificar podemos considerar que los grupos en todos los programas y
modalidades se desarrollan siempre solo dos días a la semana y que esos dos días
tienen el mismo horario en ese grupo.

##

## SORTEO

Una vez finalizado el plazo de las preinscripciones se realizará un sorteo de las plazas
en aquellos grupos donde haya más solicitantes que plazas, de la siguiente manera:
La adjudicación de plazas se realizará mediante un generador WEB de número
aleatorios totalmente externo al Ayuntamiento de Cáceres, y del que se desconoce la
fórmula que utiliza para establecer las secuencias aleatorias que proporciona. Este
generador proporcionará un número aleatorio comprendido entre el número 1 y el
asignado al último alumno/a preinscrito en cada grupo de trabajo. El número generado
designará el primer inscrito y consecutivamente hasta agotar las plazas ofertadas por
cada grupo, el resto quedarán en reserva según ese mismo orden.
Es decir, será preciso almacenar el número que ha resultado del sorteo para cada grupo,
con el fin de aceptar a los preinscritos a partir de ese número y hasta agotar las plazas
del grupo (si se llega al último se comenzará otra vez por el preinscrito número 1 de
cada grupo). Los que no sean aceptados quedarán en estado de reserva.

En los grupos donde el número de solicitantes es menor que el número de plazas no se
necesitará hacer sorteo y todos los preinscritos serán admitidos.

## 

## PAGO

No contemplaremos en nuestra base de datos la gestión del pago de las actividades.
Únicamente recogeremos que cada programa tiene una serie de tarifas específicas
(algunas precisan entregar cierta documentación), que se detallan a continuación, y que
cada inscrito admitido deberá comunicar la tarifa a la que se acoge y la forma de pago
(bimestral, cuatrimestral o anual).

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

Se podrá solicitar la baja en un programa o actividad en cualquier momento, pero
exclusivamente podrá solicitarse la devolución de las cuotas pagadas de aquellos meses
pagados y no disfrutados, independientemente del sistema de pago elegido.
A efectos estadísticos, habrá de mantenerse la información de aquellas personas que han
estado inscritas en algún grupo durante el curso 2017/2018, aún después de haber
causado baja (solo hasta el comienzo del siguiente curso), registrando la fecha efectiva
de baja en la base de datos.

## LISTA DE RESERVA

1o Las listas quedarán por el orden que se corresponde de manera correlativa a la
numeración otorgada para cada grupo de trabajo para el sorteo, al final de este listado
se incorporarán las personas que realicen la reserva a partir del mes de octubre, en
este caso el orden de prelación quedará determinado por el día hora de esta reserva,
pero siempre a partir del último alumno que participó en el sorteo.
2o Una vez que exista plaza vacante, desde el IMD o la entidad colaboradora avisará al
número de teléfono consignado en la preinscripción de la plaza vacante, en caso que
con esta llamada no sea posible contactar con el alumno, se realizará otra llamada en
horario distinto y en caso de no ser posible su localización, se dará de baja al
alumno/a.
Habrán de conocerse los preinscritos que están en reserva en un grupo y el orden que
ocupan en dicha lista de reserva.

## GESTIÓN DEL PERSONAL

La base de datos debe también completarse con los datos del personal que estará
encargado de impartir las actividades a los diferentes grupos, a los que se denomina
monitores. De cada monitor debemos tener los mismos datos personales que tenemos
para los inscritos y, además, el número de la seguridad social y la fecha del contrato.
Debemos tener en cuenta que un monitor podría también inscribirse como alumno en
alguno de los grupos del mismo o distinto programa (por ejemplo, una monitora de tenis
podría estar inscrita en un grupo de pilates).
Para un mejor control de las actividades este curso, el IMD ha decidido nombrar a
cuatro monitores como responsables de cada uno de los programas (uno por programa).
También, para todos los monitores, y dependiendo de las acreditaciones y títulos que
haya aportado cada uno, se quieren almacenar en la base de datos aquellas modalidades
deportivas en las que se le considera especialista (pueden ser varias).
Lo más importante, sin embargo, es llevar un control exhaustivo de la asignación de
monitores a los distintos grupos, tanto de su asignación actual (cada grupo solo tiene
asignado un monitor pero un monitor podría dar clase a varios grupos) como a lo largo
de todo el curso, porque es frecuente que los monitores roten por distintos grupos
durante el curso, bien por necesidades del IMD, bajas de compañeros o con motivo de
sus estudios (muchos son estudiantes del Grado en Ciencias del Deporte). Así pues, es
preciso mantener información de a qué grupos imparte clase un monitor y desde cuándo,
así como a qué grupos ha dado clase durante otros periodos de tiempo en el curso, almacenando información de dichos periodos. Es bastante probable, además, que un
monitor esté asignado varias veces al mismo grupo en diferentes periodos de tiempo.
