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
-I will need my ap in my vm!so I can install and run it's code(I need this in there)
(our objective is to know everything for the next stage)

###important commands
###bundle install --path vendor/bundle
#### after installing ruby 1 and 3

#### rake spec to run tests from within spec tests folder
