
Vagrant.configure(2) do |config|
#  config.vm.box = "freebsd/FreeBSD-10.3-RELEASE"
  config.vm.box = "freebsd/FreeBSD-11.0-RELEASE-p1"
  #
  # https://bugs.freebsd.org/bugzilla/show_bug.cgi?id=201904
  #
  config.vm.base_mac = "c82a1406a9e0"
  config.vm.synced_folder "./mount-vagrant", "/vagrant", type: "rsync"

  config.ssh.shell = "sh"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "1024"
  end


  config.vm.define "tftp" do |tftp|
    tftp.vm.host_name = "tftp"
    tftp.vm.provision "shell", inline: "echo y | pkg install python"
    tftp.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "provisioning/site.yml"
    end
  end
end
