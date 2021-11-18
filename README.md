# Drozer Installation ( Twisted Fix )
Welcome to my first writeup!! Briefly about me - I am a mobile security enthusiast, researcher and a comedy fan:blush:

We'll go through a step by step guide on installing drozer on Kali/Ubuntu, a dependency (Twisted) challenge encountered and a solution.

## So What's Drozer?
Drozer is a framework developed by [F-Secure Labs](https://labs.f-secure.com/tools/drozer/) for Android security assessment through dynamic analysis.
For this guide, our test OS was **Kali Linux 2021.3**

## Let's get to business...
 | ![Alt Text](https://media.giphy.com/media/1qPQfteuMNBqRyr4yH/giphy.gif) |
 |:--:|
 | <i><b>giphy.com:</b></i>|


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

    ![alt text](https://github.com/Cherry-Oh/Cherry-Oh.github.io/blob/main/drozer_run.png?raw=true)
   
   > drozer has been installed successfully:blush:

- Let's explore drozer options:
   > *drozer console [command]* : This option connects to an Agent and allows you to interact with the system from the context of the agent application on the device

   ![alt text](https://github.com/Cherry-Oh/Cherry-Oh.github.io/blob/main/drozer_connect.png?raw=true)
   
   > But we get an error about a dependency *Twisted* :thinking:
   
   From the list of [prerequisites](https://github.com/FSecureLABS/drozer#prerequisites) we installed above, Twisted was one and was installed via pip.
   Re-installing it as suggested on the image above unfortunately did not do the trick for me.
   
   #### Now What??
   
   After a few digging here and there, the commands below worked :raised_hands:
   ```markdown
   pip install --upgrade setuptools
   pip2 install twisted
   ```
   > pip and pip2 are already pre-installed in Kali
 

### 3. Re-run drozer console option:

   ![alt text](https://github.com/Cherry-Oh/Cherry-Oh.github.io/blob/main/drozer_finale.png?raw=true)

   > Voila! Drozer console working well. You can now explore drozer commands [here](https://gist.github.com/castexyz/2ef12840fccbf3b4ef7b6446d24a9352)



### Hope this helps someone... Thank You.
