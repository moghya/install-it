# How to Install ROBOMONGO.
Robo 3T (formerly Robomongo) is the free lightweight GUI for MongoDB enthusiasts.[Official Website Link](https://robomongo.org/).

### UBUNTU Operating System - Canonical Ltd., Ubuntu community

- ROBOMONGO 3T Version: 1.2
    - Prerequisites
      - No prerequisites. ROBO 3T should be compatible with the platform.
      - Download the ROBO 3T tar.gz file for linux on the [Official Website Link](https://robomongo.org/).

    - Installation Steps
    
		- Install ROBO 3T globally : 

			- Command: Type the 3 following commands:
				
				1) sudo tar xf robomongo-<version specific details>.tar.gz
				
				2) sudo sudo mv robomongo-<version specific details>/ /usr/bin/robomongo
			
				3) sudo export PATH=/usr/bin/robomongo/bin:$PATH
				
				4) Add the following line to the end of .bashrc file: alias robomongo='/usr/local/bin/robomongo/bin/robo3t'  
				
				5) Save and close the file. Now reload it using the following command: source ~/.bashrc
				
      
     - Test the installation by typing the command: robomongo.
    
    - You are ready to use.

