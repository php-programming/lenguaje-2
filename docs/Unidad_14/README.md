# Fase 5: Full Stack y Entrega de Valor

> **Objetivo de la Fase:** Crear experiencias de usuario fluidas y productos finales profesionales.

## Unidad 14: Interactividad del Cliente (Frontend Moderno)

El usuario no ve tu código PHP ni tu base de datos; ve tu interfaz. En esta unidad, aprenderemos cómo JavaScript interactúa con nuestro Backend para crear aplicaciones dinámicas que no requieren recargar la página constantemente.

### 🗺️ Mapa de Competencias

| Nivel | Habilidad | Concepto Clave | Aplicación Real |
| :--- | :--- | :--- | :--- |
| **Junior** | Manipular HTML con JS | DOM | Validar un formulario antes de enviarlo. |
| **Mid** | Comunicación Asíncrona | AJAX / Fetch | Cargar nuevos posts al hacer scroll (Infinite Scroll). |
| **Senior** | Arquitectura SPA | State Management | Construir una aplicación tipo Gmail o Trello. |

### 🏢 Caso de Estudio: "La Espera Eterna"

**Contexto:** Un sistema de reportes tarda 10 segundos en generar un PDF.

**El Problema (Web Clásica):**
*   El usuario hace clic en "Descargar".
*   El navegador se queda en blanco ("cargando...") durante 10 segundos.
*   El usuario piensa que se trabó y hace clic 20 veces más, colapsando el servidor.

**La Solución (AJAX/Fetch):**
1.  **Interacción:** El usuario hace clic. JavaScript intercepta el evento.
2.  **Feedback Inmediato:** JS muestra un "spinner" o barra de progreso instantáneamente.
3.  **Segundo Plano:** JS envía la petición al servidor asíncronamente. El usuario puede seguir navegando.
4.  **Notificación:** Cuando el servidor termina, JS recibe la respuesta y muestra "¡Tu reporte está listo!".

### 🛠️ Laboratorio de Ingeniería

**Reto: El Buscador en Tiempo Real**

1.  **Backend:** Crea un endpoint `api/buscar.php` que reciba un término (`?q=laptop`) y devuelva JSON con productos.
2.  **Frontend:** Crea un input de texto.
3.  **Lógica:** Usa el evento `input` en JS para detectar lo que el usuario escribe.
4.  **Conexión:** Usa `fetch()` para consultar tu API en cada tecla (¡Bonus si implementas "Debounce" para no saturar el servidor!).
5.  **Renderizado:** Recibe el JSON y dibuja la lista de resultados debajo del input dinámicamente.

---

## Contenidos Detallados

1.  **[El DOM y JavaScript](./01_DOM_JavaScript/14.1_DOM.md)**
    *   *Interfaz:* Cómo JavaScript ve y modifica el HTML.
2.  **[Fundamentos de AJAX](./02_Fundamentos_AJAX/14.3_AJAX.md)**
    *   *Comunicación:* El protocolo para hablar con el servidor sin recargar.
