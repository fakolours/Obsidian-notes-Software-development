Les services permettent de factoriser des méthodes et propriétés pour les utiliser dans différents composants
Pour créer un service :
```Powershell
ng generate service nom_du_service
```
Le décorateur des service :
```typescript
@Injectable
```
Ce décorateur permet d'injecter le service dans d'autres composants et d'y injecter d'autres Injectable. L'`Injectable` est déjà compris dans les autres décorateurs qu'on a utilisé.
La ligne : 
```typescript
providedIn: 'root'
```
permet d'accéder à la même instance du service à travers toute l'application; c'est-à-dire qu'on ne va pas.
Si on instancie le service on risque des problèmes sur l'accès de données. Donc pour les injecter, on fait comme pour le Router, directement dans les paramètres de constructeur du composant :
```typescript
  constructor(
    private router:Router,
    private serviceExpense:ExpenseService){}
```
## Rendre un service disponible / limité à des niveaux spécifiques
### Au niveau de l'application
```typescript
@Injectable({
	providedIn:'root' 
})
```
Le service est disponible partout grâce à `'root'`
### Au niveau du module
On supprime tout ce qu'il y a dans `@Injectable()`. Dans le `NgModule` dans lequel on veut avoir le service, on ajoute le champ : `providers` qui contiendra un tableau de services.
```ts
@NgModule({
  providers: [ExpenseService]
})
```
### Au niveau d'un composant
**ATTENTION** En injectant à plusieurs composants (intérêt du service), on perd l'utilisation du singleton en cas d'accès à différentes datas.
Fonctionne de la même manière que pour le module.