# Cheat sheets gitFlow  
  
<img src="https://raw.githubusercontent.com/PayenThibaud/Cheat-sheets-git/main/gitflowschema.png" alt="Schemagitflow" width="500"/>

## lancer git flow  
  
git flow init 
  
## Pour commencer à coder une feature, on créer une nouvelle branche par rapport à la branche dev
  
git flow feature start (nom)  
  
## Lorsqu'on a fini de coder la feature, on ferme notre branche et la merge dans la branche dev  
   
git flow feature finish (nom)  
  
## vérification du code avant lancement sur la branche main  
  
git flow release start (1.0.0)   
  
## Lancement sur la branche main après vérification  
  
git flow release finish (1.0.0)  
  
## envoyer le tag sur le dépot upstream  
  
git push origin --tags  
  
## Correction de bug / Hotfix  
  
git flow hotfix start (nom)  
  
## Une fois le correction du code, le hotfix se transmet sur la branche main et dev  
  
git flow hotfix finish (nom)  