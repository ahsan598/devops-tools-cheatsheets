# 🚀 Vagrant VM Commands Cheat Sheet

### 🔧 VM Lifecycle Commands

| Command             | Description                                                                 |
| ------------------- | --------------------------------------------------------------------------- |
| `vagrant init`      | Initializes a new Vagrant environment (creates a `Vagrantfile`).            |
| `vagrant up`        | Starts and provisions the VM defined in the `Vagrantfile`.                  |
| `vagrant halt`      | Shuts down the running VM (gracefully).                                     |
| `vagrant reload`    | Restarts the VM and applies changes to the `Vagrantfile`.                   |
| `vagrant destroy`   | Stops and deletes all resources created by Vagrant for that VM.             |
| `vagrant suspend`   | Suspends the VM (saves the current state).                                  |
| `vagrant resume`    | Resumes a suspended VM.                                                     |
| `vagrant provision` | Reruns the provisioning (e.g., shell or Ansible) without restarting the VM. |


### 🧠 Information and Debugging

| Command                    | Description                                                      |
| -------------------------- | ---------------------------------------------------------------- |
| `vagrant status`           | Shows the current status of the VM (running, not created, etc.). |
| `vagrant ssh`              | SSH into the running VM.                                         |
| `vagrant ssh <vm_name>`    | SSH into a specific VM in a multi-VM setup.                      |
| `vagrant global-status`    | Lists all active Vagrant environments on your system.            |
| `vagrant box list`         | Lists all boxes installed locally.                               |
| `vagrant box add <box>`    | Adds a new box from Vagrant Cloud or URL.                        |
| `vagrant box remove <box>` | Removes a box from your local system.                            |
| `vagrant box update`       | Updates the box to the latest version from the source.           |


### 🗑️ Cleanup & Management

| Command                         | Description                                                    |
| ------------------------------- | -------------------------------------------------------------- |
| `vagrant plugin list`           | Shows installed Vagrant plugins.                               |
| `vagrant plugin install <name>` | Installs a plugin (e.g., `vagrant-disksize`).                  |
| `vagrant destroy -f`            | Forcefully destroys the VM without prompt.                     |
| `vagrant halt -f`               | Force shutdown the VM.                                         |
| `vagrant ssh-config`            | Outputs SSH config details for the VM (useful for custom SSH). |
