# Ampath Developer Box
This is the ampath developer box. It provides a dev environment for the ampath team and contributors as will well a demo setup similar-ish to our production setup if you wanna poke around.

# Getting started
This box uses [Vagrant](https://www.vagrantup.com/intro/index.html)  so head over to https://www.vagrantup.com/intro/getting-started/index.html first if you haven't

Then.

```
git clone https://github.com/AMPATH/ampathDevBox
```

```
cd ampathDevBox
```
Edit the dotenv file using your favorite text editor
```
sudo nano .env
```
Change 

```
WORKSPACE_DIR=/home/achachiez/Code/ampathworkspace
```
to 
``` 
WORKSPACE_DIR=path to your workspace
```
Finally run

```
vagrant up
```
When done visit http://localhost:8080/ngx-amrs/#/login for the precompiled version

Click the cog at the bottom left side of the screen and make sure to select AMRS POC as the server settings template and click done to go back to the login screen.

Use pocadmin as the username and POCadmin123 as the password

For development run

```
vagrant ssh 
```

And then 

```
cd workspace
```

This folder maps to the folder you defined in WORKSPACE_DIR so any code you put in it is available for your editor.
