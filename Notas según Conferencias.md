# Tipos de Clases (según la responsabilidad)

- Clases entidades
- Clases controladoras
- Clases interfaz
- Clases auxiliares

# Asociación o Colaboración entre clases (Agregación y Composición)

> • Unión de individuos con un fin determinado.
>
> • Relación mental que se establece entre dos conceptos, ideas o recuerdos que tienen algo en común o entre las cuales se puede establecer una implicación intelectual o sugerida.

La Asociación se expresa como `tiene -- un`, `parte -- de` se establece entre 2 conceptos cuando 1 es componente del otro, pero ambos no son la misma cosa, sin importar cuan abstracta sea la generalidad. Ejemplos:
- Carro tiene un Motor (Las clases Carro y Motor ambas tienen una asociación o colaboración entre clases)
- Árbol tiene Hoja (Las clases Árbol y Hoja ambas tienen una asociación o colaboración entre clases)
- Escuela tiene Estudiante (Las clases Escuela y Estudiante ambas tienen una asociación o colaboración entre clases)
- Autor tiene varios Libro (Las clases Autor y Libro ambas tienen una asociación o colaboración entre clases)
- Libro tiene un Autor (Las clases Libro y Autor ambas tienen una asociación o colaboración entre clases)

## Características de la Asociación o Colaboración entre clases

* Multiplicidad: Cuántas instancias de un tipo A pueden asociarse a una instancia del tipo B en determinado momento.

Tabla
![Tabla de Multiplicidad](./assets/Multiplicidad%20Tabla%20con%20Todos%20los%20Tipos.jpg)

### Ejemplo de Multiplicidad

Ejemplo de 1 a 1
![1 a 1](./assets/Multiplicidad%20(1%20a%201).jpg)

Ejemplo de 1 a Mucho
![1 a Mucho](./assets/Multiplicidad%20(1%20a%20Mucho).jpg)

Ejemplo de 1 a N
![1 a N](./assets/Multiplicidad%20(1%20a%20N).jpg)

Ejemplo de Mucho a Mucho
![Mucho a Mucho](./assets/Multiplicidad%20(Mucho%20a%20Mucho).jpg)

# Agregación Tipo de Asociación (Débil)

Los objetos de la clase componente **no** son dependientes de la existencia de los objetos de la clase compuesta, es decir, se establece una relación **débil** entre ellos donde el tiempo de vida de el objeto de la clase componente **no** está limitado por la existencia del objeto compuesto.

> La *parte* **NO** depende del *todo*

Ejemplo en UML utilizando Multiplicidad
![UML con Multiplicidad](./assets/Agregacion%20UML%20Multiplicidad.jpg)

# Composición Tipo de Asociación (Fuerte)

Los objetos de la clase componente son dependientes de la existencia de los objetos de la clase compuesta, es decir, se establece una relación **fuerte** entre ellos donde el tiempo de vida de el objeto de la clase componente está limitado por la existencia del objeto compuesto.

> La *parte* **depende**  del *todo*

Ejemplo en UML utilizando Multiplicidad
![UML con Multiplicidad](./assets/Composicion%20UML%20Multiplicidad.jpg)

# Asociación -- Código

Ejemplo sobre una Secundaria y Estudiantes, donde Secundaria es la clase controladora y Estudiantes es la clase entidad. Existe una asociación débil, o sea una AGREGACIÓN

Características Importantes
- Siempre se agrega un atributo tipo **arreglo** de la clase entidad.
- Siempre se agrega un atributo tipo int de **cantidad real**
- Siempre se agrega un atributo tipo int de **cantidad máxima**

## UML y Código JAVA

UML donde se representa la clase Secundaria como clase controladora y la clase Estudiante como clase entidad. Asociación débil en otras palabras, AGREGACIÓN
![UML de la Asociación](./assets/Asociaci%C3%B3n%20UML%20y%20Codigo(1).jpg)

Código de la clase Secundaria que al ser la clase controladora es la que tiene los 3 atributos predeterminados:

1. arreglo de la clase entidad 
2. un campo de la cantidad real de tipo int. 
3. un campo de la cantidad maxima de tipo int.

![Codigo de la Asociacion](./assets/Asociaci%C3%B3n%20UML%20y%20Codigo.jpg)

# Asociación - Agregación vs Composición -- Diferencias en el Código


El código está siendo escrito desde la clase Secundaria por ser la clase controladora de ahí en caso que exista:

