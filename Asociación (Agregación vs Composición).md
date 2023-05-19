La agregación y la composición son dos tipos de relaciones de asociación entre clases. La principal diferencia entre ellas es la fuerza de la relación.

La agregación es una relación más débil en la que una clase es un contenedor o una colección de objetos de otra clase, pero los objetos contenidos pueden existir independientemente del contenedor. Por ejemplo, en el ejemplo anterior, mencionado en el archivo [Asociación (Agregación)](./Asociaci%C3%B3n%20(Agregaci%C3%B3n).md), un jugador puede existir sin estar asociado a un equipo.

Por otro lado, la composición es una relación más fuerte en la que los objetos contenidos no pueden existir sin el contenedor. En otras palabras, si el objeto contenedor es destruido, los objetos contenidos también son destruidos. Un ejemplo podría ser una clase Casa y una clase Habitacion. Una casa tiene varias habitaciones y si la casa es destruida, las habitaciones también lo son.

Además de la agregación y la composición, hay otros tipos de relaciones entre clases como 
- la herencia (una clase extiende a otra), 
- la implementación (una clase implementa una interfaz)
- la dependencia (una clase usa a otra).