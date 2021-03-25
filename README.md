# Todo app

On a fini l'intégration HTML/CSS de cette jolie todo app mais maintenant elle est un peu trop statique à mon goût... Et si on dynamisait un petit peu tout ça à grosse dose de JS ? 😁

---

## On prépare le terrain

Pour cette première étape on devra écouter l'évènement de soumission du formulaire pour:

- Empêcher le rechargement de la page

- Récupérer la valeur du champ de texte

- Afficher un message d'erreur si le champ de texte est vide

---

## Ajouter un todo

Ca y est on y est, on va ajouter le contenu de notre champ de texte fraîchement validé à notre liste de notre page HTML ! ✨✨

Pour ce faire on va:

- récuperer la liste qui porte la class CSS 'todo-list'
- créer un élément li avec la class CSS 'todo-list\_\_task'
- créer trois éléments span
  - le deuxième élément contiendra le texte du champ de texte
  - le dernier des éléments devra avoir la class CSS 'delete-cross'

Ensuite on va ajouter ces trois éléments dans notre élément li

Et enfin ajouter notre élément li dans la liste avant l'élément avec la class CSS '.todo-list\_\_footer'.
Pfiou... 😩

---

## Marquer un todo comme fait

Pour que notre liste serve à quelque chose, on veut pouvoir marquer nos todo comme "fait" sans pour autant les supprimer...

Pour ça on va ajouter la class CSS 'complete' lors du click sur l'élément avec la class CSS 'todo-list\_\_task' le plus proche concerné et on va agir sur l'input de type checkbox en le cochant

Si on reclique sur un todo marqué comme "fait", il doit passer à "non fait" et ainsi de suite ...

---

## Supprimer un todo

Si on peut ajouter... Il faut pouvoir supprimer ! 💡

On aura deux possibilitées

- la 1ère consistera a cliquer sur la petite croix présente lors du survol sur l'élément li contenant le todo

  - il faudra donc ajouter un évènement à cette croix pour réagir au click

- pour la 2ème on ne vas pas y aller avec le dos de la cuillère 🥄, on va tout simplement supprimer TOUT les todo marqués comme fait en se servant du bouton "Clear Completed"

  - Récuperer en javascript tout les éléments qui ont la class CSS 'complete' et les supprimer du document lors du click sur le bouton "Clear Completed" (il faudra peut être y ajouter un évènement pour qu'il se passe quelque chose) 😄😄
    Et... c'est tout 😄

---

## Liste dynamique

On peut ajouter et supprimer un todo... Trop cool ! 👍

Par contre le nombre de todo situé en bas à gauche de notre liste ne change pas... 😬

On va devoir changer ça...

Pour ça on va changer le texte contenu dans l'élément avec l'id "todo-count" et lui donner le nombre de todo restants à faire 😄

<details>
<summary>Spoiler</summary>
Il me semble que les todo marqués comme "fait" ont la class CSS 'complete' 🤔
On ne devrait pas avoir trop de mal à récuperer ceux qui ne sont pas fait du coup 😄

</details>

---

## Le grand ménage

On va s'occuper de trier maintenant 😄

On va donner une utilité aux boutons "All", "Active" et "Completed" du footer de notre liste

- quand on click sur "All", on veut voir les todos "fait" et "non fait"
- quand on click sur "Active", on veut voir que les todos "non fait"
- quand on click sur "Completed", on veut voir que les todos "fait"

---

## Jour / Nuit

<div style="text-align:center;margin: 2rem 0;">
  <img src="./images/jour-nuit.gif" />
</div>

On va adapter notre todo app pour lui appliquer un theme clair ou un theme sombre ! ☀️ 🌕

1. on va d'abord récuperer l'élément qui servira à changer entre le mode sombre et le mode clair (notre "switch") à savoir l'élément avec la class "theme-toggle".
2. on va aussi récupérer tout les éléments qui ont la class "dark" ou la class "light" en fonction du thème de base
3. une fois notre "switch" récupéré on va lui ajouter un écouteur d'évènement au click pour changer son attribut src et choisir la bonne image et changer la class CSS des éléments du point 2
   - s'ils ont la class "dark" on changera pour "light" et inversement
