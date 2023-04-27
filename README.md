# JSbasic
### Repositorio de los algoritmos realizados en el curso de Alura sobre Frontend.

Los archivos presentes en esta página, son básicos en programación y son algunos de los realizados en un curso en linea. El código en su mayoria esta hecho en *javascript*. Sin embargo, la intención aquí es aprender la sintáxis tanto de *JS* como repasar algo de *HTML*, *CSS* y *Markdown*. Realizo esta pagina como resumen de los algoritmos y aprovecho para realizar un registro de lo aprendido en clase.


### Lógica de programación: Primeros pasos.

Los siguientes algoritmos se realizaron durante el transcurso del contenido de la clase **Lógica de programación: Primeros pasos"**. Cada video desarrolla uno o dos algorimtos con difentes temas. Trate de desarrollar la mayoría, sin embargo, solo he consignados los más interesantes a mi criterio.

**calculoImc.html**

    <meta charset="UTF-8">

    <h1>PROGRAMA CALCULO DE ÍNDICE DE MASA CORPORAL.</h1>
    <script>
        var numeroSalto = 3; // variable que cambia los saltos de línea cuando se invoca la funcion "imprimir".
        
            function saltarLinea(salto) {
                // repeat multiplica un string tantas veces como su argumento.
                document.write("<br>".repeat(salto));
                document.write("<hr>");
            }

            function imprimir(frase){
                document.write(frase);
                saltarLinea(numeroSalto);
            }
        
            function calcularImc(nombre, peso, altura) {
                imc = peso/(altura*altura);
                imprimir("El índice de IMC de "+ nombre +" es: " + Number(imc.toFixed(2)));
            }

        var nombre = prompt("Ingrese su nombre: ")
        var peso = prompt("Ingrese su peso: ");
        var altura = prompt("Ingrese su altura: ");

        calcularImc(nombre, peso, altura);    
        
    </script>

---

**calculoComsumo.html**

    <meta charset="UTF-8">
    <script>

        document.write("<h3>¿Alcohol o gasolina?</h3><br>");
        document.write("Calculo de la eficiencia de consumo.<br>");
        document.write("Comparación entre alcohol o gasolina.<br>");
        document.write("<br>");
        document.write("Capacidad del tanque: <i>40 litros</i>.<br>");
        document.write("Kilometros recorridos con gasolina: <i>480 litros</i>.<br>");
        document.write("Kilometros recorridos con alcohol: <i>300 litros</i>.<br>");
        var eficiencia_gasolina = 480/40;
        var eficiencia_alcohol = 300/40;
        document.write("La eficiencia del carro con gasolina es: <i>"+eficiencia_gasolina +"</i> k/litro.<br>");
        document.write("La eficiencia del carro con alcohol es: <i>"+eficiencia_alcohol +"</i> k/litro.<br>");

    </script>

---

**saltoLinea.html**

    <meta charset="UTF-8">

    <h1>PROGRAMA</h1>
    <script>

            function saltarLinea(salto) {
                document.write("<br>".repeat(salto));
                document.write("<hr>");
            }

            function imprimir(frase){
                document.write(frase);
                saltarLinea(numeroSalto);
            }
        
        var anho = 2023;
        var numeroSalto = 3;

        imprimir("Juan tiene " + (anho - 1995) + " años.");
        
        imprimir("Pedro tiene " + (anho - 1990) + " años.");
        
        imprimir("Amanda tiene " + (anho - 1998) + " años.");
        
        imprimir("Lina tiene " + (anho - 2000) + " años.");
        

    </script>

### Práctica con juegos y animaciones.

Siguiendo con el curso de "prograciónme tope con algo interesante. Los siguientes algoritmos los organice de forma progresiva para llegar a un pequeño juego hecho en html y css. Lo que pretendo es ir acumulando el paso a paso, ver el progreso y tal vez llegar a un descente, pequeño pero entretenido videojuego hecho en HTML y JS.

Iniciamos con la creación del canvas y luego la creación de varias funciones como el objetivo que es la imagen de un tiro al balnco, la función limpiarPantalla, actualizarPantalla, sortearPosicion, disenharObjetivo, actualizarPantalla y disparar. El canvas que se convierte en el área del juego y donde se regitran los disparos. Al final de esta etapa, el código queda en esto:

**target.html**

    <canvas width="600" height="400"> </canvas>

    <script>
        var pantalla = document.querySelector("canvas");
        var pincel = pantalla.getContext("2d");        
        pincel.fillStyle = "lightgrey";
        pincel.fillRect(0,0,600,400); 

        var xAleatorio;
        var yAleatorio;

        function disenharCircunferencia(x,y,radio,color){
            pincel.fillStyle = color;
            pincel.beginPath();
            pincel.arc(x,y,radio,0,2*Math.PI);
            pincel.fill();
        }

        function limpiarPantalla(){
            pincel.clearRect(0,0,600,400);
        }

        function actualizarPantalla(){
            limpiarPantalla();

        }
        function sortearPosicion(maximo){
            return Math.floor(Math.random()*maximo);
        }

        function disenharObjetivo(x,y){
            disenharCircunferencia(x,y,30,"red");
            disenharCircunferencia(x,y,20,"white");
            disenharCircunferencia(x,y,10,"red");
        }
        
        function actualizarPantalla(){
            limpiarPantalla();
            xAleatorio = 30+sortearPosicion(540);
            yAleatorio = 30+sortearPosicion(340);
            disenharObjetivo(xAleatorio,yAleatorio);
            x++;
        }

        function disparar(evento){
            var x = evento.pageX -pantalla.offsetLeft;
            var y = evento.pageY -pantalla.offsetTop;

            if(( x > xAleatorio-10) && (x < xAleatorio + 10) && (y > yAleatorio-10) && (y < yAleatorio+10)){
                alert("Tiro certero.");
            }
            
        }
        setInterval(actualizarPantalla,1000);
        pantalla.onclick=disparar;

    </script> 

