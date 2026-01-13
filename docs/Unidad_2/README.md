# Unidad 2: Diseño y Estructura de Bases de Datos

## Caso de Uso del Sistema

**Escenario:** Se nos ha encargado diseñar la arquitectura de datos para el **"Sistema de Gestión Académica de Architek-Pro"**. Este sistema debe gestionar la información de estudiantes, los cursos que se ofrecen, los profesores que los imparten y las inscripciones de los estudiantes en dichos cursos.

**Requisitos de Integridad de Datos:**
1.  **Consistencia:** La información debe ser consistente en todo el sistema. El nombre de un curso debe ser el mismo independientemente de cuántos estudiantes estén inscritos.
2.  **No Redundancia:** Se debe minimizar la duplicación de datos. Almacenar el nombre de un profesor en cada registro de inscripción es ineficiente y propenso a errores.
3.  **Prevención de Anomalías:** El diseño debe impedir operaciones que dejen la base de datos en un estado inconsistente. Por ejemplo, no debe ser posible eliminar a un estudiante y dejar sus registros de inscripción "huérfanos".
4.  **Escalabilidad:** El diseño debe soportar el crecimiento futuro de Architek-Pro, tanto en volumen de datos como en complejidad de las relaciones.

## Introducción a la Unidad

Bienvenidos a la Unidad 2. Aquí abordamos el esqueleto de casi cualquier aplicación de software compleja: la **base de datos**. Un diseño de base de datos deficiente es una de las formas más seguras de acumular deuda técnica y condenar un proyecto al fracaso.

En esta unidad, trataremos el diseño de bases de datos como una disciplina de **ingeniería formal**. Aprenderemos el proceso algorítmico de la **Normalización**, cuyo objetivo es cumplir con los requisitos de integridad de nuestro caso de uso.

### Hoja de Ruta de la Unidad

*   **Sección 1: [Fundamentos de Bases de Datos Relacionales](./01_Fundamentos_BDRR/README.md)**
    *   Estableceremos el vocabulario técnico del modelo relacional (Entidades, Atributos, Claves) y los principios de integridad de datos.

*   **Sección 2: [El Proceso de Normalización](./02_Normalizacion/README.md)**
    *   Este es el núcleo de la unidad. Analizaremos las **anomalías de datos** y utilizaremos las **Dependencias Funcionales** como herramienta para progresar a través de la Primera, Segunda y Tercera Forma Normal (1NF, 2NF, 3NF), refactorizando el esquema de nuestro Architek-Pro en cada paso.

*   **Sección 3: [Herramientas de Gestión](./03_Herramientas_Gestion/README.md)**
    *   Finalmente, revisaremos las herramientas gráficas (GUIs) como MySQL Workbench o DBeaver, contextualizándolas como interfaces para implementar y consultar el diseño lógico que hemos construido.

Al finalizar esta unidad, usted será capaz de diseñar esquemas de bases de datos normalizados que sean eficientes, robustos y que garanticen la integridad de los datos, la piedra angular de cualquier sistema de software fiable.
