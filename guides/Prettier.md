# How to Install Prettier for Javascript in Jetbrains Webstorm IDE.

 An opinionated code formatter, Supports many languages, Integrates with most editors [Official Website Link](https://prettier.io/).

### Windows Operating System - Microsoft Windows 10

- Prettier 1.11.1
    - Prerequisites
      - Install Webstorm IDE [Official Website Link](https://www.jetbrains.com/webstorm/).

    - Installation Steps
		- Install prettier globally : 

			- Command : npm install -g prettier.
			- Output  : C:\Users\DEEPAK AHIRE\AppData\Roaming\npm\prettier -> C:\Users\DEEPAK AHIRE\AppData\Roaming\npm\node_modules\prettier\bin\prettier.js
				+ prettier@1.9.2
				added 1 package in 16.264s

		- Go to webstorm preferences : Ctrl+Alt+S

		- Go to tools -> external tools

		- Add a new external tool by clicking '+' icon.

		- Setup the properties for tool as follows : 
	
			A) Name : -- Give any name --
			B) Program : C:\Users\DEEPAK AHIRE\AppData\Roaming\npm\prettier.cmd (.cmd in case of Windows)
			C) Parameters : --write --single-quote --trailing-comma=all $FilePathRelativeToProjectRoot$
			D) Working directory : $ProjectFileDir$

		- Setup the shortcut for using the tool using keymap in preferences : (shift + p) (You can choose any).

		- You are ready to use.

### UBUNTU Operating System - Canonical Ltd., Ubuntu community

- Prettier 1.12.1
    - Prerequisites
      - Install Webstorm IDE [Official Website Link](https://www.jetbrains.com/webstorm/).

    - Installation Steps
		- Install prettier globally : 

			- Command : sudo npm install -g prettier. (Check the installation paths in global installations).

		- Go to webstorm preferences : Ctrl+Alt+S

		- Go to tools -> external tools

		- Add a new external tool by clicking '+' icon.

		- Setup the properties for tool as follows : 
	
			A) Name : -- Give any name --
			
			B) Program : /usr/local/bin/prettier (Link to Perl script (application/x-perl))
			
			C) Parameters : --write --single-quote --trailing-comma=all $FilePathRelativeToProjectRoot$
			
			D) Working directory : $ProjectFileDir$

		- Setup the shortcut for using the tool using keymap in preferences : (shift + p) (You can choose any).

		- You are ready to use.


