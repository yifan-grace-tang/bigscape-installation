# BiG-SCAPE Installation Guide

> [!CAUTION]
> __Please read through this entire guide before getting started as it will save you a lot of time troubleshooting errors later on__. 

Even if you have never installed similar softwares on your computer before, you should be able to install BiG-SCAPE _as long as you read this guide thoroughly_.

## Before You Get Started

Unless otherwise specified, use the copy button feature on GitHub __only__, do not attempt to manually type commands into your terminal. Below is the icon you should look for to copy commands into your clipboard:

![GitHub Copy Icon](./img/copy-code.png)

If commands are expected to take a long time to complete they will be indicated with this icon ⌛. Ttil his means that either you should wait until a confirmation/continue action or wait until you can type again.

When editing text in the terminal window you __cannot highlight__ a particular area __and delete__ with your keyboard. Instead to delete a portion of your command you must use your left arrow and navigate to the portion you want to edit

__Mac: Terminal__

When referring to the `terminal` application on your Mac you can open the launchpad and look for this icon:

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b3/Terminalicon2.png/240px-Terminalicon2.png" width="100" height="100"/>

__Windows: Command Prompt__

When referring to the `command prompt` application on your Windows computer you can look for this icon:

<img src="https://upload.wikimedia.org/wikipedia/en/e/ef/Command_prompt_icon_%28windows%29.png" width="100" height="100"/>

## Installation Roadmap

For __Mac__ based installation follow these steps (in order):

1) [Brew Installation (Mac)](#brew-installation)
2) [Miniconda Installation (Mac)](#miniconda-installation)
3) [BiG-SCAPE Installation (Mac)](#big-scape-installation)

For __Windows__ based installation follow these steps (in order):

1) [Miniconda Installation (Windows)](#miniconda-installation)
2) [BiG-SCAPE Installation (Windows)](#big-scape-installation)

## 🍻 Brew Installation (Mac)

<details>
<summary> </summary>
 
`brew` is a package manager for Mac which means in laymans term that it more easily installs missing softwares from your computer that are required later in the installation pipeline. While not explicitely required it will massively ease the process later on when certain commands are missing from your machine. The main installation guide is available [here](https://brew.sh) but first reference the instructions below.

</details>

1) Check if `brew` is already installed on your computer. Open your `terminal` <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b3/Terminalicon2.png/240px-Terminalicon2.png" width="20" height="20"/> applicaction and paste into your terminal:

```bash
brew -v
```

2) If `brew` is already installed, you will see a message similar to the one below (versions can differ). Proceed to the [Miniconda Installation](#miniconda-installation) section.

```bash
Homebrew 4.3.7
```

3) If you see the message below - proceed to step 4:

```bash
zsh: command not found: brew
```

4) Copy and paste the following command into your `terminal` and click `return`:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

5) When prompted for your __password__ as seen below, type your computer login password 
__Missing Image Here__

__Note:__ The information you type will not appear on the terminal, so just finish typing your password and click `return`.

6) Paste into your terminal:

```bash
(echo; echo "eval \"\$($(brew --prefix)/bin/brew shellenv)\"") >> /Users/$USER/.zprofile
```

7) Paste into your terminal:
```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```

8) Check if `brew` is successfully installed on your computer. Paste:

```bash
brew -v
```

9) If `brew` is successfully installed, you will see a message similar to the one below (versions can differ). Proceed to the [Miniconda Installation](#miniconda-installation) section.

```bash
Homebrew 4.3.7
```
 
## 🐍 Miniconda Installation (Mac)

<details>
<summary> </summary>

`conda` handles the required `python` dependencies needed for BiG-SCAPE to function and also manages the creation of the BiG-SCAPE virtual environment where you will run the BiG-SCAPE commands from. The official documentation for Miniconda installation is available [here](https://docs.anaconda.com/miniconda/), but start by referring to the instructions below.

</details>

> [!WARNING]  
> __Follow the file download instructions very carefully! If you don't download the right file, there will be lots of troubleshooting.__

> [!NOTE]
> Miniconda is also refered to as `conda` and those terms will be used interchangibly in this installation guide.

1) Check if conda is already installed on your computer. Paste in your `terminal` <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b3/Terminalicon2.png/240px-Terminalicon2.png" width="20" height="20"/> :

```bash
conda -V
```

2) If the `conda` is already installed, you will see a message similar to the one below (versions can differ). Proceed to the [BiG-SCAPE Installation (Mac)](#big-scape-installation) section.

```bash
conda 24.5.0
```

3) If the `conda` is __not__ installed, then you will see the message below - proceed to step 4:

```bash
zsh: command not found: conda
```


5) Copy and paste the following command into yout `terminal`:

```bash
curl -sL \
  "https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh" > \
  "Miniconda3.sh"
```
__Insert cd Downloads__
6) Paste into your terminal:

```bash
bash Miniconda3-latest-MacOSX-x86_64.sh
```

7) __***Insert screenshots of what to do when you see what__.

8) Close your `terminal` window and open a __new__ `terminal` window.

9) Check if conda is successfully installed on your computer. Paste in your `terminal`:

```bash
conda -V
```

10) If the `conda` is sucessfully installed, you will see a message similar to the one below (versions can differ). Proceed to the [BiG-SCAPE Installation (Mac)](#big-scape-installation) section.

```bash
conda 24.5.0
```

## BiG-SCAPE Installation (Mac)

1) Open a new `terminal` <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b3/Terminalicon2.png/240px-Terminalicon2.png" width="20" height="20"/>  window.

2) Paste into your terminal:

```bash
cd Desktop && mkdir bigscape && cd bigscape
```
3) Paste into your terminal:

```bash
wget https://github.com/medema-group/BiG-SCAPE/archive/refs/tags/v1.1.5.zip
```
4) Paste into your terminal:

```bash
unzip v1.1.5
```
5) Paste into your terminal:
```bash
cd BiG-SCAPE-1.1.5
```
6) Paste into your terminal:

```bash
conda env create -f bigscape_dependencies.yml
```

7) Finally, copy and paste the command below. You will see a change in your terminal after this completes with a `(bigscape)` in the beginning of your line __Insert Image__:

```bash
conda activate bigscape
```
8) Validate the installation by pasting the command below:

```bash
python bigscape.py --version
```
9) Paste into your terminal:

```bash
wget https://ftp.ebi.ac.uk/pub/databases/Pfam/current_release/Pfam-A.hmm.gz && gunzip Pfam-A.hmm.gz
```
10) Paste into your terminal:
```bash
hmmpress Pfam-A.hmm
```






