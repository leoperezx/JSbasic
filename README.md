# JSbasic
### Repositorio de los algoritmos realizados en el curso de Alura sobre Frontend.

Los archivos presentes en esta página, son básicos en programación y son algunos de los realizados en un curso en linea. El código en su mayoria esta hecho en *javascript*. Sin embargo, la intención aquí es aprender la sintáxis tanto de **JS** como repasar algo de **HTML**, **CSS** y **Markdown**. Realizo esta pagina como resumen de los algoritmos y aprovecho para realizar un registro de lo aprendido en clase.

### Algoritmos
calculoImc.html
`
<meta charset="UTF-8">

<h1>PROGRAMA CALCULO DE ÍNDICE DE MASA CORPORAL.</h1>
<script>
    var numeroSalto = 3; // estos variable cambia los saltos de línea cuando se invoca la funcion "imprimir".
    
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
`
---

calculoComsumo.html
`
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
`
---

saltoLinea.html
`
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
`