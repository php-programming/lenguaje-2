# Sección 1: Controlador de Vistas

Esta sección se enfoca en la infraestructura necesaria para renderizar vistas. En lugar de hacer `include` directamente en los controladores, crearemos una abstracción que maneje la lógica de presentación.

## Contenidos

1.  **[Definición de Vistas](./12.1_Definicion_Vistas.md)**: El rol teórico de la vista: presentación pura sin lógica de negocio.
2.  **[Generación del Controlador](./12.2_Generacion_Controlador.md)**: Implementación de la clase `View`, uso de `extract()` para variables y `ob_start()` para buffering de salida.
