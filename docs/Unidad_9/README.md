# Fase 4: Arquitectura de Software

> **Objetivo de la Fase:** Construir aplicaciones, no solo páginas web.

## Unidad 9: El Patrón MVC (Modelo-Vista-Controlador)

Si la POO son los ladrillos, el MVC es el plano del edificio. Es el patrón arquitectónico que separa las responsabilidades para que el código sea mantenible, escalable y testeable.

### 🗺️ Mapa de Competencias

| Nivel | Habilidad | Concepto Clave | Aplicación Real |
| :--- | :--- | :--- | :--- |
| **Junior** | Entender la separación | M-V-C | Saber dónde poner una consulta SQL (Modelo) y dónde poner HTML (Vista). |
| **Mid** | Implementar flujo de datos | Routing -> Controller -> View | Crear una nueva página en un framework como Laravel o Symfony. |
| **Senior** | Diseñar APIs | JSON Responses | Crear un backend desacoplado para una App Móvil. |

### 🏢 Caso de Estudio: "El Monolito Indomable"

**Contexto:** Un sistema legado tiene un archivo `index.php` de 5,000 líneas que mezcla consultas SQL, lógica de validación, envío de emails y código HTML.

**El Problema:**
*   Para cambiar el color de un botón, el diseñador puede romper accidentalmente la consulta SQL.
*   Es imposible hacer pruebas automáticas.
*   Nadie quiere trabajar en ese proyecto.

**La Solución (Refactorización a MVC):**
1.  **Modelo:** Se extrae toda la lógica de base de datos a clases `User`, `Product`.
2.  **Vista:** Se mueve todo el HTML a plantillas limpias en la carpeta `views/`.
3.  **Controlador:** Se crea una clase que recibe la petición, llama al Modelo y carga la Vista.
4.  **Resultado:** El diseñador trabaja en las Vistas sin riesgo. El backend trabaja en los Modelos. El código es limpio y profesional.

### 🛠️ Laboratorio de Ingeniería

**Reto: El Mini-Framework**

Construirás tu propio framework MVC desde cero (sin librerías) para entender la magia:
1.  **Router:** Un script que lea la URL (`/producto/ver/5`) y decida qué hacer.
2.  **Controller:** Una clase `ProductoController` con el método `ver($id)`.
3.  **Model:** Una clase simulada que devuelva datos.
4.  **View:** Un archivo PHP simple que muestre los datos en HTML.

---

## Contenidos Detallados

1.  **[Controlador de Modelos](./01_Controlador_Modelos/README.md)**
    *   *Orquestación:* Cómo el controlador conecta los datos con la interfaz.
2.  **[Controlador de Operaciones Genéricas](./02_Controlador_Generico/README.md)**
    *   *Eficiencia:* Creando un `BaseController` y `BaseModel` para no repetir código (DRY).
3.  **[JSON (JavaScript Object Notation)](./03_JSON/README.md)**
    *   *Interoperabilidad:* Cómo convertir nuestros objetos PHP en datos que JavaScript puede entender.
