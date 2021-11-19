 # Nodejs-Passport-Login[ tutorial](https://youtu.be/-RCnNyD0L-s)

## Notes on installation and setup:
repo's `.gitignore ` ignores .env so you need to create one locally.

*timestamp 14:00*
"database" of users is proxied as an empty array.  The new user object creates id's as a timestamp,
and the user's p/w of choice is stored as a hashed passwords, meaning:  safer

*timestamp 14:20*
note: anytime application saves/reloads, the variable `users` will be reset to its original state, that is, an empty array. refer to line 20 of server.js:  ```const users = []```

consequently, since no db is used, it is being saved in memory, which is not something we want to do in production.
## Why?

*timestamp 23:30*
 ```npm install express-session && express-flash```
the express-session library retrieves secretkey from .env file


express-flash library

*timestamp 24:00*
`server.js`
the conditional written at top of server.js file asks whether node environment status is !"in production",
prompting  require the dotenv package, which is listed as a devDependency in package.json

*timestamp ~30:00*
the power of using `session` with `passport`, is that `req.user` will ALWAYS be set to the user that is authenticated, at that moment.

One problem, though: a non-authenticated user may still access  `localhost:3000/` and find *some* information, for example:
![error message displayed on DOM](view_NonCredentialedUser.png)

Thus, middleware aka Passport.  Executes a function with 3 args(req,res,next)

Thus, non-credentialed/non-logged in traffic redirects to `/register`

if(user is authenticated by PassPort){return: go to the next}
else redirect them to `/Register` route

npm i method-override to change POST method to DELETE.

now use this template as a plug in to state-quarters-collector