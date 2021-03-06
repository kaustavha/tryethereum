tryethereum
===========

Try Ethereum with an online interface  

## Installation  
You need nodejs, mongo-db and the coffeescript node module installed, the rest of the dependencies should take care of themselves.  
If a build failure occurs, look in Cakefile, that's where all the tasks are.  

[http://nodejs.org/](http://nodejs.org/)  
[http://docs.mongodb.org/manual/installation/](http://docs.mongodb.org/manual/installation/)  
[http://coffeescript.org/](http://coffeescript.org/)  
Also install python 2.7.5+ if you don't have it.  

Quickstart for *ubuntu systems:   
```
sudo apt-get install nodejs && sudo npm install -g coffee-script
echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | sudo tee /etc/apt/sources.list.d/mongodb.list  
sudo apt-get update  
sudo apt-get install mongodb-org=2.6.0 mongodb-org-server=2.6.0 mongodb-org-shell=2.6.0 mongodb-org-mongos=2.6.0 mongodb-org-tools=2.6.0  
sudo service mongod start  
```

Then get out of su and run:  
```
sudo cake build  
```

You can also run "sudo cake -s build" to skip git cloning pyethereum and serpent and installing bower, git and pip

Note:  
- If you get an error from the server related to pyethtool command not found  
Include the files in pyethereum/bin in your path or copy them to /usr/local/bin on ubuntu based OSs  

- Sometimes mongo might get derpy. 
```
sudo pkill -9 mongodb
sudo mongod --repair
```
Now you can run things from the cakefile again.

- Express might not close or release port 3000, you'll get a Error: listen EADDRINUSE
```
sudo fuser -k 3000/tcp
```

That should fix it.
## TODO
- Hooks for c++ implementation install
- UI