<h1 align="center">
  <br>
  <img src="https://raw.githubusercontent.com/ByManGe1/GradientBG-Web/main/image.png" alt="" width="500"></a>
  <br>
</h1>

### Evento DOMContentLoaded:

```javascript
document.addEventListener("DOMContentLoaded", () => {
```
-  Este evento se dispara cuando el contenido del DOM ha sido completamente cargado.

### Selección del elemento interactivo:

```javascript
const interBubble = document.querySelector(".interactive");
```
-  Se selecciona el primer elemento con la clase "interactive" y se almacena en la variable interBubble.

### Variables de posición:

```javascript
let curX = 0;
let curY = 0;
let tgX = 0;
let tgY = 0;
```
-  Se declaran variables para representar las coordenadas actuales (curX y curY) y las coordenadas objetivo (tgX y tgY) del elemento interactivo.

### Función de movimiento:

```javascript
function move() {
   curX += (tgX - curX) / 20;
   curY += (tgY - curY) / 20;
   interBubble.style.transform = `translate(${Math.round(curX)}px, ${Math.round(curY)}px)`;
   requestAnimationFrame(() => {
      move();
   });
}
```
-  La función move calcula las nuevas coordenadas actuales (curX y curY) basándose en las coordenadas objetivo (tgX y tgY) de manera suave mediante un efecto de interpolación.
-  Se utiliza requestAnimationFrame para realizar una animación más eficiente y suave.

### Evento de ratón:

```javascript
window.addEventListener("mousemove", (event) => {
   tgX = event.clientX;
   tgY = event.clientY;
});
```
-  El evento de ratón (mousemove) actualiza las coordenadas objetivo (tgX y tgY) con las coordenadas del ratón en la pantalla.

### Inicio del movimiento:

```javascript
move();
```
- Se llama a la función move para iniciar el seguimiento del ratón por parte del elemento interactivo.


