# Anidamiento

El nesting o anidamiento en SASS es una de las características más famosas que tiene, el problema es que genera muchas malas prácticas.

El nesting consiste en poder meter selectores dentro de selectores, lo cual hace que la escritura y el mantenimiento sean más ágiles.

```text
.menu {
  display: flex;
  list-style: none;
  flex-direction: column;
  align-items: center;

  @media screen and (min-width: 768px) {
    flex-direction: column;
    justify-content: space-between;
  }
}
```

El gran problema que se genera con esta opción es el anidamiento múltiple

Si esto es mala práctica en CSS

```text
    .menu{
        display:flex;
    }

    .menu li{
        color:red;
    }

    .menu li a{
        text-decoration:none;
    }
```

NO hagas esto en SASS

```text
  .menu {
    display: flex;
    li {
      color: red;
      a {
          text-decoration: none;
        }
      }
    }
```

Para evitar este tipo de problemas tenemos las metodologías para escribir CSS y SASS nos da la opción de utilizar el operador `&` para repetir al selector padre.

Si nosotros tenemos esta estructura en CSS

```text
  .menu{
    display:flex;
  }

  .menu__item{
    color:red;
  }

  .menu__link{
    text-decoration:none;
  }
```

Con SASS la podemos replicar así

```text
    .menu {
      display: flex;

      &__item {
          color: red;
      }

      &__link {
          text-decoration: none;
      }
    }
```

Al usar el operador `&` tenéis que tener cuidado con los espacios, los espacios son sintaxis en `CSS` por lo que no es lo mismo poner `&:hover` que `& :hover`

Otra opción extra que tenemos para usar el anidamiento, es el anidamiento de propiedades, su uso no es muy famoso pero, nos ayuda a escribir menos y organizar mejor algunas sintaxis

```text
  .menu {
    border-bottom: {
      width: 2px;
      style: solid;
      color: red;
    }

    grid-template: {
      columns: 1fr auto 1fr;
      rows: repeat(3, 100px);
    }
}
```
