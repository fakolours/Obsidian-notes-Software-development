Les modules contiennent tout ce qui est [[Components]],[[Directives]], etc. 
Les créer permet d'organiser de plus gros projets en ayant des modules bien répartis avec leurs composants au lieu d'avoir 10000 composants dans le module racine.
Pour générer les modules :
```Powershell
ng generate module **nom_module**
```
Le décorateur d'un module :
```typescript
@NgModule({
})
```
Il contient plusieurs catégories, dont les plus importantes :
- `declarations` pour déclarer tous les composants, pipes, directives qu'il contient
- `imports` pour les classes importées d'autres modules pour que celui-ci fonctionne correctement
- `providers` pour les injections de dépendances
- `bootstrap` pour le composant racine, composant lancé au démarrage de l'appli
Quand on crée un module, on peut déplacer les composants assez facilement à l'intérieur. POur bouger les routes, on peut copier coller puis rajouter dans `imports`:
```typescript
RouterModule.forChild(modulesRoutes)
```
Alors que dans `imports` de `app-routing` on a :
```typescript
RouterModule.forRoot(RootRoutes)
```
Dernière étape pour intégrer le module, ajouter dans le `imports` de `app.module.ts`
Pour que les routes soient chargés correctement (i.e. on veut que les routes du modules soient vues avant la 404), il faut importer le nouveau module avant le `AppRoutingModule`