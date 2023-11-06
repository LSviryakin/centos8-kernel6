# centos8-kernel6
Методическое пособие по выполнению домашнего задания по курсу «Администратор Linux. Professional»
Цель домашнего задания
Научиться обновлять ядро в ОС Linux. Получение навыков работы с Vagrant, Packer и публикацией готовых образов в Vagrant Cloud. 
Описание домашнего задания
1) Обновить ядро ОС из репозитория ELRepo
2) Создать Vagrant box c помощью Packer
3) Загрузить Vagrant box в Vagrant Cloud

>packer build centos.json
virtualbox-iso.centos-8stream: output will be in this color.

==> virtualbox-iso.centos-8stream: Retrieving Guest additions
==> virtualbox-iso.centos-8stream: Trying C:\Program Files\Oracle\VirtualBox/VBoxGuestAdditions.iso
==> virtualbox-iso.centos-8stream: Trying file://C:/Program%20Files/Oracle/VirtualBox/VBoxGuestAdditions.iso
==> virtualbox-iso.centos-8stream: file://C:/Program%20Files/Oracle/VirtualBox/VBoxGuestAdditions.iso => C:/Program Files/Oracle/VirtualBox/VBoxGuestAdditions.iso
==> virtualbox-iso.centos-8stream: Retrieving ISO
==> virtualbox-iso.centos-8stream: Trying https://mirror.linux-ia64.org/centos/8-stream/isos/x86_64/CentOS-Stream-8-x86_64-latest-boot.iso
==> virtualbox-iso.centos-8stream: Trying https://mirror.linux-ia64.org/centos/8-stream/isos/x86_64/CentOS-Stream-8-x86_64-latest-boot.iso?checksum=sha256%3A7d1967869643a66c83cedd5580cb45c0810ca9f6f47a8e36a8efbcf4824219a8
==> virtualbox-iso.centos-8stream: https://mirror.linux-ia64.org/centos/8-stream/isos/x86_64/CentOS-Stream-8-x86_64-latest-boot.iso?checksum=sha256%3A7d1967869643a66c83cedd5580cb45c0810ca9f6f47a8e36a8efbcf4824219a8 => D:\_Labs_Linux_Learn\VM\packer\packer_cache\68b1b1881f001ea10d1f0497aa49cdaebdd93946.iso
==> virtualbox-iso.centos-8stream: Starting HTTP server on port 8360
==> virtualbox-iso.centos-8stream: Creating virtual machine...
==> virtualbox-iso.centos-8stream: Creating hard drive builds\packer-centos-vm.vdi with size 10240 MiB...
==> virtualbox-iso.centos-8stream: Mounting ISOs...
    virtualbox-iso.centos-8stream: Mounting boot ISO...
==> virtualbox-iso.centos-8stream: Creating forwarded port mapping for communicator (SSH, WinRM, etc) (host port 4242)
==> virtualbox-iso.centos-8stream: Executing custom VBoxManage commands...
    virtualbox-iso.centos-8stream: Executing: modifyvm packer-centos-vm --memory 1024
    virtualbox-iso.centos-8stream: Executing: modifyvm packer-centos-vm --cpus 2
    virtualbox-iso.centos-8stream: Executing: modifyvm packer-centos-vm --nat-localhostreachable1 on
