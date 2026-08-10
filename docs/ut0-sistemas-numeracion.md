<p style="font-size: 1.3em;"><strong>CFGS Administración de Sistemas Informáticos y en Red (1º curso)</strong></p>

Material elaborado para el módulo **0371. Fonaments de Maquinari / Fundamentos de Hardware**

# Sistemas de numeración y cambio de base

## Programación de Aula

!!! info "Nota"
    Esta es una unidad de **nivelación/repaso**, previa al Tema 1, que no corresponde a un RA específico del Real Decreto de título. Se recomienda impartirla al inicio del curso como base matemática necesaria para comprender la representación binaria de la información (RA1) y sirve de apoyo transversal a todo el módulo.

### Planificación Temporal (3 sesiones / 6 horas)

| Sesión | Contenido |
| ------ | --------- |
| 1 | Sistemas de numeración: concepto de base. El sistema binario |
| 2 | Los sistemas octal y hexadecimal. Conversiones directas entre bases |
| 3 | Aritmética binaria: suma y resta. Repaso y ejercicios |

## 1. Sistemas de numeración: el concepto de base

Un **sistema de numeración** es un conjunto de símbolos y reglas que permiten representar cantidades. La característica que define un sistema de numeración es su **base**: el número de símbolos distintos que utiliza.

El sistema que usamos habitualmente es el **decimal (base 10)**, con diez símbolos (0-9). Cada posición dentro de un número representa una potencia de la base, que aumenta de derecha a izquierda:

$$
2\,451 = 2 \times 10^3 + 4 \times 10^2 + 5 \times 10^1 + 1 \times 10^0
$$

Un ordenador, al trabajar internamente solo con dos estados (encendido/apagado, 1/0), utiliza de forma nativa el **sistema binario (base 2)**. Sin embargo, escribir números binarios largos resulta poco práctico para las personas, por lo que en informática también se usan el **sistema octal (base 8)** y, sobre todo, el **sistema hexadecimal (base 16)**, que permiten representar la misma información de forma más compacta y legible.

| Sistema | Base | Símbolos utilizados |
| -------- | ---- | --------------------- |
| Binario | 2 | 0, 1 |
| Octal | 8 | 0, 1, 2, 3, 4, 5, 6, 7 |
| Decimal | 10 | 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 |
| Hexadecimal | 16 | 0-9, A, B, C, D, E, F (donde A=10, B=11, C=12, D=13, E=14, F=15) |

## 2. El sistema binario

Cada dígito binario se llama **bit** (*binary digit*), y solo puede valer 0 o 1. En un número binario, cada posición representa una potencia de 2:

$$
1011_2 = 1 \times 2^3 + 0 \times 2^2 + 1 \times 2^1 + 1 \times 2^0 = 8 + 0 + 2 + 1 = 11_{10}
$$

### 2.1 Conversión de binario a decimal

Se suma el valor de la potencia de 2 correspondiente a cada posición donde haya un 1:

!!! example "Ejemplo"
    $$110101_2 = 1{\cdot}2^5 + 1{\cdot}2^4 + 0{\cdot}2^3 + 1{\cdot}2^2 + 0{\cdot}2^1 + 1{\cdot}2^0 = 32+16+0+4+0+1 = 53_{10}$$

### 2.2 Conversión de decimal a binario

El método más habitual es el de las **divisiones sucesivas entre 2**: se divide el número entre 2 repetidamente, anotando el resto (0 o 1) de cada división, hasta llegar a un cociente 0. El número binario resultante se lee de abajo hacia arriba (del último resto al primero).

!!! example "Ejemplo: convertir 53 a binario"
    | División | Cociente | Resto |
    | --------- | -------- | ----- |
    | 53 ÷ 2 | 26 | 1 |
    | 26 ÷ 2 | 13 | 0 |
    | 13 ÷ 2 | 6 | 1 |
    | 6 ÷ 2 | 3 | 0 |
    | 3 ÷ 2 | 1 | 1 |
    | 1 ÷ 2 | 0 | 1 |

    Leyendo los restos de abajo hacia arriba: **53₁₀ = 110101₂**

## 3. El sistema octal

El sistema octal (base 8) sigue el mismo principio que el binario y el decimal, pero con potencias de 8.

### 3.1 De octal a decimal

!!! example "Ejemplo"
    $$247_8 = 2{\cdot}8^2 + 4{\cdot}8^1 + 7{\cdot}8^0 = 128 + 32 + 7 = 167_{10}$$

### 3.2 De decimal a octal

Igual que con el binario, pero dividiendo sucesivamente entre 8 en lugar de entre 2.

## 4. El sistema hexadecimal

El sistema hexadecimal (base 16) es el más utilizado en informática para representar valores binarios de forma compacta (direcciones de memoria, colores en diseño web, códigos de error...).

### 4.1 De hexadecimal a decimal

!!! example "Ejemplo"
    $$2F_{16} = 2{\cdot}16^1 + F{\cdot}16^0 = 2{\cdot}16 + 15{\cdot}1 = 32+15 = 47_{10}$$

