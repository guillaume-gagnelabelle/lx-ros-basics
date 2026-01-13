<p align="center">
<a href="https://duckietown.com"><img src="./assets/images/dtlogo.png" alt="Duckietown Logo" width="50%"></a>
</p>

# Avant de commencer

Avant de commencer ce laboratoire, nous devons configurer votre compte sur l'ordinateur local que vous utiliserez pour toutes vos séances de travaux pratiques dans le cadre du cours AA3331.

1. Cliquez sur la session de connexion appropriée (soit la session du mardi, soit celle du jeudi). Le mot de passe doit être `TcrdhwrAplfIWJ`. Vous serez immédiatement invité(e) à créer un mot de passe. Veuillez retenir ce mot de passe, car c'est celui que vous utiliserez tout au long du semestre.
2. Ouvrez un terminal en appuyant sur `Ctrl-Alt-T`.
3. Installez le Duckietown Shell avec `pipx install duckietown-shell`.
4. Assurez-vous que le fichier exécutable se trouve dans votre chemin d'accès avec `pipx ensurepath`
5. Vous devez vous déconnecter puis vous reconnecter pour que cette modification prenne effet.
6. L'un des deux membres du groupe doit se rendre sur https://hub.duckietown.com, créer un compte et générer un jeton. Une fois l'inscription terminée, le jeton sera disponible à l'adresse https://hub.duckietown.com/profile/. Il s'agit d'une longue chaîne de caractères commençant par `dt2-....`. Vous pouvez la copier dès maintenant en utilisant le bouton situé à gauche.
7. De retour dans le terminal, tapez `dts`. Cela initialisera le "Duckietown Shell". Lors du processus de configuration, il vous sera demandé de saisir le jeton que vous venez de copier. Lorsqu'on vous demande quel type de profil choisir, sélectionnez `ente`.
8. Enfin, exécutez la commande `dts setup mkcert`, qui est nécessaire pour exécuter VSCode dans le navigateur.


# **Labo 1: ROS Bases**

# Introduction

Dans le cadre de cette laboratoire, vous découvrirez les bases de [ROS (Robot Operating System)](https://ros.org/).


##  Mais d'abord...

Assurez-vous que votre système est à jour.

- 💻 Veillez toujours à ce que votre  Duckietown Shell soit mise à jour vers la dernière version: `pipx upgrade duckietown-shell`

- 💻 Mettre à jour les commandes du shell: `dts update`

- 💻 Assurez-vous que toutes les images Docker présentes sur votre ordinateur sont à jour: `dts desktop update`

- 🚙 Assurez-vous que toutes les images Docker présentes sur votre ordinateur sont à jour: `dts duckiebot update ROBOTNAME`
(where `ROBOTNAME` is the name of your Duckiebot - real or virtual.)


# Comment réaliser cet exercice de laboratoire ?

## Lancez l'éditeur de code.

Ouvrez l'éditeur de code (VSCode) en exécutant la commande suivante:

```
dts code editor
```

Attendez qu'une URL s'affiche dans le terminal, puis cliquez dessus ou copiez-la et collez-la dans la barre d'adresse de votre navigateur pour accéder à l'éditeur de code. Le premier élément que vous verrez dans l'éditeur de code est ce même document. 

**Vous pouvez poursuivre votre travail à partir de là**


## Les notebooks "Jupyter"

**REMARQUE** : Vous devez lire ce message depuis l'éditeur de code de votre navigateur.

Dans l'éditeur de code, utilisez la barre latérale de navigation située à gauche pour accéder au
dossier `notebooks` et ouvrir le premier notebook.

Suivez les instructions du notebook et parcourez les notebooks dans l'ordre.

Une fois que vous avez terminé toutes les tâches des carnets de notes, vous pouvez suivre les instructions suivantes pour tester votre code.

## Exécution de votre code

### Tester avec le Duckiematrix (optionnel)

Il peut être utile de tester votre code dans un environnement de simulation avant de l'essayer sur le robot réel. Pour cela, nous avons le Duckiematrix.

Pour tester votre code dans Duckiematrix, vous aurez besoin d'un robot virtuel. Vous pouvez en créer un avec la commande suivante:

```
dts duckiebot virtual create [VBOT]
```

où `[VBOT]` peut être n'importe quoi (mais n'oubliez pas ce nom pour la suite).

Vous pouvez ensuite démarrer votre robot virtuel avec la commande:

```
dts duckiebot virtual start [VBOT]
```

Vous devriez le voir avec le statut « Booting » (démarrage) et enfin « Ready » (prêt) si vous consultez la commande `dts fleet discover` :

```
     | Hardware |   Type    | Model |  Status  | Hostname 
---  | -------- | --------- | ----- | -------- | ---------
[VBOT] |  virtual | duckiebot | DB21J |  Ready   | [VBOT].local
```

Maintenant que votre robot virtuel est prêt, vous pouvez démarrer Duckiematrix. Depuis ce répertoire d'exercices, exécutez la commande suivante :

```
dts code start_matrix
```

Vous devriez voir le simulateur Duckiematrix, basé sur Unity, démarrer. L'écran de démarrage ressemblera à ceci :

![duckiematrix_start](assets/duckiematrix_start.png)

À partir d'ici, vous pouvez cliquer n'importe où dans la fenêtre et appuyer sur la touche [ENTRÉE] pour l'activer. Vous pouvez ensuite déplacer le petit canard vers le Duckiebot à l'aide des touches « w », « a », « s » et « d », ou modifier l'angle de la caméra pour observer le Duckiebot avec la souris. Vous pouvez également passer à une vue de dessus en appuyant sur la touche « v », ce qui vous donnera une vue similaire à celle-ci :

![duckiematrix_overhead](assets/duckiematrix_overhead.png)


### "Build" votre code

Vous pouvez build le code avec

```
dts code build -R ROBOTNAME
```

où ROBOTNAME peut être un robot réel ou virtuel.

### Tester le code

Vous pouvez ensuite exécuter votre code avec

```
dts code workbench -R ROBOTNAME [-m]
```

où ROBOTNAME peut être un robot réel ou virtuel, mais s'il s'agit d'un robot virtuel, vous devez inclure l'option `-m` pour indiquer que vous souhaitez le tester dans Duckiematrix.


Si vous ne l'avez pas encore fait, **il est temps de [commencer le premier notebook!](./notebooks/01_navigating_file_system.ipynb)**

## Credits

This learning experience is provided by Duckietown in collaboration with 
[Prof. Romulo Meira-Goes, Ph.D](https://www.eecs.psu.edu/departments/directory-detail-g.aspx?q=rzm5911) 
(Pennsylvania State University). Visit the 
[Duckietown Website](https://www.duckietown.com) for more learning materials, documentation, and demos.
