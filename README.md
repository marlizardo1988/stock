# Control de Stock — Legion S.A.
## Aplicación PWA para control físico de inventario

---

## ¿Qué archivos hay?
- `index.html` — La aplicación completa
- `manifest.json` — Configuración para instalar como app
- `sw.js` — Service Worker para funcionamiento offline
- `README.md` — Este archivo

---

## ¿Cómo publicar la app en Internet? (Gratis)

La app necesita estar en un servidor web para que los celulares puedan acceder.
La opción más simple y GRATUITA es **GitHub Pages** o **Netlify**.

### Opción A: Netlify (más fácil, 5 minutos)

1. Crear cuenta gratis en https://netlify.com
2. Entrar al dashboard → "Add new site" → "Deploy manually"
3. Arrastrar la CARPETA `stock-control` al área de deploy
4. Netlify genera una URL del tipo: `https://amazing-name-123.netlify.app`
5. ¡Listo! Compartir esa URL con el equipo

### Opción B: GitHub Pages

1. Crear cuenta en https://github.com
2. Crear repositorio nuevo (público)
3. Subir los 3 archivos (index.html, manifest.json, sw.js)
4. Ir a Settings → Pages → Source: main branch
5. URL quedará: `https://tuusuario.github.io/nombre-repo`

---

## ¿Cómo instalar la app en el celular?

### Android (Chrome)
1. Abrir la URL de la app en Chrome
2. Tocar los 3 puntitos (menú) → "Agregar a pantalla de inicio"
3. Confirmar → La app aparece como ícono en el celular

### iPhone (Safari)
1. Abrir la URL en Safari (NO Chrome en iPhone)
2. Tocar el botón compartir (cuadrado con flecha)
3. "Agregar a pantalla de inicio" → Agregar
4. La app aparece como ícono en el celular

---

## Flujo de uso

1. **Cargar PDF** → Subir el informe "Saldos de Stock" exportado del sistema contable
2. **Seleccionar materiales** → Buscar y elegir los artículos a controlar
3. **Conteo físico** → Para cada artículo: ingresar cantidad contada y comentario
4. **Reporte** → Ver resumen de diferencias y exportar a Excel

---

## Notas técnicas

- El parseo del PDF funciona directamente en el navegador (sin servidor)
- Los datos se mantienen en memoria durante la sesión
- Varias personas pueden usar la app simultáneamente desde sus propios celulares
- Para compartir resultados entre personas → cada uno exporta su Excel
- Funciona sin internet una vez instalada (service worker)

---

## Requerimientos del PDF
El PDF debe ser el informe "Saldos de Stock (Lote/Serie)" del sistema Legion/Crystal Reports.
Los artículos deben tener el formato: CÓDIGO (6 dígitos) + DESCRIPCIÓN + números de Entrada/Salida/Saldo.
