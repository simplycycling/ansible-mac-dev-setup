# ansible-mac-dev-setup
Basic setup for my Mac.

## What it does
- Creates a directory structure inside of ~/Documents.
- Restores my dotfiles, along with a couple of dot dirs, .vim, and .irssi.
- Installs most of the apps that I use that can be installed via homebrew.

#### TODO:
Ascertain what remaining apps that need to be installed manually can be installed via brew.

### Update...
Now it does a lot more. It took a little bit of doing to get the homebrew role going - evidently, there was an Ansible 
issue...long story short, it's fixed now, so if it won't let you install caskroom/cask/brew-cask 
(line 38 vars/main.yml), update Ansible. That should take care of it.

### Requirements
- Ansible
- Git
- geerlingguy.homebrew
- geerlingguy.dotfiles

### Run
What needs to be done from a clean install, until you can run this playbook:

- Install Ansible, via pip
- Install geerlingguy's homebrew and dotfiles roles from Ansible Galaxy
- Install homebrew
- Install Google Drive (that's just me - YMMV)
- Install xcode cli tools
- Install git
- Clone this repo
- cd into repo, run:

`ansible-playbook -i inventory main.yml -K` (you'll prompted for your sudo password)

#### Troubleshooting
The first time I ran this with geerlingguy's homebrew role, I ran into an Ansible bug, that, long story short, wasn't 
letting me install caskroom/cask/brew-cask. I wish I had made note of the bug, for posterity's sake, but I didn't. Oh
well. Bottom line, if you get an error saying you can't install it, upgrade to the latest version of Ansible. It was 
fixed in late November, and once I upgraded, it worked flawlessly.

### Credit where credit is due
As mentioned before, I used two of Jeff Geerling's roles:
- geerlingguy.homebrew
- geerlingguy.dotfiles

They're both available on Ansible Galaxy. They're both good - homebrew gets a ton done, and dotfiles is brilliant.
To help set that stuff up, I borrowed a bit from his Ansible role for setting up his Mac:

https://github.com/geerlingguy/mac-dev-playbook

There's a lot of stuff I didn't use from his playbook, but there are definitely a lot of great ideas.

