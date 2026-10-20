# 🚀 Semana 1: De la "Estructura" al "Objeto" y Lógica de Bucles

> **Materia:** Programación Orientada a Objetos / Estructura de Datos  
> **Objetivo Semanal:** Corregir errores de traza en bucles, transicionar de `struct` en C a `class` en Java, y dominar arreglos unidimensionales y bidimensionales.

---

## 🛠️ Retos Obligatorios de la Semana

### Reto 1: El Promedio Inteligente
* **Conceptos clave:** Uso correcto de bucles `while`, división con casting a `double`, conteo de iteraciones.

```java
import java.util.Scanner;

/**
  * @author: Josselin Nero F.
  *
**/
// RETO 1: "El Promedio Inteligente"
// Objetivo: Calcular el promedio de N notas ingresadas por el usuario.
// El ingreso termina cuando el usuario ingresa un número negativo.
public class PromedioInteligente {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Paso 1: Variables necesarias
        double suma = 0;     // Acumula la suma de las notas
        int contador = 0;    // Cuenta cuántas notas válidas se ingresaron
        int nota;            // Guarda la nota que se lee en cada vuelta

        // Paso 2: Lectura inicial y condición del while
        System.out.println("Ingresa calificaciones (negativo para terminar):");
        nota = scanner.nextInt();

        // Seguimos pidiendo notas MIENTRAS la nota NO sea negativa
        while (nota >= 0) {
            suma = suma + nota;          // Acumula la nota
            contador = contador + 1;     // Cuenta la iteración
            nota = scanner.nextInt();    // Pide la siguiente nota
        }

        // Paso 3: Cálculo del promedio
        if (contador > 0) {
            // Casting a double ANTES de dividir
            double promedio = (double) suma / contador;
            System.out.println("Promedio: " + promedio);
        } else {
            // Evita dividir entre 0 si el primer número fue negativo
            System.out.println("No se ingresaron notas válidas.");
        }

        System.out.println("Total de notas: " + contador);

        scanner.close();
    }
}
```

---
## Prueba de ejecución
<img width="610" height="198" alt="image" src="https://github.com/user-attachments/assets/b1ef7e2e-39c2-4687-a33a-7b409d9ce570" />

---
### Reto 2: “Registro de Estudiantes”
#### De `struct` en C a `class` en Java

| Aspecto | `struct` en C | `class` en Java |
| :--- | :--- | :--- |
| **Contenido** | Solo datos (campos) | Datos (atributos) **y** comportamiento (métodos) |
| **Creación** | `struct Estudiante e;`<br>*(memoria directa)* | `new Estudiante()` *(objeto en el heap, se accede por referencia)* |
| **Acceso a datos** | Público siempre | Se controla con `private` / `public` y *getters/setters* |
| **Inicialización** | Manual | Mediante **constructores** |
| **Memoria** | (`free`) | La gestiona el *Garbage Collector* |

> **La idea clave:** en C separas datos (`struct`) y funciones, y en Java los unes en una sola unidad, el **objeto**.


---

```java
// Clase que reemplaza al struct de C
class Estudiante {
    private String nombre;
    private double nota;

    // Constructor: inicializa el objeto
    public Estudiante(String nombre, double nota) {
        this.nombre = nombre;
        this.nota = nota;
    }

    public String getNombre() { return nombre; }
    public double getNota()   { return nota; }

    public void mostrar() {
        System.out.println(nombre + " - Nota: " + nota);
    }
}

public class RegistroEstudiantes {
    public static void main(String[] args) {
        // Arreglo de 5 referencias a Estudiante (inicialmente todas null)
        Estudiante[] arr = new Estudiante[5];

        // Hay que crear cada objeto con new
        arr[0] = new Estudiante("Ana", 9.0);
        arr[1] = new Estudiante("Luis", 7.5);
        arr[2] = new Estudiante("María", 8.8);   // 3er elemento
        arr[3] = new Estudiante("Carlos", 6.9);
        arr[4] = new Estudiante("Sofía", 9.5);

        // El 3er elemento está en el índice 2 (los índices empiezan en 0)
        System.out.println("Tercer estudiante:");
        arr[2].mostrar();

        // Recorrer todo el arreglo
        for (int i = 0; i < arr.length; i++) {
            arr[i].mostrar();
        }
    }
}

```

---
## Prueba de ejecución
<img width="653" height="150" alt="image" src="https://github.com/user-attachments/assets/3a784b93-6ccd-4bd7-86ef-81f4f89dff28" />

---





