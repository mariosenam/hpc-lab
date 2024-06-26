# Calcul Benin HPC Training

## Installation de R à partir des sources

Voici un guide en Markdown pour installer R à partir des sources :
Ce guide explique comment installer R à partir des sources sur un système Linux.

### Prérequis

Avant de commencer, assurez-vous d'avoir les paquets nécessaires installés sur votre système. Vous aurez besoin de :

- `build-essential`
- `libreadline-dev`
- `libx11-dev`
- `libxt-dev`
- `libpng-dev`
- `libjpeg-dev`
- `libcairo2-dev`
- `libtiff5-dev`
- `libcurl4-openssl-dev`
- `texinfo`
- `texlive`
- `gfortran`

Vous pouvez installer ces paquets avec la commande suivante (pour les systèmes basés sur Debian/Ubuntu).

Les administrateurs de **Calcul Bénin** ont déjà installé la plupart de ces paquets sur **asuka**.

sN'étant pas administrateur de **Calcul Bénin** vous pouvez ignorer cette étape ou demander aux administrateur de vous aider à les installer :

```bash
sudo apt-get update
sudo apt-get install -y build-essential libreadline-dev libx11-dev libxt-dev libpng-dev libjpeg-dev libcairo2-dev libtiff5-dev libcurl4-openssl-dev texinfo texlive gfortran
```

### Téléchargement des sources

