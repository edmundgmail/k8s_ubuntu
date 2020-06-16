# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_NO_PARALLEL'] = 'yes'

Vagrant.configure(2) do |config|

  #config.vm.provision "shell", path: "bootstrap.sh"

  # Kubernetes Master Server
  config.vm.define "kmaster" do |kmaster|
    kmaster.vm.box = "bento/ubuntu-18.04"
    kmaster.vm.hostname = "kmaster.example.com"
    kmaster.vm.network "private_network", ip: "192.168.0.26"
    #kmaster.vm.network "public_network", bridge: "External VM Switch"
    kmaster.vm.provider "hyperv" do |v|
      v.vmname = "kmaster"
      v.memory = 6144
    end
    #kmaster.vm.provision "shell", path: "bootstrap_kmaster.sh"
  end

  # Kubernetes Worker Nodes
    config.vm.define "kworker1" do |workernode|
      workernode.vm.box = "bento/ubuntu-18.04"
      workernode.vm.hostname = "kworker1.example.com"
      workernode.vm.network "private_network", ip: "192.168.0.27"
      #workernode.vm.network "public_network", bridge: "External VM Switch"
      workernode.vm.provider "hyperv" do |v|
        v.vmname = "kworker1"
        v.memory = 2048
        v.cpus = 1
      end
      #workernode.vm.provision "shell", path: "bootstrap_kworker.sh"
    end

    config.vm.define "kworker2" do |workernode|
      workernode.vm.box = "bento/ubuntu-18.04"
      workernode.vm.hostname = "kworker2.example.com"
      workernode.vm.network "private_network", ip: "192.168.0.28"
      #workernode.vm.network "public_network", bridge: "External VM Switch"
      workernode.vm.provider "hyperv" do |v|
        v.vmname = "kworker2"
        v.memory = 2048
        v.cpus = 1
      end
      #workernode.vm.provision "shell", path: "bootstrap_kworker.sh"
    end

end
