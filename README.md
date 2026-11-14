# Estado de Cuenta — Generador para correo (Cobranza MX)

Herramienta de una sola página (`index.html`, sin dependencias) para armar el estado de cuenta de un cliente y pegarlo en un correo.

## Cómo se usa
1. **Pega la cartera** copiada desde Excel (con encabezados: Razón Social, N° Docto, F Emisión, F Venc, Moneda, Total, Estado). Puede incluir varios clientes. Columnas opcionales: RFC, Abono, Fecha Abono, Saldo.
2. **Elige el cliente**, escribe su RFC (se recuerda en el navegador) y revisa la fecha de corte (por defecto, hoy).
3. **Revisa las facturas**: desmarca las que no quieras incluir. En las **ABONADAS** escribe el monto abonado y la fecha del abono; el saldo se calcula solo.
4. **Copiar para pegar en el correo** → pega en Outlook/Gmail.

El correo separa automáticamente **facturas vencidas** (con días de atraso) y **facturas vigentes**, resalta las abonadas (total, abonado, fecha de abono y saldo pendiente), agrega un resumen de saldo por moneda y los datos de pago.

## Publicar en GitHub Pages
1. Crea un repositorio y sube `index.html` y este `README.md`.
2. En el repo: **Settings → Pages → Build and deployment → Deploy from a branch**, rama `main`, carpeta `/ (root)`.
3. Comparte la URL `https://<usuario>.github.io/<repo>/` con la ejecutiva.

> Los datos de la cartera **no se suben a ningún lado**: todo se procesa en el navegador. Si el repo es público, el código (incluidos los datos bancarios de `PAGO_DEFAULT`) será visible; esos datos ya se envían a clientes, pero puedes usar un repo privado si lo prefieres.

## Cambiar datos de pago
Edita la constante `PAGO_DEFAULT` al inicio del `<script>` en `index.html` (o en la sección "Datos de pago" de la página, que se guarda solo en ese navegador).
