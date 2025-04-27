# Arreglos

## Arreglos unidimensionales
### C3D
```c
x = y[i]
x[i] = y
```

![alt text](image.png)

### Acceso
#### Pasos
1. Se obtiene la dirección del arreglo.
2. Se obtiene la dirección del elemento.
3. Se obtiene el valor del elemento.

```c
V: ARRAY [7..10] OF INTEGER

! Alto nivel
x = V[y] 

! Bajo nivel
t1 = y - 7
x = V[t1]
```

```c
x = V[y] + V[z]

t1 = y - 7
t2 = V[t1]
t3 = z - 7
t4 = V[t3]
t5 = t2 + t4
x = t5
```

```c
x = V[y+z] + V[V[a]]
t1 = y + z
t2 = t1 - 7
t3 = V[t2]

t4 = a - 7
t5 = V[t4]
t6 = t5 - 7
t7 = V[t6]

t8 = t3 + t7
x = t8
```
![alt text](image-1.png)

### Asignacion
#### Pasos
1. Se obtiene la dirección donde se va a asignar.
2. Se obtiene el valor que se va a asignar.
3. Se hace la asignación.
```c
V: ARRAY [11..15] OF INTEGER

V[x] = x + y

t1 = x - 11
t2 = y + x
V[t1] = t2
```

```c
V[V[x+y]] = 1 

t1 = x + y
t2 = t1 - 11
t3 = V[t2]

t4 = t3 - 11
V[t4] = 1
```

```c
V[ V[x] + V[y] ] = V[V[x*y]]

t1 = x - 11
t2 = V[t1]
t3 = y - 11
t4 = V[t3]
t5 = t2 + t4
t6 = t5 - 11
!V[t6] = V[V[x*y]]

t7 = x * y
t8 = t7 - 11
t9 = V[t8]
t10 = t9 - 11
t11 = V[t10]
V[t6] = t11
```
![alt text](image-2.png)

## Arreglos Bidimensionales
### C3D
```c
x = y[i, j]
x[i, j] = y
```
![alt text](image-3.png)

### Acceso

M: Array [1..3, 4..6] of Integer
x = M[p, q]
```c
t1 = p - 1
t2 = t1 * 3
t3 = t2 + q
t4 = t3 - 4
t5 = M[t4]
x = t5
```

x = M[p, p + q] 
#### Propuesta1 (No utilizada)
```c
t1 = p - 1 ! Primera Dimension
t2 = t1 * 3 !Primera parte - Segunda Dimension

t3 = p + q ! Resolviendo previo a Segunda Dimension

t4 = t2 + t3
t5 = t4 - 4 ! Segunda parte - Segunda Dimension
t6 = M[t5]
x = t6
```
![alt text](image-4.png)

#### Propuesta2 (Utilizada)
```c
x = M[p, p + q] * M[x + y, y]

t1 = p - 1 ! Primera Dimension

t2 p + q ! Resolviendo previo a Segunda Dimension

t3 = t1 * 3
t4 = t3 + t2
t5 = t4 - 4 ! Segunda Dimension

t6 = M[t5]

t7 = x + y ! Primera Dimension
t8 = t7 - 1 ! Primera Dimension
t9 = t8 * 3 ! Primera parte - Segunda Dimension
t10 = t9 + y ! Segunda parte - Segunda Dimension
t11 = t10 - 4 ! Segunda Dimension
t12 = M[t11]

t13 = t6 * t12
x = t13
```
![alt text](image-5.png)

Ejemplo2:  

![alt text](image-6.png)

## Arreglo Multidimensional
### C3D
```c
x = y[i, j, k]
x[i, j, k] = y
```
![alt text](image-7.png)

![alt text](image-8.png)

### Acceso y Asignación

![alt text](image-9.png)


#### Solucin implementada en una gramática

![alt text](image-10.png)


##### Teoria sobre tabla de simbolos y C3D

![alt text](image-11.png)

![alt text](image-12.png)

