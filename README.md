# Sistema de Gestión de Turnos Digitales (Tunomático)

## Descripción General

El presente proyecto corresponde al modelado arquitectónico de un Sistema de Gestión de Turnos Digitales denominado “Tunomático”, desarrollado utilizando UML y aplicando principios de diseño orientado a objetos junto con patrones de diseño reconocidos.

El sistema permite gestionar solicitudes de turnos, confirmaciones, cancelaciones, administración de usuarios, gestión de empleados y generación de reportes, facilitando la automatización y organización de la atención digital.

El objetivo principal es representar de manera clara la transición desde los requerimientos funcionales hasta la arquitectura física del sistema.

---

# Objetivos del Sistema

## Objetivo General

Diseñar un sistema digital de gestión de turnos que permita administrar de forma eficiente las reservas, confirmaciones y control de atención de usuarios.

## Objetivos Específicos

- Modelar los requerimientos funcionales mediante diagramas UML.
- Aplicar patrones de diseño orientado a objetos.
- Representar la arquitectura lógica y física del sistema.
- Mejorar la organización y automatización del proceso de atención.

---

# Diagrama de Casos de Uso UML

## Descripción

El diagrama de casos de uso representa las funcionalidades principales del sistema y la interacción de los actores con dichas funcionalidades.

## Actores Identificados

- Cliente
- Recepcionista
- Administrador
- Sistema de Notificaciones

## Funcionalidades Principales

- Iniciar sesión
- Solicitar turno
- Validar disponibilidad
- Confirmar turno
- Cancelar turno
- Gestionar usuarios
- Gestionar empleados
- Generar reportes
- Enviar recordatorios

---

# Justificación de Relaciones UML

## Relación <<include>>

Se utilizó la relación `<<include>>` entre:

- Solicitar Turno → Validar Disponibilidad

Esto se debe a que cada vez que un usuario solicita un turno, el sistema obligatoriamente debe validar la disponibilidad antes de registrar la reserva.

## Relación <<extend>>

Se utilizó la relación `<<extend>>` entre:

- Confirmar Turno → Enviar Recordatorio

Esto ocurre porque el envío de recordatorios es una funcionalidad opcional que se ejecuta después de confirmar un turno.

---

# Diagrama de Clases UML

## Descripción

El diagrama de clases representa la estructura lógica del sistema, incluyendo clases, atributos, métodos, relaciones y patrones de diseño aplicados.

## Clases Principales

- Usuario
- Cliente
- Administrador
- Recepcionista
- Turno
- Empleado
- Reporte
- ConexionBD
- Notificador
- EmailNotificador
- SMSNotificador
- AdaptadorWhatsApp

---

# Patrones de Diseño Aplicados

## Singleton

Aplicado en la clase `ConexionBD`.

### Justificación

Garantiza que exista una única instancia de conexión a la base de datos, evitando múltiples conexiones innecesarias y mejorando el control del acceso a datos.

---

## Bridge

Aplicado en las clases `Notificador`, `EmailNotificador` y `SMSNotificador`.

### Justificación

Permite separar la abstracción del sistema de notificaciones de sus implementaciones concretas, facilitando la incorporación de nuevos medios de comunicación.

---

## Adapter

Aplicado en la clase `AdaptadorWhatsApp`.

### Justificación

Permite adaptar servicios externos de mensajería al sistema sin modificar la estructura principal del módulo de notificaciones.

---

# Relaciones UML Aplicadas

## Herencia

- Cliente hereda de Usuario.
- Administrador hereda de Usuario.
- Recepcionista hereda de Usuario.

## Asociación

- Cliente se relaciona con Turno.
- Empleado se relaciona con Turno.

## Dependencia

- Reporte depende de ConexionBD.
- Turno depende de ConexionBD.

## Agregación

- Notificador utiliza implementaciones de notificación.

---

# Diagrama de Implementación UML

## Descripción

El diagrama de implementación representa la arquitectura física del sistema y la distribución de componentes.

## Componentes Identificados

- Cliente Web
- Servidor de Aplicaciones
- Base de Datos MySQL
- API de Notificaciones
- Servicio Externo de Email/SMS

## Tecnologías Simuladas

- Java
- MySQL
- JDBC
- API REST
- Arquitectura Cliente-Servidor

---

# Decisiones Técnicas

## Uso de Arquitectura Cliente-Servidor

Se implementó una arquitectura cliente-servidor para separar la interfaz de usuario de la lógica de negocio y persistencia de datos.

## Uso de Base de Datos Centralizada

Se utilizó una base de datos MySQL centralizada para mantener integridad y consistencia de la información.

## Modularización del Sistema

El sistema fue dividido en módulos independientes para facilitar mantenimiento, escalabilidad y reutilización de componentes.

---

# Reflexión Final

El desarrollo de este modelado UML permitió comprender la importancia de la planificación arquitectónica antes de implementar un sistema real.

La utilización de diagramas UML facilitó la representación clara de funcionalidades, relaciones entre clases y estructura física del sistema. Además, la aplicación de patrones de diseño permitió mejorar la organización, reutilización y mantenibilidad del software.

Finalmente, el proyecto demuestra cómo las buenas prácticas de diseño orientado a objetos contribuyen al desarrollo de sistemas más escalables, estructurados y profesionales.

---

# Conclusión

El Sistema Tunomático cumple con los requerimientos planteados para la gestión digital de turnos, incorporando modelado UML completo, relaciones correctas y patrones de diseño orientados a buenas prácticas de ingeniería de software.

El proyecto refleja adecuadamente la transición desde los requerimientos funcionales hasta la arquitectura física del sistema.