- Agregación, recibe el objeto entidad cuando sea necesario por parámetro
- Composición, recibe los atributos necesarios para crear el objeto primero y luego realizar la operación que sea necesario

Ejemplo visual:
![Agregación vs Composición en Código](./assets/Asociaci%C3%B3n%20(Agregacion%20vs%20Composicion%20con%20respecto%20al%20codigo).jpg)

# Herencia

La Herencia se expresa como `es -- un`, se establece entre 2 conceptos cuando 1no es una especialización del otro (Generalización-Especialización). La herencia es un recurso mediante el cual se puede definir una clase como heredera, descendiente o derivada de otra(s) clase(s), que se denominará clase padre o clase base. Esta relación entre clases define que una clase comparte su estructura de comportamiento definida en otra(s) clases. La herencia representa una jerarquía de abstracciones, en la que una subclase hereda de una superclase. 

Se usa el control de acceso `protected` para los atributos de la clase padre donde son miembros privados pero las clases derivadas pueden acceder.

## Herencia, su importancia

Con la herencia se puede resolver las características siguientes:

1. Una clase derivada(hija) hereda todos los atributos y los métodos de sus clases ancestrales. 
2. Una clase derivada(hija) tiene acceso a todos los atributos y métodos no privados de sus clases ancestrales. 
3. La clase derivada(hija) puede redefinir los métodos heredados. (Extensión por especialización)
4. La clase derivada(hija) puede agregar en su definición nuevos atributos y nuevos métodos a los ya heredados. (Extensión por ampliación)


## Transitividad y Simétrica

Transitividad -> SI

La relación de herencia, es una **relación transitiva**, pues siempre que se tienen 3 clases A, B y C, tales que A es-un B y B es-un C, entonces se cumplirá que A es-un C.

Simétrica -> NO

La relación de herencia, **NO** es una relación simétrica, pues nunca sucederá que dadas dos clases A y B, tales que A es-un B, entonces B es-un A. Ejemplo donde si Perro es-un Mamífero no puede establecerse Mamífero es-un Perro, porque no todos los mamíferos son perros.

## Diagrama UML

Herencia en el UML
![Herencia en el UML](./assets/Herencia%20UML.jpg)

Los atributos deben ser considerados como `protected` y en el UML se usa el `#` para definirlos.
![Herencia uso del Protected](./assets/Herencia%20UML%20Protected.jpg)

## Clases hijas

La clase que deriva o extiende como una especialización de la clase padre en código se utiliza la palabra clave `extends` (JAVA). Ejemplo donde la clase hija extiende de la clase padre.
![Herencia de una clase hija con el uso de extends](./assets/Herencia%20Codigo%20Extends.jpg)

La clase que deriva o extiende como una especialización de la clase padre en código se utiliza la palabra clave `super` para representar la presencia de la clase padre(JAVA). En el método constructor de la clase hija se hace uso de la palabra reservada antes de  cualquier posible acción propia del nuevo constructor. Ejemplo de código
![Herencia en Codigo uso SUPER](./assets/Herencia%20Codigo%20Super.jpg)

### Super, palabra reservada

- Así como `this` es una referencia a la propia clase, `super` es una referencia a la superclase.
- Así como `this()` es para invocar a constructores de la propia clase, `super()` es para invocar constructores de la superclase.
- Así como `this.` es para acceder a atributos e invocar métodos de la propia clase, `super.` es para acceder a atributos e invocar métodos de la superclase.

## Asignación y Herencia

¿Puede un hijo comportase como un padre?

`“sí”` pues la clase descendiente tiene toda la funcionalidad de la clase base, por lo tanto un objeto hijo puede hacer todo lo que hace un objeto padre.

¿Puede un padre comportase como un hijo?

`“no”` pues la clase descendiente puede ampliar o especializar la funcionalidad de la clase base, por lo tanto un objeto hijo puede tener un comportamiento que el  padre no lo puede tener.

Ejemplo en código
![Comportamiento de la clases Padre e Hija con respecto a la asignacion](./assets/Herencia%20Comportamiento%20de%20la%20clase%20Padre%20e%20Hija.jpg)

## Casting & Instance of

### Casting

Para asignar una clase padre o base a una variable de tipo que es hija, tiene que utilizarse el casting, donde explícitamente se dice que el objeto base se comporte como el objeto hijo.
![Casting](./assets/Herencia%20Comportamiento%20de%20la%20clase%20Padre%20e%20Hija%20CASTING.jpg)

