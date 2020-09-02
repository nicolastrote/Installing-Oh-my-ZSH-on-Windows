# Installing OH-My-ZSH & ZSH & Cygwin & Cmder INSTALLATION, CONFIGURATION AND THEME
![alt text](https://github.com/nicolastrote/MY-ZSH-CONFIG/blob/master/ntrote-zsh-color-awesome.png)

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
  * Click on the arrow on the wget line and choose the latest version.
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
In the repository https://github.com/powerline/fonts/ you can download and install several fonts. Personnaly I will go with UbuntuMono. 
* CLic on each ttf file's links, and clic on the "Download" button
* Double click on each files downloaded, it will launch Windows Font Tool
* Click on install for each ttf files

## CMDER INSTALLATION
CMDER is software package that provides great console experience.
* Download the full version of CMDER : https://cmder.net/
* Extract it in Program Files
 
## CMDER SETUP
* Run cmder.exe
* click on open Settings
  * General > Fonts > 
    * Ubuntu Mono derivative Powerline
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
`Win + Esc : Minimize/Restore
Win + Down : Create New Console
Win + T : Create new console (With Dialog)
Win + N : Split: Duplicate active ‘shell’ split to bottom
Win + Right : Switch Next Console
Win + Left : Switch Previous Console
Win + Q : Close active Console
Win + E : Close all Consoles
Win + Alt + P : Show Settings
Win + Alt + Space : Show ConEmu Menu`

## Oh-my-zsh INSTALL
Oh-My-Zsh is a delightful, open source, community-driven framework for managing your ZSH configuration.
* ```cd Downloads```
* ```git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh```
* ```cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc```

## Oh-my-zsh SETUP












## INSTALLATION iTERM2
Why iTerm2? Because you can split your iTerm windows vertically or horizontally to infinite!
Download and install iTerm2 from https://iterm2.com/downloads/stable/iTerm2-3_1_6.zip

Tell iTerm2 to use ZSH
 * go to iTerm2 preferences.
 * head to Profiles -> General.
 * paste /bin/zsh in the Command textbox and restart iTerm2.

For color download : 
 * https://raw.githubusercontent.com/mbadolato/iTerm2-Color-Schemes/master/schemes/Solarized%20Dark%20-%20Patched.itermcolors
 * https://raw.githubusercontent.com/altercation/solarized/master/iterm2-colors-solarized/Solarized%20Light.itermcolors
Term → preferences → profiles → colors → load presets

If you like my theme, you can download my color theme from the repository: [ntrote.itermcolors](https://github.com/nicolastrote/MY-ZSH-CONFIG/blob/master/ntrote.itermcolors)

For launch iterm2 with saved windows : 
![alt text](https://github.com/nicolastrote/MY-ZSH-CONFIG/blob/master/ntrote-iterm2.png)

## LOCAL PATH
  * uncomment the 2d ligne in .zshrc file to activate access to your local path
```
# If you come from bash you might have to change your $PATH.
export PATH=$HOME/bin:/usr/local/bin:$PATH
```
For React Native development you can add:
```
export PATH=$HOME/bin:/usr/local/bin:$PATH
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
export NODE_TLS_REJECT_UNAUTHORIZED=0
``` 
## INSTALLATION POWEERLINE10K FONT+ICONS
And installation for a "powerline" style
```$ git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k```
edit .zshrv config file and change the theme name : 
```
$ nano ~/.zshrc
  ZSH_THEME="powerlevel10k/powerlevel10k"
  POWERLEVEL9K_MODE="awesome-patched"
```
for configuring
```
p10k configure
```

## INSTALLATION POWERLINE FONTS
source : https://github.com/gabrielelana/awesome-terminal-fonts/tree/patching-strategy/patched
Those font are ready to go with font awesome icons!
 * download [SourceCodePro-Powerline-Awesome-Regular.ttf](https://github.com/nicolastrote/MY-ZSH-CONFIG/blob/master/SourceCodePro%2BPowerline%2BAwesome%2BRegular.ttf)
 * on mac just double-clic to install
 * in the .zshrc file add the POWERLEVEL9K_MODE parameter for activate font awesome icons.
```
$ nano ~/.zshrc
  POWERLEVEL9K_MODE='awesome-patched'
  ZSH_THEME="powerlevel9k/powerlevel9k"
```
And add in iTerm the font
 * Set this font in iTerm2 (iTerm → Preferences → Profiles → Text → Change Font), best to do this for "Font" and for "Non-ASCII Font".
 * Term → preferences → profiles > Police > modifed...
 * choose source-code-pro   13px
 
## ENABLE WORD JUMP & AUTOCOMPLETION
By default, word jumps (option + → or ←) and word deletions (option + backspace) do not work. 
To enable these, go to 
  * iTerm → Preferences → Profiles → Keys → Load Preset... → Natural Text Editing
  
## AUTOSUGGESTION
https://github.com/zsh-users/zsh-autosuggestions
- `git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`
- `nano ~/.zshrc`
- add:
`plugins=(zsh-autosuggestions)`
- restart terminal