Téléchargez la dernière version de R depuis le [site officiel](https://cran.r-project.org/sources.html) . Par exemple, pour télécharger R 4.1.0, utilisez la commande suivante :

```bash
wget https://cran.r-project.org/src/base/R-4/R-4.1.0.tar.gz
```

Assurez-vous de modifier les numéros de version et les chemins en fonction de la version spécifique de R que vous souhaitez installer.

### Extraction des sources

Extrayez l'archive téléchargée :

```bash
tar -xvzf R-4.1.0.tar.gz
cd R-4.1.0
```

### Préparation de l'environnement d'installation

Vous pouvez créer un dossier pour accueil le programme R à la fin de l'installation :

```bash
mkdir -p $HOME/softwares/R/4.1.0
```

### Configuration de la compilation

Avant de compiler R, vous devez configurer le processus de compilation :

```bash
./configure --prefix=$HOME/softwares/R/4.1.0 --enable-R-shlib --with-blas --with-lapack
```

L'option `--prefix` permet de spécifier le répertoire de destination du programme R.

L'option `--enable-R-shlib` permet de créer une bibliothèque partagée de R, ce qui est utile pour lier R à d'autres applications. Vous pouvez afficher toutes les options de configuration en faisant :

```bash
./configure -h
```

### Compilation et installation

Pour compiler et installer R, utilisez la commande suivante :

```bash
make
make check # Optionel
make install
```

Félicitations vous venez d'installer R dans le répertoire `$HOME/softwares/R/4.1.0`.

Vous pouvez vérifier le contenu en faisant :

```bash
ls $HOME/softwares/R/4.1.0
```

Le répertoire `bin` contient les binaires(executables) de notre programme **R**. Vous pouvez lister le contenu du répertoire en faisant :

```bash
ls $HOME/softwares/R/4.1.0/bin
```

### Vérification de l'installation

Vérifiez que R est correctement installé en exécutant la commande suivante :

```bash
cd # pour retourner dans votre répertoire personnel
./softwares/R/4.1.0/bin/R --version
```

ou

```bash
cd $HOME/softwares/R/4.1.0/bin # pour vous rendre dans le répertoire d'installation
./R --version
```

Vous devriez voir la version de R que vous venez d'installer.

### Installation des packages R

Pour cette section vous pouvez lancer **R** à partir de votre de répertoire personnel ou d'installation.

```bash
./R
```

Listez les packages disponibles sur **R** en faisant :

```R
> installed.packages()
```

Vous pouvez installer le package _readxl_ qui permet de lire les fichiers excel en faisant :

```R
> install.packages()
```

### Conclusion

Vous avez maintenant installé R à partir des sources sur votre système. Vous pouvez maintenant commencer à utiliser R pour vos projets statistiques et graphiques.

## Installation de Python à partir des sources

Ce guide explique comment installer Python à partir des sources sur un système Linux.

### Prérequis

Avant de commencer, assurez-vous d'avoir les paquets nécessaires installés sur votre système. Vous aurez besoin de :

- `build-essential`
- `libssl-dev`
- `libreadline-dev`
- `libffi-dev`
- `zlib1g-dev`

Vous pouvez installer ces paquets avec la commande suivante (pour les systèmes basés sur Debian/Ubuntu).

Les administrateurs de **Calcul Bénin** ont déjà installé la plupart de ces paquets sur **asuka**.

N'étant pas administrateur de **Calcul Bénin** vous pouvez ignorer cette étape ou demander aux administrateur de vous aider à les installer :

```bash
sudo apt-get update
sudo apt-get install -y build-essential libssl-dev libreadline-dev libffi-dev zlib1g-dev
```

### Téléchargement des sources

Téléchargez la dernière version de Python depuis le [site officiel](https://www.python.org/downloads/source/). Par exemple, pour télécharger Python 3.12.4, utilisez la commande suivante :

```bash
wget https://www.python.org/ftp/python/3.12.4/Python-3.12.4.tgz
```

Assurez-vous de modifier les numéros de version et les chemins en fonction de la version spécifique de Python que vous souhaitez installer.

### Extraction des sources

Extrayez l'archive téléchargée :

```bash
tar -xvzf Python-3.12.4.tgz
cd Python-3.12.4
```

### Préparation de l'environnement d'installation

Vous pouvez créer un dossier pour accueil le programme R à la fin de l'installation :

```bash
mkdir -p $HOME/softwares/python/3.12.4
```

### Configuration de la compilation

Avant de compiler Python, vous devez configurer le processus de compilation :

```bash
./configure --enable-optimizations --prefix=$HOME/softwares/python/3.12.4
```

L'option `--prefix` permet de spécifier le répertoire de destination du programme R.

L'option `--enable-optimizations` permet d'optimiser la vitesse de l'interpréteur Python en activant certaines optimisations au moment de la compilation.

Vous pouvez afficher toutes les options de configuration en faisant :

```bash
./configure -h
```

### Compilation et installation

Pour compiler et installer Python, utilisez la commande suivante :

```bash
make -j2
make install
```

L'option `-j2` permet de paralléliser la compilation en utilisant tous deux (02) cœurs de votre processeur, ce qui accélère le processus.

Félicitations vous venez d'installer **Python** dans le répertoire `$HOME/softwares/python/3.12.4`.

Vous pouvez vérifier le contenu en faisant :

```bash
ls $HOME/softwares/python/3.12.4
```

Le répertoire `bin` contient les binaires(executables) de notre programme **Python**. Vous pouvez lister le contenu du répertoire en faisant :

```bash
ls $HOME/softwares/python/3.12.4/bin
```

### Vérification de l'installation

Vérifiez que **Python** est correctement installé en exécutant la commande suivante :

```bash
cd # pour retourner dans votre répertoire personnel
./softwares/python/3.12.4/bin/python3 --version
```

ou

```bash
cd $HOME/softwares/python/3.12.4/bin # pour vous rendre dans le répertoire d'installation
./python3 --version
```

Vous devriez voir la version de **Pyhton** que vous venez d'installer.

### Configuration pour rendre permanente l'utilisation de la version de Python installée

Pour ce faire il vous faut modifier le fichier .bashrc qui se trouve dans votre répertoire personnel en utilisant l'editeur de votre choix `nano` ou `vim` etc

```bash
cd # Pour repartir dans votre dossier personnel
vim .bashrc
```

Votre fichier doit ressembler à ceci :

```bash
# .bashrc

# Source global definitions
if [ -f /etc/bashrc ]; then
	. /etc/bashrc
fi

# User specific environment
if ! [[ "$PATH" =~ "$HOME/.local/bin:$HOME/bin:" ]]
then
    PATH="$HOME/.local/bin:$HOME/bin:$PATH"
fi
export PATH

# Uncomment the following line if you don't like systemctl's auto-paging feature:
# export SYSTEMD_PAGER=

# User specific aliases and functions

export PATH=$HOME/softwares/python/3.12.4/bin:$PATH

```

Afin que vos changements soient pris en compte vous pouvez vous déconnecter et vous reconnecter ou pouvez taper la commande suivante :

```bash
source .bashrc
```

### Installation des packages Python

Le gestionnaire de paquet de **Python** est `pip3`. Pour installer un paquet utilisez la commande.

```bash
pip3 install --user pandas
```

### Conclusion

Vous avez maintenant installé Python à partir des sources sur votre système. Vous pouvez maintenant commencer à utiliser Python pour vos projets.
