2 options existent : **Forms module** et **reactive forms module**.
Forms module : Plus sur le template
Reactive : Plus sur le composant
Librairie: `@angular/forms`
On doit importer : `NgForm` et se traduit en HTML par `<form>`.
On doit importer : `NgModel` pour contrôler les champs (validité, valeur etc.). On peut en parallèle utiliser la directive `NgModelGroup` pour générer des sous-groupes de champ.
`NgModel` crée une liaison bidirectionnel entre le template et le composant.
Générer un formulaire revient à générer un composant.
