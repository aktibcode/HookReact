# Chapitre : ERREURS COURANTES


# useRef()

Le `useRef()`Hook est une fonction qui renvoie un objet de référence mutable dont la propriété actuelle est initialisée sur l'argument passé (initialValue). L'objet renvoyé persistera pendant toute la durée de vie du composant.

Cet exemple peut vous aider :

```
function App() {
 let [name, setName] = useState("Ned stark");
 // we declare the input inside the variable
 let nameRef = useRef();
 // we are referring to input to change the value
 const submitButton = () => {
   setName(nameRef.current.value);
 };

 return (
   <div className="App">
     <p>{name}</p>
     <h1>Who is your favorite Games of throne character</h1>

     <div>
       <input
         placehoder="enter your preferred GOT character..."
         ref={nameRef}
         type="text"
       />
       <button type="button" onClick={submitButton}>
         Submit
       </button>
     </div>
   </div>
 );
}
```

Dans cette fonction, nous récupérons la valeur d'entrée en utilisant la méthode useRef au lieu de l'événement onChange. Cela peut être un événement de bogue potentiel si cela fonctionne pour l'instant. Une référence créée avec **useRef** ne sera créée que lorsque le composant aura été monté. Les références peuvent être utilisées pour accéder aux nœuds DOM ou aux éléments React, et pour conserver les variables mutables.

# Déstructuration à l'aide d'un objet :

N'oubliez pas : les hooks utilisent des tableaux pour stocker des données.
Comme nous l'avons mentionné précédemment, les hooks sont appliqués dans un tableau :

`const { state, setState} = useState("intial state")`

Si nous effectuons une déstructuration à l'aide des accolades, nous recevrons cette erreur :

![](https://i.imgur.com/QpxQ3hA.png)

Rappel : ce code est incorrect. Il faut utiliser des hooks et non des accolades.

`const [state, setState] = useState("intialState)`

# Hooks à l'intérieur d'une condition :

Nous devons éviter de créer le hook d'état dans une condition, car cela violerait les règles du hook. Une fois ces règles enfreintes, cette erreur se produit :

```
import React, { useState } from 'react'

const Welcome = props =>{
 if(props.name==='ned stark'){
   const [bgColor,setBgColor ]= useState('white')
 }
 else{
   const [bgColor, setBgColor] = useState('black')
 }

 return (
   <h1 style={{backgroundColor:{bgColor}}} >{props.name}</h1>
 )
}

export default Welcome
```

### Sortir

![](https://i.imgur.com/hh8jHIo.png)

# Hooks à l'intérieur d'une boucle :

Une autre erreur courante consiste à utiliser le hook à l'intérieur des boucles. Voici un exemple pour illustrer l'erreur.

```
function App() {
 for (let i = 1; i < 5; i++) {
   const [state, setstate] = useState(i);
 }
 return (
   <div>
     <h1>{state}</h1>
   </div>
 );
}

export default App;
```

### Sortir

![](https://i.imgur.com/sLGZlrx.png)

# Imbrication avant d'utiliser l'état :

Nous ne pouvons pas imbriquer dans une fonction avant d'utiliser notre état.

```
function App({ date }) {
 function updateCount(byValue) {
   const [currentDate, setCurrentDate] = useState(new Date());
   const [count, setCount] = useState(0);
   setCount(count + byValue);
   setCurrentDate(new Date());
 }

 function formatDate() {
   const hour = currentDate.getHours();
   const minute = currentDate.getMinutes();
   const second = currentDate.getSeconds();

   return `${hour}:${minute}:${second}`;
 }

 const prettyDate = formatDate();

 return (
   <div className="App">
     <h2>
       You clicked {count} times, last time at {prettyDate}!
     </h2>

     <button onClick={() => updateCount(-1)}>Decrement</button>
     <button onClick={() => updateCount(1)}>Increment</button>
   </div>
 );
}
```

# useState à l'intérieur d'un effet :

Nous allons maintenant passer en revue certains points où nous invoquons useEffect.
**Remarque importante :** l'utilisation combinée de useState et useEffect génère une boucle infinie.
Par conséquent, n'appelez pas useState à l'intérieur d'un useEffect.

# Résumons !

Pour résumer, nous ne pouvons appeler les Hooks qu'au niveau supérieur.
Nous devons être conscients de ces règles :

* Ne déclarez pas de hooks dans les instructions if.
* Ne déclarez pas de hooks dans les boucles.
* Ne déclarez pas de hooks dans une fonction imbriquée.
* Assurez-vous toujours d'utiliser les crochets au lieu des accolades.


Erreurs courantes

[Ouvrir le lien](https://kentcdodds.com/blog/react-hooks-pitfalls/)