### 4.2 De decimal a hexadecimal

Igual que en los casos anteriores, dividiendo sucesivamente entre 16. Cuando el resto de una división sea mayor que 9, se sustituye por su letra equivalente (10=A, 11=B... 15=F).

## 5. Conversiones directas entre binario, octal y hexadecimal

Convertir entre binario y octal, o entre binario y hexadecimal, **no requiere pasar por el decimal**, ya que tanto el 8 como el 16 son potencias exactas de 2 (8=2³, 16=2⁴). Esto permite hacer la conversión agrupando bits directamente.

### 5.1 De binario a octal

Se agrupan los bits del número binario **de 3 en 3**, empezando por la derecha (rellenando con ceros a la izquierda si hace falta), y se convierte cada grupo a su dígito octal equivalente.

!!! example "Ejemplo: convertir 110101₂ a octal"
    Se agrupa de 3 en 3: `110` `101`
    - `110` = 6
    - `101` = 5

    **110101₂ = 65₈**

### 5.2 De binario a hexadecimal

Se agrupan los bits **de 4 en 4**, empezando por la derecha, y se convierte cada grupo a su dígito hexadecimal equivalente.

!!! example "Ejemplo: convertir 11010101₂ a hexadecimal"
    Se agrupa de 4 en 4: `1101` `0101`
    - `1101` = 13 = D
    - `0101` = 5

    **11010101₂ = D5₁₆**

### 5.3 Tabla de referencia rápida

| Decimal | Binario | Octal | Hexadecimal |
| -------- | -------- | ----- | ------------- |
| 0 | 0000 | 0 | 0 |
| 1 | 0001 | 1 | 1 |
| 2 | 0010 | 2 | 2 |
| 3 | 0011 | 3 | 3 |
| 4 | 0100 | 4 | 4 |
| 5 | 0101 | 5 | 5 |
| 6 | 0110 | 6 | 6 |
| 7 | 0111 | 7 | 7 |
| 8 | 1000 | 10 | 8 |
| 9 | 1001 | 11 | 9 |
| 10 | 1010 | 12 | A |
| 11 | 1011 | 13 | B |
| 12 | 1100 | 14 | C |
| 13 | 1101 | 15 | D |
| 14 | 1110 | 16 | E |
| 15 | 1111 | 17 | F |

!!! info "Recuerda"
    Es muy habitual identificar la base de un número mediante un subíndice (1010₂) o un prefijo (0x2F para hexadecimal, 0b1010 para binario en programación), ya que un mismo número de dígitos como "10" significa algo completamente distinto según la base en la que se interprete.

## 6. Aritmética binaria

### 6.1 Suma binaria

La suma en binario sigue las mismas reglas que en decimal, pero con solo dos símbolos. Las combinaciones posibles son:

| Operación | Resultado |
| ---------- | --------- |
| 0 + 0 | 0 |
| 0 + 1 | 1 |
| 1 + 0 | 1 |
| 1 + 1 | 0, y **me llevo 1** (acarreo) |
| 1 + 1 + 1 (con acarreo) | 1, y me llevo 1 |

!!! example "Ejemplo: 1011₂ + 0110₂"
    ```
      1011
    +  0110
    ------
      10001
    ```
    Comprobación: 1011₂ = 11₁₀, 0110₂ = 6₁₀, 11+6 = 17₁₀ = 10001₂ ✓

### 6.2 Resta binaria

Sigue una lógica similar, tomando "prestado" de la posición siguiente cuando haga falta restar 1 a 0 (igual que en decimal, cuando restamos y el minuendo es menor que el sustraendo).

!!! note "En la práctica"
    Los ordenadores, internamente, no restan de esta forma: usan una técnica llamada **complemento a 2**, que permite convertir cualquier resta en una suma. Este tema, más avanzado, se suele tratar en profundidad en módulos posteriores de programación o arquitectura de computadores.

## Ejercicios prácticos

!!! task "Tarea"
    **Ejercicio 1**. Convierte los siguientes números binarios a decimal: 1101₂, 100110₂, 11111₂.

    **Ejercicio 2**. Convierte los siguientes números decimales a binario: 25, 100, 17.

    **Ejercicio 3**. Convierte 345₈ a decimal, y 200₁₀ a octal.

    **Ejercicio 4**. Convierte 1A3₁₆ a decimal, y 500₁₀ a hexadecimal.

    **Ejercicio 5**. Convierte directamente (sin pasar por decimal) el número binario 111010110₂ a octal y a hexadecimal.

    **Ejercicio 6**. Realiza las siguientes sumas en binario, y comprueba el resultado convirtiendo los números a decimal: 1101₂ + 1011₂, y 10010₂ + 00111₂.

    **Ejercicio 7**. Un color en diseño web se representa en hexadecimal como #A3C1E8. Explica cuántos bits ocupa cada componente de color (rojo, verde, azul) y por qué se usa precisamente el sistema hexadecimal para esta representación.

    **Ejercicio 8**. Completa una tabla como la del punto 5.3 para los números del 16 al 20, en las cuatro bases (decimal, binario, octal, hexadecimal).
