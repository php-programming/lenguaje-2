# Fase 3: Paradigmas y Modularidad

> **Objetivo de la Fase:** Dejar de escribir código que "funciona" para escribir código que "perdura".

## Unidad 7: Programación Orientada a Objetos (POO)

La POO no es una "forma elegante" de programar; es una estrategia de gestión de la complejidad. En sistemas con 100,000 líneas de código, la POO es lo único que evita que el proyecto colapse bajo su propio peso.

### 🗺️ Mapa de Competencias

| Nivel | Habilidad | Concepto Clave | Aplicación Real |
| :--- | :--- | :--- | :--- |
| **Junior** | Crear Clases y Objetos | Encapsulamiento | Modelar un `Usuario` con datos privados. |
| **Mid** | Reutilizar código | Herencia y Polimorfismo | Crear un sistema de `Pagos` que acepte `PayPal` o `Stripe` indistintamente. |
| **Senior** | Desacoplar sistemas | Interfaces e Inyección de Dependencias | Escribir código que sea fácil de testear y modificar. |

### 🏢 Caso de Estudio: "El Sistema de Notificaciones Rígido"

**Contexto:** Una startup envía alertas por Email. De repente, el CEO quiere enviar también SMS y Push Notifications.

**El Problema (Código Procedural):**
*   El código está lleno de `if ($tipo == 'email') { ... }`.
*   Para añadir SMS, hay que modificar 20 archivos.
*   Cada cambio rompe algo que ya funcionaba.

**La Solución (POO + Polimorfismo):**
1.  Definir una **Interfaz** `Notificable` con un método `enviar($mensaje)`.
2.  Crear clases `EmailNotificador`, `SMSNotificador`, `PushNotificador` que implementen la interfaz.
3.  El sistema principal solo sabe que tiene una lista de objetos `Notificable`. No le importa de qué tipo son. Simplemente llama a `->enviar()`.
4.  **Resultado:** Añadir un nuevo tipo de notificación (ej. WhatsApp) implica crear una nueva clase, sin tocar el código existente. Esto cumple el principio **Open/Closed** (Abierto a extensión, cerrado a modificación).

### 🛠️ Laboratorio de Ingeniería

**Reto: El Zoológico Polimórfico**

1.  **Diseño:** Crea una clase abstracta `Animal` con métodos como `comer()` y `dormir()`.
2.  **Especialización:** Crea clases hijas `Leon`, `Pinguino`, `Serpiente`.
3.  **Contrato:** Define una interfaz `Auditable` con el método `reportarEstado()`. Haz que solo algunos animales la implementen.
4.  **Ejecución:** Crea un script `Veterinario.php` que acepte un array de animales y ejecute sus métodos sin saber exactamente qué animal es cada uno.

---

## Contenidos Detallados

1.  **[Fundamentos de POO](./01_Fundamentos_POO/7.1_Definicion_POO.md)**
    *   *Paradigma:* Por qué modelamos el software como objetos.
2.  **[Propiedades Avanzadas](./02_Propiedades_Avanzadas/7.5_Interfaces.md)**
    *   *Arquitectura:* El poder de los contratos (Interfaces) y la organización (Namespaces).
