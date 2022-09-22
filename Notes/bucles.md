# Bucles

Un bucle se utiliza cuando queremos repetir la misma acción varias veces, en SASS tenemos tres tipos de bucles:

## Bucle @for

Este bucle sirve para dar n vueltas, necesita 3 valores para ejecutarse, una variable que actuará de índice, un valor numérico desde donde empezará el bucle y otro donde terminará. Tenemos 2 opciones para crear este bucle:

```SCSS
  @for $index from start to end {
      // Código a ejecutar
  }

  @for $index from start through end {
      // Código a ejecutar
  }
```

La única diferencia entre estas dos sintaxis es que si se usa `to` el número final se excluye y si se usa `through`, el número final se incluye.

## Bucle @each

Este bucle sirve para recorrer listas o mapas, es ideal para estilos que se repiten con una pequeña variación.

```SCSS
  $colors: red, blue, green, yellow

  @each $color in $colors {
    .#{$color} {
      color:$color
    }
  }

  $colors-map: (
    primary: red,
    secondary: blue,
    alernative: green,
  );

@each $key, $color in $colors-map {
  .#{$key} {
    color: $color;
  }
}
```

También existe un bucle `@while` pero su uso es muy reducido y para casos muy avanzados y complejos, además en la propia documentación recomiendan usar `@for` o `@each` en su lugar siempre que sea posible.
[https://sass-lang.com/documentation/at-rules/control/while]
