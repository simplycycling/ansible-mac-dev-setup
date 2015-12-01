# ansible-mac-dev-setup
Basic setup for my Mac.

## What it does
Not much. Creates a directory structure inside of ~/Documents.

Ok, now it does some more. Clones some git repos. Also, I'm using Jeff Geerling's homebrew role. Is it any good? It 
looks pretty good. Who knows? I'll update as I go along.

### Update...
Now it does a lot more. It took a little bit of doing to get the homebrew role going - evidently, there was an Ansible 
issue...long story short, it's fixed now, so if it won't let you install caskroom/cask/brew-cask 
(line 38 vars/main.yml), update Ansible. That should take care of it.

## What it will do
More. At very least, I'll set it up to download some of my git repos.

Apple is such a pain, though. There's a bunch of stuff I'll still have to do
manually.

### Requirements
- Ansible
- Git

There will certainly be more requirements, as this progresses.

### Run
-Pretty simple- A bit more complex, now:

- Install Ansible, via pip
- Install geerlingguy's homebrew and dotfiles roles from Ansible Galaxy
- Install homebrew
- Install Google Drive (that's just me - YMMV)
- Install xcode cli tools
- Install git
- Clone this repo
- cd into repo, run:
    ansible-playbook -i inventory main.yml -K (you'll need to enter your sudo password)
    
### Credit where credit is due
As mentioned before, I used two of Jeff Geerling's roles:
- geerlingguy.homebrew
- geerlingguy.dotfiles

They're both available on Ansible Galaxy. They're both good - homebrew gets a ton done, and dotfiles is brilliant.
To help set that stuff up, I borrowed a bit from his Ansible role for setting up his Mac:
https://github.com/geerlingguy/mac-dev-playbook
There's a lot of stuff I didn't use from his playbook, but there are definitely a lot of great ideas.

