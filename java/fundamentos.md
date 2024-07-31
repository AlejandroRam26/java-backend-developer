# Fundamentos

### Características

- Orientado a objetos.

- Multiplataforma.

- Rápido.

- Seguro.

- Versátil.

## Sintaxis Básica

Se basa en conceptos como clase, objeto, método, variable y estructuras de control de flujo.

**Identificadores**: se utilizan identificadores para nombrar variables, métodos y clases. Deben cumplir las siguientes reglas:

- Estar compuestas por letras en inglés (a-z, A-Z), números (0-9), guión bajo (\_) o dólar ($).

- Los números no pueden ser los primeros caracteres.

- La nomenclatura es:

  - Paquetes: minúsculas `package`.

  - Clases e interfaces: camelCase `ClassName`.

  - Variables y métodos: camelCase `variableMetodo`.

## Tipos de Datos y Variables

Una variable es un espacio donde se guarda un valor durante la ejecución del programa. A esta variable se le asigna un tipo de dato, el cual determina su valor. Deben ser declaradas antes de usarse.

### Declaración de una Variable

```java
// tipo nombre;
int cantidad;
// declaraciones validas
int a,b;
float pi;
double d;
char a;
```

### Inicialización de una Variable

```java
// para inicializar una variable se le debe asignar un valor
// nombre = valor;
cantidad = 55;
// ejemplos
// los decimales se indican con un punto '.'
pi = 3.14f; // los float deben tener una 'f' al final
d = 20.22d;
a = ´c´; // los char deben estar envueltos en '´''
```

Es posible declarar e inicializar una variable al mismo tiempo

```java
// tipo nombre = valor;
int a=2, b=3, c=4;
float pi = 3.14f;
char a = ´c´;
```

### Tipos de Variables

En Java, hay tres tipos:

1- Locales:

- Son declaradas dentro del cuerpo de un método.

2- De Instancia:

- Son declaradas fuera de un método, son especificas del objeto.

3- Estáticas:

- Se inicializan solo una vez. Deben inicializarse antes de cualquier variable de instancia.

```java
class Clase{
    static int a = 2; // variable estática
    int dato = 24; // variable de instancia
    void metodo(){
        int b = 87; // variable local
    }
}
```

### Tipos de Datos

#### Primitivos

Incluyen:

| Tipo      | Valor por Defecto | Tamaño  |
| --------- | ----------------- | ------- |
| `byte`    | 0                 | 1 byte  |
| `short`   | 0                 | 2 bytes |
| `int`     | 0                 | 4 bytes |
| `long`    | 0L                | 8 bytes |
| `float`   | 0.0f              | 4 bytes |
| `double`  | 0.0d              | 8 bytes |
| `boolean` | false             | 1 bit   |
| `char`    | ‘\u0000’          | 2 bytes |

##### Puntos a recordar:

- Todos los tipos numéricos tienen signo (+/-).

- El Tamaño de los tipos es el mismo en todas las plataformas.

- El tipo `char` es 2 bytes porque es un carácter **UNICODE**.

#### No Primitivos

Incluyen:

- `String`: cadenas de texto

- `Array`: arreglo de datos.

- `Class`: clases.

- `Interface`: interfaces.

### Conversiones

Una variable de un tipo puede recibir el valor de otro tipo.

1. La variable de menor capacidad se asigna a otra de mayor capacidad.

   ```java
   double d;
   int i = 8;
   d = i;
   ```

   El proceso es automático y no explícito. Este proceso es llamado **Conversión**.

2. La variable de mayor capacidad se asigna a otra de menor capacidad.

   ```java
   double d = 8;
   int i;
   i = (int)d;
   ```

   Se debe especificar explícitamente el **operador de conversión de tipos**. A este proceso se lo llama **Conversión de Tipos**.

   Si no se especifica el operador de conversión, el compilador arrojara un error.

_Ejemplo:_

```java
class Prueba{
    public static main(String[] args){
        byte x;
        int a = 270;
        double b = 128.128;
        System.out.println("int convertido a byte");
        x = (byte)a;
        System.out.println("a y x " + a + " " + x);
        System.out.println("double convertido a int");
        a = (int)b;
        System.out.println("b y a " + b + " " + a);
        System.out.println("\ndouble convertido a byte");
        x = (byte)b;
        System.out.println("b y x " + b + " " + x);
    }
}
```

_Salida:_

```
int convertido a byte
a y x 270 14
double convertido a int
b y a 128.128 128

double convertido a byte
b y x 128.128 -128
```

## Estructuras Condicionales

Es una porción de código la cual indica al algoritmo que acción ejecutar, dependiendo de una condición dada.

Consta de tres partes:

- **Condición**: se especifica la expresión que se evaluara, se usan operadores de comaparación entre vairables o valores. Pueden ser verdaders o falsas (`true` o `false`).
  - **Operadores de comparación**: `<`,`>`,`==`, `!=`, `<=`,`>=`.
