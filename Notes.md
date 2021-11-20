
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
Open question: - why import express-flash library?

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
