# Sección 1: Fundamentos de los Sistemas de Control de Versiones (VCS)

Esta sección establece las bases teóricas indispensables para comprender la filosofía y arquitectura detrás de Git. Antes de ejecutar un solo comando, es crucial entender el *porqué* de un VCS y cómo su diseño impacta directamente en la eficiencia y resiliencia de los flujos de trabajo en ingeniería de software.

## Contenidos

1.  **[¿Qué es un VCS? Un Enfoque Sistémico](./1.1_Que_es_un_VCS.md)**: Se define formalmente un VCS, superando la analogía del "viaje en el tiempo" para presentarlo como un modelo de datos inmutable y una única fuente de verdad (`Single Source of Truth`).
2.  **[Arquitecturas de VCS: Centralizada vs. Distribuida](./1.2_Arquitecturas_VCS.md)**: Se analiza y compara la arquitectura cliente-servidor (CVCS) con la arquitectura peer-to-peer (DVCS), justificando la dominancia del modelo distribuido en el desarrollo de software moderno.
3.  **[Git como un Grafo Acíclico Dirigido (DAG)](./1.3_Git_como_DAG.md)**: Se profundiza en la estructura de datos subyacente de Git, explicando cómo el modelo de un DAG es la clave para su performance, integridad y capacidades de ramificación.

Al finalizar esta sección, usted comprenderá los principios fundamentales que hacen de Git una herramienta robusta y no simplemente una secuencia de comandos a memorizar.
