# My Base Virtual Machine
## About
A development Ubuntu Server 14.04 LTS virtual machine configured using [Puphpet](https://puphpet.com). The machine has Apache, Ruby, Python, MongodB, and Nodejs installed. There are also gulp, eslint, htmlhint, csslint, browser-sync, live-server, yeoman, and bower packages installed for nodejs.

## Installation
Clone the repository into a virtual machine folder within your projects directory. The entire project directory will be available at `/var/www/` on the virtual server when it is running. The directory structure should be as such:
```
Project Directory
|
|___.VirtualMachines(or a name of your choosing)
|   |
|   |___DirectoryToCloneTo
|
|___Project1
|   |
|   |___Project1-Files
|
|___Project2
|   |
|   |___Project2-Files
|
|___etc.
```

## Usage
- After cloning the repo, you can spin up the virtual machine by running `vagrant up` in a terminal from the cloned directory.
- 'Project Directory' is mapped to '/var/www/' on the VM and is served by Apache at '192.168.56.101'.
- The default hostname is 'mark.dev', you can add this to your [hosts file](https://en.wikipedia.org/wiki/Hosts_(file) so you don't have to use that ugly IP address.
- 'vagrant ssh' in the terminal will allow to to work on the VM's command line
- `vagrant share` allows you to share your local development work across the internet instantly even allowing people to SSH into your projects and collaborate. The only hard part is the URL.


### Important Notes
- Once the first `vagrant up` completes, you must run `vagrant provision` to fix NPM permissions. This will allow NPM to install packages globally and also affects Yeoman since it utilizes NPM global installation.
- Apache will create an 'html' folder in your project directory. It is annoying but there isn't a way to stop this that will withstand updates to puphpet files, so I let it be. It is safe to remove the directory manually.

### Forwarded Ports
* 8080 is used for 'vagrant ssh' thus is forwarded to 22 on VM
* 1 to 1 forwards for alternative servers
  - 8000 for live-server (You must set the port when starting as live server uses 8080 by default)
  - 3001 for browser-sync UI
  - 3000 for browser-sync

### After working with the Virtual Machine
- 'vagrant suspend' eats more disk space but saves machine state
- `vagrant halt` shuts down the machine but keeps provisions
- `vagrant destroy` for when you mess up the machine or want it all the way gone

