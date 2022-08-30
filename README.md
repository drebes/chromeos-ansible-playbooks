# Playbook for installing various (mostly developer) tools into ChromeOS Linux environment

Last tested on ChromeOS Flex (104.0.5112.105), Linux Development Environment (Crostini), based on Debian bullseye.

## What is included

* [Docker](https://docs.docker.com/engine/install/debian/)
* [Google Cloud  (gcloud) CLI](https://cloud.google.com/sdk/docs/install#deb)
* [Obsidian](https://flathub.org/apps/details/md.obsidian.Obsidian)
* SSH Agent
* [Terraform](https://www.terraform.io/cli/install/apt)
* [Visual Studio Code](https://code.visualstudio.com/docs/setup/linux)
* Visual Studio Code Extensions:
  - [Cloud Code](https://marketplace.visualstudio.com/items?itemName=GoogleCloudTools.cloudcode)
  - [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
  - [GitHub Pull Requests and Issues](https://marketplace.visualstudio.com/items?github.vscode-pull-request-github)
  - [HashiCorp Terraform](https://marketplace.visualstudio.com/items?itemName=HashiCorp.terraform)
  - [Kubernetes](https://marketplace.visualstudio.com/items?itemName=ms-kubernetes-tools.vscode-kubernetes-tools)
  - [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
  - [YAML](https://marketplace.visualstudio.com/items?redhat.vscode-yaml)
* Extra Packages:
  - bind9-dnsutils
  - jq
  - netcat-openbsd
  - opensc
  - python3-venv

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
the `git_config` variables in the file `group_vars/all` and setting it to your appropriate value.

#### Extra packages

You can configure the list of extra packages that get installed by modifying the 
the `packages` variable under `extra_packages` in the file `group_vars/all` and setting it to the list of packages
you'd like to have.

#### Visual Studio Code extensions

You can configure the list of Visual Studio Code extensions that get installed by modifying the 
the `extensions` variable under `vscode` in the file `group_vars/all` and setting it to the list of extensions
you'd like to have.