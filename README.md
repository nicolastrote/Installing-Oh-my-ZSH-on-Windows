# Installing OH-My-ZSH INSTALLATION
![alt text](https://github.com/nicolastrote/Installing-Oh-my-ZSH-on-Windows/blob/master/ohmyzsh-demo.PNG)

Installation and template for my zsh:
 * cygwin
 * apt-cyg
 * zsh
 * oh-my-zsh
 * Cmder
 * POWEERLINE10K theme Solarized: Light and Solarized Dark
 * POWERLINE fonts

## CYGWIN INSTALLATION
Cygwin is a large collection of GNU and Open Source tools which provide functionality similar to a Linux distribution on Windows.
* Download Cygwin : https://cygwin.com/install.html
* Install at C:\cygwin64
  * At packages screen, search for wget
  * Click on the arrow on the wget line and choose the latest version:
  ![alt text](https://github.com/nicolastrote/Installing-Oh-my-ZSH-on-Windows/blob/master/cigwin-web.jpg)
  * Then Continue.
  
## APT-CYG INSTALLATION
Apt-cyg is a Cygwin package manager. In Cygwin write :
* ```wget rawgit.com/transcode-open/apt-cyg/master/apt-cyg```
* ```install apt-cyg /bin```

## USEFULL TOOLS INSTALLATION
* ```apt-cyg install zsh git gdb dos2unix openssh vim nano```

## USER'S FOLDER SETUP
We need to configurate in cigwin you're home folder
* ``` nano C:/cygwin64/etc/nsswitch.conf```
* Add this line to the bottom: ```db_home: windows```
* CTRL+X and YES for exit & saving your changes in nano

## CMDER POWERLINE FONT INSTALLATION
We will use meslo font which is one of the recommended font for Powerline Theme.
* download at https://github.com/romkatv/powerlevel10k/blob/master/README.md#meslo-nerd-font-patched-for-powerlevel10k
* click on the ttf file
* Windows font tool should open and click Install button

## CMDER INSTALLATION
CMDER is software package that provides great console experience.
* Download the full version of CMDER : https://cmder.net/
* Extract it in Program Files
 
## CMDER SETUP
* Run cmder.exe
* click on open Settings
  * General > Fonts > 
    * MesloLGS NF
    * uncheck Alternative font
  * General > Size & Pos > Check Snap To desktop edges
  * General > Appearance > 
    * remove Check from Show Button In tab bar
    * remove Check from Show Search Field
    * select hide scrollbar
  * General > Tab bar > select auto show
  * General > Confirm > remove Check confirmation of creating new tab
  * General > Taskbar > 
    * check Don't show ConEmu Window on taskbar
    * check Auto Minimize to TSA (default)
  * Startup > Tasks > 
    * click on + button and add those informations
      * name: cygwin:ZSH
      * icon: -icon "C:\cygwin64\Cygwin.ico"
      * start console: C:\cygwin64\bin\mintty.exe /usr/bin/zsh --login -i -new_console:d:%USERPROFILE%
 * General > choose your startup... > choose in the dropdown selector {cygwin:ZSH}
 * Features > Colors > choose Monokai Scheme (default)
 * Keys & Macro > 
   * Win + Esc : Minimize/Restore
   * Win + Down : Create New Console
   * Win + T : Create new console (With Dialog)
   * Win + N : Split: Duplicate active ‘shell’ split to bottom
   * Win + Right : Switch Next Console
   * Win + Left : Switch Previous Console
   * Win + Q : Close active Console
   * Win + E : Close all Consoles
   * Win + Alt + P : Show Settings
   * Win + Alt + Space : Show ConEmu Menu
 * Keys & Macro > Keyboard > check "Support Special hotkeys"
 * Keys & Macro > Paste > Multi Lines is Checked
 
## Oh-my-zsh INSTALL
Oh-My-Zsh is a delightful, open , community-driven framework for managing your ZSH configuration.
* ```cd Downloads```
* ```git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh```
* ```cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc```

## Oh-my-zsh SETUP
* Right click on the window of your terminal (not the menu) > options
* Change font-size and Apply the settings , a new .minttyrc file has beeen create
* ```nano .minttyrc``` and paste
BoldAsFont=no
RightClickAction=paste
Font=MesloLGS NF
FontHeight=10
Term=xterm-256color
BoldAsColour=yes
ConfirmExit=no
Scrollbar=none
Transparency=medium
OpaqueWhenFocused=yes
SelectionShowSize=1
BackgroundColour=19,38,58
ForegroundColour=228,228,228
CursorColour=228,228,228
Black=40,40,40
BoldBlack=107,107,107
Red=255,43,28
BoldRed=243,91,80
Green=2,192,97
BoldGreen=0,253,127
Yellow=251,188,46
BoldYellow=253,197,86
Blue=0,126,180
BoldBlue=0,179,255
Magenta=255,0,194
BoldMagenta=239,133,214
Cyan=87,208,249
BoldCyan=141,219,245
White=207,207,207
BoldWhite=255,255,255

## Oh-my-zsh THEME
* install Powerlevel10k theme
* cd Downloads
* git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
* nano ~/.zshrc and change ZSH_THEME FOR: ZSH_THEME="powerlevel10k/powerlevel10k"
* for configuring
```
p10k configure
```
  
## AUTOSUGGESTION
https://github.com/zsh-users/zsh-autosuggestions
- `git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`
- `nano ~/.zshrc`
- add in the plugins line:
`plugins=(git zsh-autosuggestions)`
- restart terminal
