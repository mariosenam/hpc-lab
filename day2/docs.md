# Calcul Benin HPC Training : Premiers pas avec le Terminal GNU/Linux

Le terminal est un outil puissant et essentiel pour naviguer et interagir avec votre système Linux. Ce guide vous aidera à comprendre et à utiliser les commandes de base du terminal.

## Modèle des commandes Linux

Les commandes Linux suivent généralement cette structure :

```bash
[commande] [options] [paramètres...]
```

### Description des éléments

- **`[commande]`** : Le nom de la commande à exécuter (par exemple, `ls`, `grep`, `cp`).
- **`[options]`** : Modificateurs qui changent le comportement de la commande. Ces options commencent souvent par un tiret (`-`) ou deux tirets (`--`), par exemple `-l` ou `--recursive`.
- **`[paramètres...]`** : Les paramètres sont les arguments supplémentaires que la commande traite, comme des noms de fichiers ou des chemins.

### Exemples concrets

2. **Recherche de texte avec `grep`**

   ```bash
   grep -i "texte" fichier.txt
   ```

   - `grep` : Commande pour rechercher du texte dans un fichier.
   - `-i` : Option pour ignorer la casse.
   - `"texte"` : Texte à rechercher (paramètre).
   - `fichier.txt` : Fichier dans lequel faire la recherche (paramètre).

3. **Copie de fichiers avec `cp`**

   ```bash
   cp -r source/ destination/
   ```

   - `cp` : Commande pour copier des fichiers ou dossiers.
   - `-r` : Option pour copier de manière récursive (nécessaire pour copier des dossiers).
   - `source/` : Dossier source à copier.
   - `destination/` : Dossier de destination.

---

Ce modèle vous sert de référence pour comprendre comment composer et exécuter des commandes Linux.

## Commandes de base

### Navigation dans le système de fichiers

1. **Afficher le répertoire courant avec `pwd`**

```bash
pwd
```

pwd : Commande pour afficher le chemin du répertoire courant.

2. **Liste des fichiers avec `ls`**

```bash
ls -l /home/user
```

- `ls` : Commande pour lister les fichiers.
- `-l` : Option pour afficher la liste en format détaillé.
- `/home/user` : Paramètre indiquant le chemin du répertoire.

3. **Copie de fichiers avec `cp`**

```bash
cp -r source/ destination/
```

- `cp` : Commande pour copier des fichiers ou dossiers.
- `-r` : Option pour copier de manière récursive (nécessaire pour copier des dossiers).
- `source/` : Dossier source à copier.
- `destination/` : Dossier de destination.

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

Voici un exemple de script Bash qui utilise les commandes grep, cut, et sort pour extraire, transformer et trier des données dans un fichier texte. Imaginons que nous ayons un fichier texte (data.txt) contenant des informations sur des utilisateurs sous la forme suivante

```bash
id,name,age,city
1,Alice,30,Paris
2,Bob,25,London
3,Charlie,35,Paris
4,David,28,Berlin
5,Eve,22,Paris
```

Ce script extrait les noms des utilisateurs vivant à dans une ville donné, les trie par ordre alphabétique, puis affiche le résultat.

Voici un script bash plus avancé qui utilise `grep`, `cut`, et `sort` :

```bash
#!/bin/bash

# Vérifier que deux arguments sont passés (le fichier et le nom de la ville) à notre script
if [ "$#" -ne 2 ]; then
  echo "Usage: $0 <fichier> <ville>"
  exit 1
fi

# Arguments
file="$1"
city="$2"

# Utiliser grep pour sélectionner les lignes contenant la ville spécifiée,
# cut pour extraire la colonne des noms, puis sort pour trier
grep "$city" "$file" | cut -d',' -f2 | sort
```

Pour exécuter ce script :

1. Créez le fichier :

```bash
nano extract.sh
```

2. Ajoutez le contenu ci-dessus.
3. Rendez le script exécutable :

```bash
chmod +x extract.sh
```

4. Exécutez le script :

```bash
./extract.sh data.text Paris
```

On peut faire la même chose pour extraire des informations spécifiques depuis ce fichier. Le fichier de log contiendra des entrées avec des informations sur des calculs.

## Automatisation des tâches sous Linux

### 1. **Utilisation de `at` (pour des tâches ponctuelles)**

La commande **`at`** permet de planifier l'exécution d'une commande ou d'un script à un moment donné dans le futur. Contrairement à `cron`, qui permet de planifier des tâches répétitives, `at` est utilisé pour des tâches **ponctuelles**.

### Exemple :

Planifier l'exécution d'un script à 15h demain :

```bash
at 15:00 <<EOF
echo "Bienvenue à la formation HPC de Calcul Bénin" > result_at.text
EOF
```

### Commandes utiles :

- `atq` : Afficher les tâches planifiées.
- `atrm` : Supprimer une tâche planifiée.
- `at now + 5 minutes` : Exécuter une commande après 5 minutes.

---

## 2. **Utilisation de `cron` (pour des tâches planifiées)**

Le **démon `cron`** permet de planifier l'exécution de commandes ou de scripts à des moments spécifiques. Il est basé sur des **fichiers de configuration** appelés **crontabs**. Un fichier `crontab` définit quand et quelle commande ou script doit être exécuté.

### Syntaxe du fichier `crontab`

Le fichier `crontab` suit la structure suivante :

```bash
* * * * * /chemin/vers/commande
- - - - -
| | | | |
| | | | +---- Jour de la semaine (0 - 7) [0 ou 7 = dimanche]
| | | +------ Mois (1 - 12)
| | +-------- Jour du mois (1 - 31)
| +---------- Heure (0 - 23)
+------------ Minute (0 - 59)
```

### Exemple :

Planifier un script pour qu'il s'exécute tous les jours à 3h du matin :

```bash
0 3 * * * /home/user/script.sh
```

### Commandes utiles :

- `crontab -e` : Éditer le crontab de l'utilisateur actuel.
- `crontab -l` : Lister les tâches planifiées.
- `crontab -r` : Supprimer toutes les tâches planifiées.

## 3. **Utilisation de `watch` (pour des tâches répétées à intervalles réguliers)**

La commande **`watch`** permet d'exécuter une commande à intervalles réguliers et d'afficher le résultat dans le terminal.

### Exemple :

Exécuter la commande `ls` toutes les 5 secondes :

```bash
watch -n 5 ls
```

Cela affichera les fichiers du répertoire toutes les 5 secondes.

---

## 4. **Scripts shell pour automatiser des séries de tâches**

Les **scripts shell** permettent de regrouper plusieurs commandes dans un fichier exécutable. Ces scripts peuvent être utilisés pour automatiser des séries de tâches.

### Exemple d'un script simple :

Créez un fichier `backup.sh` :

```bash
#!/bin/bash

# Sauvegarder le répertoire /home/user
tar -czf /home/user/backup_$(date +%F).tar.gz /home/user

# Nettoyer les anciennes sauvegardes (plus de 30 jours)
find /home/user -name "backup_*.tar.gz" -type f -mtime +30 -exec rm {} \;
```

Rendez le script exécutable :

```bash
chmod +x /home/user/backup.sh
```

Exécutez le script manuellement :

```bash
/home/user/backup.sh
```

Ou planifiez-le avec `cron` pour l'exécuter automatiquement à intervalles réguliers.

## Conclusion

Le terminal peut sembler intimidant au début, mais avec un peu de pratique, il devient un outil extrêmement puissant et flexible pour interagir avec votre système GNU/Linux. Continuez à explorer et à expérimenter avec ces commandes pour devenir plus à l'aise avec le terminal.
