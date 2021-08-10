# MacBook Ansible Setup

This installs the software I use on my MacBook.
It's intended to be a living repository that I'll update as I add/remove
software.

Heavily inspired by [Jeff Geerling's](https://github.com/geerlingguy)
[mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook) 

## Installation

1. Install Apple's command line tools (`xcode-select --install` to launch the installer).

2. Upgrade pip: `sudo pip3 install --upgrade pip`

3. Install Ansible: `pip3 install ansible`

4. Sign in to Mac App Store

5. Run `./requirements.yml` to install required Ansible roles.

6. Run `./main.yml` to run the playbook. Enter MacOS password when prompted.

### Running a specific set of tasks

You can choose which tasks to run by specifying a set of tags.

    ansible-playbook main.yml -K --tags "dotfiles,homebrew"

Available tags are:
| Tag           | Description |
| ------------- | ----------- |
| `homebrew`    | Installs/updates [Homebrew](https://brew.sh/) and any packages or casks |
| `dotfiles`    | Clones my [dotfiles](https://github.com/geoffholden/dotfiles) repository and installs it |
| `mas`         | Installs/updates any applications from the Mac App Store |
| `dock`        | Configures the Dock |
| `appsettings` | Applys any additional application settings |


