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
    - [oh-my-posh Installation](#oh-my-posh-installation)
  - [Procedures](#procedures)
    - [Modify Terminal Settings](#modify-terminal-settings)
    - [Set Terminal Profile](#set-terminal-profile)
    - [Customize Terminal Theme (Optional)](#customize-terminal-theme-optional)
  - [Author](#author)

## Prerequisites

### Install Windows Terminal
- #### Windows 11
  - [Microsoft Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal-preview/9n0dx20hk701#activetab=pivot:overviewtab) is the default terminal for Windows 11
- #### Windows 10
  - Need to install [Microsoft Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal-preview/9n0dx20hk701#activetab=pivot:overviewtab) from the Microsoft Store or you can check their [GitHub repo](https://github.com/Microsoft/Terminal) as well.

### Setup Powerline Fonts
For fancy characters in the terminal, Powerline like fancy fonts will be needed. Here, I'm gonna use [FiraMono Nerd Font](https://objects.githubusercontent.com/github-production-release-asset-2e65be/27574418/5b8e7c00-4531-11ea-9838-c3a20ed19894?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20211208%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20211208T144417Z&X-Amz-Expires=300&X-Amz-Signature=f9deb10bd66524c4f258131f1b4551d67386753f79af40e53c5293ad59605ee0&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=27574418&response-content-disposition=attachment%3B%20filename%3DFiraMono.zip&response-content-type=application%2Foctet-stream), download from their official website: [Nerd Fonts](https://www.nerdfonts.com/font-downloads). Download and install any powerline font into your machine.

### Git Installation
It's time to download and install git from the official source. Here you will find it: [Git SCM](https://git-scm.com/). I'm not gonna show you how to install git (😜).

### OH-MY-POSH Installation
Make sure you have installed 'winget - Windows Package Manager' already. To check run the following command in your terminal:
```sh
winget --version
```

and you will be able to see the version number like this:
![Windows Package Manger - Winget](./assets/images/winget.png)

If you have not installed already then install windows package manager from Microsoft Store or install it from Microsoft Official Site manually: [Get Winget]('https://docs.microsoft.com/en-us/windows/package-manager/winget/').

#### **Alternative:**
Simply run the command:
```sh
Set-ExecutionPolicy Bypass -Scope Process -Force; Invoke-Expression ((New-Object System.Net.WebClient).DownloadString('https://ohmyposh.dev/install.ps1'))
```

or head to the official site: [oh-my-posh installation]('https://ohmyposh.dev/docs/installation/windows')

## Procedures

### Modify Terminal Settings

Open terminal `settings.json` by pressing [`Ctrl + ,`] in any code editor. Then, select all by pressing [`Ctrl + a`] and hit delete button. Now we need to copy and paste everyting from the given link to our `settings.json`. Then save by pressing [`Ctrl + s`] and close `settings.json` file.

- `settings.json` file will be found here: [Terminal settings.josn](./Windows%20Terminal%20Settings/settings.json)

**Note:** This settings will only work if you do not change your git installation directory. If you do so, then change the `commandline` and `icon` file path in the `settings.json`.

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

It will create, or open default shell profile in default notepad editor. In this stage, we will copy the strings from below and paste them into the `$profile` file:

```sh
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\hotstick.minimal.omp.json" | Invoke-Expression
```

Save and close it. For the `PATH` to be reloaded, a restart of your terminal is advised.

### Customize Terminal Theme (Optional)
If anyone wish to customize terminal theme as I did then he/she can do by updating `{themename}.json` file. I'm providing my one here.

- `{themename}.json` file will be found here: [Theme settings.josn](./Terminal%20Theme%20Settings/hotstick.minimal.omp.json)

**Steps to do so**
- Find out `oh-my-posh` theme directory. i.e:

```sh
$env:POSH_THEMES_PATH
```

Result will be something like this:
`C:\Users\{your_user_name}\AppData\Local\Programs\oh-my-posh\themes`

- Select the right json theme file. i.e: `hotstick.minimal.omp.json` and open it with any editor.
- Replace all the data with this theme [settings](./Terminal%20Theme%20Settings/hotstick.minimal.omp.json). Copy all the settings and paste them to your theme settings file. Save it and simply close it.

For the `PATH` to be reloaded, a restart of your terminal is advised. Now you are able to see a eye catchy terminal like this one.

![Windows Terminal Preview](./assets/images/first-look.png)
Hurrah! We have done it. 😀

## Author

- Website - [AminBabu](aminbau.talkativecoder.com)
- Twitter - [@aminbabu07](https://www.twitter.com/aminbabu07)
