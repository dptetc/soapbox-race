# soapbox-race

Webserver to handle cars and pilots profiles.

##How to:
My advice is to download Eclipse JavaEE, and after that download eGit Maven SCM profile from the Eclipse marketplace(both free). After importing the project from the SCM profile, build the server with the built-in maven using `clean compile assembly:single`.

##Running the server:

- mysql db server running
- openfire xmpp server running (try openfire/README.md file)
- edit soapbox.properties file 

    java -jar soapbox-race-version-jarname.jar
    
example:

    java -jar soapbox-race-1.0.jar

##How to login

- Users + Password hashes(SHA-1) (default MySQL entries):

```
format:
email            passwordHash
debug@player1    a94a8fe5ccb19ba61c4c0873d391e987982fbbd3
debug@player2    a94a8fe5ccb19ba61c4c0873d391e987982fbbd3
debug@player3    a94a8fe5ccb19ba61c4c0873d391e987982fbbd3
```

- Get loginToken and userID with:

`http://ip-to-http-host:1337/soapbox/Engine.svc/user/authenticateUser?email=SOME_EMAIL&password=SOME_HASH_PASSWORD`

examples:

    http://localhost:1337/soapbox/Engine.svc/user/authenticateUser?email=debug@player1&password=a94a8fe5ccb19ba61c4c0873d391e987982fbbd3
    http://localhost:1337/soapbox/Engine.svc/user/authenticateUser?email=debug@player2&password=a94a8fe5ccb19ba61c4c0873d391e987982fbbd3
    http://localhost:1337/soapbox/Engine.svc/user/authenticateUser?email=debug@player3&password=a94a8fe5ccb19ba61c4c0873d391e987982fbbd3


- Launch soapbox.exe with the parameters: 

`soapbox.exe ANYTHING_YOU_WANT http://ip-to-http-host:1337/soapbox/Engine.svc loginToken userId`

example:

`soapbox.exe US http://localhost:1337/soapbox/Engine.svc 3484061174147 3`

##How to create users

- Create user

`http://ip-to-http-host:1337/soapbox/Engine.svc/user/createUser?email=SOME_EMAIL&password=SOME_HASH_PASSWORD`

example

`http://localhost:1337/soapbox/Engine.svc/user/createUser?email=myuser@somewhere&password=a94a8fe5ccb19ba61c4c0873d391e987982fbbd3`

##Launcher development

Please follow https://github.com/berkay2578/soapbox-race-launcher for more info.
