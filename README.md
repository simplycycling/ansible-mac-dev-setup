# ansible-mac-dev-setup
Basic setup for my Mac.

## What it does
Not much. Creates a directory structure inside of ~/Documents.

## What it will do
More. At very least, I'll set it up to download some of my git repos.

Apple is such a pain, though. There's a bunch of stuff I'll still have to do
manually.

### Requirements
- Ansible
- Git

There will certainly be more requirements, as this progresses.

### Run
Pretty simple:

- Install Ansible, via pip
- Install git
- Clone this repo
- cd into repo, run:
    ansible-playbook -i inventory main.yml

