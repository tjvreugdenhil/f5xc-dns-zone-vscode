**########### PREPARATION ##############
**
1) Download Visual Studio Code: https://code.visualstudio.com/

2) Install “REST Client” Extension from the Visual Studio Code Marketplace: Files ending with .http or .rest will automatically be syntax highlighted
Ctrl + Shift + X -> search for humao.rest-client -> install

3) Install “Dotenv Official” Extension from the Visual Studio Code Marketplace: This is used to quickly reference API tokens without exposing API tokens in code. 
Ctrl + Shift + X -> search for dotenv.dotenv-vscode ->  install 

4) Create API Token from F5 XC tenant:  Administration > Personal Management > Credentials > Add Credentials

5) Rename ".env.sample" to ".env" 
   a. paste API token into the .env file 
   b. paste f5 XC tenant name into the .env file 

**########### CREATE F5-XC DNS ZONE & RECORDS ##############
**
6) Verify F5 DNS Zone does not exist:  {Send Request}:  "GET f5xc-demo.com.rest"

7) Create F5 DNS Zone: {Send Request}: "POST f5xc-demo.com zone.rest"

8) Verify F5 DNS Zone: {Send Request}:  "GET f5xc-demo.com.rest"

9) Replace F5 DNS Zone with new records: {Send Request}:  "PUT f5xc-demo.com zone.rest"


**############ ADDITIONAL INFORMATION  #############
**
#POST - Creates DNS Zone. If one already exists, it will give an error.

#PUT - Replaces DNS Zone 

#GET - Lists DNS Zone or use "curl GET f5xc-demo.com zone.rest"
#DELETE - Deletes DNS Zone

#If using "f5xc-backup.sh" - install jq for Windows by running this curl in gitbash or the vscode bash terminal
curl -L -o /usr/bin/jq.exe https://github.com/stedolan/jq/releases/latest/download/jq-win64.exe

#Install vscode thunder client extension to build REST collections: 
Ctrl + Shift + X -> search for rangav.vscode-thunder-client -> install 

#install gitignore for .env file:
Ctrl + Shift + X -> codezombiech.gitignore -> install 