==> virtualbox-iso.centos-8stream: Starting the virtual machine...
==> virtualbox-iso.centos-8stream: Waiting 10s for boot...
==> virtualbox-iso.centos-8stream: Typing the boot command...
==> virtualbox-iso.centos-8stream: Using SSH communicator to connect: 127.0.0.1
==> virtualbox-iso.centos-8stream: Waiting for SSH to become available...
==> virtualbox-iso.centos-8stream: Connected to SSH!
==> virtualbox-iso.centos-8stream: Uploading VirtualBox version info (7.0.12)
==> virtualbox-iso.centos-8stream: Uploading VirtualBox guest additions ISO...
==> virtualbox-iso.centos-8stream: Pausing 20s before the next provisioner...
==> virtualbox-iso.centos-8stream: Provisioning with shell script: scripts/stage-1-kernel-update.sh
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream: We trust you have received the usual lecture from the local System
    virtualbox-iso.centos-8stream: Administrator. It usually boils down to these three things:
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream:     #1) Respect the privacy of others.
    virtualbox-iso.centos-8stream:     #2) Think before you type.
    virtualbox-iso.centos-8stream:     #3) With great power comes great responsibility.
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream: CentOS Stream 8 - AppStream                     8.3 MB/s |  34 MB     00:04
    virtualbox-iso.centos-8stream: CentOS Stream 8 - BaseOS                        7.3 MB/s |  52 MB     00:07
    virtualbox-iso.centos-8stream: CentOS Stream 8 - Extras                         12 kB/s |  18 kB     00:01
    virtualbox-iso.centos-8stream: CentOS Stream 8 - Extras common packages         12 kB/s | 6.9 kB     00:00
    virtualbox-iso.centos-8stream: elrepo-release-8.el8.elrepo.noarch.rpm          9.3 kB/s |  13 kB     00:01
    virtualbox-iso.centos-8stream: Dependencies resolved.
    virtualbox-iso.centos-8stream: ================================================================================
    virtualbox-iso.centos-8stream:  Package             Arch        Version                Repository         Size
    virtualbox-iso.centos-8stream: ================================================================================
    virtualbox-iso.centos-8stream: Installing:
    virtualbox-iso.centos-8stream:  elrepo-release      noarch      8.3-1.el8.elrepo       @commandline       13 k
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream: Transaction Summary
    virtualbox-iso.centos-8stream: ================================================================================
    virtualbox-iso.centos-8stream: Install  1 Package
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream: Total size: 13 k
    virtualbox-iso.centos-8stream: Installed size: 5.0 k
    virtualbox-iso.centos-8stream: Downloading Packages:
    virtualbox-iso.centos-8stream: Running transaction check
    virtualbox-iso.centos-8stream: Transaction check succeeded.
    virtualbox-iso.centos-8stream: Running transaction test
    virtualbox-iso.centos-8stream: Transaction test succeeded.
    virtualbox-iso.centos-8stream: Running transaction
    virtualbox-iso.centos-8stream:   Preparing        :                                                        1/1
    virtualbox-iso.centos-8stream:   Installing       : elrepo-release-8.3-1.el8.elrepo.noarch                 1/1
    virtualbox-iso.centos-8stream:   Verifying        : elrepo-release-8.3-1.el8.elrepo.noarch                 1/1
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream: Installed:
    virtualbox-iso.centos-8stream:   elrepo-release-8.3-1.el8.elrepo.noarch
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream: Complete!
    virtualbox-iso.centos-8stream: ELRepo.org Community Enterprise Linux Repositor 327 kB/s | 248 kB     00:00
    virtualbox-iso.centos-8stream: ELRepo.org Community Enterprise Linux Kernel Re 1.7 MB/s | 2.1 MB     00:01
    virtualbox-iso.centos-8stream: Dependencies resolved.
    virtualbox-iso.centos-8stream: ================================================================================
    virtualbox-iso.centos-8stream:  Package              Arch      Version                  Repository        Size
    virtualbox-iso.centos-8stream: ================================================================================
    virtualbox-iso.centos-8stream: Installing:
    virtualbox-iso.centos-8stream:  kernel-ml            x86_64    6.5.10-1.el8.elrepo      elrepo-kernel    116 k
    virtualbox-iso.centos-8stream: Installing dependencies:
    virtualbox-iso.centos-8stream:  kernel-ml-core       x86_64    6.5.10-1.el8.elrepo      elrepo-kernel     38 M
    virtualbox-iso.centos-8stream:  kernel-ml-modules    x86_64    6.5.10-1.el8.elrepo      elrepo-kernel     34 M
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream: Transaction Summary
    virtualbox-iso.centos-8stream: ================================================================================
    virtualbox-iso.centos-8stream: Install  3 Packages
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream: Total download size: 72 M
    virtualbox-iso.centos-8stream: Installed size: 113 M
    virtualbox-iso.centos-8stream: Downloading Packages:
    virtualbox-iso.centos-8stream: (1/3): kernel-ml-6.5.10-1.el8.elrepo.x86_64.rpm 405 kB/s | 116 kB     00:00
    virtualbox-iso.centos-8stream: (2/3): kernel-ml-core-6.5.10-1.el8.elrepo.x86_6 4.2 MB/s |  38 MB     00:08
    virtualbox-iso.centos-8stream: (3/3): kernel-ml-modules-6.5.10-1.el8.elrepo.x8 2.5 MB/s |  34 MB     00:13
    virtualbox-iso.centos-8stream: --------------------------------------------------------------------------------
    virtualbox-iso.centos-8stream: Total                                           5.2 MB/s |  72 MB     00:13
    virtualbox-iso.centos-8stream: ELRepo.org Community Enterprise Linux Kernel Re 937 kB/s | 1.7 kB     00:00
    virtualbox-iso.centos-8stream: Importing GPG key 0xBAADAE52:
    virtualbox-iso.centos-8stream:  Userid     : "elrepo.org (RPM Signing Key for elrepo.org) <secure@elrepo.org>"
    virtualbox-iso.centos-8stream:  Fingerprint: 96C0 104F 6315 4731 1E0B B1AE 309B C305 BAAD AE52
    virtualbox-iso.centos-8stream:  From       : /etc/pki/rpm-gpg/RPM-GPG-KEY-elrepo.org
    virtualbox-iso.centos-8stream: Key imported successfully
    virtualbox-iso.centos-8stream: Running transaction check
    virtualbox-iso.centos-8stream: Transaction check succeeded.
    virtualbox-iso.centos-8stream: Running transaction test
    virtualbox-iso.centos-8stream: Transaction test succeeded.
    virtualbox-iso.centos-8stream: Running transaction
    virtualbox-iso.centos-8stream:   Preparing        :                                                        1/1
    virtualbox-iso.centos-8stream:   Installing       : kernel-ml-core-6.5.10-1.el8.elrepo.x86_64              1/3
    virtualbox-iso.centos-8stream:   Running scriptlet: kernel-ml-core-6.5.10-1.el8.elrepo.x86_64              1/3
    virtualbox-iso.centos-8stream:   Installing       : kernel-ml-modules-6.5.10-1.el8.elrepo.x86_64           2/3
    virtualbox-iso.centos-8stream:   Running scriptlet: kernel-ml-modules-6.5.10-1.el8.elrepo.x86_64           2/3
    virtualbox-iso.centos-8stream:   Installing       : kernel-ml-6.5.10-1.el8.elrepo.x86_64                   3/3
    virtualbox-iso.centos-8stream:   Running scriptlet: kernel-ml-core-6.5.10-1.el8.elrepo.x86_64              3/3
    virtualbox-iso.centos-8stream:   Running scriptlet: kernel-ml-6.5.10-1.el8.elrepo.x86_64                   3/3
    virtualbox-iso.centos-8stream:   Verifying        : kernel-ml-6.5.10-1.el8.elrepo.x86_64                   1/3
    virtualbox-iso.centos-8stream:   Verifying        : kernel-ml-core-6.5.10-1.el8.elrepo.x86_64              2/3
    virtualbox-iso.centos-8stream:   Verifying        : kernel-ml-modules-6.5.10-1.el8.elrepo.x86_64           3/3
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream: Installed:
    virtualbox-iso.centos-8stream:   kernel-ml-6.5.10-1.el8.elrepo.x86_64
    virtualbox-iso.centos-8stream:   kernel-ml-core-6.5.10-1.el8.elrepo.x86_64
    virtualbox-iso.centos-8stream:   kernel-ml-modules-6.5.10-1.el8.elrepo.x86_64
    virtualbox-iso.centos-8stream:
    virtualbox-iso.centos-8stream: Complete!
    virtualbox-iso.centos-8stream: Generating grub configuration file ...
    virtualbox-iso.centos-8stream: done
    virtualbox-iso.centos-8stream: Grub update done.
