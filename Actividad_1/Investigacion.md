# Investigacion   

1. **CPU (Unidad Central de Procesamiento)**: Es el componente principal de un sistema informático encargado de interpretar y ejecutar instrucciones. Actúa como el "cerebro" del ordenador, gestionando y coordinando las operaciones de todos los demás componentes. La CPU consta de varias unidades funcionales, incluyendo la Unidad Aritmético-Lógica (ALU), la Unidad de Control y los registros internos.  

2. **ALU (Unidad Aritmético-Lógica)**: Es una subunidad de la CPU responsable de realizar operaciones aritméticas (como suma, resta, multiplicación) y lógicas (como AND, OR, NOT). La ALU toma los datos de los registros, ejecuta las operaciones requeridas y devuelve los resultados para su almacenamiento o uso posterior.   


3. **Registros**: Son pequeñas unidades de almacenamiento dentro de la CPU que contienen datos, instrucciones y el estado actual del procesador, permitiendo a la CPU ejecutar tareas con rapidez y eficacia.   

    - **Registros de propósito general**: Se utilizan para almacenar datos temporales y resultados intermedios; pueden ser utilizados por cualquier instrucción.  
 
    - **Registros de propósito específico**: Diseñados para tareas de control específicas; algunos ejemplos son el Contador de Programa, el Registro de Direcciones de Memoria, el Registro de Datos de Memoria y el Registro de Instrucción Actual.    


4. **Unidad de Control**: Es la parte de la CPU que dirige el flujo de datos e instrucciones dentro de la CPU, descodifica y procesa las entradas, gestiona la ejecución de las instrucciones y coordina la comunicación entre otros componentes de la CPU y los periféricos. 


5. **Buses de datos y de dirección**:

    - **Bus de datos**: Transporta los datos que se están procesando o transfiriendo. Es bidireccional, lo que significa que puede enviar y recibir datos entre la CPU, la memoria y los dispositivos de entrada/salida. El ancho del bus de datos, es decir, la cantidad de bits que puede transferir simultáneamente, influye directamente en el rendimiento del sistema.


    - **Bus de dirección**: Transporta las direcciones de memoria que indican la ubicación de los datos que se desean leer o escribir. Es unidireccional, ya que la CPU envía las direcciones a la memoria o a los dispositivos de entrada/salida. El ancho del bus de direcciones determina la cantidad máxima de memoria que el sistema puede direccionar. 


6. **Memoria RAM y memoria ROM**:

    - **RAM (Memoria de Acceso Aleatorio)**: Es una memoria volátil que almacena datos e instrucciones que la CPU necesita de manera inmediata. Su contenido se pierde al apagar el sistema.

    - **ROM (Memoria de Solo Lectura)**: Es una memoria no volátil que contiene instrucciones y datos permanentes, esenciales para el arranque y funcionamiento básico del sistema. Su contenido no se pierde al apagar el sistema.

   Ambos términos siguen siendo vigentes en la arquitectura de computadores actual, aunque las tecnologías subyacentes han evolucionado con el tiempo.

7. **Opcode**: Es la parte de una instrucción de máquina que especifica la operación a realizar. Cada instrucción en lenguaje de máquina se compone de un opcode que indica a la CPU qué operación debe ejecutar, como una suma, una carga de datos o una comparación.  


# Ejercicio 2: simulación   

 
 1. **Componentes principales y su función**

    - **ROM**: Se encarga de almacenar el código con las  instrucciones del programa.

    - **RAM**:Es una memoria de lectura y escritura que almacena datos temporales mientras el programa está en ejecución. En este sistema, se utiliza para registrar la información proveniente del teclado y para almacenar los valores que determinan la imagen en la pantalla. Como la CPU puede modificar su contenido en tiempo real, la RAM es clave para la interacción del usuario con el programa.

    - **CPU**: Es el núcleo del sistema y se encarga de ejecutar las instrucciones almacenadas en la ROM. A partir de cada instrucción, la CPU puede realizar diversas tareas, como operar con datos, gestionar la memoria o controlar dispositivos de entrada y salida.

    - **Teclado**: Está conectado a la memoria y funciona como un conjunto de entradas digitales que la CPU puede leer. Cada tecla representa un valor específico en la memoria, y cuando el usuario la presiona, la CPU detecta el cambio y ejecuta instrucciones que pueden modificar la pantalla o realizar otras operaciones dentro del sistema.

    - **Pantalla**: Refleja los valores almacenados en la memoria, lo que significa que cualquier cambio en la RAM afecta directamente la imagen mostrada. En este caso, el programa está diseñado para oscurecer progresivamente la pantalla cuando se mantiene presionada una tecla, lo que implica que la CPU está escribiendo valores en la memoria que corresponden a un estado más oscuro de la imagen.