- **Bloque verdadero**: es el código que se ejecuta si la condición fue `true`.
- **Bloque falso**: es el código que se ejecuta si la condición fue `false`.

> Los bloques de código se escriben entre corchetes `{}`.

### Estructura `if`

Se escribe `if (condición)`. Evalúa la condición entre paréntesis devolviendo un valor booleano. Si es `true` ejecutara el bloque de código, si es `false` lo omitirá y seguirá la ejecución.

```java
int edad = 17;
if (edad < 18){ // condicion
    // codigo a ejecutar
    System.out.println("Eres Menor de edad");
}
```

### Estructura `else if`

Comprueba una condición si el primer `if` no fue `true`. Se escribe `else if (condicion)`. Si es `true` ejecutara el bloque de código, si es `false` lo omitirá y seguirá la ejecución.

```java
String clima = "lluvioso";
if (clima == "soleado"){ // primera condicion
    // codigo a ejecutar
    System.out.println("Salir a pasear");
}
else if (clima  == "lluvioso"){ // segunda condicion
    // codigo a ejecutar
    System.out.println("Quedarse en casa");
}
else if (clima  == "nuboso"){ // tercera condicion
    // codigo a ejecutar
    System.out.println("Salir con precaucion");
}
```

A diferencia del `if` que se declara al inicio, `else if` puede estar declarado más de una ves.

### Estructura `else`

Si ninguna condición a sido verdadera entonces se ejecutara el código. se escribe solamente `else` seguido de la implementación del código.

```java
if (clima == "soleado"){ // primera condicion
    // codigo a ejecutar
    System.out.println("Salir a pasear");
}
else if (clima  == "lluvioso"){ // segunda condicion
    // codigo a ejecutar
    System.out.println("Quedarse en casa");
}
else if (clima  == "nuboso"){ // tercera condicion
    // codigo a ejecutar
    System.out.println("Salir con precaucion");
}
else {
    // codigo a ejecutar por defecto
    System.out.println("Tomar una siesta");
}
```

_Ejemplo:_

```java
class Main {
    static void main(String[] args){
        verTiempo("soleado");
        verTiempo("lluvioso");
        verTiempo("nuboso");
        verTiempo("estrellado");
    }
    public static void verTiempo(String clima){
        if (clima == "soleado"){ // primera condicion
            // codigo a ejecutar
            System.out.println("El clima esta soleado");
            System.out.println("Salir a pasear\n");
        }
        else if (clima  == "lluvioso"){ // segunda condicion
            // codigo a ejecutar
            System.out.println("El clima esta lluvioso");
            System.out.println("Quedarse en casa\n");
        }
        else if (clima  == "nuboso"){ // tercera condicion
            // codigo a ejecutar
            System.out.println("El clima esta nuboso");
            System.out.println("Salir con precaucion\n");
        }
        else {
            // codigo a ejecutar por defecto
            System.out.println("No hay registro");
            System.out.println("Tomar una siesta\n");
        }
    }
}
```

_Salida:_

```
El clima esta soleado
Salir a pasear

El clima esta lluvioso
Quedarse en casa

El clima esta nuboso
Salir con precaucion

No hay registro
Tomar una siesta
```

> Las variables de tipo `String` pueden usar el método `.equals()` para compararse.

### Estructura `switch`

Esta versión hace el código mas limpio y legible que el `if`, `else if` y `else`.

Evalúa una **expresión** o variable contra varios valores posibles, son expresados como `cases`, y ejecuta un bloque de código, el cual es finalizado por la palabra clave `break`.

```mermaid
sequenceDiagram
    sdasd
```

_Ejemplo:_

```java
class Main{
    static void main(String[] args){
        int diaSemana = 12;
        switch (dia){
            case 1:
                System.out.printpl("Es lunes");
                break;
            case 2:
                System.out.printpl("Es martes");
                break;
            case 3:
                System.out.printpl("Es miercoles");
                break;
            case 4:
                System.out.printpl("Es jueves");
                break;
            case 5:
                System.out.printpl("Es viernes");
                break;
            case 6:
                System.out.printpl("Es sabado");
                break;
            case 7:
                System.out.printpl("Es domingo");
                break;
            default:
                System.out.printpl("¿Que dia es hoy?");
                break;
        }
    }
}
```

_Salida:_

```
¿Que dia es hoy?
```

> Se prueba cada caso hasta que se devuelve `true`.
>
> En el caso de que ninguno devuelva `true`, se ejecutara el bloque `default`.

## Funciones

## Fecha y Tiempo

## Bucles

## Manejo de Excepciones

## Estructuras de Datos

## POO, Interfaces y Clases

## Paquetes

## Archivos y APIs
