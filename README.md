Qowala live
===========

Qowala live is an open source Twitter client to display your home timeline, your lists and tracked tweets with specified hashtags. 

### Official instance:

The official instance server is at : https://live.qowala.eu

### Git repositories:

They are two mirrored git repositories of the project:

- Framasoft: https://git.framasoft.org/KillianKemps/Qowala-live
- Github: https://github.com/KillianKemps/Qowala-live

### Qowala live v1.0 functionalities:

- One pod for several users
- Display user's timeline
- Display user's lists
- Track tweets according hashtags
- Send tweets

![Qowala live Screenshot](http://www.killiankemps.fr/data/images/capture-d-ecran-2015-05-31-a-20.17.19.png)

### How to install Qowala live

- Rename **config/template_twitter.json** to **config/twitter.json** and put in your Twitter credentials (you can get the credentials on *Twitter Developer Website* at http://apps.twitter.com after creating your own app).

- Give your application Read & Write permissions on Twitter Application Management Dashboard

![Twitter App Manager](http://www.killiankemps.fr/data/images/qowala-live-twitter-settings.png)

- For the callback URL in **config/twitter.json** you have to put the domain name where the app will be hosted and add to it '/auth/twitter/callback'.

##### Ubuntu 14.04 process:
- Automatically: You can just launch the **Qowala-live_InstallationScript.sh**, it will do automatically what is below
- Manually: Follow below instructions

###### Install NodeJS
    curl -sL https://deb.nodesource.com/setup | sudo bash -
    sudo apt-get install nodejs
    sudo apt-get install build-essential
    
###### Install MongoDB
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
    echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | sudo tee /etc/apt/sources.list.d/mongodb.list
    sudo apt-get update
    sudo apt-get install -y mongodb-org
    
###### Install the dependencies
    npm install
    
###### Run the app
    nodejs app.js

##### Production mode
    sudo npm install -g forever
    forever -l forever.log -ao stdout.log -e stderr.log start app.js
    
*NodeJS installation process inspired by Digital Ocean: https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server*

*MongoDB installation process inspired by MongoDB.org http://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/*

#### To develop
The recommanded way to launch the app for development is to use **Vagrant**.

In the Qowala live's directory do

    vagrant up
    
Make sure that **MongoDB** and **NodeJS** are installed (follow instructions above).

Then run
    
    vagrant ssh
    cd /vagrant/
    npm install
    node app.js
    
You will then be able to access the client in your browser at **http://192.168.12.34:8080/**

# Project released under MIT License

The MIT License (MIT)

Copyright (c) 2015 Killian Kemps & Adrien Touminet

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