2. **Flujo de Ejecución del Programa**

    - **Inicio y Reset**: Cuando el sistema se enciende o se presiona el botón de reset, la CPU comienza a ejecutar el programa desde la ROM. En este punto, se inicializan los registros internos, el contador de programa y la memoria RAM, asegurando que el sistema arranque en un estado definido. La CPU carga la primera instrucción desde la ROM y se prepara para procesarla.  

    - **Bucle de Ejecución**: La CPU sigue un ciclo constante de lectura, decodificación y ejecución de instrucciones. Cada instrucción indica una operación específica, como mover datos entre la memoria y los registros, realizar cálculos o controlar dispositivos externos. Si la instrucción involucra la memoria, la CPU accede a la RAM para leer o escribir valores según lo requiera el programa.  

    - **Detección de Entrada del Teclado**: El sistema está diseñado para detectar cuando una tecla está presionada. Las teclas están conectadas a la memoria y cada una tiene una dirección específica. Cuando el usuario presiona una tecla, el estado de la memoria cambia, y la CPU lo interpreta al leer la dirección correspondiente. Dependiendo del programa almacenado en la ROM, esta entrada se usa para modificar otras partes de la memoria y afectar la salida visual en la pantalla.

    - **Modificación de la Pantalla**: La pantalla refleja los valores almacenados en la memoria RAM. Cuando la CPU detecta una tecla presionada, ejecuta instrucciones que cambian progresivamente los datos en la RAM, generando el efecto de oscurecimiento en la pantalla. Si la tecla se mantiene presionada, el programa sigue sobrescribiendo la memoria con valores que representan un color más oscuro, haciendo que la pantalla se vuelva completamente negra con el tiempo.

 # Concepto de programa almacenado

    1. **¿Qué es un programa y dónde se almacena?**

        Un programa es un conjunto de instrucciones que la CPU ejecuta para realizar tareas específicas. Se almacena en la memoria ROM o RAM.

    2. **Si pongo un comentario en un programa como: //variable tipo contador. ¿Dónde se almacena dicho comentario?**

        os comentarios no se almacenan en la memoria del programa. Solo son útiles para los programadores y se eliminan durante el proceso de ensamblado.

    3. **¿Dónde se almacena una variable?**

        Las variables se almacenan en la memoria RAM durante la ejecución del programa.

#  Fetch-Decode-Execute

1. **Paso 1: Fetch (Búsqueda)**: En esta etapa, la CPU obtiene la siguiente instrucción que debe ejecutar. Aquí es donde entra en juego el Program Counter (PC), un registro especial de la CPU que almacena la dirección de memoria de la siguiente instrucción a ejecutar.

2. **Paso 2: Decode (Decodificación)**: Una vez que la CPU tiene la instrucción en el Instruction Register (IR), debe interpretarla para saber qué operación realizar.

# Tipos de Instrucciones del Procesador

 El procesador del caso de estudio utiliza distintos tipos de instrucciones para ejecutar operaciones, las cuales pueden clasificarse en las siguientes categorías:

 1. **Instrucciones de Transferencia de Datos:**  
    Estas instrucciones permiten mover datos entre registros, memoria y dispositivos de entrada/salida. Se utilizan para cargar valores en registros, almacenar datos en memoria o intercambiar información entre diferentes componentes.  
    Ejemplo: MOV A, B (Copia el valor del registro B al registro A).

2. **Instrucciones Aritméticas y Lógicas:**  
    Son utilizadas para realizar operaciones matemáticas (suma, resta, multiplicación, división) y lógicas (AND, OR, NOT, XOR). Estas instrucciones modifican registros y afectan los indicadores de estado del procesador.  

3. **Instrucciones de Control de Flujo:**  
    Permiten modificar la secuencia de ejecución del programa mediante saltos condicionales e incondicionales, llamadas a subrutinas y retornos.  

4. **Instrucciones de Entrada y Salida (I/O):**  
    Estas instrucciones permiten la comunicación del procesador con dispositivos externos, como sensores, teclados o pantallas.   
       

# Decodificación en la CPU:
El proceso de decodificación en la CPU consiste en interpretar una instrucción en lenguaje de máquina para determinar qué operación realizar. Primero, la CPU busca la instrucción en la memoria usando el Program Counter (PC). Luego, decodifica el tipo de instrucción (tipo A o tipo C) y extrae los campos de operación, destino y salto. Por ejemplo, una instrucción tipo A (bit más significativo en 0) almacena un valor en el Registro A, mientras que una tipo C (bits más significativos en 111) realiza operaciones como sumas o saltos. Además, la CPU gestiona registros, ejecuta operaciones aritméticas y lógicas, controla el flujo del programa y accede a la memoria y periféricos. Estas funcionalidades permiten ejecutar programas de manera eficiente.  

# Codigo 
El programa suma los números del 1 al 100 almacenando el resultado en sum. Utiliza un bucle que incrementa i y lo suma a sum hasta que i supera 100. Finalmente, el programa entra en un bucle infinito en la etiqueta END.
