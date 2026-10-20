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

# 📚 Reporte de Actividades - Semana 1: Fundamentos de Java y Estructuras Básicas

> **Autor:** Josselin Nero  
> **Materia / Módulo:** Programación / Java  

---

## 🎯 Objetivo de la Semana
Realizar la transición del paradigma de programación estructurada (C) hacia la programación orientada a objetos básica en **Java**. Durante esta semana se afianzó la sintaxis fundamental, el manejo de entrada/salida de datos con `Scanner`, el uso de condicionales y la manipulación de arreglos de 1 y 2 dimensiones.

---

## 📑 Resumen de la Ruta de Aprendizaje

| Fase | Reto / Tema | Ruta en HackerRank | Qué Refuerza |
| :--- | :--- | :--- | :--- |
| **Entrenamiento** | Documentación de `Scanner` + ejemplo práctico | Documentación Oracle Java | Sintaxis básica de Entrada/Salida (I/O) |
| **Reto Obligatorio** | **Java Stdin and Stdout I** | `Java > Introduction` | Reemplazo de `scanf` en C por `Scanner` |
| **Entrenamiento** | Ejercicios de `if-else` en papel | Cuaderno / PDF | Lógica booleana y operadores |
| **Reto Obligatorio** | **Java If-Else** | `Java > Introduction` | Operadores relacionales y condicionales anidadas |
| **Entrenamiento** | Declaración de arreglo de 5 enteros en papel | Cuaderno / PDF | Índices base cero (desde 0) |
| **Reto Obligatorio** | **Java 1D Array** | `Java > Introduction` | Recorrido e inicialización de arreglos |
| **Entrenamiento** | Dibujar una matriz $3 \times 3$ en papel | Cuaderno / PDF | Matrices e índices 2D |
| **Reto Obligatorio** | **Java 2D Array** | `Java > Introduction` | Matrices y bucles anidados |

---

## 📝 Detalle de Actividades y Retos

### 1. Documentación e I/O con `Scanner`
<img width="441" height="704" alt="image" src="https://github.com/user-attachments/assets/a0602155-a616-46dc-82b8-ab00e475d173" />



---


#### 🔹 Java If-Else
* **Concepto:** Evaluación de condiciones complejas.
* **Solución:** Uso de estructuras `if / else if` para clasificar un número entero $N$ según las reglas:
<img width="472" height="695" alt="image" src="https://github.com/user-attachments/assets/fada436f-4340-44bb-89ac-ab10166e4b61" />

<img width="456" height="148" alt="image" src="https://github.com/user-attachments/assets/bb87648a-9800-4db1-8832-511ef854076c" />


#### 🔹 Java Array 
* **Concepto:** Arreglos unidimensionales.
* **Arreglo:** Declarar un arreglo de 5 enteros en papel.
* **Matriz de 3x3:**
<img width="470" height="521" alt="image" src="https://github.com/user-attachments/assets/64451911-5752-42c4-8015-40299e8883ca" />

---

## ✅ Resultados (Anexos)
### 2. Retos de HackerRank Completados

#### 🔹 Java Stdin and Stdout I
<img width="886" height="382" alt="image" src="https://github.com/user-attachments/assets/f7672b69-768a-4ee8-8748-291d37ac1cf3" />
<img width="705" height="491" alt="image" src="https://github.com/user-attachments/assets/1dbb635e-260c-42ca-9ff5-fe3d7c429a7c" />


#### 🔹 Java If-Else
<img width="886" height="394" alt="image" src="https://github.com/user-attachments/assets/1b8cc16a-2cd0-4c14-b051-63194eae6d3b" />
<img width="624" height="429" alt="image" src="https://github.com/user-attachments/assets/adafc2ea-4a06-43d2-a262-494d37775ae8" />


#### 🔹 Java 1D Array
<img width="886" height="361" alt="image" src="https://github.com/user-attachments/assets/4a2c1875-a178-4284-99fe-879ec2bb8fe1" />
<img width="886" height="433" alt="image" src="https://github.com/user-attachments/assets/29ce2bd1-6cf2-4cc5-88e1-0982851f31a7" />



#### 🔹 Java 2D Array
<img width="886" height="587" alt="image" src="https://github.com/user-attachments/assets/b055b9a9-3d19-426d-aa3f-414de47ee1af" />







