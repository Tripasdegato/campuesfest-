# Bugs de CampusFest

Los ocho defectos descritos abajo están corregidos en esta rama. Sus pruebas de regresión están activas en `tests/bugs.test.js`.

Para reproducir la solución, ejecuta `npm test`; todas las pruebas deben pasar. Las pistas de abajo describen qué debía corregirse en cada caso.

> No cambies lo que la prueba espera. El marcador usa **pruebas oficiales** sobre tu sitio publicado: si “arreglas” la prueba en lugar del código, no suma puntos.

| Bug | Defecto corregido | Implementación | Puntos |
|---|---|---|---|
| **BUG-0 · guiado** | Los cupos disponibles nunca son negativos y un evento sobrevendido cuenta como lleno | `src/js/logic.js` → `spotsLeft` | 20 |
| **BUG-1** | Los eventos se ordenan cronológicamente, incluso al cambiar de mes | `src/js/logic.js` → `sortByDate` | 10 |
| **BUG-2** | La búsqueda ignora acentos y mayúsculas | `src/js/logic.js` → `matchesSearch` | 10 |
| **BUG-3** | Las fechas muestran el mes correcto | `src/js/logic.js` → `formatShortDate` | 10 |
| **BUG-4** | Los eventos sin costo muestran **“Gratis”** | `src/js/logic.js` → `formatPrice` | 10 |
| **BUG-5** | El número de lugares usa singular o plural correctamente | `src/js/logic.js` → `spotsLabel` | 10 |
| **BUG-6** | Los eventos que ya pasaron muestran **“Finalizado”** | `src/js/logic.js` → `countdownLabel` | 10 |
| **BUG-7** | El texto secundario cumple el contraste mínimo 4.5:1 | `src/css/styles.css` → `--text-muted` | 10 |

## Pistas de implementación

<details><summary>BUG-0</summary>Un número nunca debe bajar de 0. Busca <code>Math.max</code>.</details>
<details><summary>BUG-1</summary>Se compara el texto “dd/mm”. Las fechas originales vienen como “2026-11-24”: ese formato sí se ordena bien como texto.</details>
<details><summary>BUG-2</summary>“ó” y “o” son letras distintas. Busca <code>normalize('NFD')</code> para quitar acentos.</details>
<details><summary>BUG-3</summary>En JavaScript, <code>getMonth()</code> empieza en 0 (enero = 0).</details>
<details><summary>BUG-4</summary>Si el precio es 0, regresa otra palabra.</details>
<details><summary>BUG-5</summary>Cuando queda exactamente 1, la palabra va en singular.</details>
<details><summary>BUG-6</summary>¿Qué pasa cuando <code>days</code> es negativo?</details>
<details><summary>BUG-7</summary>El texto normal necesita un contraste de al menos 4.5:1 contra el fondo blanco. Prueba un gris más oscuro y revisa el mensaje de la prueba.</details>
