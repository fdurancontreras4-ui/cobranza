# Estado de Cuenta — Generador para correo (Cobranza MX)

Herramienta de una sola página (`index.html`, sin dependencias) para armar el estado de cuenta de un cliente y pegarlo en un correo.

## Cómo se usa
1. **Pega la cartera** copiada desde Excel (con encabezados: Razón Social, N° Docto, F Emisión, F Venc, Moneda, Total, Estado y opcionalmente Monto Pagado, Fecha de Pago, Banco, RFC, Saldo). Las facturas CANCELADAS o pagadas por completo quedan fuera.
2. **Marca las razones sociales del cliente** (busca, por ejemplo, "EULEN" y pulsa "Marcar las que se ven"), escribe el RFC de cada una (se recuerda en el navegador) y revisa la fecha de corte.
3. **Revisa las facturas**: desmarca las que no quieras incluir. En las **ABONADAS** escribe el monto abonado y la fecha del abono; el saldo se calcula solo.
4. **Copiar para pegar en el correo** → pega en Outlook/Gmail.

El correo separa **facturas vencidas** y **vigentes** (el título muestra cuántas son y el monto total) y, dentro de cada una, arma **una tabla por razón social** con su subtotal. Las abonadas muestran total, abonado, fecha de abono y saldo pendiente. Al final hay un resumen de saldo por razón social y los datos de pago.

## Publicar en GitHub Pages
1. Crea un repositorio y sube `index.html` y este `README.md`.
2. En el repo: **Settings → Pages → Build and deployment → Deploy from a branch**, rama `main`, carpeta `/ (root)`.
3. Comparte la URL `https://fdurancontreras4-ui.github.io/cobranza/` con la ejecutiva.

> Los datos de la cartera **no se suben a ningún lado**: todo se procesa en el navegador. Si el repo es público, el código (incluidos los datos bancarios de `PAGO_DEFAULT`) será visible; esos datos ya se envían a clientes, pero puedes usar un repo privado si lo prefieres.

## Cambiar datos de pago
Edita la constante `PAGO_DEFAULT` al inicio del `<script>` en `index.html` (o en la sección "Datos de pago" de la página, que se guarda solo en ese navegador).
