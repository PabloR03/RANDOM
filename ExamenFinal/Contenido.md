# Memoria Dinamica

Se almacena en la memoria de forma dinámica, es decir, se reserva espacio en la memoria para almacenar datos en tiempo de ejecución. Esto permite crear estructuras de datos que pueden crecer o decrecer según sea necesario. 

## Heap

El puntero que vamos a usar como referencia sera la letra H.

### Ejemplo Declaracion

```cpp
Struct rectangulo{
    int base;
    int altura;
};

void main(){
    rectangulo r1;
    rectangulo r2;
}
```

r1 y r2 son variables del tipo locales, por lo que se almacenan en la pila (Stack).

![alt text](image.png)

### Ejemplo Instanciacion

```cpp
Struct rectangulo{
    int base;
    int altura;
};

void main(){
    rectangulo r1 = new rectangulo;
    rectangulo r2 = new rectangulo;
}
```
Al instanciar r1 y r2, se almacenan en el heap. En este caso, la memoria se reserva en tiempo de ejecución. En el heap r1 y r2 tiene 2 espacios uno para base y otro para altura.

En este punto el heap va a almacenar 2 direcciones de memoria que apuntan al Heap. 

![alt text](image-1.png)

### Ejemplo Grafico

![alt text](image-2.png)

![alt text](image-3.png)

```
Struct rectangulo{
    int base;
    int altura;
};

void  arear( int base, int altura){
    rectangulo r1 = new rectangulo;
    r1.base = base;
    r1.altura = altura;
    Printf("El area es: ", r1.base * r1.altura);
}

void main(){
    int x, y;
    x = 5;
    y = 2;
    arear(x, y);
}
```

C3D

```c3d
proc arear(){
    t1 = P + 2
    stack[t1] = H
    H = H + 2 // rectangulo r = new rectangulo() -> Guardar en R la direccion del Heap

    t2 = P + 2
    t3 = stack[t2] // t3 = 0 posicion del rectangulo
    t4 = t3 + 0 // base "Puntero del Heap"
    t5 = P + 0 // Variable x
    t6 = stack[t5] // t6 = 5 base
    heap[t4] = t6 // Guardar el valor de x en la base del rectangulo

    t7 = P + 2
    t8 = stack[t7] // t8 = 0 posicion del rectangulo
    t9 = t8 + 1 // altura "Puntero del Heap"
    t10 = P + 1 // Variable y
    t11 = stack[t10] // t11 = 2 altura
    heap[t9] = t11 // Guardar el valor de y en la altura del rectangulo

    t12 = P + 2 
    t13 = stack[t12] // t13 = 0 posicion del rectangulo
    t14 = t13 + 0 // base "Puntero del Heap"
    t15 = heap[t14] // t15 = 5 base

    t16 = P + 2
    t17 = stack[t16] // t17 = 0 posicion del rectangulo
    t18 = t17 + 1 // altura "Puntero del Heap"
    t19 = heap[t18] // t19 = 2 altura

    t20 = t15 * t19 // Area

    Write(t20) // Imprimir el area
}

proc main(){
    t21 = P + 0 // Variable x
    stack[t21] = 5 // Guardar el valor de x en la pila

    t22 = P + 1 // Variable y
    stack[t22] = 2 // Guardar el valor de y en la pila

    t23 = P + 0 // Variable x
    t24 = stack[t23] // t24 = 5 base
    t25 = P + 2 // Cambio de entorno
    t26 = t25 + 0 // t26 Como nuevo puntero de la pila apunta a la posicion 0 (base)
    stack[t26] = t24 // Guardar el valor de x en la pila

    t27 = P + 1 // Variable y
    t28 = stack[t27] // t28 = 2 altura
    t29 = P + 2 // Cambio de entorno
    t30 = t29 + 1 // t30 Como nuevo puntero de la pila apunta a la posicion 1 (altura)
    stack[t30] = t28 // Guardar el valor de y en la pila

    P = P + 2 // Cambiar el puntero de la pila a la posicion 2 (arear)

    arear() // Llamar a la funcion arear

    P = P - 2 // Cambiar el puntero de la pila a la posicion 0 (main)
}


```

![alt text](image-4.png)

# Comprobacion de tipos 

Existen dos tipos de comprobacion de tipos:
1. **Estatica**: Se realiza en tiempo de compilacion. Se verifica que los tipos de datos sean compatibles entre si.
2. **Dinamica**: Se realiza en tiempo de ejecucion. Se verifica que los tipos de datos sean compatibles entre si en tiempo de ejecucion.

## Comprobacion de tipos estaticos

### Comprobacionde tipos
- Flujo de control (break, continue, return)
- Comprobacion de unicidad (Tabla de simbolos)

### La base de comprobacion estatica
- Tabla de simbolos
- Traduccion Dirigida por la Sintaxis

## Estrategia de imlementacion

Traduccion dirigida por la sintaxis
- Comprobacion Estatica // Verificacion de tipos adecuados para entoces si seguir a la siguiente fase
- Generacion de C3D

## Sistema de tipos
- Conjunto de reglas que define como un lenguaje de programacion organiza y clasifica los valores y las expresiones en los tipos de datos.
- Como pueden manipular estos tipos y como interactuan entre si.
- Tipos de datos primitivos: enteros, flotantes, booleanos, caracteres, cadenas de texto, error_tipo, vacio.

## Expresion de tipos
- Cada parte del programa tiene un tipo de dato asociado.
    - Expresiones:
        - Expresion aritmetica
        - Expresion relacional
        - Expresion booleanas  
        ![alt text](image-5.png)
        ![alt text](image-7.png)

    - Proposiciones
        - Asignaciones
        - Flujos de control
        ![alt text](image-6.png)
        ![alt text](image-8.png)






