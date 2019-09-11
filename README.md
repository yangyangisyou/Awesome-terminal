# Awesome-terminal - How to change your terminal style

### A. Install Python & Powerline
1. **Install python**
```bash=
brew install python
easy_install pip
pip install --user powerline-status
```

2. **If the version is python3, change to pip3**


**Doesn't work?**
If you have some problem, re-install the powerline-status.
```bash=
pip uninstall powerline-status
pip3 uninstall powerline-status
```
---
### B. Make sure where the python's powerline direction is
**1st**
```bash=
ls {path}/powerline/bindings/bash/powerline.sh
```
or

**2nd**
```bash=
. {path}/powerline/bindings/bash/powerline.sh
```
---
### Note

If first line is works, below is a example, change ls to dot sign.

```bash=
ls /Library/Frameworks/Python.framework/Versions/3.7/lib/python3.7/site-packages/powerline/bindings/bash/powerline.sh
```

change to 
```bash=
. /Library/Frameworks/Python.framework/Versions/3.7/lib/python3.7/site-packages/powerline/bindings/bash/powerline.sh
```
/*
Find powerline install Location:
pip show powerline-status
there is a line like Location: {path}
*/

---

### C. Install Fonts
1. **Install fonts**
```bash=
git clone https://github.com/powerline/fonts.git
cd fonts
./install.sh
```
2. **If you have already installed, you can change your terminal style.**
 command + < 
If you want to see immediately, change the basic(預設值), if not, you can change whatever you want.
```
終端機->偏好設定->描述檔->（預設值/其他）->文字->字體更改
```
3. **Change your style**
monofur for powerline (or something u like)
4. **If success, or not**
open new terminal, if so, you will see something special.

![](https://i.imgur.com/grclM2G.png)


### D. Modify .bash_profile

1. **Modify or create .bash_profile**
```bash=
touch ./.bash_profile
open ./.bash_profile
```

2. **Put the script to .bash_profile at the bottom**

```bash=
if [[ -f /Library/Frameworks/Python.framework/Versions/3.7/lib/python3.7/site-packages/powerline/bindings/bash/powerline.sh ]]; then
    . /Library/Frameworks/Python.framework/Versions/3.7/lib/python3.7/site-packages/powerline/bindings/bash/powerline.sh
fi
```

3. **Install dotfiles**
```bash=
git clone https://github.com/MilesChou/dotfiles.git
cd dotfiles/
cp -r .config/powerline ~/.config/
```

#### if your installation is successful, you can see the terminal become 2 line.

![](https://i.imgur.com/lGewJEf.png)


4. **Install bash-completion**
```bash=
brew install bash-completion
```
5. **Put the "Bash completion for brew" script to .bash_profile at the bottom**

```bash=
if [[ -f $(brew --prefix)/etc/bash_completion ]]; then
    . $(brew --prefix)/etc/bash_completion
fi
```


### Reference
**[1] powerline**：   http://wiki.framins.com/#!linux/powerline.md
**[2] bash_profile**： https://github.com/MilesChou/dotfiles/blob/master/.bash_profile
