# shell-setups

## 1. Vorraussetzungen

### 1.1 windows-terminal

[JetBrains Mono Nerd Font](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/JetBrainsMono) installieren

#### Terminal Default Settings:
```
"defaults":
        {
            // Put settings here that you want to apply to all profiles.
            "showTerminalTitleInTitlebar": false,
            "padding": "25",
            "colorScheme": "One Half Dark",
            "useAcrylic": true,
            "acrylicOpacity": 1,
            "fontFace": "JetBrains Mono Nerd Font"
        },
```

### 1.2 wsl
[aktivieren, auf wsl 2 updaten und als default setzen](https://docs.microsoft.com/de-de/windows/wsl/install-win10)


## 2. PowerShell [oh-my-posh](https://github.com/JanDeDobbeleer/oh-my-posh):
```
$ Install-Module posh-git -Scope CurrentUser
$ Install-Module oh-my-posh -Scope CurrentUser
```
#### -> In PoSh Profil (In PoSh "code $profile"): 
```
Import-Module posh-git
Import-Module oh-my-posh
Set-Theme Robbyrussell
```

## 3. Ubuntu
### 3.1 zsh installieren
```
$ sudo apt install zsh 
```
### 3.2 [prezto](https://github.com/sorin-ionescu/prezto) installieren 
```
$ git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
```

#### -> ~/.zshrc entfernen
```
$ setopt EXTENDED_GLOB
  for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
    ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
  done
```
#### -> zsh als default
```
$chsh -s /bin/zsh
```
#### -> neuer Terminal Tab

### 3.3 Theme setzen
#### -> Welche bestehen?
```
$ prompt -l
```

#### -> preview 
```
$ prompt -p name
```

#### -> setzen in .zpreztorc
```
zstyle ':prezto:module:prompt' theme 'cloud' '>' 'red' 'yellow'
```

#### -> neuer Terminal Tab

#### -> Für [Spaceship](https://github.com/denysdovhan/spaceship-prompt) Theme [prezto-contrib](https://github.com/belak/prezto-contrib):
```
$ cd $ZPREZTODIR
$ git clone --recurse-submodules https://github.com/belak/prezto-contrib contrib
```

#### -> setzen in .zpreztorc unter ladende module liste, über 'prompt'
```
'contrib-prompt' \
```
#### dann spaceship als theme setzen

### 4. [node/npm lts mit nvm installieren](https://docs.microsoft.com/de-de/windows/nodejs/setup-on-wsl2)
```
   $ touch ~/.bashrc
   $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
   // restart bash
   $ nvm install --lts
```


further reading:
[some dotfiles of somebody](https://github.com/spencerwooo/dotfiles)
