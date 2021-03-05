<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Svelte_Logo.svg/1200px-Svelte_Logo.svg.png" alt="Sve" style="zoom:60%;" />











# ¿Qué es Svelte?

Svelte es un framework dedicado principalmente a la creación de interfaces de usuario, pero este se diferencia de framewoks como React o Vue ya que estos funcionan o dependen de un **DOM Virtual** el cual obliga al navegador a hacer un trabajo adicional además de acumular o funcionar como un "recolector de basura".



**Svelte** es un framework compilado, es decir antes de renderizar los componentes el código ha de ser compilado, esto no lo hace más lento, sino que impulsa el rendimiento ya que convierte sus componentes en código imperativos que además de ser muy eficientes actualizan quirúrgicamente el **DOM** lo que permite realizar aplicaciones extensas con muy alto rendimiento.



En su primera versión se buscaba comprobar una hipótesis: en la que se demostró que un compilador diseñado y especializado podría generar un código totalmente funcional que permitiese al usuario la mejor de las experiencias. La segunda implementó nuevas mejoras a esta anterior.



La tercera versión y "actual", fué la más puntera , brindando la mejor experiencia de desarrollador y con la que se facilito la escritura de componentes con menos texto.



##### BREAK...

- La opinión colectiva de aquellos que prueban Svelte se puede definir en una sola palabra, **futuro**. 
- Los desarrolladores aclaran que todavía queda mucho por venir y que Svelte todavía no esta cerca ni de estar terminado.



# Uso...

Svelte como anteriormente hemos mencionado se utiliza como framework y es dedicado principalmente para los desarrolladores de entornos para clientes o "**Front/ed**", es decir es el encargado de comunicarse con el servidor para facilitar el tránsito de información entre el cliente y la "aplicación".

Algunas de las empresas más famosas que han utilizado este framework son:



<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e5/Rakuten_TV_logo.svg/1024px-Rakuten_TV_logo.svg.png" style="zoom:30%;" />



<img src="https://upload.wikimedia.org/wikipedia/commons/4/4e/Avast_Software_white_logo.png" style="zoom:36%;" />



<img src="https://logodownload.org/wp-content/uploads/2014/05/philips-logo-1.png" style="zoom:10%;" />



# Estructura

Svelte tiene la siguiente estructura de carpetas:

