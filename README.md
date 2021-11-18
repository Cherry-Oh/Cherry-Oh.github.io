# Drozer Installation using Terminal
Welcome to my first writeup!! Briefly about me - I am a mobile security enthusiast, researcher and a comedy die hard fan:blush:

We'll go through a step by step guide on installing drozer on Kali/Ubuntu and a few challenges with solutions encountered.

## So What's Drozer?
Drozer is ....

For this guide, our target OS is Kali Linux 20.X...

## Let's get to business...
![Alt Text](https://media.giphy.com/media/1qPQfteuMNBqRyr4yH/giphy.gif)

### 1. Prerequisites:
- Install dependencies from [drozer_prerequisites](https://github.com/FSecureLABS/drozer#prerequisites)
- Download and install **pip 2.7** 
   > Note: Ensure you save the python file under ***/usr/lib/python2.7***
```markdown
curl https://bootstrap.pypa.io/pip/2.7/get-pip.py --output get-pip.py
sudo python2.7 get-pip.py
```
   > You can use pip2 that's already pre-installed

### 2. Install & Run:
- Download latest drozer release (drozer-2.4.4-py2-none-any.whl) from [drozer_releases](https://github.com/FSecureLABS/drozer/releases)
- Install drozer:
```markdown
pip2.7 install drozer-2.4.4-py2-none-any.whl
OR
pip2 install drozer-2.4.4-py2-none-any.whl
```
- Run drozer:

   | ![alt text](https://github.com/Cherry-Oh/Cherry-Oh.github.io/blob/main/drozer_run.png?raw=true) |
   |:--:|
   | <i>drozer has been installed successfully:blush:</i>|

- Let's explore drozer options:
   > *drozer console [command]* : This option connects to an Agent and allows you to interact with the system from the context of the agent application on the device

   ![alt text](https://github.com/Cherry-Oh/Cherry-Oh.github.io/blob/main/drozer_connect.png?raw=true)
   
   > But we get an error about a dependency *Twisted* :thinking:
   
   From the list of [prerequisites](https://github.com/FSecureLABS/drozer#prerequisites) we installed above, Twisted was one and was installed via pip.
   Re-installing it as suggested on the image above unfortunately did not do the trick for me.
   
   Now What??
   
   After a few digging here and there, the commands below worked :raised_hands:
   ```markdown
   pip install --upgrade setuptools
   pip2 install twisted
   ```
   > pip and pip2 were already pre-installed in Kali





```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Cherry-Oh/Cherry-Oh.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://su
