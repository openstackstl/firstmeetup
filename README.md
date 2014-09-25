firstmeetup
===========

first meet up demo using devstack


Here are the steps to spin up new VM using vagrant and setting up OpenStack using devstack


#mkdir devstack_vagrant
#cd devstack_vagrant/
#vagrant box add precise64 http://files.vagrantup.com/precise64.box
#vagrant init precise64
#vagrant up && vagrant ssh


After logging into the vagrant VM perform the following steps

#sudo apt-get install git
#git clone https://github.com/openstack-dev/devstack.git
#cd devstack && ./stack.sh

After installing OpenStack at the end devstack is going to spit out the IP address where you can access Horizon.

Since you cannot access that IP directly from your laptop, you need to change the "Vagrantfile" that was created by 
vagrant at ~/devstack_vagrant/.

Update the Vagrantfile to allow portforwarding from port 8080 to port 80 on the VM. You can refer to the Vagrantfile available
at this github repository

After making the changes and closing the file, execute the following command for Vagrant to load the changes made to Vagrantfile
#vagrant reload

Access Horizon dashboard from your laptop using the IP address at port 8080.
