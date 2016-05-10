# My Base Virtual Machine
## About
An Ubuntu Server 14.04 LTS virtual machine configured using [Puphpet](https://puphpet.com). The machine has Apache, Ruby, Python, MongodB, and Nodejs installed. There is also gulp, eslint, htmlhint, csslint, browser-sync, live-server, yeoman, and bower packages installed for nodejs.

## Installation
Clone the repository into a virtual machine folder within your projects directory. The entire project directory will be available at `/var/www/` on the virtual server when it is running. The directory structure should be as such:
```
Project Directory
|
|___.VirtualMachines
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
After cloning the repo, you can spin up the virtual machine by running `vagrant up` in a terminal from the cloned directory.

### Important Notes
- Once the first `vagrant up` completes, you must run `vagrant provision` to fix NPM permissions. This will allow NPM to install packages globally and also affects Yeoman since it utilizes NPM global installation.
- Probably more

### Great benefits
- `vagrant share` allows you to share your local development work across the internet instantly even allowing people to SSH into your projects and collaborate. The only hard part is the URL.


### After working with the Virtual Machine
- Run `vagrant halt` in the terminal to stop the machine but keep provisioning. Further `vagrant up` commands will be much quicker and allow you to pick up where you left off.
- `vagrant destroy` will kill the machine and free memory but take longer to spin the machine up again(also see "Important Notes" if you do this)

