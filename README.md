Hello, and thank you for taking a look at my repository. This was something something I have been meaning to put together for sometime. I am currently working in an IT Consulting position, and for several months looked for a solution to time tracking. I liked to use Notepad++ due to it being lightweight and very customizable, and figured there had to be a simple macro solution to imprint a timestamp of the current date and time in Notepad++. After searching for quite some time, I came across an answer provided by [Devin Bost on StackOverflow.](https://stackoverflow.com/users/1887281/devinbost) addressing a similar question. All credit should go to Devin. I have made a few changes to the text output string, and have updated the installation as Notepad++ has updated through the years. Even though I have set this up five or six times over the years, I always have to pull information from Devin's response and a few other location, and spend longer than I would like to admit troubleshooting. The goal of this repository is to centralize the scripts and the installation procedure, along with providing an approachable guide to configure this.

## Installation

The installation will assume that you have the latest version of Notepad++ and Python installation on your workstation.

1. Copy both the time-start.py and time-stop.py files from the repository.

2. We need to first enable the PythonScripts plugin in Notepad++:
From the menu bar in Notepad++, select: "Plugins" and then "Plugins Admin". Checkmark the box next to PythonScript and select Install.

3. Restart Notepad++

C:\Program Files\Notepad++\plugins\PythonScript\scripts
C:\Users\Ben\AppData\Roaming\Notepad++\plugins\config\Python\scripts
C:\Users\Ben\AppData\Roaming\Notepad++\plugins\config

move: time-start.py, time-stop.py to this directory

relaunch Notepad++

If you go to: Plugins -> PythonScript -> Configuration...
You should now see your: time-start.py & time-stop.py scripts in the machine scripts section

Settings -> Shortcut Mapper...

```python
import time
# import sys
timeStr = time.strftime('START' '--' '%A -- %B %d %Y' + ' @ ' + '%X %p' )
# sys.stdout.write(timeStr)
editor.addText( timeStr )
```
Output:
```text
START--Saturday -- December 03 2022 @ 20:22:39 PM
```

```python
import time
# import sys
timeStr = time.strftime('END' '--' '%A -- %B %d %Y' + ' @ ' + '%X %p' )
# sys.stdout.write(timeStr)
editor.addText( timeStr )
```
Output:
```text
END--Saturday -- December 03 2022 @ 20:22:39 PM
```
