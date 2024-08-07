# Chapitre : PRESENTATION DES HOOKS REACT


# Introduction aux hooks React

La `16.8<span> </span>`mise à jour de React a été une révolution majeure dans la façon dont React traite et interagit avec les composants et tout cela grâce aux hooks.

Les hooks font beaucoup de bruit dans la communauté React car ils réduisent la complexité de la gestion des états.
Dans cette compétence, nous allons voir :

* Que sont les hooks React ?
* Qu'est-ce que le hook useState ?
* Qu'est-ce que useEffect hook ?
* Qu'est-ce que le hook useRef ?
* Comment fabriquer vos propres crochets personnalisés ?

# useState

En décrivant l'utilisation de l'état dans la Super Skill précédente, nous avons vu que l'état ne peut être mis à jour qu'à l'aide de la `this.setState`méthode.
L'état est caractérisé par deux éléments principaux : une **valeur** (aka `getter`) et une méthode pour définir cette valeur (aka `setter`).

La même logique s’applique toujours à la `useState()<span> </span>`méthode.

# Déclaration d'une variable d'état :

Tout d’abord, nous devons apprendre à déclarer une variable d’état dans notre composant :

1. Importez le hook useState.
2. Déclarez votre variable d'état dans un tableau (le getter et le setter)
3. Initialisez votre variable d'état avec useState( ).
   Cet exemple vous aidera à mieux comprendre :

```
import React, { useState } from "react";
```

![](https://i.imgur.com/u2Okeq3.png)

# Accéder à l'État

Maintenant que nous avons déjà déclaré l'état de notre composant, nous devons pouvoir accéder à la valeur de cet état.
Comme toute autre variable en JavaScript, si nous voulons la valeur d'un état, nous invoquons le nom de l'état comme indiqué dans l'exemple ci-dessous :

```
import React, { useState } from "react";

const MyFunctionComponent = props => {
 // setting the state hooks
 const [name, setName] = useState("Arya Stark");
 return (
   <div>
     {/* here we use the getter to get the state value */}
     <p>hello my name is {name}</p>
   </div>
 );
};
```

# Définir la valeur de l'état :

Pour modifier la valeur de l'état, nous devons utiliser le setter que nous avons implémenté dans la déclaration d'état. Dans cet exemple, la méthode setName agit comme le setter (ou le modificateur) :

```
const MyFunctionComponent = props => {
 // declaring the state hooks
 const [name, setName] = useState("Arya Stark");
 // here we use the setter to change the content of the name state
 const handleClick = () => setName('Tyron Lanyster')
 return (
   <div>
     {/* here we use the getter to get the state value */}
     <p>hello my name is {name}</p>
     <button onClick={handleClick}>Click if you want to give the crown to Tyron Lanyster</button>
   </div>
 );
};
```

# Points clés à garder à l’esprit :

Maintenant que nous savons ce que fait le hook useState() et que nous avons l'état initial de notre composant, nous devons pouvoir accéder à la valeur de cet état.
Comme toute autre variable en JavaScript, si nous voulons la valeur d'un état, il suffit d'invoquer le nom de l'état, comme indiqué dans l'exemple ci-dessous :

```
import React, { useState } from "react";   
  
function Welcome() {   
const [name, setName] = useState(“Jane”)  
    return (  
<div>  
<h1> Welcome {name} </h1>  
</div>  
  )  
}   
  
export default Welcome; 
```

Sortir:

![](https://i.imgur.com/MuPncY4.png)


Ces ressources peuvent vous aider

Exemples d'utilisation de useState()

[https://daveceddia.com/usestate-hook-examples/](https://daveceddia.com/usestate-hook-examples/)
