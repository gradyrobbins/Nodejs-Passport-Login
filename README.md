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



## Additional Notes, with correlating video timestamps: 

### *Tutorial timestamp@ 14:00* 
This node app does NOT hit an *external* database.  
Our *"database"* ... is initialized as an empty array, inside `server.js`>> `const users = []`. 


A new user's uniqueId will be generated as a timestamp.toString()
And their p/w is stored as a hashed password. 
A user is deleted upon logout, using ```npm i method-override```dependency to change the logout button's onClick POST/ method to a DELETE/

### *Tutorial timestamp@ 14:20*
Tutorial claims that anytime application saves/reloads, the variable `users` will be reset to its original state, that is, an empty array.
**Open question, How to verify ``` server.js:``` >>  ```const users = []```?**

### Tutorial *23:30*
 ```npm install express-session && express-flash```
the express-session library retrieves secretkey from .env file
express-flash library - why import?

### Tutorial *timestamp 24:00*
`server.js`
the conditional written at top of server.js file asks whether node environment status is !"in production",
prompting require the dotenv package, which is listed as a devDependency in package.json
### Tutorial *timestamp ~30:00*
the power of using `session` with `passport`, is that `req.user` will ALWAYS be set to the user that is authenticated at that moment.

One problem, though: a non-authenticated user may still access  `localhost:3000/` and find *some* information, for example:
![error message displayed on DOM](view_NonCredentialedUser.png)

Thus, middleware aka Passport.  Executes a function with 3 args(req,res,next)

Thus, non-credentialed/non-logged in traffic redirects to `/register` 

if(user is authenticated by PassPort){return: next }
else redirect them to `/Register` route



### Next steps: 

I aim implement this auth onto state-quarter-collector.onrender.com.  Then connect the web app to a render disk so that the user's quarter data will persist.  
