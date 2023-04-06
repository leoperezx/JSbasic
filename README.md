# JSbasic
### Repositorio de los algoritmos realizados en el curso de Alura sobre Frontend.

Los archivos presentes en esta página, son básicos en programación y son algunos de los realizados en un curso en linea. El código en su mayoria esta hecho en *javascript*. Sin embargo, la intención aquí es aprender la sintáxis tanto de **JS** como repasar algo de **HTML**, **CSS** y **Markdown**. Realizo esta pagina como resumen de los algoritmos y aprovecho para realizar un registro de lo aprendido en clase.

### Algoritmos
calculoImc.html
`
&lt;meta charset="UTF-8"&gt;

&lt;h1&gt;PROGRAMA CALCULO DE ÍNDICE DE MASA CORPORAL.&lt;/h1&gt;
&lt;script&gt;
    var numeroSalto = 3; // estos variable cambia los saltos de línea cuando se invoca la funcion "imprimir".
    
        function saltarLinea(salto) {
            // repeat multiplica un string tantas veces como su argumento.
            document.write("&lt;br&gt;".repeat(salto));
            document.write("&lt;hr&gt;");
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
    
&lt;/script&gt;
`
---

calculoComsumo.html
`
&lt;meta charset="UTF-8"&gt;
&lt;script&gt;

    document.write("&lt;h3&gt;¿Alcohol o gasolina?&lt;/h3&gt;&lt;br&gt;");
    document.write("Calculo de la eficiencia de consumo.&lt;br&gt;");
    document.write("Comparación entre alcohol o gasolina.&lt;br&gt;");
    document.write("&lt;br&gt;");
    document.write("Capacidad del tanque: &lt;i&gt;40 litros&lt;/i&gt;.&lt;br&gt;");
    document.write("Kilometros recorridos con gasolina: &lt;i&gt;480 litros&lt;/i&gt;.&lt;br&gt;");
    document.write("Kilometros recorridos con alcohol: &lt;i&gt;300 litros&lt;/i&gt;.&lt;br&gt;");
    var eficiencia_gasolina = 480/40;
    var eficiencia_alcohol = 300/40;
    document.write("La eficiencia del carro con gasolina es: &lt;i&gt;"+eficiencia_gasolina +"&lt;/i&gt; k/litro.&lt;br&gt;");
    document.write("La eficiencia del carro con alcohol es: &lt;i&gt;"+eficiencia_alcohol +"&lt;/i&gt; k/litro.&lt;br&gt;");

&lt;/script&gt;
`
---

saltoLinea.html
`
&lt;meta charset="UTF-8"&gt;

&lt;h1&gt;PROGRAMA&lt;/h1&gt;
&lt;script&gt;

        function saltarLinea(salto) {
            document.write("&lt;br&gt;".repeat(salto));
            document.write("&lt;hr&gt;");
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
    

&lt;/script&gt;
`