# Condicionales

Es algo habitual que en SASS tengamos un bloque de código que en función de una condición actue de una forma u otra.

Lo que se evalúa en la condición debe resolverse con `true` o `false` y en función del tipo de dato tenemos distintos operadores

- Si el valor que queremos evaluar es un `boolean` sólo es necesario escribir el nombre de la variable.
- Si el valor es numérico podemos evaluar igualdad con `==`, si es mayor con `>`, si es menor con `<`, si es mayor o igual con `>=` y si es menor o igual con `<=`
- Para el resto de valores sólo podemos evaluar si es igual con `==` o si es distinto con `!=`

Para controlar esa condición tenemos la regla `@if` y la sintaxis es:

```
  @if condición{
    //código a ejecutar
  }

  $rounded: true;

  .img {
    width: 200px;
    height: 200px;

    @if $rounded {
        border-radius: 50%;
    }
  }
```

Es posible que queramos evaluar más de una condición para ejecutar el código dentro del condicional, para ello tenemos dos palabras clave `and` y `or`, si usamos un `and` se deben cumplir todas las condiciones, si usamos `or` sólo se debe cumplir una de ellas.

```
  $rounded: true;
  $color: red;

  .img {
    width: 200px;
    height: 200px;

    @if $rounded and color == blue {
        border-radius: 50%;
    }
  }
```

También podemos establecer distintas condiciones para ejecutar distintas partes del código, para ello tenemos `@else if` y `@else`

En el caso de `@else if` funciona exáctamente igual que un `@if` la única diferencia es que debe usarse seguido de un `@if`, ya que es un segundo condicional, después de un `@if` podemos poner tantos `@else if` como necesitemos.

```
  $color: red;

  .card {
    @if $color == red {
      width: 100px;
    } @else if $color == green {
      width: 150px;
    }
  }
```

El `@else` se utiliza como última opción, por eso no lleva condición, puede ponerse después de un `@if` o después del último `@else if` que hayamos puesto, en el caso de que ninguna condición se cumpla, se ejecutará el código del `@else`

```

  $color: red;

  .card {
    @if $color == red {
      width: 100px;
    } @else {
      width: 200px;
    }
  }
```

También tenemos una versión del `@if` que sería similar a un operador ternario en programación, sirve para asignar un sólo valor de forma sencilla y sin tener que crear una estructura de `@if @else`.

La sintaxis es:

```
  if(condición, true, false)

  $rounded:true;

  .card{
    border-radius: if($rounded, 20px, 0)
  }
```
