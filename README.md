AppHouse
---
A hosting platform for node.js application.

Feature
-
* Support all node.js applications.
* Support multi-instance for each application.
* Support sandbox, stand-alone instance to isolate each application.
* Auto-restart application when it crashes.
* Support virtual host

Installation
-
1. Download AppHouse from repository:

        git clone https://cfsghost@github.com/cfsghost/AppHouse.git

2. Install dependencies with NPM utility:

        npm install

3. Start AppHouse as root:

        sudo node apphouse.js

    *Note: AppHouse needs root permission to make safety sandbox with chroot*

Application Deployment
-
There is no need modifying your application for AppHouse, just put your application on specific folder:

1. Create a directory for new application:

        mkdir apps/myapp

2. Put your application in the new place (using `express` to generate application for example):

        cd apps/myapp
        npm install express jade
        express

3. Restart AppHouse

    *Note: AppHouse will run `app.js` in application folder.*

Application Settings
-
You can modify `apphouse.cfg` in the application directory, it's formatted using JSON(JavaScript Object Notation).

Here is options:

* `domains` : set domains for application. (An application can have multiple domain)

    Example:
    
        domains: [ "test1.example.com", "test2.example.com" ]

* `instances` : set number of instances for application. (Default: 1)

Management Tools
-
AppHouse doesn't have tools to manage applications and service, but we've created a new project to do this job:

https://github.com/cfsghost/AppHouse-Manager
License
-
Licensed under the GPL-2.0
Authors
-
Copyright(c) 2012 Fred Chien <<fred@mandice.com>>

Copyright
-
Copyright(c) 2012 Mandice Company. (http://www.mandice.com/)