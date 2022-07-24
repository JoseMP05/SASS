# Tipos de datos

En SASS tenemos distintos tipos de datos:

- String: Los strings son cadenas de caracteres, pueden ir con comillas o sin ellas, tanto CSS como SASS no hacen diferenciación entre ellas. La única excepción es la propiedad content en los pseudoelementos `::after` y `::before` que SIEMPRE deben ir entre comillas.

  Si tenemos un valor entre comillas y necesitamos quitárselas existe la función `unquote()`, de igual forma, si el valor las necesita, pero no las tiene, existe la función `quote()`

```text
    $logo:assets/logos/logo.png

    $logo:'assets/logos/logo.png'
```

- Number: Los valores number son cualquier valor numérico con o sin unidad, excepto los colores.

```text
    $size: 200px;
    $size: 200;
    $size: 2rem;
```

- Color: El valor color es para colores en cualquier notación, keyword, rgb, etc.

```text
    $red: red;
    $dark: #333;
    $blue: rgb(51,187,255);
```

- Boolean: Como en cualquier otro lenguaje, admite los valore `true` y `false`.

```text
    $dev: true;
    $dev: false;
```

- List (array): Una lista es cualquier secuencia de valores (tipos de datos) separados por espacios o por comas.

  Para recuperar un valor de la lista, tenemos la función `nth(lista, index)`

```text
    $border: 1px solid red;
    $borders: '1px solid red', '5px dashed blue';
    $colors: red, blue, green;
    $sizes: 10px, 20, 30;
```

- Map (objeto): Un map es una estructura de datos formado por clave valor, igual que un objeto en otros lenguajes.

  Para recuperar un valor de un map, tenemos la función `map-get(map, key)`

```text
    $colors:(
        bg:#333,
        text: #666
    )
```
