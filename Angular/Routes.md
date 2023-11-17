Pour utiliser les routes, pas besoin de créer de nouveau fichier. Il faut aller dans le fichier `app-routing`.
Elles sont construites de la liste `Routes` de la sorte :
```typescript
{path:'url_voulue', component: DefinedComponent},
```
Pour créer le mouvement côté utilisateur il faut ajouter la ligne :
```HTML
<router-outlet></router-outlet>
```
Tout ce qui se trouve au dessus de la ligne sera affiché sur toutes les pages. Tout ce qui se trouve en dehors des balises sera affiché au dessus et en dessous.

Pour accéder à la route courante (la route sur laquelle est l'utilisateur), on peut utiliser la directive `ActivatedRoute` (à importer de `'@angular/router'`).
On a cette route côté dev :
```URL
http://localhost:4200/expense/:id
```
Coté utilisateur :
```URL
http://localhost:4200/expense/3
```
Pour récupérer `id` : 
On a le constructeur :
```typescript
constructor(private route: ActivatedRoute){}
```
et :
```typescript
  ngOnInit(): void {
    const catId: string|null = this.route.snapshot.paramMap.get('id')
  }
```
Little explanation here :
- On ne peut pas récupérer un nombre puisque la conversion (+ devant une `string`) ne fonctionne pas si la valeur retournée est `null`
- `snapshot` donne la data de `router` à cet instant
- `paramMap` est une map avec tous les paramètres de l'URL
- `get(param)` est la méthode qui permet d'obtenir la valeur de `param` dans l'URL

Pour avoir un lien vers une autre page sur un click:
Ici `router` est de type `Router`
1. Créer une fonction dans le `.ts` du composant:
```typescript
goToOtherPage(){
    this.router.navigate(['/adresse_page'])
  }
```
2. Utiliser la fonction sur l'endroit à cliquer dans le `.html`:
```HTML
<a (click)="goToOtherPage()">Retour</a>
```
3. Pour aller sur des pages qui dépendent d'un `id` par exemple : 
```typescript
  goToFront(categorie: Categorie){
    this.router.navigate(['/expense',categorie.id]);
  }
```
Résulte en :
```
http://localhost:4200/expense/1
```
Côté HTML, on a :
```HTML
<a (click)="goToFront(categorie1)">Retour</a>
```
## Priorité des routes
Lorsqu'Angular lis les routes dans `app-routing`, elles sont lues dans l'ordre.
Meaning : La première route qui correspond sera celle qui sera renvoyée.
L'opérateur `'**'` permet de récupérer toutes les routes, il faut donc le placer en dernier pour ne pas bloquer les routes apparaissant après.

La variable/fonction `routerLink` permet de créer un lien de la même manière que la `router.navigate` mais côté HTML:
```HTML
    <a routerLink="/expenses" >
        Retourner à l' accueil
    </a>
```