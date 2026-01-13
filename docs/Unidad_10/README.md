# Unidad 10: Carga de Clases y Enrutamiento

## Introducción

Esta unidad se centra en la infraestructura del framework MVC que estamos construyendo. Abordaremos dos problemas fundamentales: cómo cargar eficientemente las decenas de clases que componen nuestra aplicación sin llenar el código de `require_once`, y cómo traducir las URLs amigables que ve el usuario en llamadas a métodos específicos de nuestros controladores.

## Contenidos

1.  **[Autoload](./01_Autoload/README.md)**
    *   Implementaremos un sistema de carga automática de clases usando `spl_autoload_register()`.
    *   Eliminaremos la necesidad de inclusiones manuales, limpiando nuestro código.
2.  **[Método de Enrutamiento](./02_Enrutamiento/README.md)**
    *   Configuraremos el servidor web (Apache) para usar el patrón Front Controller.
    *   Crearemos un `Router` que analice la URL y despache la petición al controlador correcto.
3.  **[Rutas Personalizadas](./03_Rutas_Personalizadas/README.md)**
    *   Evolucionaremos nuestro Router para soportar un mapeo explícito de URLs.
    *   Permitiremos URLs totalmente desacopladas de la estructura de archivos interna.
