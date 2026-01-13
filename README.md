# 🚀 Sistema de Ingeniería de Sistemas Asistido (SISA)
> **Perfil:** Catedrático Senior 2026 | **Enfoque:** Análisis, Diseño y Complejidad.

## 📊 Roadmap de Aprendizaje e Interactividad
A continuación, se presenta la arquitectura del conocimiento. Cada unidad incluye un **Laboratorio de Código** ejecutable.


Breve descripción
------------------
SISA es un repositorio docente modular en Markdown diseñado para la enseñanza de Ingeniería de Software. Contiene unidades teóricas, laboratorios prácticos y diagramas (Mermaid) organizados dentro de la carpeta `docs/`. El sitio está diseñado para publicarse con MkDocs (tema Material) y tiene un pipeline de despliegue en GitHub Actions.

Herramientas del Entorno
------------------------
Para que este proyecto sea interactivo, se recomiendan las siguientes herramientas/extensiones:

1. **Prettier** — Consistencia visual y formateo (recomendado para edición local).  
2. **Mermaid Preview / Editor** — Visualizar y editar diagramas Mermaid.  
3. **REST Client** — Probar URIs y endpoints desde la edición en VS Code.

Quickstart (local)
------------------
Instala dependencias y levanta el servidor de desarrollo local:

```powershell
pip install -r requirements.txt
mkdocs serve
```

Para construir el sitio estático:

```powershell
mkdocs build
```

Estructura clave
-----------------
- `docs/` — Contenido por unidad (teoría, laboratorios, diagramas).  
- `mkdocs.yml` — Configuración del sitio (tema, navegación, extensiones).  
- `requirements.txt` — Dependencias para MkDocs y Material.  
- `.github/workflows/deploy.yml` — Pipeline CI/CD para despliegue automático.  

Objetivos y público
-------------------
- **Propósito:** Proveer material didáctico trazable y reproducible para cursos de Ingeniería de Software.  
- **Público:** Estudiantes, docentes y profesionales que buscan referencia modular y laboratorios prácticos.

Cambios recientes relevantes
---------------------------
- Se añadió la sección "🛡️ Integridad Académica y Fuentes" en `docs/index.md`.  
- Se normalizaron tablas Markdown y se validaron bloques Mermaid en varias páginas de la Unidad 2 para garantizar un render consistente con MkDocs.

Cómo contribuir
----------------
- Edita contenido bajo la carpeta `docs/` y abre Pull Requests.  
- Mensajes de commit: usa el formato `docs: <breve descripción>` para cambios en la documentación.  

Soporte y verificación
----------------------
Si `mkdocs serve` falla (exit code 1), copia el log del servidor y compártelo; con gusto diagnostico la causa (configuración, plugin o bloqueo de puerto).

---

Copyright © 2026 Alonzo Centeno. Todos los derechos reservados.