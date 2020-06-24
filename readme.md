#Vagrant provision class :taco:

Today's learning obectives:

-provisioning
-setting up a  working app


##Sudo code of what we want to do:

#### Question you might ask
Some one from the team is handing youcode. Dont just accept, ask for context. Examples:
-what language
-what frameworks?
are there tests?
is there a package that need to be installled? is there a package list of some sort?
- specific packages or versions that dont work?
- any other info


####response thank you for asking.! Well we have a good read me .
-its all built on js node(oh okay look out for this terminology
-just bundle install and run the rake file(smile)



I want to create a machine and set up a working app in it.
I want it in a VM because it will be a standardised environment.


The steps we need to take:

Well I know the environment will be:
- ubuntu/xenial64-(installed)
- I will need nodejs
- check how to install stuff init
-I want it on port 80
-I will need a reverse proxy to get to my app talking on port 80
-I will need my ap in my vm! so I can install and run it's code(I need this in there)
(our objective is to know everything for the next stage)

###important commands
###bundle install --path vendor/bundle
#### after installing ruby 1 and 3
#### rake spec to run tests from within spec tests folder

Provisioning and tests
This exercise utilised vagrant and VirtualBox to make sure the provision file passed all the tests.

Installation

To get this box running:
clone the repo
make sure you are on the root of the project and can see the Vagrant file
then run:

vagrant up

Now you can see nginx running on 2 locations:
ip: 192.168.10.100
development.local/

Vagrantfile
What is it?

Vagrantfile is a Ruby file used to configure Vagrant on a per-project basis.

What goes on the vagrant file?
It's main function is to describe the virtual machines required for a project as well as how to configure and provision these machines.

Virtual Machine
How do I send a folder into my VM?

config.vm.synced_folder("app", "/app")

How do I write a script (sh) for my VM?
config.vm.provision "shell", path: "environment/provision.sh"



How do I spin up a VM?
vagrant up

How do I destroy a VM?
vagrant destroy

How do I re re-run the provision script without killing/destroy the VM?
vagrant reload

Provisioning
What do we want to run as a provision for shell commands. What dependencies are needed? Node js? nginx? If we dont use provisions, Vagrant will just run a blank ubuntu server

Be careful with placement of syntax!
Nginx:
sudo apt-get update -y

sudo apt-get install nginx -y

service nginx start
Nodejs
apt-get install nodejs npm -y

npm install -g pm2

sudo nvm use 6

curl -sL https://deb.nodesource.com/setup_6.x | sudo bash -
sudo apt-get install -y nodejs

sudo npm install pm2 -g
Considerations
Do I have ruby?
Do I have bundler?
Have I installed all the ruby dependencies to run the test? - bundle install how do I run the test? rake spec
Am I in the right location to run these commands?
