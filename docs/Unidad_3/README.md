# Fase 2: El Lenguaje y los Datos (Backend Core)

> **Objetivo de la Fase:** Dejar de pensar en "scripts" y empezar a pensar en "servicios" y "estructuras de datos".

## Unidad 3: Fundamentos de Ingeniería Backend con PHP

PHP no es solo un lenguaje para hacer páginas web; es el motor que impulsa el 77% de la web (incluyendo Facebook, Wikipedia y WordPress). En esta unidad, no solo aprenderás sintaxis, sino cómo funciona el protocolo HTTP y cómo el servidor procesa la información.

### 🗺️ Mapa de Competencias

| Nivel | Habilidad | Concepto Clave | Aplicación Real |
| :--- | :--- | :--- | :--- |
| **Junior** | Crear scripts funcionales | Variables y Tipos | Formularios de contacto simples. |
| **Mid** | Manipular estructuras complejas | Arrays Asociativos | Procesar respuestas JSON de una API. |
| **Senior** | Entender el ciclo de vida HTTP | Request/Response | Optimizar el tiempo de carga (TTFB). |

### 🏢 Caso de Estudio: "El Carrito de Compras Fantasma"

**Contexto:** Un usuario añade un producto al carrito, navega a otra página y el carrito está vacío.

**Análisis de Ingeniería:**
*   **El Error:** El desarrollador junior usó una variable simple `$carrito` en un script PHP.
*   **La Realidad:** PHP es "stateless" (sin estado). Cuando el script termina de ejecutarse (milisegundos), todas las variables mueren. La memoria se libera.
*   **La Solución:** Se necesita persistencia.
    *   *Corto plazo:* Sesiones (`$_SESSION`) o Cookies.
    *   *Largo plazo:* Base de Datos (MySQL).
*   **Lección:** Entender el ciclo de vida de PHP es más importante que memorizar funciones.

### 🛠️ Laboratorio de Ingeniería

**Reto: El Procesador de Nómina**

Crea un sistema simple que:
1.  Defina una estructura de datos (Array Multidimensional) con 5 empleados:
    *   `['nombre' => 'Ana', 'salario_base' => 3000, 'ventas' => 5]`
2.  Implemente lógica de negocio:
    *   Si `ventas > 10`, bono del 10%.
    *   Si `ventas > 5`, bono del 5%.
3.  Genere una salida HTML limpia (una tabla) mostrando el desglose.
4.  **Requisito de Calidad:** Usa tipado estricto (`declare(strict_types=1);`) y valida que los salarios no sean negativos.

---

## Contenidos Detallados

1.  **[Arquitectura Cliente-Servidor](./01_Entorno_y_Arquitectura/3.1_Arquitectura_Cliente_Servidor.md)**
    *   *Infraestructura:* Cómo Apache y PHP conversan para servir una petición.
2.  **[Sintaxis, Tipado y Variables](./02_Sintaxis_y_Tipado/3.2_Sintaxis_Tipado.md)**
    *   *Calidad:* Por qué el tipado fuerte evita desastres financieros.
3.  **[Arrays: Estructuras de Datos](./03_Estructuras_de_Datos/3.3_Arrays.md)**
    *   *Técnica:* Manejo eficiente de colecciones de datos en memoria.
