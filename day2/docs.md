# Calcul Benin HPC Training : Premiers pas avec le Terminal GNU/Linux

Le terminal est un outil puissant et essentiel pour naviguer et interagir avec votre système Linux. Ce guide vous aidera à comprendre et à utiliser les commandes de base du terminal.

## Commandes de base

### Navigation dans le système de fichiers

- `pwd` : Affiche le chemin du répertoire courant.

  ```bash
  pwd
  ```

- `ls` : Liste les fichiers et dossiers du répertoire courant.

  ```bash
  ls
  ```

- `cd <dossier>` : Change de répertoire.
  ```bash
  cd /chemin/vers/dossier
  cd ..  # Reculer d'un répertoire
  ```

### Gestion des fichiers et dossiers

- `mkdir <nom_dossier>` : Crée un nouveau dossier.

  ```bash
  mkdir mon_dossier
  ```

- `rmdir <nom_dossier>` : Supprime un dossier vide.

  ```bash
  rmdir mon_dossier
  ```

- `rm <nom_fichier>` : Supprime un fichier.

  ```bash
  rm mon_fichier.txt
  ```

- `rm -r <nom_dossier>` : Supprime un dossier et tout son contenu.

  ```bash
  rm -r mon_dossier
  ```

- `cp <source> <destination>` : Copie un fichier ou un dossier.

  ```bash
  cp fichier.txt /chemin/vers/destination/
  cp -r dossier_source/ dossier_destination/
  ```

- `mv <source> <destination>` : Déplace ou renomme un fichier ou un dossier.
  ```bash
  mv fichier.txt /chemin/vers/destination/
  mv ancien_nom.txt nouveau_nom.txt
  ```

### Affichage et édition de fichiers

- `cat <nom_fichier>` : Affiche le contenu d'un fichier.

  ```bash
  cat fichier.txt
  ```

- `less <nom_fichier>` : Affiche le contenu d'un fichier page par page.

  ```bash
  less fichier.txt
  ```

- `nano <nom_fichier>` : Ouvre un éditeur de texte en ligne de commande.

  ```bash
  nano fichier.txt
  ```

- `vim <nom_fichier>` : Ouvre un éditeur de texte avancé en ligne de commande.
  ```bash
  vim fichier.txt
  ```

### Gestion des processus

- `ps` : Affiche les processus en cours.

  ```bash
  ps
  ```

- `top` : Affiche les processus en temps réel.

  ```bash
  top
  ```

- `kill <PID>` : Termine un processus avec l'identifiant donné.
  ```bash
  kill 1234
  ```

### Redirection et pipes

- `>` : Redirige la sortie vers un fichier (écrase le contenu existant).

  ```bash
  echo "Bonjour" > fichier.txt
  ```

- `>>` : Redirige la sortie vers un fichier (ajoute au contenu existant).

  ```bash
  echo "Bonjour encore" >> fichier.txt
  ```

- `|` : Utilise la sortie d'une commande comme entrée pour une autre.
  ```bash
  ls -l | less
  ```

### Utilisation de l'historique des commandes

- `history` : Affiche l'historique des commandes.

  ```bash
  history
  ```

- `!<numéro>` : Réexécute une commande à partir de l'historique.
  ```bash
  !42  # Réexécute la commande numéro 42
  ```

### Commandes avancées : `grep`, `cut`, `sort`

- `grep` : Recherche des motifs dans un fichier.

  ```bash
  grep "motif" fichier.txt  # Recherche "motif" dans fichier.txt
  ```

- `cut` : Coupe des sections d'une ligne de texte.

  ```bash
  cut -d',' -f1 fichier.csv  # Affiche la première colonne d'un fichier CSV
  ```

- `sort` : Trie les lignes d'un fichier texte.
  ```bash
  sort fichier.txt  # Trie les lignes de fichier.txt par ordre alphabétique
  ```

### Scripts Bash

Les scripts bash sont des fichiers contenant une série de commandes qui sont exécutées dans un terminal. Voici un exemple simple de script bash :

1. Créez un fichier script :

```bash
nano mon_script.sh
```

2. Ajoutez le contenu suivant :

```bash
#!/bin/bash
echo "Bonjour, monde !"
ls -l
```

3. Rendez le script exécutable :

```bash
chmod +x mon_script.sh
```

4. Exécutez le script :

```bash
./mon_script.sh
```

### Exemple de script bash avec `grep`, `cut`, `sort`

Voici un script bash plus avancé qui utilise `grep`, `cut`, et `sort` :

```bash
#!/bin/bash

# Affiche les utilisateurs du système, trie par nom et affiche les trois premiers

# Récupère les utilisateurs
cut -d: -f1 /etc/passwd | sort | head -n 3

# Recherche les utilisateurs ayant /bin/bash comme shell par défaut
grep "/bin/bash" /etc/passwd | cut -d: -f1 | sort
```

Pour exécuter ce script :

1. Créez le fichier :

```bash
nano utilisateurs.sh
```

2. Ajoutez le contenu ci-dessus.
3. Rendez le script exécutable :

```bash
chmod +x utilisateurs.sh
```

4. Exécutez le script :

```bash
./utilisateurs.sh
```

## Conclusion

Le terminal peut sembler intimidant au début, mais avec un peu de pratique, il devient un outil extrêmement puissant et flexible pour interagir avec votre système GNU/Linux. Continuez à explorer et à expérimenter avec ces commandes pour devenir plus à l'aise avec le terminal.
