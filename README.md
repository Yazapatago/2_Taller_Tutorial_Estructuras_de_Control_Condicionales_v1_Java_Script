---

# Sección 8: Estructuras de Control Condicionales - Tomando Decisiones

Hasta ahora, nuestros programas se ejecutan línea por línea, de arriba hacia abajo. Pero, ¿qué pasa si queremos que el programa haga una cosa en una situación y otra cosa diferente en otra situación? **¡Para eso están las estructuras condicionales!** Nos permiten controlar el flujo de ejecución del programa basándose en si ciertas condiciones son verdaderas o falsas.

Imagina que estás en un camino y llegas a una bifurcación. Dependiendo de la señal (la condición), tomarás el camino de la izquierda o el de la derecha.

---

## 8.1 Sentencia `if`: Si la Condición se Cumple...

La sentencia `if` es la estructura condicional más básica. Permite ejecutar un bloque de código **solo si una condición específica es `true`**.

### Sintaxis en JavaScript:
```javascript
if (condicion_a_evaluar) {
  // Bloque de código que se ejecuta SI la condición es true
  console.log("La condición es verdadera.");
  // ... más instrucciones ...
}
// El código que no está dentro del bloque se ejecuta siempre
console.log("Esto se ejecuta siempre, después del if.");
```

- `condicion_a_evaluar`: Es una expresión que se evalúa como `true` o `false`.  
  Ejemplos: `edad > 18`, `es_valido`, `temperatura > 0 && temperatura < 100`
- Se usan **llaves `{}`** para definir el bloque.
- **Importante**: Usa `===` para comparación estricta (valor y tipo).

### Ejemplos Prácticos:

```javascript
// Ejemplo 1: Verificar si un número es positivo
let numero = -15;
if (numero > 0) {
  console.log(`El número ${numero} es positivo.`);
}
console.log("Fin del ejemplo 1.");

// Con número negativo
numero = -5;
if (numero < 0) {
  console.log(`El número ${numero} es positivo.`); // NO se ejecuta
}
console.log("Fin del ejemplo 1 con número negativo.");

// Ejemplo 2: Permitir acceso si es mayor de edad
const edadCliente = parseInt(prompt("Bienvenido/a, por favor ingresa tu edad: "));

if (edadCliente >= 18) {
  console.log("Acceso permitido. ¡Disfruta!");
  console.log("Puedes comprar bebidas alcohólicas.");
}

console.log("Gracias por visitarnos.");
```

---

## ¡A Tu Teclado!

### Ejercicio 8.1.1:
Pide al usuario su calificación en un examen (un número). Si la calificación es mayor o igual a 3.0, imprime:  
**"¡Felicidades, has aprobado!"**

```javascript
// Escribe tu código aquí
const calificacion = parseFloat(prompt("Ingresa tu calificación (ej: 4.5): "));
if (calificacion >= 3.0) {
  console.log("¡Felicidades, has aprobado!");
} else {
  console.log("No has aprobado");
}
```

---

### Ejercicio 8.1.2:
Crea una variable `temperaturaCelsius` con un valor (ej: `25`).  
Si la temperatura es mayor a `30`, imprime **"¡Hace mucho calor!"**

```javascript
// Escribe tu código aquí
const temperaturaCelsius = 35;
if (temperaturaCelsius > 30) {
  console.log("¡Hace mucho calor!");
}
```

---

## 8.2 Sentencia `if-else`: Si se Cumple... Si No...

A menudo queremos hacer algo diferente si la condición es falsa. Para eso usamos `if-else`.

### Sintaxis:
```javascript
if (condicion) {
  // Se ejecuta si es true
} else {
  // Se ejecuta si es false
}
```

> **Solo uno de los bloques se ejecuta, nunca ambos.**

### Ejemplos Prácticos:

```javascript
// Ejemplo 1: Número par o impar
const numeroEvaluar = parseInt(prompt("Ingresa un número entero: "));

if (numeroEvaluar % 2 === 0) {
  console.log(`El número ${numeroEvaluar} es PAR.`);
} else {
  console.log(`El número ${numeroEvaluar} es IMPAR.`);
}

// Ejemplo 2: Acceso a un evento
const edadPersona = 17;
let mensajeAcceso;

if (edadPersona >= 18) {
  mensajeAcceso = "Bienvenido/a al evento.";
} else {
  mensajeAcceso = "Lo sentimos, debes ser mayor de edad para ingresar.";
}
console.log(mensajeAcceso);
```

---

## ¡A Tu Teclado!

### Ejercicio 8.2.1:
Pide al usuario una contraseña.  
Si es igual a `"SENA2024"`, imprime **"Acceso concedido"**.  
Sino, imprime **"Contraseña incorrecta"**

```javascript
const contrasena = prompt("Por favor ingrese su contraseña");
const contrasenaCorrecta = "SENA2024";

if (contrasena === contrasenaCorrecta) {
  console.log("La contraseña ingresada es correcta!!");
} else {
  console.log("La contraseña ingresada NO es correcta");
}
```

---

