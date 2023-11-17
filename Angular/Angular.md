Lié à [[Typescript]], [[HTML CSS]]
Sources consultées : 
[Angular Tutorial Français pour Débutant - Cours complet 9h [2022] - YouTube](https://www.youtube.com/watch?v=DTIYVffhJuU)

## Génération et premier lancement de l'application
Pour générer l'application :
```PowerSHell
ng new nom_de_l_app
```
## Développement de l'application
Les différents concepts à connaître dans Angular :
- Les [[Directives]]
- Les [[Components]]
- Les [[Pipes]]
- Les [[Routes]]
- Les [[Modules]]
- Les [[Services]]
- Les [[Formulaires]]

Lors de la génération de composants, services etc.; si on ne veut pas qu'ils soient générés dans le dossier racine, il suffit de rajouter le nom du dossier dans lequel on le veut avant son nom. Par exemple :
```Powershell
ng generate service sous-dossier/service_1 
```
Génèrera le service `service_1` dans le dossier `sous-dossier`.
A la fin de la ligne de génération, si on veut observer le comportement SANS générer réellement, on peut ajouter l'option `--dry-run` :
```Powershell
ng generate service expense/expense --dry-run
```

## Tester son application
https://angular.io/guide/testing
Les fichiers de test sont les fichiers `.spec.ts` contenus dans les composants à tous les niveaux (générés avec automatiquement)
## Gérer le stockage de données
[Local Storage](https://jscrambler.com/blog/working-with-angular-local-storage)
