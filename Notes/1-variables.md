# Variables

## Creación y uso de variables SASS

El concepto de variable es el mismo que en cualquier otro lenguaje de programación, es un espacio donde almacenamos un dato que puede cambiar.

A diferencia de otros lenguajes, no podemos crear una variable sin inicializarla, es decir, tenemos que darle un valor al crearla.

Para crear la variable pondremos `$nombre: valor;`
En una variable podemos guardar cualquier valor válido en CSS y a diferencia de las variables CSS aquí no es necesario que estén dentro de un selector.

En SASS podemos usar las variables para guardar valores de propiedades y usarlas a lo largo de nuestro código, ese es el uso más habitual.

```
    $width:200px;

    .card{
        width: $width;
    }

```

Otro uso menos habitual es el de construir selectores con variables.

Para poder hacer esto necesitamos interpolar la variable, es decir, extraer el valor para escribirlo fuera de una propiedad, para interpolar pondremos `#{$variable}` y de esta forma extraemos el valor para usarlo como selector

```
    $red:red;
    $blue: blue;
    $green: green;

    .#{$red} {
        color: $red;
    }
```

También se podrían guardar propiedades CSS en una variable, pero eso es algo que no se hace casi nunca.

## Scope (ámbito)

El ámbito de una variable determina dónde podremos usarla, en sass tenemos ámbito local (dentro de un selector) y ámbito global (fuera de un selector)
