# Órdenes de Trabajo — DMTH

Incluye una planilla nueva, el backend de Google Apps Script y la web.

## 1. Preparar la planilla

1. Subí `ordenes-de-trabajo-google-sheets.xlsx` a Drive y abrilo con Google Sheets.
2. Conservá los nombres de las pestañas: `SOPORTE`, `PERSONAL`, `LISTAS` e `IMPRESION`.
3. En `LISTAS` podés agregar nuevos orígenes, destinos, móviles, secciones y estados. Los desplegables de `SOPORTE` los toman automáticamente.
4. En `PERSONAL` se carga y actualiza el personal disponible para formar cuadrillas.

## 2. Conectar Google Apps Script

1. Dentro de la planilla: **Extensiones > Apps Script**.
2. Reemplazá el contenido por `Code.gs` y guardá.
3. Implementá como **Aplicación web**, ejecutando como tu cuenta y con acceso según la política de SIPROSA.
4. Copiá la dirección que termina en `/exec`.

## 3. Publicar la web en Vercel

1. Abrí `index.html` y reemplazá `PEGAR_URL_DEL_WEB_APP_DE_APPS_SCRIPT_AQUI` por la URL `/exec` anterior.
2. Subí `index.html` a un repositorio nuevo de GitHub.
3. Importá ese repositorio en Vercel y desplegalo.

La web principal incluye carga de órdenes, selección de cuadrilla desde `PERSONAL`, alta de valores nuevos para las listas, buscador, edición y una impresión con original y duplicado.

## Módulo nuevo: retiros de depósito

- `retiros-deposito.html` es una página independiente para solicitar librería, higiene personal, limpieza y otros insumos. Subila al mismo repositorio de GitHub junto a `index.html`.
- El registro queda en `RETIROS_DEPOSITO`; no afecta ni utiliza las órdenes de trabajo.
- `LISTAS_RETIRO` permite agregar sectores, categorías, unidades y estados.
- `IMPRESION_RETIRO` contiene original y duplicado compactos para imprimir en una sola hoja A4. La página también permite **Imprimir > Guardar como PDF**.

Para guardar como PDF, usá el botón **Imprimir** y elegí **Guardar como PDF** en el cuadro de impresión del navegador.

> Nota: según la política de seguridad de Google, una web externa puede requerir que el Web App de Apps Script sea accesible para los usuarios que la usan. Si el navegador bloqueara la comunicación desde Vercel, la solución más directa es usar la misma aplicación desde la URL de Apps Script o crear un proxy seguro en Vercel.
