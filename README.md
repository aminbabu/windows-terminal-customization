# Customize Your Windows Terminal - Like A Pro

No more default windows terminal! Let's customize our windows terminal like a pro using [oh-my-posh](https://ohmyposh.dev/docs/windows/) a prompt theme engine for any shell.

![Windows Terminal Preview](./assets/images/windows-terminal.png)

## Table of contents

- [Customize Your Windows Terminal - Like A Pro](#customize-your-windows-terminal---like-a-pro)
  - [Table of contents](#table-of-contents)
  - [Prerequisites](#prerequisites)
    - [Install Windows Terminal](#install-windows-terminal)
    - [Setup Powerline Fonts](#setup-powerline-fonts)
    - [Git Installation](#git-installation)
    - [Execution Policy](#execution-policy)
    - [Required Modules](#required-modules)
    - [PowerShell Core (optional)](#powershell-core-optional)
  - [My process](#my-process)
    - [Modify Terminal Settings](#modify-terminal-settings)
    - [Import Modules & Install Terminal Theme](#import-modules--install-terminal-theme)
    - [Set Terminal Profile](#set-terminal-profile)
    - [Customize Terminal Theme (Optional)](#customize-terminal-theme-optional)
  - [Author](#author)

## Prerequisites

### Install Windows Terminal

First of all, need to install [Microsoft Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal-preview/9n0dx20hk701#activetab=pivot:overviewtab) from the Microsoft Store or you can check their [GitHub repo.](https://github.com/Microsoft/Terminal) as well.

### Setup Powerline Fonts

To do some fancy styling in our terminal, now we need to install some Powerline like fancy fonts. Here, I'm gonna use use [FiraMono Nerd Font](https://objects.githubusercontent.com/github-production-release-asset-2e65be/27574418/5b8e7c00-4531-11ea-9838-c3a20ed19894?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20211208%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20211208T144417Z&X-Amz-Expires=300&X-Amz-Signature=f9deb10bd66524c4f258131f1b4551d67386753f79af40e53c5293ad59605ee0&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=27574418&response-content-disposition=attachment%3B%20filename%3DFiraMono.zip&response-content-type=application%2Foctet-stream), download from their official website: [Nerd Fonts](https://www.nerdfonts.com/font-downloads). Download and install any powerline font into your machine.

### Git Installation

It's time to download and install git from the official source. Here you will find it: [Git SCM](https://git-scm.com/). I'm not gonna show you how to install git (😜).

### Execution Policy
Sometimes we face some difficulties to install any module in PowerShell. To solve the matter simply run the command.

```sh
Set-ExecutionPolicy Unrestricted -Scope CurrentUser
```
Or,
```sh
Set-ExecutionPolicy Unrestricted
```

### Required Modules
Now run [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal-preview/9n0dx20hk701#activetab=pivot:overviewtab) as adminstator. Before installing any module, we need to set windows execution policy to unrestricted so that we can do the rest without any exception. Let's write the follwing commands and hit enter one by one to install them into our machine.

```sh
Install-Module posh-git -Scope CurrentUser
Install-Module oh-my-posh -Scope CurrentUser
```

### PowerShell Core (optional)

If you are using PowerShell Core, install PSReadLine module using the following command.

```sh
Install-Module -Name PSReadLine -Scope CurrentUser -Force -SkipPublisherCheck
```

## My process

### Modify Terminal Settings

Open terminal `settings.json` by pressing [`Ctrl + ,`] in any code editor. Then, select all by pressing [`Ctrl + a`] and hit delete button. Now we need to copy and paste everyting from the given link to our `settings.json`. Then save by pressing [`Ctrl + s`] and close `settings.json` file.

- `settings.json` file will be found here: [Terminal settings.josn](./Windows%20Terminal%20Settings/settings.json)

**Note:** This settings will only work if you do not change your git installation directory. If do so, then change the `commandline` and `icon` file path in the `settings.json`.

### Import Modules & Install Terminal Theme

To import Oh My Posh run the following commands one by one.

```sh
Import-Module posh-git
Import-Module oh-my-posh
```

All are set. Now It's time to see all the installed theme those we can use as our default terminal theme. To see them copy and paste the command to windows terminal.

```sh
Get-PoshThemes
```

From here I am using [Hotstick Minimal](https://github.com/JanDeDobbeleer/oh-my-posh/blob/main/themes/hotstick.minimal.omp.json) as my default one. To do so run the given command.

```sh
Set-PoshPrompt -Theme hotstick.minimal
```

### Set Terminal Profile

To ensure all the modules imported and theme installed correctly edit the default terminal profile. First of all let's see where our terminal profile is located by running the command.

```sh
echo $profile
```

It will produce result as follows.

`C:\Users\{your_username}\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1`

Simply run the command.

```sh
notepad $profile
```

It will create, or open default shell profile in default notepad editor. In this stage, we will copy the strings from below and paste them into the `$profile` file, save it and close it. Finally, close the terminal and reopen it.

```sh
Import-Module posh-git
Import-Module oh-my-posh
Set-PoshPrompt -Theme hotstick.minimal
```

### Customize Terminal Theme (Optional)
If anyone wish to customize his/her terminal theme as mine then he/she can do through updating `{themename}.json` file. I'm providing my one here.

- `settings.json` file will be found here: [Theme settings.josn](./Terminal%20Theme%20Settings/hotstick.minimal.omp.json)

**Steps to do so**
- Find out `oh-my-posh` theme directory. i.e:

```sh
C:\Users\{your_username}\Documents\WindowsPowerShell\Modules\oh-my-posh\themes
```
- Select the right json theme file. i.e: `hotstick.minimal.omp.json` and open it with any editor.
- Erase everything from the json theme file. Open my json theme [settings](./Terminal%20Theme%20Settings/hotstick.minimal.omp.json) file. Copy all the settings and paste them to your theme settings file. Save it and simply close it.

Now you are able to see a eye catchy terminal like this one.

![Windows Terminal Preview](./assets/images/first-look.png)
Hurrah! We have done it. 😀

## Author

- Website - [AminBabu](aminbau.talkativecoder.com)
- Twitter - [@AminBabu\_](https://www.twitter.com/AminBabu_)