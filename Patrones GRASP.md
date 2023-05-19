# Tipos de Clases (según la responsabilidad)

- Clases entidades
- Clases controladoras
- Clases interfaz
- Clases auxiliares

# Patrones GRASP

> GRASP: General Responsibility Assignment Software Patterns

Sirve como una descripción de un problema bien conocido que suele incluir:
  - Problema
  - Solución concreta
  - Ejemplos
  - Beneficios

Existen varios aspectos a tener en cuenta
- Experto de la Información: Asignar una responsabilidad a la clase que tiene la información necesaria para cumplir la responsabilidad (patrón experto).
- Creador: Asignar a la clase B la responsabilidad de crear una instancia de clase A. Guía la asignación de responsabilidades relacionadas con la creación de objetos.
- Alta Cohesión: Una clase debe de hacer lo que respecta a su entidad, y no hacer acciones que involucren a otra clase o entidad.
- Bajo Acoplamiento: Tener las clases lo menos ligadas entre sí. Si se produce una modificación en alguna, debe procurarse que se tenga la mínima repercusión posible en el resto de clases, potenciando la reutilización, y disminuyendo la dependencia entre clases.
- Controlador: Este patrón sugiere que la lógica de negocio debe estar separada de la capa de presentación, esto para aumentar la reutilización de código y a la vez tener un mayor control.