### Ejercicio 8.2.2:
Pide al usuario la temperatura actual en °C.  
- Si es < 10 → **"Hace frío, ¡abrígate!"**  
- Sino → **"La temperatura es agradable o cálida."**

```javascript
const temperaturaActual = parseFloat(prompt("Ingrese la temperatura actual en °C: "));

if (temperaturaActual < 10) {
  console.log("Hace frío, ¡abrígate!");
} else {
  console.log("La temperatura es agradable o cálida.");
}
```

---

## 8.3 Sentencia `if-else if-else`: Múltiples Caminos

Cuando hay **más de dos posibilidades**, usamos `else if`.

### Sintaxis:
```javascript
if (condicion1) {
  // ...
} else if (condicion2) {
  // ...
} else if (condicion3) {
  // ...
} else {
  // Ninguna condición anterior fue verdadera
}
```

> Se evalúan en orden. **La primera que sea `true` gana**.

### Ejemplos Prácticos:

```javascript
// Ejemplo 1: Clasificar un número
let numero = 0;
// numero = parseInt(prompt("Ingresa un número: "));

if (numero > 0) {
  console.log(`El número ${numero} es POSITIVO.`);
} else if (numero < 0) {
  console.log(`El número ${numero} es NEGATIVO.`);
} else {
  console.log(`El número es CERO.`);
}

// Ejemplo 2: Menú de cafetería
console.log("--- Bienvenido a la Cafetería SENA ---");
console.log("1. Tinto");
console.log("2. Café con Leche");
console.log("3. Aromática");

const opcionTexto = prompt("Selecciona una opción (1, 2 o 3): ");
const opcion = parseInt(opcionTexto);
let precio = 0;

if (opcion === 1) {
  console.log("Has seleccionado Tinto. ¡Excelente elección!");
  precio = 1000;
} else if (opcion === 2) {
  console.log("Has seleccionado Café con Leche. ¡Muy rico!");
  precio = 1500;
} else if (opcion === 3) {
  console.log("Has seleccionado Aromática. ¡Perfecto para relajarse!");
  precio = 800;
} else {
  console.log("Opción no válida. Por favor, selecciona 1, 2 o 3.");
}

if (precio > 0) {
  console.log(`El precio es: $${precio}`);
}
```

---

## ¡A Tu Teclado!

### Ejercicio 8.3.1:
Pide una calificación (0.0 a 5.0). Clasifícala así:
- < 3.0 → **"Reprobado"**
- 3.0 - 3.9 → **"Aceptable"**
- 4.0 - 4.5 → **"Sobresaliente"**
- > 4.5 → **"Excelente"**
- Fuera de rango → **"Nota inválida"**

```javascript
const calificacion = parseFloat(prompt("Por favor ingrese su nota (0.0 - 5.0): "));
console.log(`La nota ingresada es ${calificacion}`);

if (calificacion < 3.0) {
  console.log("Estado Estudiante: Reprobado");
} else if (calificacion >= 3.0 && calificacion <= 3.9) {
  console.log("Estado Estudiante: Aceptable");
} else if (calificacion >= 4.0 && calificacion <= 4.5) {
  console.log("Estado Estudiante: Sobresaliente");
} else if (calificacion > 4.5 && calificacion <= 5.0) {
  console.log("Estado Estudiante: Excelente");
} else {
  console.log("La nota ingresada no se encuentra en el rango de 0.0 - 5.0");
}
```

---

### Ejercicio 8.3.2:
Pide un día de la semana (en minúsculas).  
- `"sabado"` o `"domingo"` → **"¡Es fin de semana!"**  
- `"lunes"` → **"¡Ánimo, comienza la semana!"**  
- Otros días → **"Día de semana laboral/estudio."**  
- Inválido → **"Día no válido"**

```javascript
const dia = prompt("Por favor ingrese un día de la semana: ").toLowerCase();
console.log(`El día ingresado es: ${dia}`);

if (dia === "sabado" || dia === "domingo") {
  console.log("¡Es fin de semana!");
} else if (dia === "lunes") {
  console.log("¡Ánimo, comienza la semana!");
} else if (["martes", "miercoles", "jueves", "viernes"].includes(dia)) {
  console.log("Día de semana laboral/estudio...");
} else {
  console.log("EL VALOR INGRESADO NO ES VÁLIDO!!!!");
}
```

---

## 8.4 Lógica con `&&`, `||` y `!` en Condiciones

Ya vimos los operadores lógicos ```and```, ```or``` y ```not```. Son extremadamente útiles para construir condiciones más complejas y específicas dentro de nuestras estructuras ```if```, ```else if``` y ```else```.

- ```and (&&)```: Útil cuando múltiples sub-condiciones deben ser verdaderas simultáneamente.
- ```or (||)```: Útil cuando al menos una de varias sub-condiciones necesita ser verdadera.
- ```not (!)```: Útil para invertir una condición.

| Operador | Significado       | Ejemplo                               |
|----------|-------------------|----------------------------------------|
| `&&`     | Y (AND)           | `edad >= 18 && tieneLicencia`          |
| `\|\|`   | O (OR)            | `esFestivo \|\| dia === "domingo"`     |
| `!`      | NO (NOT)          | `!estaRegistrado`                      |