El resultado me gusto y quice ir mas allá. No tengo claro por que recorde los videojuego de la vieja escuela. Esos del *"Atari 2600"*, con sus imagenes de 8-bit pero, me agrado la idea de mejorar el video juego utilizando un personaje de *Space-invaders* la puesto el personaje utilizando mi forma de hacer el personaje, un compañero del aula virtual donde estoy estudiando me hablo de una mejor forma de hacer el mapa de bits (bitmap en ingles). Gracias a eso puede hacer el personaje de una forma mas sencilla y elegante. Esto me alento a seguir mejorando y se me ocurrio animar al personaje. 

El resultado parcial es un pequeño videojuego basado en el anterior pero con un personaje animado. Cuando veo un personaje en los videojuego hay algo que se activa en mi y seguro los que saben de videojuegos lo podrán justificar mejor. 

**Space_invaders_minigame.html**

    <canvas width="600" height="400"></canvas>
    <script> 
    var pantalla = document.querySelector("canvas");
    var pincel = pantalla.getContext("2d");
    pincel.fillStyle="black";
    pincel.strokeRect(0,0,600,400); // marco o limite del área del juego.

    const arrSize = 8;
    const numBits = 11;
    // si1, si2, si3 son un mismo personaje.  
    si1 = new Uint16Array(arrSize)
    si1[0] = 0b00100000100
    si1[1] = 0b00010001000
    si1[2] = 0b00111111100
    si1[3] = 0b01101110110
    si1[4] = 0b11111111111
    si1[5] = 0b10111111101
    si1[6] = 0b10100000101
    si1[7] = 0b00011011000

    si2 = new Uint16Array(arrSize)
    si2[0] = 0b00100000100
    si2[1] = 0b00010001000
    si2[2] = 0b00111111100
    si2[3] = 0b01101110110
    si2[4] = 0b11111111111
    si2[5] = 0b00111111100
    si2[6] = 0b00100000100
    si2[7] = 0b00100000100

    si3 = new Uint16Array(arrSize)
    si3[0] = 0b00100000100
    si3[1] = 0b00010001000
    si3[2] = 0b10111111101
    si3[3] = 0b11101110111
    si3[4] = 0b11111111111
    si3[5] = 0b00111111100
    si3[6] = 0b00100000100
    si3[7] = 0b01100000110

    const mag = 5; // escala (tamaño) del invasor
    var xAleatorio , yAleatorio;

    function sortearPosicion(maximo){ return Math.floor(Math.random()*maximo); }

    function limpiarPantalla(){ pincel.clearRect(0,0,600,400); }

    function dibujarRectangulo(x, y) { pincel.fillRect(x,y, mag, mag) }

    function pintar(modelo){

        pincel.strokeRect(0,0,600,400); // marco o limite del área del juego.
        xAleatorio = sortearPosicion(600-(mag*numBits));
        yAleatorio = sortearPosicion(400-(mag*arrSize));

        for (let i = 0; i < arrSize; i++) {
            for (let j = 0; j < 16; j++) {
                if (modelo[i] & (1024>>j)) {
                    // Acá debe dibujar el pixel que corresponde.
                    
                    dibujarRectangulo(xAleatorio+(j)*mag,yAleatorio+(i)*mag)
                }
            }
        }

    }

    var secuencia = [si1,si2,si3];
    var capas = secuencia.length;

    var ritmo = 0;
    var signo = 1;

    function animacion(){
        // limpiarPantalla();
        if(ritmo >= capas-1){
            signo = -1;
        }else if(ritmo <= 0){
            signo = 1;
        }
        ritmo += signo;
        return ritmo;
    }

    function actualizarPantalla(){

        limpiarPantalla();
        pintar(secuencia[ritmo]);
        
    }

    function disparar(evento){
            var x = evento.pageX -pantalla.offsetLeft;
            var y = evento.pageY -pantalla.offsetTop;

            if(( x > xAleatorio) && (x < xAleatorio + mag*numBits) && (y > yAleatorio) && (y < yAleatorio+mag*arrSize)){
                alert("Tiro certero.");
            }
            
        }


    setInterval(animacion,200);
    setInterval(actualizarPantalla,700);
    pantalla.onclick=disparar;

    </script> 

Es solo mi primer intento de videojuego pero, desde ya tengo algunas ideas mas para seguir mejorandolo. Se que debo separar cada una de las funciones que implican cambio o animación. Ya agrege una propiedad para el personaje que es la *magnitud* y quiero agragar otra para el tamaño del "paso" cuando se mueve. Estas propiedades son las que pienso manipular a medida que el juegador suba de nivel. Por otro lado, presenta agunos problemas a la ora de "sentir" el disparo dentro del área del personaje cuado cambia su magnitud, habrá que analizar bien que es lo que pasa para corregirlo. Por ahora, esas serán las mejoras, llegara el momento en que mensare en algun sistame de puntuación.  

> :copyright: [Leoperez](http://leoperezx.github.io) 