![](https://i.imgur.com/Ifczs7c.png)



Podemos ver la carpeta principal con nombre **Svelte**, dentro de estas las subcarpetas **node_modules**, **public**, **scripts**, **src** y los subficheros **.gitignore**, **package-lock.json**, **package.json**, **README.md** y **rollup.config.js**.

- Se usa **rollup** en lugar de **webpack** como herramienta para construir el bundle de salida.

- En **public** encontramos los archivos como imágenes, hojas de estilo, páginas principales o auxiliares, también podemos ordenar los mismos creando carpetas dedicadas para cada elemento, por ejemplo, una carpeta **images** que contenga todas las imágenes, otra **styles** que contenga los archivos **.css** o **.scss**, en general los archivos de estilos y así sucesivamente.
- La carpeta **scripts** contiene la lógica de nuestro framework.
- Y por último la carpeta **src**, esta será sobré la que trabajaremos normalmente creando componentes entre otras muchas cosas.



### ESTRUCTURA INTERNA

**Main.js** es el archivo de entrada en el cual cargaremos los componentes y situaremos en el DOM.

```javascript
import App from "./App.svelte";

const app = new App({
  target: document.body,
  props: {
    name: "world"
  }
});

export default app;
```



Podemos distinguir la siguiente composición:

- En la parte superior,  se importa e instancia el componente de entrada que viene desde **App.svelte**.
- La instancia se crea mediante un objeto de configuración  donde se le indica el elemento DOM al que queremos que se inserte nuestro componente mediante la propiedad **target**.
- Pasamos al componente unas propiedades(**props**) al igual que puede pasar en otros frameworks como **vue** y **react**.



Finalmente analizaremos el archivo **App.svelte**:

```html
<script>
  export let name;
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<h1>Hello {name}!</h1>
```

Los componentes de Svelte están estructurados en tres secciones:

- La primera contendra el código js del componente.
- La segunda el estilo definido para el componente.
- Para terminar un markup HTML que renderizará la estructura de los componentes que creemos. 



# Sintaxis

Svelte utiliza la misma sintaxis que javascript, html y css, ya que el componente, como hemos visto anteriormente puede contener las tres, por ello es necesario tener un conocimiento básico de estos.



Pero tiene algunos conceptos como la **reactividad**, **lógica**, y algunos más que requieren de gadgets de códigos o auxiliares para el correcto funcionamiento, los cuales podemos entender y comprender mejor siguiendo los pasos del tutorial de **Svelte**. 

- [Tutorial Svelte](https://svelte.dev/tutorial/basic)



# ¿Por qué utilizar Svelte?



##### *Antes que nada aclaremos algunos puntos fuertes de **Svelte**:*

- Con Svelte no tendrás que aprender otras sintaxis ni familiarizarte con otra forma de trabajo ya que utiliza principalmente **HTML, CSS y JS**, con lo que realmente **escribirás muchísimo menos código**.
- **No tiene un virtual DOM**, con lo que el navegador no tendrá esa carga y todo se sentirá y será muchísimo más ágil.
- **Es completamente reactivo** y no depende de librerías de estados ya que propiamente Svelte se encargara de aportar esta reactividad.

Ahora sí, comencemos...



#### SVELTE VS REACT VS VUE

Primeramente veamos un componente de **React:**

```react
import React, { useState } from 'react';

export default () => {
  const [a, setA] = useState(1);
  const [b, setB] = useState(2);

  function handleChangeA(event) {
    setA(+event.target.value);
  }

  function handleChangeB(event) {
    setB(+event.target.value);
  }

  return (
    <div>
      <input type="number" value={a} onChange={handleChangeA}/>
      <input type="number" value={b} onChange={handleChangeB}/>

      <p>{a} + {b} = {a + b}</p>
    </div>
  );
};
```

Es sencillo, fácil de comprender y "estamos acostumbrados".



Prosigamos con un componente de **Vue**:

```vue
<template>
  <div>
    <input type="number" v-model.number="a">
    <input type="number" v-model.number="b">

    <p>{{a}} + {{b}} = {{a + b}}</p>
  </div>
</template>

<script>
  export default {
    data: function() {
      return {
        a: 1,
        b: 2
      };
    }
  };
</script>
```

Se va pareciendo a nuestro anfitrión...



Finalmente tenemos un componente de **Svelte**:

```html
<script>
	let a = 1;
	let b = 2;
</script>

<input type="number" bind:value={a}>
<input type="number" bind:value={b}>

<p>{a} + {b} = {a + b}</p>
```



Para realizar la misma funcionalidad, requerimos distintos tamaños de código que se traducen a uso de memoria.



#### Profundicemos algo más...



###### ELEMENTOS DE NIVEL SUPERIOR

En **React** y **Vue**, un componente debe tener un y solo un elemento de nivel superior.

Por ejemplo en *React* intentar devolver dos elementos de nivel superior en una función de componente seria igual a un código sintácticamente invalido.

*"(Puede usar un fragmento - `<>`- en lugar de a `<div>`, pero es la misma idea básica y aún da como resultado un nivel adicional de sangría)."*

En *Vue*, su marcador necesita o requiere esta envuelto en una etiqueta o elemento `<template>` lo que lo hace redundante.



###### FIJACIONES

En **React** es necesario responder a los eventos de entrada y esto lo tenemos que hacer nosotros mismos.

Por ejemplo para la siguiente función:

```react
function handleChangeA(event) {
  setA(+event.target.value);
}
```

Esto es algo que consume espacio y da lugar a bugs.

En cambio **Svelte** y **Vue** controlan esto mediante el `v-model` atributo.



###### EXPRESAR

**Svelte** actualiza el estado del componente usando un operador de asignación, en cambio, **React** utiliza un estado. 



> **SVELTE**

``````javascript
let count = 0;

function increment() {
  count += 1;
}
``````

> **REACT**

``````react
const [count, setCount] = useState(0);

function increment() {
  setCount(count + 1);
}
``````

Esto se traduce a que en **React**, tarda más en comprender la intención del autor.

> **VUE**

Usa una funcion data que devuelve un objeto literal con las propiedades de nuestro estado local.



# Ejemplo práctico

Podemos ver el ejemplo en el siguiente enlace:

- [Ejemplo Svelte](https://stackblitz.com/edit/lets-get-to-know-svelte)



En caso de error, realizaremos un Hello World, como de costumbre.

#### **Tutorial Instalación**

Podremos iniciar un proyecto nuevo mediante el comando `npx degit sveltejs/template NombreProyecto` ó  descargarlo desde [Svelte.zip](https://github.com/sveltejs/template/archive/master.zip) y descomprimirlo.

Seguidamente en la consola, situados en la ruta del proyecto lanzaremos el comando`npm install` y esperaremos a que se nos instalen las dependencias, una vez terminado lanzaremos la aplicación con el comando `npm run dev`.



##### Mi primer Hello Wold con Svelte

No hay más misterios la template instalada esta definida por defecto con este código.



### Webgrafía

- https://svelte.dev/blog/write-less-code
- https://svelte.dev/blog/virtual-dom-is-pure-overhead
- https://svelte.dev/blog/svelte-3-rethinking-reactivity
- https://sumatd.com/blog/svelte-caracteristicas/
- https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_getting_started



### ¿Te ha gustado Svelte? Esto quizás te interese...



- [Examples Svelte](https://svelte.dev/examples#hello-world)
- [Repl Svelte](https://svelte.dev/repl/c6aefed780b949139dea95a323d8e48f?version=3.19.2)
- **Svelte Comunities**
  - https://dev.to/t/svelte
  - https://svelte-community.netlify.app/resources/
  - https://gitter.im/Svelte-Developers-Worldwide/community?at=5f2b8133c6dbab651243459e
- **Svelte curses**
  - [freeCodeCamp.org - English](https://www.youtube.com/watch?v=ujbE0mzX-CU)
  - [midudev - Spanish](https://www.youtube.com/watch?v=Xsxm8_BI63s)
  - [Silvestre Vivo - Spanish](https://www.youtube.com/watch?v=q9yZTfcZnKo&list=PLtEoLIi1AQhWzcCE76KQi4OLHqlDu_XUh)

































