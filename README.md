 
# Introduction
The course setup for `cs-15` will be as follows:
1. You will be working on the `VSCode` development environment.
2. You will be using the `remote-containers` extension in `VSCode`. 
3. You will be using a provided `Docker` container with course files, scripts, etc. so you can easily access and work with the starter code, compile, run, and run `valgrind` on your local system, etc. 
   
## Background (optional)
### Docker
`Docker` is a tool which allows for the creation/maintenance
of what are known as `containers`. `Docker containers` are effectively mini-operating systems that can come pre-packaged with software, etc. Such
containers are commonly used for packaging applications with all the stuff they need to run. Rather than have to build a different version of a given piece of software on multiple systems, using `Docker containers`, you can make one build of your software, and then run it anywhere the containers are supported.

### Remote Containers
`VS Code` has an extension named `remote containers`; this allows you to work 'inside' of a `Docker container` that is on your local desktop. This means that you can have access to a whole other operating system which comes pre-packaged with all of the necessary software for the course 


# Install Prerequisites
1. [Install Docker Desktop](https://www.docker.com/products/docker-desktop/)
3. [Install VSCode](https://code.visualstudio.com/)
4. [Install the remote containers extension for VSCode](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Note for Windows Users
For Windows users, WSL2 is encouraged, however is not required. See the details here on installation as it relates to remote-containers. https://code.visualstudio.com/docs/remote/containers. [Link for WSL2 installation walkthrough](https://docs.microsoft.com/en-us/windows/wsl/install)

# Installing the Docker Container
## Download the Build Scripts
Open a terminal in VSCode, and navigate to where you would like to make a cs-15 folder for your course work this semester. Then, run the following command in the integrated terminal:

```
git clone https://www.github.com/mattrussell2/15-docker.git cs-15
````

This will clone the repository (download all of the files required to build the container). Now, in your terminal, run:
```
cd .devcontainer
chmod +x prep_install
./prep_install
```
Enter your eecs `utln` when prompted. 

## Build the container
Great! Now, we have the blueprint for the container, but we need to build it. In `VSCode`, 

*  [On Windows] press `ctrl + shift + p` 
*  [On Mac]     press `cmd + shift + p`
*  Search for `Remote-containers: Open Folder in Container`
*  Select the `cs-15` directory from the steps above
*  The window should refresh - and the docker container will be built. 

## Notes
* If you see an error related to the `Docker daemon`, make sure you have `Docker` running in the background. 
* Be sure to indicate that you trust the author of the container. 
* Feel free to press the button to view the logs and see what's happening - this step will take about 5-10m. It will only have to happen once. After the container is built, it'll be quick to load.
* In rare cases, your system might hang at the very beginning (on step 2 or 3). If it's doing this, then run the command `rm ~/.docker/config.json` to remove the docker config file, and start over.      

Once the installation is complete, you should see `Dev Container: cs-15` in the lower left corner of the `VS Code` window. Press the `+` symbol on the right-hand side of your terminal window to open a new terminal from within the Container.

## register-utln
Run the command
```
register-utln
```
This will create an ssh-key for you, so you don't need to enter your password to connect to the halligan server. This will make downloading support code, etc. much easier, and will allow for automated backups.

## Automatic Backups
Also, once the above step is completed, every time that you save a file in your container, it will be automatically uploaded to the homework server under the path `/h/your_utln/cs-15/...` - where the `...` will be the path to the files under your local system, starting from your local `cs-15` directory.

## Workflow
Okay! For the future, anytime you want to work on `cs-15` stuff:
1. Open `VS Code`
2. Press `ctrl/cmd + shift + p` 
3. Select `Remote-containers: Open Folder in Container`
4. Select the `cs-15` directory. 
5. Open a terminal with the `+` key. 
6. Do your work!

### After opening `VSCode`, you can usually simply click on the `cs-15 [Dev Container]` link instead of doing steps 2-4 above. 

# pull-code
The `pull-code` script is used to pull starter code for an assignment from the homework server to your local system. 
## 
```
pull-code HWNAME
```
This script will pull the starter code for a given homework. For instance, running 
```
pull-code hw1
``` 
Will download the homework 1 starter code files. If you've already been working on a homework, make sure to make a local backup before running this command!

# jumbotest
This command is to use our in-house unit testing framework. See here for details: https://gitlab.cs.tufts.edu/mrussell/JumboTest