### Instance of

El operador `instanceof` en Java sirve para comprobar si un objeto es de una clase o interfaz determinada

Por ejemplo, si tenemos una clase Animal y una clase Perro que hereda de Animal, podemos usar el operador instanceof para saber si un objeto de tipo Perro es también de tipo Animal:

```java
Perro perro = new Perro();
System.out.println(perro instanceof Animal); // true
```
El operador instanceof devuelve un valor booleano (true o false) que podemos usar en una condición o asignación. Sin embargo, hay que tener cuidado de no abusar de este operador, ya que puede romper el principio de sustitución de Liskov y generar código acoplado y difícil de mantener

#### Ejemplo sencillo

Un ejemplo simple y sencillo del uso del operador instanceof en Java podría ser el siguiente:

```java
// Definimos una interfaz llamada Saludable que tiene un método saludar
interface Saludable {
void saludar();
}

// Definimos una clase Persona que implementa la interfaz Saludable
class Persona implements Saludable {
private String nombre;

// Constructor de la clase Persona
public Persona(String nombre) {
this.nombre = nombre;
}

// Método saludar que imprime el nombre de la persona
public void saludar() {
System.out.println("Hola, soy " + nombre);
}
}

// Definimos una clase Robot que también implementa la interfaz Saludable
class Robot implements Saludable {
private String modelo;

// Constructor de la clase Robot
public Robot(String modelo) {
this.modelo = modelo;
}

// Método saludar que imprime el modelo del robot
public void saludar() {
System.out.println("Beep boop, soy el robot " + modelo);
}
}

// Definimos una clase principal con el método main
public class EjemploInstanceOf {

public static void main(String[] args) {
// Creamos un array de objetos de tipo Object
Object[] objetos = new Object[4];
objetos[0] = new Persona("Ana");
objetos[1] = new Robot("R2D2");
objetos[2] = new Persona("Pedro");
objetos[3] = new Robot("WALL-E");

// Recorremos el array con un bucle for
for (int i = 0; i < objetos.length; i++) {
// Si el objeto en la posición i implementa la interfaz Saludable
if (objetos[i] instanceof Saludable) {
// Hacemos un casting de objetos usando la interfaz
Saludable ref = (Saludable) objetos[i];
// Invocamos el método saludar del objeto
ref.saludar();
}
}
}
}

```

La salida del programa sería:
```
Hola, soy Ana
Beep boop, soy el robot R2D2
Hola, soy Pedro
Beep boop, soy el robot WALL-E
```

# Polimorfismo

> • Derivado de su forma original en griego.(poly = muchas, morphos  =  forma). 
> 
> • Significa la capacidad de adoptar varias formas. 

En la programación, una entidad polimórfica es aquella a la que se le permite tener valores, comportamientos  o significados de tipos  diferentes en el curso de la ejecución de un programa.

Se puede ver el polimorfismo, su uso, en 3 formas distintas:

- Variables, variables polimórficas.
- Métodos Virtuales, por la herencia (Extensión por especialización).
- Métodos de sobrecarga.
- Métodos abstractos (REVISAR)


## Variables polimórficas

En la programación orientada a objetos, una variable polimórfica es un objeto al cual se le permite tener valores de tipos diferentes en el curso de la ejecución de la aplicación. 

Para ello el valor que se asigna (tipo Dinámico) debe ser compatible con el tipo de declaración del objeto (tipo Estático). 

Un tipo de dato es compatible con otro, si es un descendiente en la jerarquía de clases o es del mismo tipo.

Ejemplo gráfico
![Variables polimórficas](./assets/Polimorfismo%20en%20las%20Variables%20.jpg)

## Extensión por especialización (Uso de la HERENCIA)(Métodos VIRTUALES)

Cuando se usa esta forma de polimorfismo, se permite la posibilidad a que las clases derivadas puedan redefinir sus métodos con respecto a lo provisto por la clase padre.

Técnicas presentes:

- Sustitución(Remplazo) => Define una nueva implementación completamente diferente a la definida en el padre.
- Refinamiento => Define una nueva implementación empleando la implementación definida en el padre(es distinta pero no cambia por completo). 

### UML y Código

UML 

