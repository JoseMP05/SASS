# Content

La directiva content nos permite añadir todo el código CSS que necesitemos en el mixin , esto es muy útil para cuando sólo queremos definir en el mixin la estructura base y después añadir todo lo que necesitemos.

Para utilizarlo sólo tenemos que incluir @content dentro de nuestro mixin en el punto donde queremos que se añada el código extra.

Un ejemplo muy común son los pseudo elementos, habitualmente los pseudoelementos **::before** y **::after** tienen unos valores que se repiten.

```SCSS
@mixin pseudo {
  content : '';
  position: absolute;
  @content;
}
```

## @content para media queries

Escribir media queries es algo bastante pesado si lo tenemos que hacer muchas veces en el mismo sitio web , para
estos casos podemos usar **_@content_** y escribirlo una sola vez.

Si nosotros queremos añadir la media query hover , podemos crear este mixin y no tenemos que volver a preocuparnos de la sintaxis.

```SCSS
@mixin hover {
  @media (hover: hover) {
    @content;
}
 }
```

Para media queries responsive también podemos usar la directiva **_@content_**

La versión más simple la podemos escribir

```SCSS
@mixin responsive ($breakpoint) {
  @media screen and (min-width: $breakpoint ) {
    @content;
}
 }```

Pero podemos hacer esto mucho más intuitivo. Sabiendo que los estilos
fuera de la media query serán los de móvil, podemos crear un mapa con
el resto de media queries.

```SCSS
$breakpoints: (
  tablet: 640px,
  laptop: 1024px,
  desktop: 1440,
);
@mixin responsive ($key) {
  @media screen and (min-width: map-get($breakpoints, $key)){
    @content ;
 }```
