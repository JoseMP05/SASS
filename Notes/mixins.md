# Mixins

Los `mixins` en SASS son estructuras de código reutilizables, dentro pueden tener todo lo que hemos visto a lo largo del curso.
La forma más simple para declarar un `mixin` es `@mixin nombre{código del mixin}`, de esta forma siempre que queramos reutilizar ese código lo tendremos ahí disponible.

Un uso frecuente para los `mixins` es el reseteo de listas, las listas por defecto tienen unos valores que habitualmente queremos borrar.

```
  @mixin reset-list{
    list-style:none;
    padding-left:0;
    margin-top:0;
    margin-bottom:0
  }
```

Cuando queramos reutilizar ese pedazo de código, sólo tendremos que poner `@include reset-list` dentro de nuestro selector.

```
  @mixin reset-list {
    list-style: none;
    padding-left: 0;
    margin-top: 0;
    margin-bottom: 0;
  }

  .menu {
    @include reset-list;
  }
```

## Mixin con parámetros definidos

Para los casos en los que el `mixin` necesita personalización en lugar de únicamente valores predefinidos, tenemos la opción de pasarle parámetros para que se sustituyan en el código.

Para pasarle parámetros a un mixin tendremos que poner entre paréntesis todos los valores que queramos pasarle externamente.

```
  @mixin button($color, $bg) {
    color: $color;
    background-color: $bg;
  }
```

Además, si queremos darle un valor por defecto a ese parámetro se lo pondremos así:

```
  @mixin button($color:red, $bg:#333) {
    color: $color;
    background-color: $bg;
  }
```

De esta forma si no le pasamos parámetros establecerá los colores por defecto que le hemos asignado.

## Mixin con parámetros múltiples

En algunas situaciones es posible que necesitemos un mixin y no tengamos claro el número de parámetros que necesitamos, si creamos un mixin que sea para asignar border-radius, en algunos casos le pasaremos un sólo parámetro, en otros dos, tres o incluso 8 parámetros.

Para estos casos tenemos el operador de tres puntos `...`, con este operador nuestro mixin quedaría así.

```
  @mixin radius($radius...) {
    border-radius: $radius;
  }
```

De esta forma dará igual cuantos argumentos pasemos.

```
  .card {
    @include radius(4px 10px);
  }

  .card-2 {
    @include radius(4px 10px 20px 8px);
  }
```

En la compilación se escribiran todos los argumentos

```
  .card {
    border-radius: 4px 10px;
  }

  .card-2 {
    border-radius: 4px 10px 20px 8px;
  }
```
