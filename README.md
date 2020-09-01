# Installing OH-My-ZSH & ZSH & Cygwin & Cmder INSTALLATION, CONFIGURATION AND THEME
![alt text](https://github.com/nicolastrote/MY-ZSH-CONFIG/blob/master/ntrote-zsh-color-awesome.png)

Installation and template for my zsh:
 * zsh
 * oh-my-zsh
 * iTerm2
 * POWEERLINE10K theme Solarized: Light and Solarized Dark
 * POWERLINE fonts

## PRELEMINARY: HOMEBREW INSTALLATION
Brew is a package manager for OSX
```
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew -v
```
or if you have already brew installed
```$ brew update```

## INSTALLATION ZSH
```brew install zsh```

## INSTALLATION OH-MY-ZSH
```$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"```

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
