# ubuntu-dev-machine-setup | Ubuntu 21.10

## Description

This repo contains Ansible playbooks to configure your system as a development machine upon a clean install.

It installs:

- base
- vim
- zsh
- vscode
- i3wm
- dotfiles
- custom keyboard with german special characters on a second layer and switched escape and capslock
- TODO: git SSH key
- TODO: intellij
- TODO: chromium-browser
- TODO: chromium bookmarks
- TODO: VirtualBox for ansible testing purposes
- TODO: spotify
- TODO: signal
- TODO: Noisetorch (get latest artefakt using this approach https://blog.markvincze.com/download-artifacts-from-a-latest-github-release-in-sh-and-powershell/#:~:text=Artifacts%20from%20this%20particular%20release,%2Fproject%2Freleases%2Flatest%20.)

## Step 0 | Pre-requisites for running the ansible playbooks

On the system which you are going to setup using Ansible, perform these steps.

You need to install `ansible` and `git` before running the playbooks. You can either install it using `pip` or `apt`.

```sh
/usr/bin/sudo apt install ansible git
```

And clone this repo

## Step 1 | Running the playbooks to configure your system

**Invoke the following as yourself, the primary user of the system. Do not run as `root`.**

```sh
ansible-playbook main.yml -vv -e "local_username=$(id -un)" -K
```

Enter the sudo password when asked for `BECOME password:`.

After all is done, give your laptop a new life by rebooting.

## Further Steps

- Login into jira using `jira login`

## Known Issues

- If the ansible playbook halts after completing a few tasks, simply run the playbook again. Since most of the tasks are idempotent, running the playbook multiple times won't break anything.
- If your terminal shows any weird characters because of installing one of the zsh themes, simply change the font to a suitable Nerd Font from the terminal's settings.
- If you are unable to install snapd and snap packages, remove the file `/etc/apt/preferences.d/nosnap.pref` (this is not a known issue but a feature)
- If you get a black screen after logout, deactivate wayland in the (gdm3 config)[/etc/gdm3/custom.conf] see (here)[https://askubuntu.com/a/1079363]

---

## Pull Requests and Forks

You are more than welcome to send any pull requests. However, the intention of this repo is to suit my development needs. So it might be better if you *fork* this repo instead for your own needs and personalization.

---

