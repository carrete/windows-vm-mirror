# windows-vm

Only Linux and macOS are supported.

## Download and install:

* [Git LFS](https://git-lfs.github.com)
* [VirtualBox](https://www.virtualbox.org)
* [Docker](https://www.docker.com)

A recent [coreutils](https://www.gnu.org/software/coreutils/coreutils.html)
and [curl](https://curl.haxx.se) are also required.

## Run `make vm-start`

This will download [the latest Window 10 virtual machine](https://developer.microsoft.com/en-us/windows/downloads/virtual-machines),
and import this into VirtualBox. This will take several hours to complete
depending on network bandwidth, and CPU and hard-drive access speeds.

* The directory `Shared/` in this repository is available as shared drive `Z:`
  in the virtual machine.

* SSH traffic to `localhost` on port `9022` is forwarded to the virtual
  machine. Connect to the virtual machine with `ssh User@localhost -p 9022`.
  Password is `password`.

## Provision virtual machine

TODO:

## Run `make run-compile`

This will run `Compile.bat` located in `Shared/` inside the virtual machine as
`Z:\Compile.bat`.

Before running the script, the virtual machine will be started in headless
mode, if the virtual machine is not running.

To run a new script, `FooBar.bat` for example, create `FooBar.bat` in
`Shared/` and run `make run-foobar`. There is no need to update the Makefile.

## Run `make vm-shutdown`

This will poweroff the virtual machine.
