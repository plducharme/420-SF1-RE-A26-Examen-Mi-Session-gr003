# Examen de Mi-Session partie pratique Automne 2026 gr003

# Instructions
- Inscrire votre nom et numéro de DA dans l'entête de chaque fichier
- Ne pas oublier de faire le "push" pour la remise (vous pouvez utiliser "commit and push" de PyCharm)
  - Si vous avez fait un ou plusieurs "commit" sans faire de "push", vous devez faire un "push" final avant l'heure limite de l'examen
  - Pour ce faire, aller dans `Git` > `Push...` dans PyCharm
- Le fait de faire des "commit and push" permet de remettre votre code au fur et à mesure

# Documentation
- Vous pouvez consulter la documentation officielle sur [python.org](https://docs.python.org/fr/3.14/library/)
  - https://docs.python.org/fr/3.15/builtins/stdtypes.html
- Vous avez accès au dépôt du cours sur github.com pour consulter les exemples vus en classe [420-SF1-RE-A26](https://github.com/plducharme/420-SF1-RE-A26)
- Vous avez aussi accès aux notes de cours dans LÉA.

## Loto-Cubes (54 pts)
### Instructions
- Écrire le code dans le module ``loto_3_sur_9.py``
- Ne pas oublier d'inscrire votre nom et votre numéro de DA dans l'entête du fichier

### Énoncé
Vous devez implémenter un jeu de loto qui simule le tirage de cubes de couleurs dans un sac. Maintenant avec tirage bonus!!!

### Règles
- Le sac de cube contient 3 cubes bleus, 3 cubes verts et 3 cubes rouges
- Vous devez initialiser une liste nommée ``sac_cubes`` représentant le sac contenant les cubes à partir de la str ``sac_cubes_str`` qui vous est fournie.  
- Le joueur a un solde initial de 10 tickets
- À chaque partie, 3 cubes sont tirés du sac
  - Les cubes sont remis dans le sac entre chaque tirage
    - i.e. La liste de cubes reste toujours la même
  - Vous devez définir la fonction ``effectuer_tirage(sac_cubes: list) -> tuple[str, str, str]`` prenant en paramètre la liste de cubes (i.e. ``sac_cubes``) qui retournera 3 str choisies au hasard dans la liste passée en paramètre.
    - Vous devez utiliser la fonction ``random.choice()``
- Vous devez définir la fonction ``tirage_bonus(gain: int) -> int``
  - cette fonction permet de calculer les tickets bonus
  - prend en paramètre le gain
  - retourne le nombre de ticket bonus
  - vous devez utiliser ``random.randint()`` pour générer un nombre entre 100 (inclus) et 999 (inclus)
  - compter le nombre de chiffres pareils
    - Si il n'y a aucun chiffre pareil, retourner 0 ticket bonus
    - S'il y a 2 chiffres pareils, retourner la moitié du nombre de tickets gagnés en bonus
    - S'il y a 3 chiffres pareils, retourner la nombre de tickets gagnés en bonus
    - ex:
      - si la personne gagne 4 ticket et obtient ``666``, retournez 4 tickets en bonus
      - si la personne gagne 4 ticket et obtient ``144``, retournez 2 tickets en bonus
      - si la personne gagne 4 ticket et obtient ``142``, retournez 0 tickets en bonus
- Chaque partie coûte 1 ticket pour jouer
  - Le ticket sera déduit de son solde peu importe s'il gagne ou perd
  - Le tirage se fera en faisant appel à la fonction définie ci-dessus
- Les règles de gains sont les suivantes
  - Si le joueur obtient 3 cubes bleus
    - il gagne 10 tickets
    - appeler la fonction ``tirage_bonus()`` (voir plus haut) en passant le gain en paramètre et ajouter les tickets bonus aux gains
  - Si le joueur obtient au moins 2 cubes rouges
    - il gagne 6 tickets + tickets bonus
    - appeler la fonction ``tirage_bonus()`` (voir plus haut) en passant le gain en paramètre et ajouter les tickets bonus aux gains
  - Si le joueur obtient 3 cubes verts
    - il obtient 4 tickets
    - appeler la fonction ``tirage_bonus()`` (voir plus haut) en passant le gain en paramètre et ajouter les tickets bonus aux gains
  - S'il obtient 3 cubes de couleurs différentes, il obtient 1 ticket
  - Dans tous les autres cas, il n'obtient aucun gain
- Les gains sont ajoutés au solde du joueur
- Tant que le joueur possède des tickets, vous devez lui poser la question suivante:
  - ``"Continuer à jouer [o/n]? ``
    - S'il répond ``o``, on procède à une nouvelle partie
    - S'il répond ``n``, on quitte le jeu en lui indiquant son total de gains ou pertes
      - ex: son solde final est de 14, on affiche ``total des gains: 4``
      - ex: son solde final est de 2, on affiche ``total des pertes: 8``
      - ex: son solde final est de 10, on affiche ``kif-kif``
- Si le ne possède plus de tickets, on affiche ``Vous avez perdu!`` et l'on quitte le programme

### Barème
- création de la liste de cube (6 pts)
- fonction ``effectuer_tirage()`` (8 pts)
- fonction ``tirage_bonus()`` (10 pts)
- boucles de jeu (6 pts)
- Coût du tirage et mise à jour du solde (6 pts)
- Règles de gains (10 pts)
- Affichage exact des messages et questions à l'utilisateur (6 pts)
- Présences de commentaires explicatifs (2 pts)

## Vérifications
- Ne pas oublier d'inscrire votre nom et votre numéro de DA dans l'entête de chaque fichier
- Assurez-vous que votre code respecte les conventions de nommage et de style (PEP 8)
- Assurez-vous d'avoir fait un "push" de votre code avant l'heure limite de l'examen
- Vous pouvez toujours vérifier le contenu de votre remise en consultant le dépôt git directement sur github.com