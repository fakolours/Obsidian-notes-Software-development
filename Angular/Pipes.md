Sert à transformer une data avant de l'afficher.
Du côté HTML:
``` HTML
<balise>{{ data | pipe }} </balise>
```
Le `|` est le séparateur pour les pipes.

Les pipes sont combinables et sont générés de la gauche vers la droite. Chaque nouveau pipe nécessite le `|`.

Les pipes sont modifiables sous certaines conditions en passant des paramètres.


### Pipes par défaut
Il y a une série de pipes déjà disponible pour tous les projets.
### Générer et personnaliser des pipes
```powershell
ng generate pipe **nom_pipe**
```
La fonction ``transform`` est la plus importante :
```typescript
transform(expense: Categorie): string {
    if(expense.current_value > 0.8*expense.limit){
      return "card red"
    }else{
      return "card"
    }
  }
```
Les pipes peuvent être utilisées sur des contenus ou sur des contenants.
```HTML
<div class="{{categorie | closeToLimit}}">Contenu</div>
```
Les deux morceaux de codes précédents fonctionnent ensemble. `categorie` sera traité comme le premier argument de ``transform``. On peut ajouter `...args[]` dans le cas ou on écrirait ce genre de ligne :
Les pipes peuvent être utilisées sur des contenus ou sur des contenants.
```HTML
<div class="{{categorie | closeToLimit = spec_value }}">Contenu</div>
```