==> virtualbox-iso.centos-8stream: Provisioning with shell script: scripts/stage-2-clean.sh
    virtualbox-iso.centos-8stream: [sudo] password for vagrant: Last metadata expiration check: 0:02:28 ago on Mon 06 Nov 2023 05:28:15 AM EST.
    virtualbox-iso.centos-8stream: Dependencies resolved.
    virtualbox-iso.centos-8stream: Nothing to do.
    virtualbox-iso.centos-8stream: Complete!
    virtualbox-iso.centos-8stream: 39 files removed
==> virtualbox-iso.centos-8stream: Gracefully halting virtual machine...
    virtualbox-iso.centos-8stream: [sudo] password for vagrant:
==> virtualbox-iso.centos-8stream: Preparing to export machine...
    virtualbox-iso.centos-8stream: Deleting forwarded port mapping for the communicator (SSH, WinRM, etc) (host port 4242)
==> virtualbox-iso.centos-8stream: Exporting virtual machine...
    virtualbox-iso.centos-8stream: Executing: export packer-centos-vm --output builds\packer-centos-vm.ovf --manifest --vsys 0 --description CentOS 8 Stream with kernel 6.x --version 8
==> virtualbox-iso.centos-8stream: Cleaning up floppy disk...
==> virtualbox-iso.centos-8stream: Deregistering and deleting VM...
==> virtualbox-iso.centos-8stream: Running post-processor: vagrant
==> virtualbox-iso.centos-8stream (vagrant): Creating a dummy Vagrant box to ensure the host system can create one correctly
==> virtualbox-iso.centos-8stream (vagrant): Creating Vagrant box for 'virtualbox' provider
    virtualbox-iso.centos-8stream (vagrant): Copying from artifact: builds\packer-centos-vm-disk001.vmdk
    virtualbox-iso.centos-8stream (vagrant): Copying from artifact: builds\packer-centos-vm.mf
    virtualbox-iso.centos-8stream (vagrant): Copying from artifact: builds\packer-centos-vm.ovf
    virtualbox-iso.centos-8stream (vagrant): Renaming the OVF to box.ovf...
    virtualbox-iso.centos-8stream (vagrant): Compressing: Vagrantfile
    virtualbox-iso.centos-8stream (vagrant): Compressing: box.ovf
    virtualbox-iso.centos-8stream (vagrant): Compressing: metadata.json
    virtualbox-iso.centos-8stream (vagrant): Compressing: packer-centos-vm-disk001.vmdk
    virtualbox-iso.centos-8stream (vagrant): Compressing: packer-centos-vm.mf
Build 'virtualbox-iso.centos-8stream' finished after 38 minutes 55 seconds.

==> Wait completed after 38 minutes 55 seconds

==> Builds finished. The artifacts of successful builds are:
--> virtualbox-iso.centos-8stream: 'virtualbox' provider box: centos-8-kernel-6-x86_64-Minimal.box


> vagrant box add --name centos8-kernel6 centos-8-kernel-6-x86_64-Minimal.box
==> box: Box file was not detected as metadata. Adding it directly...
==> box: Adding box 'centos8-kernel6' (v0) for provider:
    box: Unpacking necessary files from: file://D:/_Labs_Linux_Learn/VM/packer/centos-8-kernel-6-x86_64-Minimal.box
    box:
==> box: Successfully added box 'centos8-kernel6' (v0) for ''!

> vagrant box list
centos8-kernel6  (virtualbox, 0)
generic/centos8  (virtualbox, 4.3.2)
generic/centos8s (virtualbox, 4.3.2)

> vagrant init centos8-kernel6
A `Vagrantfile` has been placed in this directory. You are now
ready to `vagrant up` your first virtual environment! Please read
the comments in the Vagrantfile as well as documentation on
`vagrantup.com` for more information on using Vagrant.