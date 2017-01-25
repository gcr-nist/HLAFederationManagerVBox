# hal1
Vagrant.configure(2) do |config|
  config.vm.box = "box-cutter/ubuntu1404-desktop"
  config.vm.network :private_network, ip: '192.168.50.101'
  config.vm.network :forwarded_port, guest: 22, host: 2221, id: 'ssh'

  config.vm.define :ucef_ubuntu1404_box do |t|
  end
  config.vm.synced_folder "../../", "/cpswt"
  
  config.vm.provider "virtualbox" do |vb|
	# force cable connected on VB
	vb.customize ['modifyvm', :id, '--cableconnected1', 'on']
    # Display the name of the virtualbox 
    vb.name = "HLA1"
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true
    # Set the machine settings
    vb.customize [
      "modifyvm", :id,
      "--memory", "4096",
      "--vram", "32",
      "--cpus", "2",
      "--monitorcount", "1",
      "--accelerate3d", "off",
    ]
  end
  config.vm.provision "shell", :path => "bootstrap.sh", privileged: false
end