### Ejemplos Prácticos:

```javascript
// Ejemplo 1: Acceso a área restringida
const edad = 25;
const esEmpleado = true;
const tienePaseEspecial = false;

if ((esEmpleado && edad > 21) || tienePaseEspecial) {
  console.log("Acceso permitido al área restringida.");
} else {
  console.log("Acceso DENEGADO al área restringida.");
}

// Ejemplo 2: Beca
const promedioNotas = 4.2;
const ingresosFamiliares = 1500000;

if (promedioNotas > 4.0 && ingresosFamiliares < 2000000) {
  console.log("¡Felicidades! Cumples los requisitos para la beca.");
} else {
  console.log("No cumples todos los requisitos para la beca.");
}

// Ejemplo 3: Usando !
const estaLloviendo = false;
if (!estaLloviendo) {
  console.log("¡Perfecto! Podemos salir a jugar.");
} else {
  console.log("Mejor nos quedamos en casa.");
}
```

---

## ¡A Tu Teclado!

### Ejercicio 8.4.1:
Pide edad y si tiene carnet de biblioteca (`"si"` o `"no"`).  
Para pedir un libro especial: **edad ≥ 15 && carnet === "si"**

```javascript
const edad = parseInt(prompt("Ingrese su edad: "));
const carnet = prompt("¿Tienes carnet de la biblioteca? (si/no): ").toLowerCase();

if (edad >= 15 && carnet === "si") {
  console.log("Puedes solicitar el libro especial!!");
} else {
  console.log("No cumples los requisitos para el libro especial.");
}
```

---

## 8.5 Condicionales Anidados: Decisiones Dentro de Decisiones

Un `if` dentro de otro `if`.

```javascript
if (condicionExterior) {
  if (condicionInterior) {
    // ...
  } else {
    // ...
  }
} else {
  // ...
}
```

### Ejemplos Prácticos:

```javascript
// Ejemplo 1: Login con rol
const usuarioLogin = "aprendizSENA";
const contrasenaLogin = "python123";

const usuarioIngresado = prompt("Usuario: ");
const contrasenaIngresada = prompt("Contraseña: ");

if (usuarioIngresado === usuarioLogin) {
  console.log("Usuario correcto.");
  if (contrasenaIngresada === contrasenaLogin) {
    console.log("¡Bienvenido/a de nuevo, aprendizSENA!");
    const esAdmin = false;
    if (esAdmin) {
      console.log("Tienes permisos de administrador.");
    } else {
      console.log("Tienes permisos de usuario estándar.");
    }
  } else {
    console.log("Contraseña incorrecta.");
  }
} else {
  console.log("Usuario no encontrado.");
}
```

---

## ¡A Tu Teclado!

### Ejercicio 8.5.1:
Pide un número entero.  
- Si es positivo → verifica si es **par** o **impar**  
- Si no es positivo → "El número no es positivo"

```javascript
const numero = parseInt(prompt("Ingrese un número entero: "));

if (numero > 0) {
  if (numero % 2 === 0) {
    console.log(`El número ${numero} es POSITIVO y es PAR`);
  } else {
    console.log(`El número ${numero} es POSITIVO y es IMPAR`);
  }
} else {
  console.log(`El número ${numero} no es positivo`);
}
```

---

## ¡Desafíate!

### Reto 8.1: Juego de Adivinanza

```javascript
console.log("¡Bienvenido al juego de adivinanza!\n");
const numeroSecreto = 7;
const numeroUsuario = parseInt(prompt("Adivina el número (1-10): "));

if (numeroUsuario === numeroSecreto) {
  console.log("¡Felicidades! Adivinaste.");
} else if (numeroUsuario < numeroSecreto) {
  console.log("Muy bajo, intenta de nuevo.");
} else {
  console.log("Muy alto, intenta de nuevo.");
}
```

---

### Reto 8.2: Mini Calculadora

```javascript
console.log("...MINI CALCULADORA...");
console.log("1. Sumar\n2. Restar\n3. Multiplicar\n4. Dividir");

const opcion = parseInt(prompt("Selecciona una opción (1-4): "));

if (opcion >= 1 && opcion <= 4) {
  const num1 = parseFloat(prompt("Ingresa el 1er número: "));
  const num2 = parseFloat(prompt("Ingresa el 2do número: "));

  if (opcion === 1) {
    console.log(`${num1} + ${num2} = ${num1 + num2}`);
  } else if (opcion === 2) {
    console.log(`${num1} - ${num2} = ${num1 - num2}`);
  } else if (opcion === 3) {
    console.log(`${num1} * ${num2} = ${num1 * num2}`);
  } else if (opcion === 4) {
    if (num2 === 0) {
      console.log("Error: No se puede dividir por cero.");
    } else {
      console.log(`${num1} / ${num2} = ${num1 / num2}`);
    }
  }
} else {
  console.log("Opción no válida.");
}
```

---
