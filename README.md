Requirements
--------------------------------------------------------------------------------
1. Install Vagrant <https://www.vagrantup.com/downloads.html>

1. Install VirtualBox and VirtualBox Extension Pack <https://www.virtualbox.org/wiki/Downloads>

1. Add `vagrant` and `VBoxManage` to your PATH.
    - This is most likely already done by the installation binaries.
      It's added to the system path.
    - To test this, type these commands in a terminal:

            ~$ vagrant --version
            Vagrant 1.8.1
            ~$ VBoxManage --version
            5.0.14r105127

    - You may need to log out and back in for the path modifications to take
      effect.
      
1. Install Bazel according to your operating system <https://docs.bazel.build/versions/master/install.html>

Usage
--------------------------------------------------------------------------------
1. Clone this repository onto your computer somewhere.

        git clone https://github.com/valkyrierobotics/dev-environment.git

1. Go into the directory and build the VM.

        vagrant up

1. Some errors during the `vagrant up` process can be addressed by
   re-provisioning the vagrant box. This is useful if, for example, an
   `apt-get` invocation timed out and caused the provisioning process to abort.

        vagrant provision

1. Once build, reboot the VM so it starts the GUI properly.

        vagrant reload

1. You can then log in and open a terminal. The username and password are both
   `user`.

1. Download the code and build it.

        git clone https://github.com/valkyrierobotics/mass.git
        cd mass
        bazel build //y2017/... -- $(cat NO_BUILD_AMD64)
