# BiG-SCAPE Installation Guide

__Please read through this entire guide before getting started as it will save you a lot of time troubleshooting errors later on__. This BiG-SCAPE Installation Guide attempts to provide extremely specific step-by-step instructions in order to install all the required dependencies needed to run BiG-SCAPE from your computer. 

Even if you have never installed similar softwares on your computer before, you should be able to install BiG-SCAPE _as long as you read this guide thoroughly_.


> [!WARNING]
> Use the copy button feature on GitHub __only__, do not type commands into your terminal window unless instructed to by the protocol.

![GitHub Copy Icon](./img/copy-code.png)
_Look for this icon_

> [!WARNING]
> When editing text in the terminal window you cannot highlight a particular area and delete with your keyboard, instead to delete a portion of your command you must use your left arrow and navigate to the portion you want to edit

This BiG-SCAPE Installation Guide attempts to provide specific step-by-step instructions in order to install all the required dependencies needed to run BiG-SCAPE from your computer. 

When referring to the `terminal` application on your Mac you can open the launchpad and look for this icon:

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b3/Terminalicon2.png/240px-Terminalicon2.png" width="150" height="150"/>

When referring to the `command prompt` application on your Windows computer you can look for this icon:

<img src="https://upload.wikimedia.org/wikipedia/en/e/ef/Command_prompt_icon_%28windows%29.png" width="150" height="150"/>

For __Mac__ based installation follow these steps (in order):

1) [Brew Installation](#brew-installation)
2) [Miniconda Installation](#miniconda-installation)
3) [BiG-SCAPE Installation](#big-scape-installation)

For __Windows__ based installation follow these steps (in order):

1) [Miniconda Installation](#miniconda-installation)
2) [BiG-SCAPE Installation](#big-scape-installation)

If commands are expected to take a long time to complete they will be indicated with the  <img src="https://upload.wikimedia.org/wikipedia/commons/4/42/Heures_b%C3%A9n%C3%A9voles.png" height="40" /> icon

## Brew Installation

<details>
<summary> </summary>
 
`brew` is a package manager for Mac which means in laymans term that it more easily installs missing softwares from your computer that are required later in the installation pipeline. While not explicitely required it will massively ease the process later on when certain commands are missing from your machine. The main installation guide is available [here](https://brew.sh) but first reference the instructions below.

</details>

1) Start by checking if `brew` is already installed on your machine, open your `terminal` applicaction and paste:

```bash
brew -v
```

2) If you see the below message - proceed to step 4:

```bash
zsh: command not found: brew
```

3) If the `brew` command is found you will see something along the lines of this message (the specific `brew`  version may not be 4.3.7). If you see this message proceed to the __Minoconda Installation__ section.

```bash
Homebrew 4.3.7
```

4) Copy and paste the following command into your `terminal` and click `return`:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

5) If prompted for your __password__ type your computer login password - the information you type will not appear on the terminal so just finish typing your password and cllck `return`.

6) After `brew` succesfully installs on your computer you will need to copy and paste the next two commands in succession:

```bash
(echo; echo "eval \"\$($(brew --prefix)/bin/brew shellenv)\"") >> /Users/$USER/.zprofile
```
```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```

7) `brew` should now be succesfully installed! Validate it again by using the command found in step 1.
 
## Miniconda Installation

<details>
<summary> </summary>

`conda` handles the required `python` dependencies needed for BiG-SCAPE to function and also manages the creation of the BiG-SCAPE virtual environment where you will run the BiG-SCAPE commands from. The official documentation for Miniconda installation is available [here](https://docs.anaconda.com/miniconda/), but start by referring to the instructions below.

</details>

> [!WARNING]  
> The Miniconda version that you use is very specific for BiG-SCAPE to properly function, follow these instructions _exactly_. Don't use the _M1_ specific Miniconda installation even if your Mac supports that chip.

> [!NOTE]
> Miniconda is also refered to as `conda` and those terms will be used interchangibly in this installation guide.

1) Start by verifying that conda is not installed on your machine, by pasting into your `terminal`:

```bash
conda -V
```

2) If the `conda` command is not found you will see this message - proceed to step 4:

```bash
zsh: command not found: conda
```

3) If the `conda` command is found you will see something along the lines of this message (note that the specific `conda`  version may not be 24.5.0). If `conda` is found then proceed to the __BiG-SCAPE Installation__ section.

```bash
conda 24.5.0
```

4) Start by copying and pasting the below command - this requires __Brew Installation__ (ignore this step if you are using a Windows machine):

```bash
brew install wget
```

5) Next copy and paste the command below:

```bash
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

6) After step 5 completes copy and paste the below command:

```bash
bash Miniconda3-latest-Linux-x86_64.sh
```

7) The installation of `conda` from here will require some action on your part. At certain points you will need to click `return` to continue, scroll down to finish reading the terms and conditions with your down arrow key, or when prompted to accept an agreement type the word `yes`.

8) `conda` should now be succesfully installed! Close your `terminal` window and open a new one before using the command found in step 1 to validate the installation.

## BiG-SCAPE Installation

> [!NOTE]  
> These instructions will assume that `bigscape` will run from your Mac's `Desktop` folder, however you can replace the file paths provided with custom paths if you wish in step 2.

1) Start by opening a new `terminal` window.

2) From this new window copy and paste the below command:

```bash
cd Desktop && mkdir bigscape && cd bigscape
```
3) Next copy and paste the below command - this assumes that you completed step 4 of __Miniconda Installation__:

```bash
wget https://github.com/medema-group/BiG-SCAPE/archive/refs/tags/v1.1.5.zip
```
4) Afterwards copy and paste this command:

```bash
unzip v1.1.5
```
5) Next, copy and paste this command:
```bash
cd BiG-SCAPE-1.1.5
```
6) Afterwards, copy and paste this command - this relies on succesfully completing the __Miniconda Installation__:

```bash
conda env create -f bigscape_dependencies.yml
```

7) Next, copy and paste this command you will see a change in your terminal after this completes with a `(bigscape)` popping up:

```bash
conda activate bigscape
```
8) You can validate the succesfull installation by running the below command:

```bash
python bigscape.py --version
```
9) The final commands to run (to be done in succession) can be copy and pasted from below - these may take a while to complete:

```bash
wget https://ftp.ebi.ac.uk/pub/databases/Pfam/current_release/Pfam-A.hmm.gz && gunzip Pfam-A.hmm.gz
```
```bash
hmmpress Pfam-A.hmm
```






