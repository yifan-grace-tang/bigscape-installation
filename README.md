# BiG-SCAPE Installation Guide

> [!NOTE]  
> This guide is intended for __Mac__ and __Windows__ installation for other operating systems repurpose the generic steps and instructions listed below.

This BiG-SCAPE Installation Guide attempts to provide specific step-by-step instructions in order to install all the required dependencies needed to run BiG-SCAPE from your computer. The instructions will attempt to be as granular as possible, but whenever you get stuck reference the linked information provided in each section. For __Mac__ based installation follow these steps (in order):

1) [Brew Installation](#brew-installation)
2) [Miniconda Installation](#miniconda-installation)
3) [BiG-SCAPE Installation](#big-scape-installation)

## Brew Installation

`brew` is a package manager for Mac which means in laymans term that it more easily installs missing softwares from your computer that are required later in the installation pipeline. While not explicitely required it will massively ease the process later on when certain commands are missing from your machine. The main installation guide is available [here](https://brew.sh) but first reference the instructions below.

1) Start by checking if `brew` is already installed on your machine, open your `terminal` applicaction and paste:

```bash
brew -v
```

2) If the `brew` command is not found you will see this message:

```bash
zsh: command not found: brew
```

3) If the `brew` command is found you will see something along the lines of this message (note that the specific `brew`  version may not perfectly align). If `brew` is found then proceed to the __Minoconda Installation__ section.

```bash
Homebrew 4.3.7
```

4) To install `brew` copy and paste the following command into your `terminal`:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

5) If prompted for your password type your computer login password - the information you type will not appear on the terminal so just finish typing your password and cllck enter.

6) After `brew` succesfully installs on your computer you will need to type two more commands in order to actually use `brew` from the `terminal`. In the commands below replace __USERNAME__ with your username.

```bash
echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/USERNAME/.zprofile
```
```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```

7) `brew` should now be succesfully installed! Validate it again by using the command found in step 1.
 
## Miniconda Installation

> [!WARNING]  
> The Miniconda version that you use is very specific for BiG-SCAPE to properly function, follow these instructions _exactly_. Don't use the _M1_ specific installation version even if your Mac supports that chip.

> [!NOTE]
> Miniconda is also refered to as `conda` and those terms will be used interchangibly in this installation guide.

`conda` handles the required `python` dependencies needed for BiG-SCAPE to function and also manages the creation of the BiG-SCAPE virtual environment where you will run the BiG-SCAPE commands from. The official documentation for Miniconda installation is available [here](https://docs.anaconda.com/miniconda/), but start by referring to the instructions below.


1) Start by verifying that conda is not installed on your machine, by pasting:

```bash
conda -V
```

2) If the `conda` command is not found you will see this message:

```bash
zsh: command not found: conda
```

3) If the `conda` command is found you will see something along the lines of this message (note that the specific `conda`  version may not perfectly align). If `conda` is found then proceed to the __BiG-SCAPE Installation__ section.

```bash
conda 24.5.0
```

4) In order to download the neccessary command in order to pull the `conda` install we first need to install the `wget` command using the `brew` installer we previously configured:

```bash
brew install wget
```

5) To install the correct `conda` version compatible with BiG-SCAPE copy and paste the command below:

```bash
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

6) The above command will pull the downloader to your machine, but now we need to run the installer to actually configure `conda` on your computer. Copy and paste the command below:

```bash
bash Miniconda3-latest-Linux-x86_64.sh
```

7) The installation of `conda` from here will require some action on your part. At certain points you will need to type `return` to continue, scroll down to finish reading the terms and conditions, or when prompted to accept an agreement type the word `yes`.

8) `conda` should now be succesfully installed! Validate it again by using the command found in step 1.


## BiG-SCAPE Installation




