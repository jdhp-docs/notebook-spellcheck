.. warning:: Veuillez noter que ce document est en cours de rédaction. Dans son état actuel, il n'est pas destiné à être lu par d'autres personnes que ses auteurs.

Principales extensions disponibles
==================================

* `Spellchecker <https://github.com/ipython-contrib/jupyter_contrib_nbextensions/tree/master/src/jupyter_contrib_nbextensions/nbextensions/spellchecker>`__:

  * utilise `Typo.js <https://github.com/cfinke/Typo.js>`__
  * inspirée par https://github.com/NextStepWebs/codemirror-spell-checker/blob/78773ebdd6c8cf8acd043342023636ae345ca0f3/src/js/spell-checker.js
  * inconvénients:

    * ne permet d'utiliser qu'un seul dictionnaire (choisi au moment de l'installation)
    * surligne les fautes mais ne fait aucune suggestion pour les corriger

* https://github.com/Calysto/notebook-extensions/tree/master/calysto

Solutions dépréciées :

* https://github.com/ipython-contrib/jupyter_contrib_nbextensions/wiki/aspell : une extension côté serveur

Spellchecker
============

Télécharger `jupyter_contrib_nbextensions`:: 

    git clone https://github.com/ipython-contrib/jupyter_contrib_nbextensions.git

Pour alléger l'extension spellchecker, les dictionnaires ne sont pas inclus et sont ... online.
Pour ... offline:
Télécharger les dictionnaires::

    cd jupyter_contrib_nbextensions/src/jupyter_contrib_nbextensions/nbextensions/spellchecker/typo/dictionaries/
    wget https://chromium.googlesource.com/chromium/deps/hunspell_dictionaries/+/master/fr_FR.dic
    wget https://chromium.googlesource.com/chromium/deps/hunspell_dictionaries/+/master/fr_FR.aff
    cd ../../..

Configurer spellchecker:

* ouvrir le fichier `spellchecker/config.yaml` avec un éditeur de texte
* remplacer la ligne `default: 'https://cdn.jsdelivr.net/codemirror.spell-checker/latest/en_US.dic'` par `default: './typo/dictionaries/fr_FR.dic'`
* remplacer la ligne `default: 'https://cdn.jsdelivr.net/codemirror.spell-checker/latest/en_US.aff'` par `default: './typo/dictionaries/en_US.aff'`

Installer spellchecker::

    jupyter nbextension install spellchecker --user
    jupyter nbextension enable spellchecker/main --user

Vérifier::

    jupyter nbextension list --user

À lire aussi
============

* http://www.simulkade.com/posts/2015-04-07-spell-checking-in-jupyter-notebooks.html

Discussions :

* https://github.com/ipython/ipython/issues/4072
* https://github.com/ipython/ipython/issues/3216
