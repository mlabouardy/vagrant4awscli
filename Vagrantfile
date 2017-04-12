load 'config.rb'

Vagrant.configure('2') do |config|
  config.vm.define $name do |c|
    c.vm.box = $image
    c.vm.hostname = $name
    c.vm.provider 'virtualbox' do |vb|
      vb.memory = $memory
      vb.name = $name
      vb.gui = $gui
      vb.cpus = $cpu
    end
    c.vm.synced_folder $shared_folder, '/home/vagrant/'
    c.vm.network 'private_network', ip: $ip
    c.vm.provision 'shell', path: $provision_shell
  end
end
