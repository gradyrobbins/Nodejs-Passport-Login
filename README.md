 
# Authentication Boilerplate for NodeJS WebApp
#### Special Thanks @ WebDevSimplified [35 minute tutorial](https://youtu.be/-RCnNyD0L-s) forked from their repository, linked [here](https://github.com/WebDevSimplified/Nodejs-Passport-Login)

## Before you get started:
*  `.gitignore ` ignores `.env` so you may need to create one during installation and setup.  Tutorial video has further info.
*  The tutorial employs code shortcuts and project architecture that the original authors themselves strongly discourage from use in a production environment.  Tutorial video has further info.  [More info, sourced from the npm docs ](https://docs.npmjs.com/cli/v8/commands/npm-install) informs the below Setup & Installation instructions.

## Getting started: 

### Setup 
1.  `cd ~/workspace`
2. Fork 
3. Clone 
4. Change Directories into your cloned Repository 

### Installation 
5. ```npm install --production=false``` :  With the ```--production``` flag (or when the NODE_ENV environment variable is set to production), npm will not install modules listed in devDependencies. To install all modules listed in both dependencies and devDependencies when NODE_ENV environment variable is set to production, you can use --production=false.

### Start 
6. ```npm run devStart``` 
7. go to ```localhost:3000 ```  which you *should* see auto re-direct to ```localhost:3000/login ``` as you are not yet a registered user. 

### Next steps: 
Connect this repo to onrender.com service, then configure my dashboard's advanced settings, enabling any authenticated user's submitted data to persist! 
