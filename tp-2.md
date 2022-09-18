Bouskine Nordine 

## Exercice 1. Variables d'environnement

1 - Variable PATH : trouver les commandes tapées par l'utilisateur
printenv PATH
/usr/local/sbin:/usr/local/bin
:/usr/sbin:/usr/bin:/sbin
:/bin:/usr/games:/usr/local/games
:/snap/bin

2 - Variable $HOME permet à la commande cd tapée sans argument de renvoyer vers le répertoire personnel

3 - $LANG : la langue du système
$PWD : le chemin vers le répertoire courant
$OLDPWD : le chemin vers le dernier répertoire
$SHELL : le type de shell utilisé, en l'occurence bash

4 -Création variable locale
MY_VAR="CONTENU"
echo $MY_VAR

5 - Commande bash ouvre une sessiondans la session actuelle. Les variables locales créées plus tôt ne sont plus accéssible dans la nouvelle session.

6 -
export MY_VAR="CONTENU"
bash
echo $MY_VAR
La variable a été exporté dans la nouvelle session

7 -

export NOM="nordine bouskine" ; echo $NOM

8 -

echo "Bonjour à vous $NOM"

9 - Commande unset : suppression de la variable mais pas de son contenu

10 -

echo '$HOME' "= $HOME"
Programmation Bash -

nano ~/.bashrc
PATH:$PATH:~/script


## Exercice 2. Controle de mot de passe

#!/bin/bash

mdp = "nordine"

read -s -p "Saisir un mot de passe " input

if [ _$input == _$mdp ]; then 
    echo "bon mdp"
else 
    echo "mauvais mdp"
fi

## Exercice 3. Expressions rationnelles

#!/bin/bash

function is_number()
{
    re='^[+-]?[0-9]+([.][0-9]+)?$'
    if ! [[ $1 =~ $re ]] ; then
        return 1
    else
        return 0
    fi
}

is_number $1
if [ $? -eq 0 ] ; then
    echo "nombre réel"
else
    echo "pas un nombre réel"
fi



