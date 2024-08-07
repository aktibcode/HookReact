# Chapitre : UTILISATION DE USEEFFECT


# useEffect

La `useEffect()`méthode prend :
Une fonction comme premier paramètre qui décrit l'effet que l'on souhaite appliquer. Ensuite, elle prend un tableau comme second paramètre qui déterminera quand cet effet doit apparaître ou disparaître.

Gardez donc à l'esprit que pour démarrer, nous devons utiliser un tableau vide `[ ]`comme deuxième paramètre. Cependant, ce paramètre reste facultatif.
`[]`signifie que l'effet n'utilise aucune valeur qui participe au flux de données de React et c'est la raison pour laquelle il est considéré comme sûr de l'appliquer une fois.
Il est également considéré comme une source courante de bugs lorsque la valeur est réellement utilisée.

Ce code illustrera mieux ce que nous avons mentionné :

```
// setting the useEffect to trigger while the component is been rendering 
useEffect(()=>{
 alert(`hello this a message`)
},[])
```

# useEffect

La `useEffect()`méthode permet aux fonctions des composants de gérer les effets secondaires.
Elle joue le même rôle que `componentDidMount()`, `componentDidUpdate()`, et `componentWillUnmount()`dans les classes React, elle est implémentée via une seule API.

![](https://i.imgur.com/k2a4kiO.png)

<iframe allowfullscreen="true" frameborder="0" src="https://www.youtube.com/embed/wbzMK4tNBao?list=PL-w_yrNy8uTaWNAYCFoyW0C0zPm4S9b3v"></iframe>


Ces ressources peuvent vous aider

Exemples d'utilisation de useState()

[https://daveceddia.com/usestate-hook-examples/](https://medium.com/javascript-in-plain-english/react-hooks-how-to-use-useeffect-ecea3e90d84f)
