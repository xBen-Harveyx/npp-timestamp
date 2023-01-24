<div align="center"> 
	<h2>Notepad Timestamp</h2>
	<img src="https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white" />
	<img src="https://img.shields.io/badge/Notepad++-90E59A.svg?style=for-the-badge&logo=notepad%2B%2B&logoColor=black" />
	<img src="https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue" />
	<h2>Background Information</h2>
</div>

>Hello, and thank you for taking a look at my repository. This was something something I have been meaning to put together for sometime. I am currently working in an IT consulting position, and for several months looked for a solution for tracking time on tasks. I liked to use Notepad++ due to it being lightweight and very customizable, and figured there had to be a simple macro solution to imprint a timestamp of the current date and time in Notepad++. After searching for quite some time, I came across an answer provided by [Devin Bost](https://stackoverflow.com/users/1887281/devinbost) on StackOverflow addressing a similar question. **All credit should go to Devin**. I have made a few changes to the text output string, and have updated the installation as Notepad++ has updated through the years. Even though I have set this up five or six times over the years, I always have to pull information from Devin's response and a few other location, and spend longer than I would like to admit troubleshooting. The goal of this repository is to centralize the macro scripts and the installation procedure, along with providing an approachable guide to setting this up in Notepad++.

<div align="center"> 
	<h2>Installation</h2>
</div>
The installation will assume that you have the latest version of Notepad++ and Python installation on your workstation.

1. Copy both the **time-start.py** and **time-stop.py** files from the repository to your local machine.

2. We need to first enable the **PythonScripts plugin** in Notepad++:
    - From the menu bar in Notepad++, select: "Plugins" and then "Plugins Admin". 
    - Checkmark the box next to PythonScript and select Install.
    - Restart Notepad++

3. Move both **time-start.py** and **time-stop.py** to the following folders.
    - C:\Program Files\Notepad++\plugins\PythonScript\scripts
    - C:\Users\\%username%\AppData\Roaming\Notepad++\plugins\config\Python\scripts
    - C:\Users\\%username%\AppData\Roaming\Notepad++\plugins\config

4. **Close and restart Notepad++**.

5. We need to check that the scripts are showing up in the **PythonScript plugin**. To do this:
    - From the menu bar in Notepad++, select: **Plugins**, **PythonScript**, and then **Configuration**.
        > You should now see your: **time-start.py** & **time-stop.py** scripts in the machine scripts section

6. **Once we confirm the scripts are there**, we can then assign a keybinding. To do this:
    - From the menu bar in **Notepad++**, select: **Settings** and then **Shortcut Mapper...**
    - Click the: **Plugin Commands** tab.
    - Find the scripts: **time-start.py** and **time-stop.py**
    - *highlight time-start*, Select: Modify and set a key combo to run the macro.
    - *highlight time-stop*, Select: Modify and set a key combo to run the macro.
7. Restart Notepad++ and test using the key combo you set.

<div align="center"> 
	<h2>Example Output</h2>
</div>

### **time-start.py**
```python
import time
# import sys
timeStr = time.strftime('START' '--' '%A -- %B %d %Y' + ' @ ' + '%X %p' )
# sys.stdout.write(timeStr)
editor.addText( timeStr )
```
#### **Output:**
```text
START--Saturday -- December 03 2022 @ 20:22:39 PM
```
### **time-stop.py**
```python
import time
# import sys
timeStr = time.strftime('END' '--' '%A -- %B %d %Y' + ' @ ' + '%X %p' )
# sys.stdout.write(timeStr)
editor.addText( timeStr )
```
#### **Output:**
```text
END--Saturday -- December 03 2022 @ 20:22:39 PM
```
