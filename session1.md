Raccourcis clavier ctrl+j

git --version

git config --global user.email "sitrakaradiarisainana@gmail.com"

git config --global user.email

git config --global user.name "SitrakaResearchAndPOC"

git config --global user.name 


git config --global core.editor "code --wait"

git config --global -e

Sur windows : 
git config --global core.autocrlf true

Sur MACOS ou LINUX
git config --global core.autocrlf input


mkdir random-number-app

cd random-number-app

git --version 

git init


Tapez F1 puis configurer création fichier en utf-8 : 

index.html
<h1 >hello world </h1>" 

dir

Va dans source control de visual code ctrl+shift+G: (si rien n'affiche redemarre visual code)

Dans source control, le U veut dire fichier crée

git status


Changer un fichier etat (edit ou interact ou change) en etat de staged (une sorte de salle d'attente avant commit)

git add index.html

ou 

git add .	Prépare tous les fichiers modifiés pour un commit

Regarde dans source control


git commit : 
id (hash)
message/time
auth
snapshot des changement


Installer timeline et gitlens avec visual code pour voir les differents commit

git commit -m "Add index.html file"

-m : message


git log


modifier fichier : index.html : 
-----------------
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Random Number App</title>
  </head>
  <body>
    <h1>Melvyn</h1>
  </body>
</html>


Affichage des modifications par : 

git status

git add index.html


git commit -m "Set a doctype file"

git status

git log 


ls .

Dans Timeline les differents commit

voir Gitlens à coté de terminal


style.css
---------
h1 {
	background : red;
}


Ajouter dans head : 
<link rel="stylesheet" href="style.css">

git status

git diff --staged

git diff 

git add index.html

git add style.css



git diff --staged

Regarder avec visual

git commit -m "index.html with css"




Changer style CSS : 
------------------
h1 {
  background-color: red; /* Ou background: red; */
}

body {
  margin : 0;
}


html, 
body {
  min-height: 100;
}




Si sans création de fichier : 
git status


Ajouter les fichiers modifiés en staged (c'est pas equivalent de git add .) les fichiers crées ne sont pas ajouter en staged
git commit -a -m "Remove initial style"

git commit --help

git show <id>



Création de script.js
console.log("hi");

Ajouter script .js dans body de index.html
<script src="script.js"> </script>


Recharger et inspecter sur le navigateur

git add .
git commit -m "Add script file and link to html"


commit message complexe :
-------------------------
Ajouter background : #f1f1f1 avec css dans html,body
background : #f1f1f1;

git add .

git commit

ajouter en haut : 
Add background to style.css


* use color for better representation

Si editeur vim
:q
entrée


git log
git log --pretty
git log --oneline

verifie aussi avec timeline ou gitlens


git show <id_commit>
git show
 
Stackoverflow ::


Commit avec visual-code : 
-------------------------
Remplacer h1 par
<button id="random-number">Generate random button </button>
<div id="result"> </div>



console.log("Hey");

const randomNumberEl = document.querySelector("#random-number");

randomNumberEl.addEventListener("click", () => {
  document.querySelector("#result").textContent = Math.random();
});


git status


Dans source control  : 
-> le premier button c'est open : 
-> le second button c'est discard pareil que git restore

enlever le background dans style.css

git status 

git restore style.css


git status

git show <ref>

git restore style.css


-> le button + : qui permet de l'ajouter dans staged changed

dans le champ texte ajouter : 
feat: add random button



créer un fichier todo.txt
* Afficher un champ text min et max pour le random number
* Ajouter les meilleurs styles 
* faire xxxx


console.log("Hey");

const randomNumberEl = document.querySelector("#random-number");

randomNumberEl.addEventListener("click", () => {
  document.querySelector("#result").textContent = Math.floor(
    getRandomNumber(1, 100)
  );
});

function getRandomNumber(min, max) {
  return Math.random() * (max - min) + min;
}


git add .
Et la ca vient d'ajouter mon fichier todo.txt

créer un fichier .gitignore

faire un git commit

Mauvaise manipulation : 
git rm script.js

git restore --staged script.js

Help : 
-----
git rm --help

--cached : Supprimer seulement de git mais pas dans notre folder
git rm --cached toto.txt

git commit -m "Add .gitignore and todo.txt delete"

Renommer + Changement + commit -> problème de restauration

utilise git mv script.js script2.js 




Pushed : 
git remote -v

git remote add origin https://github.com/SitrakaResearchAndPOC/random-number-app.git
git remote -v

git branch -m master main
git push -u origin main

Regarder la liste de commit et les diff en remote  


Supprimons le console.log dans script.js
----------------------------------------

En local: 
git add .
git commit -m "Remove console.log from script.js"

(la branche est à un commit devant de main)
git status

publier le changement 
git push


Ajout de readme : 
# Github en 1h
Ceci est un repository d'exemple 

-> Pas de stage directement commit

Le problème inverse : en local pas de mis à jour
git fetch
git status

Reprendre readme.md
--------------------
git pull



Sauvegarder des commit 
Si tous le monde font des commits (michel, marie ) pas trop securisé
Copier le code sur une branche et l'inserer dans la branche principale
 

git branch               # Voir les branches existantes

création d'une nouvelle branche :  
git branch nom-de-ta-nouvelle-branche a1b2c3d

création d'une nouvelle branche en changement de branche :
git switch -c add-min-max-input

git config --global help.autocorrect true


Changer index.html 

(Pas trop conseillé) 
git commit -am "add html for min max feature"

git commit -am "update js wit min max"

git push -u origin add-min-max-input


Sur github il y a deux branches

git switch main
git merge add-min-max-input

voir auss gitlens

Autres commandes 
git checkout -b ma-branche  # Créer et se déplacer sur une nouvelle branche
git checkout main        # Revenir à la branche principale
git merge ma-branche     # Fusionner une branche avec la branche actuelle



git branch nom-de-ta-nouvelle-branche a1b2c3d
git checkout -b nom-de-branche a1b2c3d



------------------
todo.txt

git rm script.js

git status

git restore script.js 

git status 

git restore --staged script.js

git status

git rm --cached todo.txt

git commit -m "add gitignore"






*******************************************************************************************
Utilise git stash :

bash
Copy
Edit
git stash
git checkout d75f6ad507d64829e2bcefee68ceca446865f620
🧤 Tes modifs sont mises de côté (stash = comme une boîte temporaire).
Tu pourras les récupérer après avec :

bash
Copy
Edit
git stash pop
 



Option 2 : Tu t'en fous des modifs → tu veux les supprimer
bash
Copy
Edit
git checkout -- test.html
git checkout d75f6ad507d64829e2bcefee68ceca446865f620
🔁 La première commande annule les changements sur test.html
La deuxième te laisse enfin revenir au commit.






