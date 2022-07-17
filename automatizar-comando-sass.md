# Automatizar comando SASS

Para automatizar el comando de sass vamos a ayudarnos de node.

Lo primero será crear un package.json a través del comando `npm init -y` Esto iniciará un proyecto de node por defecto, si queréis más información acerca de los que es y para qué sirve el package.json os dejo aquí un vídeo donde está todo explicado a fondo. https://www.youtube.com/watch?v=7HTfEG_sj9s

Una vez que tenemos generado nuestro package.json, en la propiedad `scripts` escribiremos el comando que queremos ejecutar a traves de una `key` y un `value`. La key puede ser el nombre que más os cuadre, yo voy a poner `"sass"`, y como value pondremos nuestro comando:
`"sass --watch --no-source-map ./src/scss/styles.scss ./dist/css/styles.css"`

Ahora cada vez que queramos arrancar la vigilancia de nuestro sass lo único que tendremos que escribir será `npm run sass`
