A collection of virtual machines for dealing with all sorts of
network configuration systems. I want to be able to configure
and upgrade routers as single things as well as whole systems.

You need vagrant, ansible and virtualbox in order to run this
self-sustaining on your laptop. On a Mac, they're installed
like so:

  brew install Caskroom/cask/vagrant
  brew install Caskroom/cask/virtualbox
  brew install ansible

General idea is to put the data files in mount-vagrant/ which
is mounted in /vagrant for all guest machines.

The files in there are your data and are git ignored. This
mount is how you can move files back and forth between the
host and guests.

