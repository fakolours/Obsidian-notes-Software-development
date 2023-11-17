Sont notés 
```typescript
@Directive({
selector: '[appBoarderCard]'
})
```
Pour générer une directive :
```powershell
ng generate directive **nom_de_la_directive**
```
Les [[Components]] sont des directives.
Directives d'attributs : Modifient les comportements des attributs HTML (propriétés, affichage etc.)
Directives structurelles : Modifient des éléments complets et leur comportement (ngIf, ngFor)

Pour que la directive fonctionne en interaction avec les actions de l'utilisateur : 
```typescript
@HostListener()
```
Pour intégrer la directive dans le composant.
Dans le dossier dans lequel il est contenu, au niveau de la ``<div>`` du composant :
```HTML
<div class=whatever <--nom_de_la_directive--> >
```
Si on veut modifier des propriétés de la directive, on vaut ajouter une ligne 
```typescript
@Input('/*nom_de_la_directive*/') var_name:var_type
```
La ``div`` devient :
```HTML
<div class=whatever **nom_de_la_directive**=value>
```
