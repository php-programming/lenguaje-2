# Fase 1: Fundamentos de Ingeniería y Procesos

> **Objetivo de la Fase:** Transformar al estudiante de "codificador solitario" a "ingeniero de software colaborativo".

## Unidad 1: Gestión de Código Fuente (SCM)

En la industria, el código no es propiedad personal; es un activo corporativo que debe ser gestionado, auditado y protegido. Git no es una opción, es el estándar global.

### 🗺️ Mapa de Competencias

| Nivel | Habilidad | Herramienta | Aplicación Real |
| :--- | :--- | :--- | :--- |
| **Junior** | Guardar versiones y sincronizar | `git commit`, `git push` | Backup diario de trabajo. |
| **Mid** | Resolver conflictos y aislar tareas | `git branch`, `git merge` | Trabajar en una feature sin romper producción. |
| **Senior** | Diseñar flujos de trabajo y auditar | `git rebase`, `git bisect` | Mantener un historial limpio y encontrar bugs de regresión. |

### 🏢 Caso de Estudio: "El Bug del Viernes por la Tarde"

**Contexto:** Una empresa de pagos procesa millones de dólares. El viernes a las 5 PM, se despliega una actualización. A las 5:15 PM, los clientes reportan errores 500.

**Sin SCM Profesional:**
*   El equipo entra en pánico.
*   Nadie sabe qué cambió exactamente.
*   Se intenta "arreglar en caliente" en el servidor, empeorando la situación.
*   **Resultado:** 4 horas de caída, pérdida de confianza y dinero.

**Con Git y Estrategia (Lo que aprenderás):**
1.  **Identificación:** `git log` muestra quién desplegó qué.
2.  **Reversión Inmediata:** `git revert` deshace el cambio problemático en 1 minuto. El servicio se restaura.
3.  **Análisis Post-Mortem:** El equipo usa `git bisect` en un entorno de pruebas para encontrar la línea exacta del error sin presión.
4.  **Resultado:** 5 minutos de caída, incidente gestionado profesionalmente.

### 🛠️ Laboratorio de Ingeniería

Para aprobar esta unidad, no basta con leer. Debes completar el siguiente reto en tu máquina local:

1.  **Inicializar:** Crea un repositorio para un proyecto ficticio "SISA-Core".
2.  **Simular:** Crea una rama `feature/login`. Haz 3 commits simulando el desarrollo.
3.  **Conflicto:** Vuelve a `main`, crea un cambio en el mismo archivo (simulando a otro compañero) y haz commit.
4.  **Resolución:** Intenta fusionar `feature/login` en `main`. Git reportará conflicto. Resuélvelo manualmente y finaliza el merge.
5.  **Auditoría:** Usa `git log --graph --oneline` para visualizar tu historial de bifurcación y fusión.

---

## Contenidos Detallados

1.  **[Fundamentos de los Sistemas de Control de Versiones](./01_Fundamentos_VCS/README.md)**
    *   *Teoría:* Por qué "copiar y pegar carpetas" es negligencia profesional.
2.  **[Arquitectura Interna de Git](./02_Arquitectura_Git_Local/README.md)**
    *   *Técnica:* El modelo de tres estados (Working, Staging, Repository).
3.  **[GitHub como Plataforma Colaborativa](./03_GitHub_Plataforma_Colaborativa/README.md)**
    *   *Proceso:* Pull Requests, Code Review y CI/CD.
4.  **[Estrategias de Ramificación](./04_Estrategias_de_Ramificacion/README.md)**
    *   *Estrategia:* GitFlow vs. Trunk-Based Development.
5.  **[Bonus: Hoja de Ruta de Comandos](./05_Bonus_Hoja_de_Ruta_Comandos/README.md)**
    *   *Referencia:* Tu "navaja suiza" para el día a día.
