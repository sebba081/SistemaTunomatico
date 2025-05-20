# Sistema Tunomático — Modelado Arquitectónico Profesional

## Descripción General

El presente trabajo consiste en el modelado arquitectónico completo de un Sistema de Gestión de Turnos Digitales (Tunomático), siguiendo buenas prácticas de diseño orientado a objetos y aplicando patrones de diseño reconocidos. El objetivo es demostrar la transición completa desde la visión funcional (casos de uso) hasta la arquitectura física (implementación), reflejando tanto el diseño lógico (diagrama de clases con patrones aplicados) como la distribución en nodos y componentes reales (diagrama de implementación UML).

## Diagrama de Casos de Uso UML

![Diagrama de Casos de Uso](ruta/al/diagrama/casos_de_uso.png)

### Descripción y Justificación de Relaciones

- **Actores Identificados**:
  - **Cliente**: Responsable de reservar un turno, ver su estado y poder cancelarlo.
  - **Recepcionista**: Responsable de atender a los clientes según el turno en el que se encuentra, atenderlos y posteriormente avanzar el turno y atender al nuevo cliente.

- **Relaciones Aplicadas**:
  - **<<include>>**: Utilizado en procesos donde el caso de uso depende de otro obligatorio, como en el caso de reservar un turno, es necesario generar un número para ser atendido.
  - **<<extend>>**: Utilizado en procesos donde es opcional el proceso del caso de uso, como en el caso de enviar una notificación SMS, ya que el cliente tiene la opción de querer recibirla o no.

## Diagrama de Clases UML

![Diagrama de Clases](ruta/al/diagrama/clases.png)

### Justificación Profunda de Patrones

- **Singleton (ConfiguracionSistema)**:
  - **Justificación**: Asegura que la configuración del sistema sea única y accesible globalmente, manteniendo la consistencia.
  - **Intención arquitectónica**: Proveer un punto de acceso global y controlar el acceso concurrente a la configuración del sistema.

- **Prototype (PlantillaMovimiento)**:
  - **Justificación**: Facilita la creación de objetos mediante la clonación de una instancia prototípica, reduciendo la necesidad de crear instancias desde cero.
  - **Intención arquitectónica**: Permitir la clonación eficiente de objetos complejos.

- **Adapter (Adaptador)**:
  - **Justificación**: Permite la integración con sistemas externos de notificación SMS, adaptando interfaces incompatibles.
  - **Intención arquitectónica**: Facilitar la interoperabilidad entre el sistema de gestión de turnos y servicios externos de notificación.

## Diagrama de Implementación UML

![Diagrama de Implementación](ruta/al/diagrama/implementacion.png)

### Decisiones Técnicas

- **Nodos Físicos**: El sistema se despliega en un servidor de aplicaciones que maneja las solicitudes de los clientes y recepcionistas.
- **Componentes**: Integración con servicios de mensajería SMS para notificaciones opcionales a los clientes.
- **Conexiones**: Se eligió un enfoque basado en microservicios para permitir la escalabilidad y flexibilidad del sistema.
- **Notas UML**: Explican cómo los patrones de diseño se reflejan en la arquitectura física.

## Reflexiones Finales del Modelado

El modelado arquitectónico del Sistema Tunomático ha permitido una comprensión profunda de las interacciones y dependencias dentro del sistema. La aplicación de patrones de diseño ha facilitado la creación de una arquitectura robusta y escalable, capaz de adaptarse a futuras necesidades y cambios tecnológicos.