En el UML se representa solamente, en la clase hija cuando existe el uso de Extensión por especialización, ese método que se remplaza o se refina. Es distinto a los métodos que heredan de la clase padre y se utilizan como mismo se define ese métodos original donde si se representan en ambas clases.

Código

Para la declaración e implementación de los métodos empleando JAVA:

- Sustitución(Remplazo) => En las clases hijas se agrega la cláusula `@override` encima de la declaración del método.
- Refinamiento => Se aplica en las clases hijas la cláusula `@override` encima de la declaración del método. En la implementación del método se emplea el objeto `super` para invocar el método de igual nombre pero definido en la clase padre.

Según el problema se tiene los siguientes datos

```
1. Determinar el Salario Final de un Empleado teniendo en cuenta que existe un Salario básico calculado a partir del nivel de su plaza:
▪ Nivel 1—SalarioBásico 465
▪ Nivel 2—SalarioBásico 555
▪ Nivel 3—SalarioBásico 615

2. Salario de las secretarias se enuncia en la siguiente fórmula:
    Salario = SalarioBásico + 5* añosExperiencia

3. Salario de los profesores es calculado de la siguiente forma:
Si categoríaDocente es:
       RGA o Instructor : $500
       Asistente :  $750
       Auxiliar o Titular: $1000
Si gradoCientífico es:
       Master mas $80 o Doctor mas $150. 

     
```

Sustitución(Remplazo) o Refinamiento según la propia problemática de calcular el Salario
![Polimorfismo en Método uso de extensión por especialización](./assets/Polimorfismo%20Metodos%20de%20Extension%20por%20especializacion.jpg)

### Ligadura dinámica

La función del polimorfismo se encarga de ligar o relacionar la llamada a un método con el cuerpo del método que se ejecuta finalmente.

Consiste que en tiempo de ejecución, la forma dinámica del objeto es quien determina la versión del método a ejecutar.
![Ligadura dinámica](./assets/Polimorfismo%20Ligadura%20Din%C3%A1mica.jpg)

## Sobrecarga de métodos

En la sobrecarga de métodos, es el nombre del método el que es polimórfico y el código real ejecutado estará en dependencia de los parámetros que se le suministren al método.

A diferencia de los métodos abstractos y virtuales, los métodos sobrecargados:
- No requieren de la herencia para existir. Están en la misma clase.
- No pueden tener iguales parámetros (tipo, orden, cantidad).

Ejemplo de la sobrecarga del método constructor
![Metodo constructor sobrecargado](./assets/Polimorfismo%20Sobrecarga%20de%20M%C3%A9todos.jpg)

## Métodos abstractos

El uso de un método abstracto requiere de una clase abstracta obligatoriamente

### Clase abstracta

La clase abstracta es el tipo de clase de la cual no se tiene intención de crear objetos, sino que únicamente sirve para unificar datos y operaciones de subclases. Es la clase base para la creación de subclases.

### Método abstracto

Puntos a tener en cuenta:

1. Método que no tiene cuerpo.
2. Su declaración termina con un punto y coma.
3. Sólo puede existir dentro de una clase abstracta.
4. Forzosamente habrán de estar sobreescritos en las subclases.

Características de los métodos abstractos:

- Toda clase que contenga al menos un método declarado como abstracto, tiene que ser declarada como abstracta.
- Un método abstracto expresa la existencia de un comportamiento común para todas las clases hijas pero con implementaciones diferentes en cada una.
- Toda clase hija que herede de una clase abstracta con métodos abstractos, tiene que implementar todos sus métodos abstractos o ser definida como abstracta.

### Representación en UML

Según el propio problema para presentar este tema queda en UML:
![Clase Metodo Abstracto](./assets/Polimorfismo%20Clase-Metodo%20Abstracto.jpg)

### Representación en Código

![Clase Metodo Abstracto en Codigo](./assets/Polimorfismo%20Clase-Metodo%20Abstracto%20en%20Codigo.jpg)

# Interfaz

Característica de una Interfaz en Programación

- Es un contrato que se establece con una clase que obliga a la misma a implementar los métodos definidos por la interfaz.
- Estructura que define comportamientos que las clases están obligadas a implementar.
- No contiene atributos. De tener, solo pueden ser constantes.
- Contiene métodos pero no su implementación.
- Por consenso, comienzan con ‘I’.

Ventajas en usar la Interfaz
- Obligar que las clases tengan un comportamiento determinado.
- Permite agrupar objetos distintos.
- Permite la integración entre sistemas diferentes.

