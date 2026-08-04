# Windows Subsystem for Linux (WSL)

## Installation

- Open Terminal
- Install WSL → `wsl --install`
- Enable Virtual Machine → `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
- Turn Windows features on or off
- Enable `Windows Subsystem for Linux`

## Ubuntu in WSL

- Create UNIX username
- Create secure password
- Default profile → `Ubuntu`

## SSH Key

### Terminal

- Create SSH Key → `ssh-keygen -t ed25519 -C "<email@domain.com>"`
- Create passphrase
- Initialize SSH agent → `eval "$(ssh-agent -s)"`
- Add key to the SSH agent → `ssh-add ~/.ssh/id_ed25519`
- Show SSH key → `cat ~/.ssh/id_ed25519.pub`

### GitHub

- Settings → Access → SSH and GPG keys → New SSH key
- Paste all the SSH key

## Repository Flow

### Terminal

- Initialize repository → `git init`
- Verify status → `git status`
- Add file → `git add <path>`
- Configure username → `git config --global user.name "<username>"`
- Configure email → `git config --global user.email "<email@domain.com>"`
- Create commit → `git commit -m "<message>"`

### GitHub

- Your repositories → New → Repository name → Add README file → Create repository
- Copy SSH link

### Terminal

- Add repository → `git remote add origin <git@github.com:username/Repository.git>`
- Verify references → `git remote -v`
- Upload changes → `git push origin main`