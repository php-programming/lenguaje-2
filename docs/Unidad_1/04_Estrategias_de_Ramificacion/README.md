# Sección 4: Estrategias de Ramificación (Branching Strategies)

El mecanismo de ramificación de Git es posiblemente su característica más potente, pero también la que requiere más disciplina. Una estrategia de ramificación es un **convenio de equipo**, un conjunto de reglas sobre cómo se crean, nombran y utilizan las ramas para organizar el flujo de desarrollo.

La elección de una estrategia tiene un impacto profundo en la agilidad del equipo, la estabilidad del código y la legibilidad del historial del proyecto. En esta sección, se desmitificará el concepto de rama y se analizarán los modelos de estrategia más comunes en la industria.

## Contenidos

1.  **[El Concepto de Rama en Git](./4.1_Concepto_de_Rama.md)**: Se explica qué es una rama a nivel de la implementación de Git: un simple puntero móvil. Comprender esto revela por qué la ramificación en Git es tan ligera y eficiente.
2.  **[Modelo de Ramificación: GitFlow](./4.2_GitFlow.md)**: Se detalla el modelo GitFlow, una estrategia robusta y estricta ideal para proyectos con ciclos de lanzamiento programados y la necesidad de mantener múltiples versiones en producción.
3.  **[Modelo de Ramificación: Trunk-Based Development](./4.3_Trunk_Based_Development.md)**: Se analiza el enfoque de desarrollo basado en el tronco, una estrategia más simple y rápida favorecida por los equipos que practican la Integración Continua y la Entrega Continua (CI/CD).
4.  **[Integrando Cambios: Merge vs. Rebase](./4.4_Merging_vs_Rebasing.md)**: Se comparan las dos técnicas principales para integrar cambios entre ramas, analizando los trade-offs entre la trazabilidad de un historial de fusiones y la linealidad de un historial reescrito.
