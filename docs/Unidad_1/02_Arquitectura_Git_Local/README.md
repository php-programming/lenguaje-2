# Sección 2: Arquitectura Interna de Git

Con los fundamentos teóricos establecidos, esta sección desciende al nivel de implementación local. Se analiza el modelo lógico de tres estados que Git utiliza para rastrear los cambios, la anatomía de un `commit` y los comandos esenciales para mover los cambios a través de estos estados.

Dominar este flujo de trabajo es la clave para utilizar Git de manera efectiva y deliberada, permitiendo la construcción de un historial de cambios limpio, atómico y profesional.

## Contenidos

1.  **[El Modelo de Tres Estados](./2.1_Modelo_de_Tres_Estados.md)**: Se detalla el propósito del Directorio de Trabajo, el Índice (Staging Area) y el Repositorio Local, explicando cómo interactúan para dar al desarrollador un control granular sobre el historial.
2.  **[Anatomía del Objeto Commit](./2.2_El_Objeto_Commit.md)**: Se deconstruye un `commit`, revelando que es más que un simple mensaje; es una instantánea inmutable que apunta a un árbol de contenidos y a sus padres, formando el DAG.
3.  **[Comandos Fundamentales del Flujo Local](./2.3_Comandos_Fundamentales.md)**: Se explican y demuestran los comandos `git status`, `git add`, `git commit` y `git log` como las herramientas primarias para operar dentro del modelo de tres estados.
