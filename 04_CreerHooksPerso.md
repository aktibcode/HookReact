# Chapitre : CREER DES HOOKS PERSONNALISES


# Hooks personnalisés.

Un Hook personnalisé est une fonction JavaScript dont le nom commence par "use". Il permet un partage de logique flexible.
Nous pouvons appeler d'autres Hooks dans nos Hooks personnalisés.
Avant de commencer, nous devons être capables de créer nos propres Hooks de manière personnalisée et cela garantira toujours la réutilisabilité fonctionnelle.
L'exemple suivant d'utilisateurs et de publications nous aidera à mieux comprendre l'aspect pratique des Hooks personnalisés.

![](https://i.imgur.com/O5Niw3d.png)

# Hooks personnalisés

Les hooks personnalisés sont simplement une fonction wrapper entourant nos hooks existants.
C'est tout ce qu'il y a à faire ! Le seul hic est que pour que React reconnaisse une fonction comme un hook personnalisé, son nom doit toujours commencer par use afin que vous puissiez voir en un coup d'œil que les règles des Hooks s'appliquent à elle.

# Créer un Hook personnalisé

Nous allons créer un Hook **useInterval** et ensuite nous l'utiliserons.

```
function useInterval (timeout, getValue) {
   const [value, setValue] = useState(getValue);
    useEffect(() => {
     const intervalID = setInterval(
       () => setValue(getValue()),
       timeout
     );
    return function () {
     clearInterval(intervalId);
   }
 }, []);
  return value;
 }
  const get CurrentDate = () => new Date();
  function App() {
   const date = useInterval(1000, getCurrentDate);
    return <p>Nous sommes le {date.toLocaleString(“fr-FR”)}</p>;
 }
```

# résumer

Dans cette vidéo, vous trouverez un aperçu des React Hooks

<iframe allowfullscreen="true" frameborder="0" src="https://www.youtube.com/embed/cxQZaYkBLRg?list=PL-w_yrNy8uTaWNAYCFoyW0C0zPm4S9b3v"></iframe>


Comment écrire des hooks personnalisés

[Ouvrir le lien](https://dev.to/wellpaidgeek/how-to-write-custom-hooks-in-react-1ana)
