# Sistema Tunomático — Modelado Arquitectónico Profesional

## 📌 Descripción General

Este proyecto corresponde al modelado arquitectónico completo del Sistema Tunomático, una solución digital para la gestión de turnos en entornos de atención al cliente. Se aplican principios de diseño orientado a objetos y se incorporan patrones de diseño clásicos para estructurar la solución desde su análisis funcional hasta su arquitectura física.

El objetivo es representar el sistema desde distintas perspectivas, incluyendo:
- Diagrama de Casos de Uso (funcional).
- Diagrama de Clases (lógico).
- Diagrama de Implementación (físico).

## 🧩 Diagrama de Casos de Uso UML

![Diagrama de Casos de Uso](/diagramas/diagrama%20de%20caso%20de%20uso.svg)

### ✅ Descripción y Justificación

**Actores Principales**:
- **Cliente**: Reserva, consulta y cancela turnos.
- **Recepcionista**: Atiende clientes, finaliza turnos y gestiona el flujo.

**Relaciones Aplicadas**:
- **Include**: Se utiliza cuando un caso de uso depende obligatoriamente de otro. Ejemplo: al reservar un turno, se incluye automáticamente la generación del número de turno.
- **Extend**: Se usa cuando una funcionalidad es opcional. Ejemplo: enviar una notificación SMS si el cliente opta por recibirla.

## 🧱 Diagrama de Clases UML

![Diagrama de Clases](/diagramas/diagrama%20de%20clases.svg)

### 🎯 Patrones de Diseño Aplicados

- **🔒 Singleton (ConfiguracionSistema)**
  - **Justificación**: Garantiza una única instancia de configuración compartida a nivel global.
  - **Uso arquitectónico**: Centraliza la configuración del sistema (idioma, modo de notificación).

- **📐 Prototype (PlantillaMovimiento)**
  - **Justificación**: Permite duplicar objetos complejos sin necesidad de crear nuevas instancias desde cero.
  - **Uso arquitectónico**: Clonación rápida de plantillas de atención.

- **🔌 Adapter (AdaptadorSMS)**
  - **Justificación**: Facilita la comunicación con el servicio externo de mensajería.
  - **Uso arquitectónico**: Permite adaptar la interfaz de ServicioSMSExterno al sistema interno.

## 🖥️ Diagrama de Implementación UML

![Diagrama de Implementación](/diagramas/diagrama%20de%20implementacion.svg)

### ⚙️ Decisiones Técnicas

**Nodos definidos**:
- **Cliente Web**: Punto de acceso del usuario final (navegador).
- **Servidor de Aplicaciones**: Lógica de negocio, controladores y patrones implementados.
- **Base de Datos**: Persistencia de turnos.
- **Servicio SMS**: Servicio externo consumido vía API REST.

**Componentes claves**:
- **Aplicación Tunomático**: Encapsula la lógica principal.
- **GestorTurnos**: Orquesta los casos de uso.
- **ConfiguracionSistema**: Componente global (Singleton).
- **AdaptadorSMS**: Adaptador hacia el servicio externo.

**Notas UML**:
- Se utilizó el estilo de componentes para destacar la función de cada módulo dentro del sistema.
- Las conexiones reflejan tecnologías reales (HTTP, JDBC, REST).

## 📚 Reflexiones Finales

Este modelado me permitió comprender de forma profunda cómo una idea funcional puede transformarse en una arquitectura robusta, clara y extensible. La aplicación de patrones no solo mejoró la organización del código, sino que también permitió anticipar escenarios de mantenimiento, escalabilidad y reutilización. Además, plasmar todo en UML me ayudó a visualizar las dependencias y responsabilidades de cada parte del sistema antes de escribir una sola línea de código.