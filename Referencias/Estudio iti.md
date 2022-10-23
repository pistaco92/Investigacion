# Introduccion

Sistemas de archivos. 
La programación en c
Las planificaciones de procesos las políticas. Ios métodos para sincronizar con exclusión. Sus problemas. Y sus ejemplos. Paralelismo y concurrencia. Ejemplos de paralelismo. 


# programación en C

Ocupa punteros y facilita acceso a memoria a través de ellos. Cada variable ocupa una dirección De Memoria. es un caballero sin memoria. Dado que no almacena información entre ficheros. Desde punto vista compilador, que es mas simple. 
Se utilizan *indirecciones* para acceder indirectamente.  

Sintaxis parecida a Java. Struct es una especie de objeto JavaScript. → para acceder a atributos. * para declaración ejecución y almacenamiento en punteros. (dato; pesan 4 bits )

Tipos de datos parecido a sql. Carente de (aparte de memoria) objetos y por ende de clases. Programación Funcional. (fuerza a return ). 


# Sincronizacion
A partir del arribo de la multiprogramación. es posible que un procesador haga multiples procesos. O así lo paresca. A traves de la concurrencia. Para coordinación de los procesos, Existen tácticas.

- exclusión mutua
Que 2 procesos no pueden entrar a región critica a la vez. 
¿condiciones para que funcione?
- No bloqueó axtermo 
- uno a la vez
- no calculo
- desactivar Interrupciones 

La implementación  En c es diversa. 
Métodos?
- candado
- alternancia estricta
- semáforo
	- distinto de algo A regex. Creo que en cuanto a restringcion.
- Wake up
	- Implementación Consumidor y productor

Se muestra código de cada uno. Secuencialmente cada uno es solución del anterior (Que finalmente 2 al mismo tiempo)

Solución definitiva; monitor, ojo que todo lo ve.

# Paralelismo

Cuando hay mas de un procesador(multiproceso) se es posible hacer paralelismo; procesos Al mismo tiempo. La ganancia de tiempo frente A la secuencial, depende
De la cantidad de procesadores. Y la relación entre los procesos. Dependencia, etcétera.
No se puede ocupar de 2 procesos de misma secuencia. (dada la dependencia). Ejemplo De proceso matemático.

![[2022-07-04 2022-07-04 07.23.43.excalidraw.svg]]
%%[[2022-07-04 2022-07-04 07.23.43.excalidraw.md|🖋 Edit in Excalidraw]]%%

2 conceptos, línea gruesa (alto paralelismo), y línea delgada (me acorde de lo de la cola de gato en estadística). 

Distintos tipos de paralelismo.


# Planificacione del proceso

Con relación a la secuencia persee. El So, puede optar por diversas estrategias siguiendo unas, directrices. (políticas)

Cuales?
- Fifo
- round robín
- el chico primero

Tipos?
- Soberano
- Espera 


# Interbloqueo

Se produce cuando se acaparan los recursos por los procesos. Y No se pueden mover (taco). 
Por defecto se puede hacer lo siguiente en caso de.

- omitir
- lo desenreda. 
	Pero no sin antes una operación de busqueda;
	- matriz
	- algoritmo 
	el desenredo uno de los métodos es;
	- reapropiación temporal.
		funciona en interbloqueo circular. Para cortar la cadena de dependencia. 

![[2022-07-04 2022-07-04 07.43.45.excalidraw.svg]]
%%[[2022-07-04 2022-07-04 07.43.45.excalidraw.md|🖋 Edit in Excalidraw]]%%


# Sistema de archivos 

Un archivo tiene 9 operaciones. Estas van a un directorio con meta data. Propiedad de protección. 
Un sistema de archivos cumple ciertos parámetro de calidad. 
Tipos

Paginado o indexado. Uno de ellos es secuencial, en el cual se tiene un puntero hacia el 
Siguiente. Clásico en unix. Otro es con nodos. 
Problema de rendimiento, propone solución.

---------
Tabla de particiones. HAy una maestraN (antigua y después gnu, que seria el actual, windows xp, trae para integración)

Al momento de crear un archivo. Primero el sistema revisa en las tablas FRP. Si existe. Después en la de procesos abiertos para ver si no hay interferencia. Y después finiquita agregándolo al directorio correspondiente.