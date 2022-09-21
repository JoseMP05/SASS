# Operadores

En `SASS` podemos realizar operaciones matemáticas igual que en `CSS`, pero en `SASS` tenemos la ventaja de que en la mayoría de los casos no necesitamos usar la función `calc()`

Podemos usar el operador `+` para sumar y para concatenar un valor con un string, `-` para restar, `*` para multiplicar y `%` para sacar el módulo de una división.

Si tenemos un valor numérico sin medida en una variable, podemos interpolar esa variable y añadirle la medida siempre y cuando la medida no sea en `%`

```
  $size: 20;

  .card {
    width: #{$size}px;
  }
```

Este código dará como resultado `width:20px`, esto funcionará con cualquier medida salvo con porcentaje.

Si queremos poner el valor en porcentaje, la forma más cómoda de hacerlo es concatenar el símbolo de `%` como si fuera un string.

```
  $size: 20;

  .card {
    width: #{$size} + '%';
  }
```

Es importante interpolar la variable para que la compilación no salga como string `width:"20%"`

Si queremos dividir un valor entre otro no podemos hacerlo directamente, SASS ha extraido la función de división a lo que denominan `built in modules`, son como librerías extra que tiene SASS para realizar algunas funciones.

```
  @use 'sass:math';

  $size: 20;

  .card {
    width: math.div($size, 2) + px;
  }
```

Si necesitamos dividir un valor entre otro es mucho más cómodo utilizar la función `calc()` nativa de CSS

```
  $size: 20;

  .card {
    width: calc($size / 2) + px;
  }
```

Librería math de SASS https://sass-lang.com/documentation/modules/math
