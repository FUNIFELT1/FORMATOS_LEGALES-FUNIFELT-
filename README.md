# 📄 Formatos Legales — Funifelt International

Sistema interactivo de documentos legales para colaboradores, estudiosos y demás integrantes adscritos a **Funifelt International** (NIT. 901017005).

Permite llenar, descargar e imprimir los formatos legales del proyecto directamente desde el navegador, sin necesidad de instalar nada.

---

## 📋 Documentos incluidos

| Documento | Código |
|---|---|
| Acuerdo de Confidencialidad, Propiedad Intelectual y No Uso de Código Fuente | `FI2016VPICF43` |
| Declaración Jurada de Destrucción de Datos y Borrado de Código Fuente | `FI2016VDD44` |

> El sistema está diseñado para escalar: se pueden agregar nuevos documentos al sidebar fácilmente (ver sección [Agregar nuevos documentos](#-agregar-nuevos-documentos)).

---

## 🚀 Cómo usarlo

1. Abre el archivo `index.html` en cualquier navegador (Chrome, Edge, Firefox).
2. En el menú lateral, selecciona el documento que necesitas llenar.
3. Completa los campos requeridos (marcados con `*`).
4. Usa los botones de la parte superior:
   - **🗑️ Limpiar** — borra los campos que hayas llenado.
   - **🖨️ Imprimir** — abre el diálogo de impresión del navegador.
   - **⬇️ Descargar PDF** — genera y descarga el documento en PDF con los datos ingresados (o líneas en blanco para llenar a mano si dejas campos vacíos).

No requiere conexión a internet para funcionar una vez descargado, salvo para cargar la librería de generación de PDF (`html2pdf.js` vía CDN).

---

## 🌐 Cómo subirlo a GitHub Pages

GitHub Pages permite publicar el archivo HTML como una página web accesible por enlace.

### Pasos

1. El archivo `index.html` ya está subido a este repositorio (lo subiste con ese nombre, lo cual es ideal).
2. Ve a **Settings** (Configuración) del repositorio.
3. En el menú lateral, entra a **Pages**.
4. En **Source**, selecciona la rama `principal` (o `main`) y la carpeta `/ (root)`.
5. Guarda. GitHub generará una URL del tipo:

   ```
   https://<usuario-o-organizacion>.github.io/FORMATOS_LEGALES-FUNIFELT-/
   ```

6. Espera 1-2 minutos a que se publique. La página quedará disponible públicamente en esa URL (si el repositorio es privado, necesitarás GitHub Pages con plan que lo soporte, o cambiar la visibilidad del repo).

> 💡 Como el archivo se llama `index.html`, GitHub Pages lo carga automáticamente desde la URL raíz del repositorio — no necesitas escribir el nombre del archivo en el enlace.

---

## 🔗 Cómo integrarlo a la página web de Funifelt

Para enlazar este sistema desde el sitio web oficial de Funifelt, hay dos opciones:

### Opción A — Enlace directo (recomendado, más simple)

Agrega un botón o enlace en el sitio web que apunte a la URL de GitHub Pages:

```html
<a href="https://<usuario-o-organizacion>.github.io/FORMATOS_LEGALES-FUNIFELT-/"
   target="_blank">
  Formularios Legales
</a>
```

Esto abre el sistema en una nueva pestaña, sin afectar el diseño del sitio principal.

### Opción B — Embebido con iframe

Si se prefiere que el sistema aparezca dentro de una sección del sitio web de Funifelt:

```html
<iframe
  src="https://<usuario-o-organizacion>.github.io/FORMATOS_LEGALES-FUNIFELT-/"
  width="100%"
  height="900px"
  style="border:none;">
</iframe>
```

> ⚠️ Si el sitio principal de Funifelt usa HTTPS (recomendado), la URL de GitHub Pages también debe ser HTTPS — esto es automático con GitHub Pages.

### Quién debe hacer este paso

La persona encargada del sitio web de Funifelt (`conjuntoankara.com` o el dominio correspondiente) debe:

1. Tomar la URL publicada en GitHub Pages.
2. Agregar el enlace o iframe en la sección correspondiente (por ejemplo, "Recursos para colaboradores" o "Documentos legales").
3. Publicar los cambios en el sitio.

---

## ➕ Agregar nuevos documentos

El sistema está construido para crecer. Para agregar un nuevo documento:

1. **Sidebar**: agrega un nuevo enlace dentro de `<nav class="sidebar-nav">`:
   ```html
   <a class="sidebar-link" data-doc="nuevo-doc" onclick="showDoc('nuevo-doc', this)">
     <span class="icon">📄</span> Nombre del Documento
   </a>
   ```

2. **Contenido**: agrega un nuevo bloque `<div class="document hidden" id="doc-nuevo-doc">` con la misma estructura que los documentos existentes (header, título, cuerpo, bloque de firmas, footer).

3. **JavaScript**: registra el nuevo documento en los objetos `docTitles` y `docFilenames` dentro del `<script>`:
   ```javascript
   docTitles['nuevo-doc'] = 'Título completo del documento';
   docFilenames['nuevo-doc'] = 'Funifelt_NombreDocumento_CODIGO';
   ```

---

## 🎨 Identidad visual

| Elemento | Valor |
|---|---|
| Azul oscuro (Pantone 7687 C) | `#1A428A` |
| Azul claro (Pantone 0821 C) | `#6FCFEB` |
| Blanco | `#FFFFFF` |

Marca de agua: isotipo de Funifelt en baja opacidad, repetido como fondo decorativo en cada documento.

---

## 🛠️ Tecnologías

- HTML5 + CSS3 (sin frameworks externos)
- [html2pdf.js](https://github.com/eKoopmans/html2pdf.js) (vía CDN) para exportación a PDF
- Sin backend ni base de datos — totalmente client-side

---

## 📞 Contacto

**Funifelt International**
NIT. 901017005
📧 Llámanos: +57 305 349 3168 (COL) · +31 6 8762 3593 (NL)

© 2026 Funifelt — Todos los derechos reservados.

---

👩‍💻 Desarrollo

Sistema desarrollado por Yefranlith Milagros Gil Hernández (@Ymilagros), estudiante de Ingeniería de Software en práctica empresarial en Funifelt.
