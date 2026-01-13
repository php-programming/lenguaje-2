# Sección 2: El Proceso de Normalización

Esta sección es el núcleo ingenieril del diseño de bases de datos. La normalización no es un concepto abstracto, sino un **proceso de diseño algorítmico** cuyo objetivo es refactorizar un esquema de base de datos para minimizar la redundancia y eliminar las anomalías de datos.

Utilizaremos el caso de uso del "Sistema de Gestión Académica de Architek-Pro" como nuestro campo de pruebas. Partiremos de un diseño "plano" e intuitivo (y peligrosamente incorrecto) y lo someteremos al rigor de las tres primeras Formas Normales, demostrando cómo cada paso mejora la integridad y la estructura de nuestro modelo de datos.

## Contenidos

1.  **[El Problema: Anomalías y Dependencias Funcionales](./2.1_Anomalias_y_Dependencias.md)**: Antes de la solución, definimos el problema. Se ilustran las anomalías de inserción, actualización y borrado, y se introduce la herramienta formal para detectarlas: la Dependencia Funcional.
2.  **[Primera Forma Normal (1NF): Atomicidad](./2.2_Primera_Forma_Normal.md)**: Se aborda el requisito más básico: asegurar que cada campo contenga un único valor.
3.  **[Segunda Forma Normal (2NF): Eliminación de Dependencias Parciales](./2.3_Segunda_Forma_Normal.md)**: Se ataca la redundancia en tablas con claves compuestas.
4.  **[Tercera Forma Normal (3NF): Eliminación de Dependencias Transitivas](./2.4_Tercera_Forma_Normal.md)**: Se finaliza el proceso eliminando las dependencias entre campos que no son clave, logrando el mantra: "los atributos deben depender de la clave, toda la clave y nada más que la clave".
5.  **[Desnormalización y Modelado para Análisis](./2.5_Desnormalizacion_y_BI.md)**: Se introduce el concepto de desnormalización como una técnica de optimización para consultas analíticas (OLAP) y su aplicación en modelos de Business Intelligence.
