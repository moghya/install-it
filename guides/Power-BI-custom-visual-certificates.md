# Setting up the environment
## Platform: UBUNTU 18.04.1 LTS
### Prerequisites:
  - Node JS environment. Download and Install [Node JS](https://nodejs.org/)
  - Intall or check for the latest version of npm.
    - You might face npm errors in future: "write after end".
      - Solution: Execute the following commands:
        - `npm install -g npm@latest`
        - `npm cache verify`
        - `npm i`
  - To access your visual through PowerBI, you need to add a trusted certificate for localhost. This will allow PowerBI to         load the visual assets in your browser without a security warning.
    - Install [openssl](https://www.openssl.org/)
    - Execute the following commands:
      - `sudo apt-get install openssl`
  - Browser application compatible with the certificate importer provided by the underlying platform.
    - In this case, I will be using `Chromium browser` for UBUNTU.

### Getting started: 
  - Install the Command Line Tools by executing the following coomand:
    - `npm install -g powerbi-visuals-tools`
  - To confirm it was installed correctly you can run the command without any parameters which should display the help screen.
    - `pbiviz`
  - Create a new project by:
    - `pbiviz new <project_name>`
  - Start the project:
    - `pbiviz start`
    - You will see a Visual Server has started listening to the client at **port = 8080**
  - Go to [Power BI Online](https://powerbi.microsoft.com/en-us/landing/signin/) and **Enable the Developer Mode**
  - Load your visual, and you are ready to go...
 
### Probable errors faced due to the Certificate issues:
  - The visual will throw the following error:
    - `"Can't contact visual server. Please make sure the visual server is running and configured correctly."`
  - Possibilities for the errors:
    A) 
61
​The Visual Server is not running on the localhost.
    B) No appropriate certificates avaible to the client browser to execute and run the visual online.
  - Respective Solution: 
    A) Use the command: `pbiviz start`.
    B) Create and install certificates using following commands:
      - Navigate to the project directory where the **pbiviz.json** file is present.
      - Create the certificate by executing the following coomand:
        - `pbiviz --create-cert`
        - An **authorized certificate** and a **private key** key will be generated a specific location, depending on the               platform(UBUNTU 18.04.1, in this case) you are using.
        - This certificate is issued by the localhost to the browser so that, the online client(**Power BI Online**, in our             case) can make use of it.
      - Install the certificate by executing the following command:
        - `pbiviz --install-cert`
        - **Be cautious:** This command needs a valid/compatible certificate importor to import it into the browser                     application.
      - If in case, the above command doesn't work, you can install the certificate manually:
        - Import the certificate in the browser in the `Trusted Root Certification Authorities` directory.
        
### Bypassing the security issues:
  - Please follow these steps to bypass the security issue:
    - `pbiviz start`
    - Open https://localhost:8080/assets/status in browser application(Chromium, in this case)
    - Open the Advanced
    - Click the Proceed to localhost (unsafe)
    - Back to the report with your debug visual
    - Reload visual code
    - Please let me know if it works for you well.
    
### In case the above steps do not work, try installing root/CA certificates in UBUNTU:
  - Execute the following commands to install the CA certificates: Given a CA certificate file <certificate-name>.crt, follow     these steps to install it on Ubuntu:
      - Create a directory for extra CA certificates in **/usr/share/ca-certificates**:
          - `sudo mkdir /usr/share/ca-certificates/extra`
      - Copy the CA .crt file to this directory:
          - `sudo cp <certificate-name>.crt /usr/share/ca-certificates/extra/<certificate-name>.crt`
      - Let Ubuntu add the .crt file's path relative to /usr/share/ca-certificates to /etc/ca-certificates.conf:
          - `sudo dpkg-reconfigure ca-certificates`
  
### Congratulations! you have perfectly setup the environment. You are ready to code in one of my favourite langauage, **TYPESCRIPT** !!
