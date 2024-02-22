# Barbero
# Componentes del Sistema:
Clientes: Son las personas que llegan a la barbería para cortarse el pelo.
Barbero: Es el peluquero que trabaja en la barbería y corta el pelo a los clientes.
Silla de Barbero: Es donde el barbero corta el pelo a los clientes.
Sillas de Espera: Son los asientos donde los clientes esperan su turno si el barbero está ocupado.

# Decisión del Cliente: Considera cómo un cliente decide si esperará o se irá cuando llegue a la barbería. ¿Qué factores influyen en esta decisión y cómo se puede implementar esta lógica de manera que sea coherente con el comportamiento esperado?

Cuando un cliente llega a la barbería, hay varios factores que influyen en la decision :

- ¿Está el barbero disponible? Si el barbero está libre y no está atendiendo a otro cliente, es más probable que el cliente decida quedarse.
  
- ¿Hay sillas de espera disponibles? Si hay sillas disponibles, el cliente puede decidir esperar su turno. Si no, es más probable que se vaya.
  
- ¿Cuánto tiempo ha estado esperando el cliente? Si el cliente ha esperado mucho tiempo y no ha sido atendido, es más probable que se vaya.

# Manejo de la Cola de Espera: Reflexiona sobre la estructura de datos que podría representar mejor la cola de espera. ¿Cómo garantizarías que los clientes sean atendidos en el orden correcto, especialmente cuando el barbero se desocupa y está listo para atender al siguiente cliente? 

Utilizando una estructura de datos de cola y asegurando una sincronización adecuada, podemos garantizar que los clientes sean atendidos en el orden correcto, incluso cuando el barbero se desocupa y está listo para atender al siguiente cliente.

# Concurrencia y Sincronización: Piensa en cómo gestionarías la concurrencia en este escenario. ¿Cómo asegurarías que el barbero no sea despertado por un cliente cuando ya está atendiendo a otro? ¿Cómo manejarías las situaciones en las que múltiples clientes llegan al mismo tiempo cuando solo queda una silla de espera disponible?

Para evitar que un cliente despierte al barbero ocupado, usamos una variable de condición y bloqueo para garantizar que solo un cliente pueda verificar antes de despertarlo. Para manejar la llegada de múltiples clientes con una silla de espera disponible, utilizamos un mecanismo de sincronización para controlar el acceso. Si la silla está llena, los clientes deben tener un plan de respaldo, como esperar afuera o regresar más tarde.

# Justicia y Eficiencia: Considera el equilibrio entre la justicia (asegurando que todos los clientes tengan una oportunidad justa de ser atendidos) y la eficiencia (minimizando el tiempo de espera para los clientes y el tiempo inactivo para el barbero). ¿Cómo impactan tus decisiones de diseño en este equilibrio?


Las decisiones de diseño afectan el equilibrio entre justicia y eficiencia en la barbería. Por ejemplo, una cola de espera justa garantiza que todos los clientes sean atendidos en orden, pero puede aumentar los tiempos de espera. Priorizar la eficiencia permitiendo que los clientes se salten la cola reduce los tiempos de espera, pero puede percibirse como injusto. El equilibrio depende de cómo se implementen las políticas de atención y espera.
