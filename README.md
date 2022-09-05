This is vagrantfile that starts ubuntu 20.04 virtual machine, installs docker and gitlab-runner, and starts docker and shell runners with given token.


To run this vagrantfile vagrant should be installed on your machine:
https://www.vagrantup.com/docs/installation

Then you should get registration token from gitlab: 
https://docs.gitlab.com/runner/register/

Then just run "vagrant up" with given token as environment variable:
TOKEN=*your value* vagrant up

Have a patience provisioning will take several minutes.
