# Laboratorio 3 - Análisis del Programa

### Estudiantes:
- Lester David Payes Méndez
- Mario David Tereta Sapalun

## Debate y Análisis del Programa

### Tareas Repetitivas o que pueden encapsularse en funciones

En el inicio del desarrollo del programa, discutimos con mi compañero sobre el uso de una función llamada `linea1()`, la cual podría 
usarse debido a que es una acción repetitiva en el programa. Usar esta función nos permite evitar la repetición del código cada vez 
que necesitamos leer un dato numérico utilizando el tipo de dato `double`. En aquellas funciones donde se recibe un dato entero, se 
convierte ese retorno de datos en `int`. Además, la función incluye la validación para asegurar que los datos sean correctos, es 
decir, numéricos. Si el usuario ingresa algo incorrecto, la función le pedirá que lo ingrese de nuevo, garantizando que solo se 
utilicen datos válidos.

### Variables Globales vs Locales

En el programa, las únicas variables utilizadas son las listas `estudiantes` y `calificaciones`, las cuales están declaradas dentro 
de la clase `Program`, pero fuera de cualquier función. Esto permite que sean accesibles desde cualquier función estática dentro de 
la clase, como el método `Main()`. Dado que estas variables son usadas en varias funciones estáticas, se consideran **globales** 
dentro de la clase.

Por otro lado, las funciones como `AddStudent()`, `ListStudent()`, y otras, manejan variables locales que solo existen dentro de 
esas funciones. Esto es clave para mantener el orden y la claridad en el código. Al tener las variables dentro de su ámbito 
local, se evita la modificación no controlada de variables globales, lo cual previene errores. Además, las funciones locales 
mejoran el control de los datos, hacen que el código sea más legible y fácil de mantener.

### Discusión sobre cuándo usar variables locales y globales

**Lester Payes:** Las variables globales se usan cuando varias funciones necesitan modificar o usar la misma variable sin necesidad 
de pasarlas como parámetros, mientras que las variables locales se usan cuando solo son necesarias dentro de la función en la que 
fueron declaradas.

**Mario Tereta:** Las variables globales son aquellas que se declaran fuera de la función principal, lo que les permite ser utilizadas 
en cualquier parte del programa. Las variables locales, por su parte, solo pueden ser modificadas dentro de la función donde fueron 
declaradas.

### Debate sobre la Modularización

**División del código en funciones**

Concordamos en que para mejorar la visibilidad y claridad del código, debíamos modularizarlo adecuadamente. Se crearon funciones específicas 
para manejar diferentes operaciones del programa, ya que el código original estaba desordenado al utilizar condicionales `if` en lugar de 
funciones bien definidas. Las funciones creadas para el menú fueron las siguientes:
- `AddStudent()`
- `ListStudent()`
- `PromCal()`
- `MaxCal()`

Estas funciones permiten que el código sea más organizado, evitando la redundancia y facilitando su mantenimiento. De igual manera, se implementó 
una función para agregar calificaciones a cada estudiante. Si más adelante se desea agregar una calificación para cada curso, esta función ya está 
implementada y puede ser modificada para realizar la nueva acción.

### Uso de `switch` en lugar del menú sugerido en el código original

En lugar de usar un menú con condicionales `if`, decidimos utilizar un `switch` para gestionar las diferentes opciones del programa. De esta 
manera, se llamó a las funciones previamente creadas y se gestionó la variable `opción` de una manera más eficiente. Esto mejora la organización 
del flujo de ejecución y facilita la adición de nuevas opciones en el futuro.

### Uso de `Console.Clear()` y `Console.ReadKey()`

Implementamos `Console.Clear()` en el menú principal para borrar los resultados de funciones previas seleccionadas por el usuario y mejorar la 
estética del programa. Esto ayuda a mantener la salida más limpia y organizada. Además, se utilizó `Console.ReadKey()` para que la salida no se 
borre inmediatamente después de ejecutar cada función, sino hasta que el usuario presione una tecla.

### Optimización de `WriteLine()` para mostrar el menú

En lugar de usar múltiples llamadas a `Console.WriteLine()` para mostrar el menú, se optó por usar una única línea con caracteres especiales 
como `\n` para los saltos de línea y la diagonal inversa `\` para mejorar la estética y claridad del código. Esto reduce la redundancia y hace 
que la estructura del menú sea más compacta y fácil de leer.

## Definición de Variables Locales y Globales

**Variables Globales:**
- Las listas `estudiantes` y `calificaciones` deben ser globales, ya que son utilizadas en varias funciones dentro de la clase y deben ser accesibles
  desde cualquier parte del código.

**Variables Locales:**
- Las variables dentro de funciones como `AddStudent()` o `ListStudent()`, que solo se usan dentro de esas funciones, deben ser locales. Estos datos
- no necesitan ser accesibles fuera del contexto de esas funciones.

## Preguntas Guía

1. **¿Qué ventajas tiene dividir el código en funciones?**
   - Mejora la organización del código, facilita su comprensión y seguimiento. Además, permite reutilizar funciones en diferentes partes del
   - programa, facilita el mantenimiento y mejora el trabajo colaborativo.

2. **¿Por qué es importante limitar el uso de variables globales?**
   - El uso excesivo de variables globales puede provocar modificaciones no controladas que afecten otras partes del programa. Las variables locales
   - son más seguras, ya que limitan su impacto al ámbito de la función donde fueron declaradas.

3. **¿Cómo se puede mejorar la legibilidad del código?**
   - Usando un estilo de codificación consistente (como CamelCase o snake_case), eligiendo nombres claros y descriptivos, agregando comentarios
   - útiles, y manteniendo la estructura lógica y simple del código.

## Conclusión

El programa fue desarrollado de manera modular para garantizar su facilidad de uso y mantenimiento. Las tareas repetitivas, como la entrada de datos 
numéricos, fueron encapsuladas en la función `linea1()`, que asegura que solo se ingresen datos válidos. Las variables `estudiantes` y `calificaciones` 
son globales dentro de la clase `Program`, mientras que las funciones como `AddStudent()` y `ListStudent()` manejan variables locales.

El menú fue optimizado usando un `switch` en lugar de condicionales `if`, lo que facilita la gestión de opciones. Se implementaron `Console.Clear()` y `Console.ReadKey()`
para mejorar la estética del programa. Además, la estructura del menú fue simplificada utilizando una sola llamada a `WriteLine()`, lo que redujo la redundancia y mejoró 
la legibilidad del código.
