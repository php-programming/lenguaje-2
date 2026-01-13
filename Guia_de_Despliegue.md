# Guía de Despliegue: Del Markdown a un Sitio Web con MkDocs y GitHub Pages

## Caso de Uso

**Escenario:** El proyecto SISA ha crecido hasta convertirse en un cuerpo de conocimiento detallado. Ahora se requiere que esta documentación esté disponible públicamente como un sitio web profesional, navegable y con un diseño limpio. El proceso de actualización del sitio debe ser automático cada vez que se actualiza el contenido.

**Requisitos de Sistema:**
1.  **Generación Automatizada:** El sitio web debe generarse directamente desde los archivos Markdown existentes sin intervención manual.
2.  **Alojamiento Gratuito y Versionado:** El sitio debe ser alojado utilizando una infraestructura robusta y gratuita, integrada con nuestro repositorio de Git.
3.  **Despliegue Continuo (CD):** Cada `push` a la rama `main` debe resultar en una actualización automática del sitio web público.

---

## Arquitectura de la Solución

Para cumplir con estos requisitos, hemos implementado una arquitectura de Despliegue Continuo utilizando tres componentes clave:

1.  **MkDocs:** Un generador de sitios estáticos que convierte nuestro contenido Markdown en un sitio HTML navegable.
2.  **GitHub Actions:** La plataforma de automatización que ejecuta el proceso de construcción.
3.  **GitHub Pages:** El servicio de alojamiento que sirve el contenido HTML generado al público.

### Diagrama de Flujo del Despliegue

```mermaid
graph TD
    A[Desarrollador hace 'git push' a 'main'] --> B{GitHub detecta el evento 'push'};
    B --> C(Se activa el Workflow de GitHub Actions);
    
    subgraph "Job de Despliegue en Runner Virtual"
        C1[1. Checkout del código fuente]
        C2[2. Instalar Python y dependencias de 'requirements.txt']
        C3[3. Ejecutar 'mkdocs gh-deploy']
        C4[4. El comando construye el sitio HTML]
        C5[5. Y hace 'push' del sitio a la rama 'gh-pages']
    end

    C --> C1 --> C2 --> C3 --> C4 --> C5;
    
    subgraph "Repositorio en GitHub"
        D[Rama 'main' (código fuente Markdown)]
        E[Rama 'gh-pages' (sitio web HTML compilado)]
    end

    A --> D;
    C5 --> E;

    subgraph "Servicio de GitHub Pages"
        F((Servidor Web)) -- "Sirve el contenido de" --> E
    end

    G[Visitante accede a la URL pública] --> F;

```

## Componentes del Sistema

### 1. `requirements.txt`
Este archivo es el **manifiesto de dependencias** de Python. Le dice a cualquier entorno (sea su máquina local o un runner de GitHub Actions) qué paquetes de software necesita este proyecto para funcionar.
-   `mkdocs`: El motor principal del generador de sitios.
-   `mkdocs-material`: Un tema popular y altamente configurable para MkDocs que hemos elegido para el SISA. Proporciona un diseño moderno, búsqueda integrada y soporte nativo para diagramas Mermaid.

### 2. `mkdocs.yml`
Este es el **archivo de configuración principal** para nuestro sitio de documentación.
-   `site_name`: El título que aparecerá en la barra de navegación del sitio.
-   `theme`: Especifica que estamos usando el tema `material`.
-   `markdown_extensions`: Aquí es donde habilitamos funcionalidades extendidas del Markdown. La configuración `pymdownx.superfences` es crucial, ya que activa el renderizado de bloques de código avanzados, incluyendo nuestros diagramas `mermaid`.

### 3. `.github/workflows/deploy.yml`
Este archivo define el **pipeline de Despliegue Continuo**. Le instruye a GitHub Actions sobre qué hacer cada vez que hay un `push` a la rama `main`. Los pasos clave son:
1.  **`checkout`**: Descargar el código.
2.  **`setup-python`**: Preparar el entorno de ejecución.
3.  **`pip install -r requirements.txt`**: Instalar las dependencias.
4.  **`mkdocs gh-deploy --force --clean`**: Este es el comando mágico. `mkdocs` construye el sitio HTML y, de forma transparente, lo empuja a la rama `gh-pages` en su repositorio.

## Cómo Trabajar con este Sistema

### Flujo de Trabajo Local
1.  **Instalación (solo una vez):**
    ```bash
    pip install -r requirements.txt
    ```
2.  **Desarrollo:**
    ```bash
    mkdocs serve
    ```
    Abra su navegador en `http://127.0.0.1:8000`. El sitio se recargará automáticamente cada vez que modifique y guarde un archivo `.md`.

### Flujo de Despliegue
1.  **Realice cambios:** Edite, añada o elimine archivos Markdown como lo ha hecho hasta ahora.
2.  **Confirme y suba los cambios:**
    ```bash
    git add .
    git commit -m "docs: Actualiza la documentación de la Unidad X"
    git push origin main
    ```
3.  **¡Eso es todo!** GitHub Actions se encargará del resto. Vaya a la pestaña "Actions" de su repositorio para ver el progreso del workflow. Unos minutos después, sus cambios estarán visibles en el sitio público.

## Próximos Pasos: Configuración Inicial en GitHub

Para que todo esto funcione, necesita realizar una configuración única en su repositorio de GitHub:

1.  **Vaya a la configuración de su repositorio (`Settings`).**
2.  **Navegue a la sección `Pages` en el menú de la izquierda.**
3.  **En la sección "Build and deployment", cambie la fuente (`Source`) a `Deploy from a branch`.**
4.  **Seleccione la rama `gh-pages` como la fuente y `/ (root)` como la carpeta.**
5.  **Guarde los cambios.**

GitHub le proporcionará la URL pública de su nuevo sitio de documentación.
