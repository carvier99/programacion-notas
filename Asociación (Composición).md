La composición es una relación entre dos clases en la que una clase es un contenedor o una colección de objetos de otra clase y los objetos contenidos no pueden existir sin el contenedor. La composición se representa mediante una línea con un rombo negro en el extremo del contenedor y se lee como “es parte de” o “compuesto por”.

En este ejemplo, la clase Casa tiene una lista de objetos Habitación, lo que indica que hay una relación de composición entre ambas clases. Si una instancia de Casa es destruida, todas las instancias de Habitación asociadas a ella también son destruidas. La clase Casa también tiene métodos para agregar habitaciones y obtener la lista de habitaciones.

```java
public class Casa {
    private List<Habitacion> habitaciones;

    public Casa() {
        this.habitaciones = new ArrayList<>();
    }

    public void agregarHabitacion(Habitacion habitacion) {
        habitaciones.add(habitacion);
    }

    public List<Habitacion> getHabitaciones() {
        return habitaciones;
    }
}

public class Habitacion {
    private double ancho;
    private double largo;

    public Habitacion(double ancho, double largo) {
        this.ancho = ancho;
        this.largo = largo;
    }

    public double getArea() {
        return ancho * largo;
    }
}
```

En este ejemplo podría ser una clase Computadora que representa a una computadora y una clase CPU que representa al procesador de la computadora. Una computadora tiene un procesador y si la computadora es destruida, el procesador también lo es. Por lo tanto, la relación entre Computadora y CPU es de composición.

En este ejemplo, la clase Computadora tiene un objeto CPU, lo que indica que hay una relación de composición entre ambas clases. Si una instancia de Computadora es destruida, su instancia asociada de CPU también es destruida.

```java
public class Computadora {
    private CPU cpu;

    public Computadora(CPU cpu) {
        this.cpu = cpu;
    }

    public CPU getCpu() {
        return cpu;
    }
}

public class CPU {
    private String modelo;
    private double velocidad;

    public CPU(String modelo, double velocidad) {
        this.modelo = modelo;
        this.velocidad = velocidad;
    }

    public String getModelo() {
        return modelo;
    }

    public double getVelocidad() {
        return velocidad;
    }
}
```