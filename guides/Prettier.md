# How to Install Prettier for Javascript in Jetbrains Webstorm IDE.

 An opinionated code formatter, Supports many languages, Integrates with most editors [Official Website Link](https://prettier.io/).

### Windows Operating System - Microsoft Windows 10

- Prettier 1.11.1
    - Prerequisites
      - Install Webstorm IDE [Official Website Link](https://www.jetbrains.com/webstorm/).

    - Installation Steps
      1) Install prettier globally : 

		A)Command : npm install -g prettier.
		B)Output  : C:\Users\DEEPAK AHIRE\AppData\Roaming\npm\prettier -> C:\Users\DEEPAK AHIRE\AppData\Roaming\npm\node_modules\prettier\bin\prettier.js
			+ prettier@1.9.2
			added 1 package in 16.264s

		2) Go to webstorm preferences : Ctrl+Alt+S

		3) Go to tools -> external tools

		4) Add a new external tool by clicking '+' icon.

		5) Setup the properties for tool as follows : 
	
			A) Name : -- Give any name --
			B) Program : C:\Users\DEEPAK AHIRE\AppData\Roaming\npm\prettier.cmd (.cmd in case of Windows)
			C) Parameters : --write --single-quote --trailing-comma=all $FilePathRelativeToProjectRoot$
			D) Working directory : $ProjectFileDir$

		6) Setup the shortcut for using the tool using keymap in preferences : (shift + p) (You can choose any).

		7) You are ready to use.

