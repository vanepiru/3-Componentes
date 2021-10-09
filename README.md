# Componentes

![React-components-blog-image](https://user-images.githubusercontent.com/6796155/136663866-7b684771-e864-4ac6-8e4a-e87f5aa21b12.jpg)


# ***Las diferentes formas de definir componentes***

***ECMAScript 5 – createClass***
Este fue el primer método que existió para crear componentes en React. Ejemplo:

 
```js
var miComponent = React.createClass({ 
  propTypes: {...}, 
  getDefaultProps: {...}, 
  getInitialState: {...}, 
  render: function(){...} 
})
```
La clase se crea mediante la función React.createClass , 
el cual recibe un objeto que debe de tener al menos la función render,
 adicional, se puede declarar los propTypes , defaultProps  y el estado inicial del componente.

 

***ECMAScript 6 – React.Component***
Este es el método que vimos en clase pero sin constructor, propTypes y defaultProps. En la cual los componentes se crean mediante
clases que extienden de React.Component. Ejemplo:

 
```js
import React from 'react' 
class ECMAScript6Class extends React.Component{ 
  constructor(props){ 
    super(props) 
      state = {
        ...
      } 
    } 
	
  render(){ 
    return ( 
      ... 
    ) 
  } 
}

ECMAScript6Class.propTypes = { ... } 
ECMAScript6Class.defaultProps = { ... }
```

Los propsTypes  y defaultsProps  son declarados fuera de la clase. 
Este es el componente más recomendable cuando trabajamos con componentes con estado (Stateful).
Pues permite un mejor control sobre el componente.

 

***ECMAScript 6 – Function Component***
La siguiente forma que soporta ECMAScript 6, es la creación de componentes mediante funciones, 
y es recomendado únicamente para componentes sin estado . Veamos cómo quedaría:

 
```js
cont MiComponent = ({prop1, prop2, prop2}) => ( 
  return( 
    ... 
  ) 
) 
MiComponent.propTypes = { 
  ... 
} 
MiComponent.defaultProps = { 
  ...
}
```
Observemos que el componente se reduce a una arrow function, la cual recibe como parámetros las props . El cuerpo de la función es
como el método render, podremos crear variables, poner un poco de lógica y retornar un JSX.
Adicional, se puede definir los propTypes  y defaultProps  por fuera de la función.

 

***ECMAScript 7 – React.Component***
La última forma disponible, es utilizar las nuevas sintaxis de ECMAScript 7. 
Este método es muy parecido a la creación de componentes mediante React.Componentes  ES6. Veamos cómo quedaría:

 
```js
class MiComponent extends React.Component { 
  static propTypes = {
    ...
  } 
  
  static defaultProps = { 
    ... 
  } 
  
  state = { 
	... 
  } 
  
  constructor(props){ 
    super(props) 
  } 
  
  render(){ 
    ... 
  } 
}
```
Este método es prácticamente igual que crear una clase en ES6, 
con la diferencia que es posible declarar el estado como una propiedad, adicional,
podemos declarar los defaultProps  y propTypes  dentro de la clase y marcarlos como static 
para poder ser accedidos desde fuera sin necesidad de crear una instancia.


# ***export default***

```js
import React from 'react';

class HolaMundo extends React.Component {
  render() {
    return <p>Hello, world!</p>;
  }
}

export default HolaMundo;
```

-*default export es una convención que se utiliza cuando se desea exportar solo un objeto (variable, función, clase) desde el archivo (módulo).
-*Es la característica de ES6 que se usa para exportar un módulo (archivo) y usarlo en algún otro módulo (archivo).
-*No se puede renombrar al importar en otro archivo, debe tener el mismo nombre que se utilizó para exportarlo.
