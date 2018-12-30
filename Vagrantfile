Vagrant.configure("2") do |config|
  config.vm.box = 'centos/7'
  
  config.vm.provision "file", source: "script", destination: "/tmp/script"
  config.vm.provision "file", source: "busybox_config", destination: "/tmp/busybox_config"
  config.vm.provision "file", source: "kernel_config", destination: "/tmp/kernel_config"

  config.vm.provision "shell", inline: 'bash /tmp/script'

  # config.vm.provision "file", source: "/tmp/artifacts/bzImage", destination: "/tmp/bzImage"
  # config.vm.provision "file", source: "/tmp/artifacts/initramfs.cpio.gz", destination: "/tmp/initramfs.cpio.gz"


  config.vm.synced_folder ".", "/tmp/artifacts", type: "rsync"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = '4096'
    vb.cpus = '4'
  end
end
