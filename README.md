# Playbook for installing various (developer) tools into ChromeOS Linux environment

Last tested on ChromeOS Flex (103.0.5060.132), Linux Development Environment (Crostini), based on Debian bullseye.

## What is included

linux)
* [Docker](https://docs.docker.com/engine/install/debian/)
* [Google Cloud  (gcloud) CLI](https://cloud.google.com/sdk/docs/install#deb)
* [Obsidian](https://flathub.org/apps/details/md.obsidian.Obsidian)
* [OpenSC](https://github.com/OpenSC/OpenSC/wiki)
* [Terraform](https://www.terraform.io/cli/install/apt)
* [Visual Studio Code](https://code.visualstudio.com/docs/setup/linux)

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
cd chromeos-ansible-playbooks && ansible-playbook install.yaml
```

## Customizing

If you'd like to customize the list of packages that get installed, edit `install.yaml` and
remove/modify/comment out the corresponding roles.

### Optional Setup

#### git user setup

You can configure your default (global) git commit identity (user name and email) by uncommenting
the `git_config` variable in the file `group_vars/all` and setting it to your appropriate value.
