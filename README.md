# Playbook for installing various (developer) tools into ChromeOS Linux environment

Last tested on ChromeOS Flex (103.0.5035.0), Linux Development Environment (Crostini), based on Debian bullseye

## What is included

* [Visual Studio Code](https://code.visualstudio.com/docs/setup/linux)
* [Docker](https://docs.docker.com/engine/install/debian/)
* [Terraform](https://www.terraform.io/cli/install/apt)
* [Google Cloud  (gcloud) CLI](https://cloud.google.com/sdk/docs/install#deb)
* [Obsidian](https://flathub.org/apps/details/md.obsidian.Obsidian)

## Requirements

Installing ansible:

```shell
sudo apt install ansible -y
```

Cloning this repo:

```shell
git clone https://github.com/drebes/chromeos-ansible-playbooks.git
```

Running the playbook:

```shell
ansible-playbook install.yaml
```

## Customizing

If you'd like to customize the list of packages that get install, edit `install.yaml` and
remove/comment out the corresponding roles.