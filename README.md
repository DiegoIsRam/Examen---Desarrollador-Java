# Examen Desarrollador-Java


## Ejercicio 1
#### Clase Main
```java
public class Main {
    public static void main(String[] args) {
       Rectangulo rectangulo = new Rectangulo(2,1);
        System.out.println(rectangulo.getArea());

    }
}
```
#### Interfaz Forma
```java
public interface Forma {
    double CalculaArea();
}
```
#### Clase Forma
```java
public class Rectangulo implements Forma{

    double ancho;
    double alto;

    double area = 0;

    public double getAncho() {
        return ancho;
    }

    public void setAncho(double ancho) {
        this.ancho = ancho;
    }

    public double getAlto() {
        return alto;
    }

    public void setAlto(double alto) {
        this.alto = alto;
    }

    public double getArea() {
        return CalculaArea();
    }

    public Rectangulo(double ancho, double alto) {
        this.ancho = ancho;
        this.alto = alto;
    }

    public Rectangulo(){
        this.ancho = 0;
        this.alto = 0;
    }

    @Override
    public double CalculaArea() {
        this.area = Math.abs(this.alto*this.ancho);
        return this.area;
    }
}
```

## Ejercicio 2 
```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Locale;

public class Main {
    public static void main(String[] args) {

        ArrayList<String> arraynum = new ArrayList<String>(Arrays.asList("juan","pedro","jose","maria","sofia"));
        for (String nombre:
             arraynum) {
            var nombreArray = nombre.split("");
            String nombreNuevo = "";
            for (int i = 0; i < nombre.length(); i++) {

                if (i==0){
                    nombreNuevo += nombreNuevo + nombreArray[i].toUpperCase(Locale.ROOT);
                }
                else{
                    nombreNuevo += nombreArray[i];
                }
            }
            System.out.println(nombreNuevo);


        }
    }
}
```
## Ejercicio 3 
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Ingrese el número de renglones");
        int num = Integer.parseInt(scanner.nextLine());
        System.out.println("El número que ingreso es: " + num);
        int contador = 1;
        String linea = new String();

        for (int i = 0; i < num ; i++) {
            linea = "";
            for (int j = 0; j < (i+1) ; j++) {
                linea += String.valueOf(contador) + " " ;
                contador++;
            }
            System.out.println(linea);
        }


        }
}

```
## Ejercicio 5 
```java
import java.util.*;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) {
       ArrayList<Integer> arraynum = new ArrayList<Integer>(Arrays.asList(1, 8, 5,2, 33, 54,22,6,88,13));
       System.out.println(arraynum.stream().filter(x-> (x%2)==0).collect(Collectors.toList()));
    }
}
```
## Ejercicio 7 
```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Locale;
import java.util.Scanner;

import static java.lang.Integer.parseInt;

public class Main {
    public static void main(String[] args) {
    int numeAleatorio = (int)(Math.random()*100 +1);
    Scanner scanner = new Scanner(System.in);
        System.out.println("El número aleatorio es: " + numeAleatorio);
        for (int i = 0; i < 5; i++) {
            System.out.println("------------Intento #"+(i+1)+"-----------");
            System.out.println("Adivine el numero aleatorio: ");
            int numUsuario = Integer.parseInt(scanner.nextLine());
            if (numUsuario == numeAleatorio) {
                System.out.println("Felicidades, adivinaste el número");
                break;
            }else if (numUsuario>numeAleatorio){
                System.out.println("Tu número es mayor al aleatorio");

            }else{
                System.out.println("Tu número es menor al aleatorio");

            }
            if (i+1 != 5){
                System.out.println("Intenta de nuevo");
            }else{
                System.out.println("GAME OVER");
            }
        }


    }
}
```

