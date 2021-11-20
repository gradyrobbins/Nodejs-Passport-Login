# Nodejs-Passport-Login 
# A boilerplate app, full credit to [this 35 minute YouTube tutorial](https://youtu.be/-RCnNyD0L-s)

## Before you get started:
1.  `.gitignore ` ignores `.env` so you may need to create one during installation and setup.  Tutorial video has further info.

1.  The tutorial employs code shortcuts and project architecture that the original authors themselves strongly discourage from use in a production environment.  Tutorial video has further info.  [More info, sourced from the npm docs ](https://docs.npmjs.com/cli/v8/commands/npm-install) informs the below Setup & Installation instructions.

## Getting started, in 7 steps: 

### Setup 

1.  `cd ~/workspace`
1. Fork 
2. Clone 
3. Change Directories into your cloned Repository 

### Installation 
4. ```npm install --production=false``` :  With the ```--production``` flag (or when the NODE_ENV environment variable is set to production), npm will not install modules listed in devDependencies. To install all modules listed in both dependencies and devDependencies when NODE_ENV environment variable is set to production, you can use --production=false.

### Start 
5. Invoke  ```npm run devStart``` :  as described in `package.json` 

6. spin Up ```localhost:3000 ``` which *should* auto re-direct to ```localhost:3000/login ```
nodemon monitors `server.js` for changes & restarts the app accordingly





### Next steps: 

I aim implement this auth onto state-quarter-collector.onrender.com.  Then connect the web app to a render disk so that the user's quarter data will persist.  
