#DOcumentation

##COnvention BEM

* B -> Block
* E -> Element
* M -> Modifier

```html
<!-- mainList = Block -->
<ul class="mainList mainList--xmas">
  <!--__item = Element  -->
  <li class="mainList__item">
    <!--__itemLink = Element  -->
    <a class="mainList__itemLink mainList__itemLink--isActive" href="/home">Home</a>
  </li>
  <li class="mainList__item">
    <!--__itemLink = Element  -->
    <a class="mainList__itemLink" href="/about">About</a>
  </li>
  <li class="mainList__item">
    <!--__itemLink = Element  -->
    <a class="mainList__itemLink" href="/works">Works</a>
  </li>
</ul>
```


```css
.mainList{
  display: flex;
  justify-content: space-between;

  &--xmas{
  background: green;
  }

  &__item{
    list-style: none;
  }

  &__itemLink{
    color: red;
  }
  &--isActive{
    color: white;
}
  &--isActive{
    color: white
  }
}
```
## Pseudo attributs

Les pseudos attibuts `before`et `after` permettent de créer des noeuds HTML en CSS.
Ils sont essentiellement utilisés pour ajouter des ornements, des décorations...
On peut bien entendu faire des animations avec, les positionner par rapport à leur parent (relative/ absolute). ** Ils doivent obligatoirement avoir un `content: ''` ** afin de s'afficher.

```html
<section class="cover">
  <h1 class="cover__mainTitle">Présentation des pseudo-attributs</h1>
</section>
```

```css
.cover{
  background: #FDFDFD;
  padding: 20px;

  &__mainTitle{
    text-align: center;
    font-size: 24px;
    color: green;
    position: relative;
    &::before,
    &::after{
      position: absolute;
      content:'';
      display: block;
      width: 50px;
      height: 50px;
      background: green;
    }
    &::before {
      left: 0;
    }
    &::after{
      right: 0;
    }  
  }
}
```

## REM, EM, %, VW Sizing

### %

### EM

```css
.cover{
  font-size: 100%  /*  100% = 16px  */
  &__mainTitle {
  /* 1 em = 16px / .8em =!= 16px */
  font-size: .8em;
  }
}
```

### REM

* Le REM est basé sur la taille de la racine (soit la balise <html>)qui, par défaut
a une valeur de 16px. Afin d'éviter tout calcul, il est nécéssaire de l'écraser en donnant une base de 10px soit 62.5%.
* Le REM est intéressant à utiliser si les media-queries employées sont en rem également.
Cela vous permettra de garder des proportions égales lorsqu'on va redimensionner la page.
* Ses proportions seront également gardées quand l'utilisateur zoomera dans votre page.

```css
html{
  /* 1.6rem == 16px */
  font-size: 62.5%;
}
.mainTitle {
  /* 1.6rem == 16px  */
  font-size: 1.6rem;
  /*  32rem == 320px */
  width: 32rem;
}
```
### VW(idth) / VH(eight)

* unités relatives à la taille de votre écran (peu importe le device)
* Attention au VH et à son contenu. 100vh == 100vh quoi qu'il arrive.
* VW : très utile pour les interfaces fluides.


## Liens utiles

*(caniuse) -> https://caniuse.com/
