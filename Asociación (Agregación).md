La agregación es una relación entre dos clases en la que una clase es un contenedor o una colección de objetos de otra clase. La agregación se representa mediante una línea con un rombo blanco en el extremo del contenedor y se lee como “tiene un” o “contiene un”.

Un ejemplo real podría ser una clase Equipo que representa a un equipo deportivo y una clase Jugador que representa a un jugador de ese equipo. Un equipo puede tener varios jugadores, por lo que la relación entre Equipo y Jugador es de agregación.

En este ejemplo, la clase Equipo tiene una lista de objetos Jugador, lo que indica que hay una relación de agregación entre ambas clases. La clase Equipo también tiene métodos para agregar jugadores y obtener la lista de jugadores.
```java
public class Equipo {
    private String nombre;
    private List<Jugador> jugadores;

    public Equipo(String nombre) {
        this.nombre = nombre;
        this.jugadores = new ArrayList<>();
    }

    public void agregarJugador(Jugador jugador) {
        jugadores.add(jugador);
    }

    public List<Jugador> getJugadores() {
        return jugadores;
    }
}
public class Jugador {
    private String nombre;
    private int numero;

    public Jugador(String nombre, int numero) {
        this.nombre = nombre;
        this.numero = numero;
    }

    public String getNombre() {
        return nombre;
    }

    public int getNumero() {
        return numero;
    }
}
```