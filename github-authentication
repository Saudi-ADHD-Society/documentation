# Documentation

## Github command line authentication
To access the Saudi ADHD Society's private Github repositories from the command line, you have several options, depending on whether you prefer to use Github CLI (gh) or prefer to stick with native git, as well as depending on whether you mind authenticating every time you use it or prefer to cache your credentials securely.

### A. Using Github CLI (easy way)
This method uses the easy gh command line tool, and will prompt you to sign in through your web browser using a code every session. This is not going to work if you don't have a GUI.
1. First we install Github CLI: 
```
sudo apt update && sudo apt upgrade -y

sudo apt install gh -y
```
2. Authenticate:
```
gh auth login
```
Select: github.com, HTTPS, Y, Login with a web browser.
Copy the code you are given (right-click with mouse, not ctrl-c).
3. Usage:
```
gh repo clone https://github.com/saudi-adhd-society/REPO-NAME.git
```
Again, you will need to authenticate every time.

### B. Using Github CLI (intermediate way)
This was is like A but, once you have your personal access token, can be done entirely from the command line.
1. First we install Github CLI: 
```
sudo apt update && sudo apt upgrade -y

sudo apt install gh -y
```
2. Create a new <a href="https://github.com/settings/tokens" target="_blank">personal access token</a>, selecting _repo_ and and all the checkboxes under `repo` (5 of them), as well as _read:org_ which is under _admin:org_. Name your token _ADHD GH_ or anything memorable to you. Set the expiration date to 6 months, and set yourself a reminder somewhere to renew it on that date.
3. Authenticate:
```
gh auth login
```
Select: github.com, HTTPS, Y, Paste an authentication token.
Paste your personal access token (right-click with mouse, not ctrl-v).
4. Usage:
```
gh repo clone https://github.com/saudi-adhd-society/REPO-NAME.git
```
It should authenticate automatically, but you will need to do this each time.

### C. Using Git (easy way)
This way will allow you to use native git when you have 2FA enabled by making use of Github CLI.
1. Follow steps 1-3 from B above.
2. Configure git to use GitHub CLI as a credential helper:
```
gh auth setup-git
```
3. Usage:
```
git clone https://github.com/saudi-adhd-society/REPO-NAME.git
```
It should authenticate automatically, but you will need to authenticate Github CLI each time.

### C. Using Git (intermediate way)
This way allows you to use git by itself without having to install Github CLI, but still requires you to enter your personal access token for every session.
1. Create a new personal <a href="https://github.com/settings/tokens" target="_blank">access token</a>, selecting _repo_ and and all the checkboxes under `repo` (5 of them), as well as _read:org_ which is under _admin:org_. You can name your token _ADHD Git_ or anything memorable to you. Set the expiration date to 6 months, and set yourself a reminder somewhere to renew it on that date.
2. Save your access token somewhere safe.
3. Tell git your name and email:
```
git config --global user.name 'Firstname Lastname'

git config --global user.email 'name@adhd.org.sa'
```
4. Usage:
```
git clone https://github.com/saudi-adhd-society/REPO-NAME.git
```
Enter your username when prompted.
For your password, paste your personal access token.


### D. Using Git (advanced way)
This way also uses git without making use of Github CLI and will prompt you to sign in through a pop up window using your Github username and password.
1. Install utilities to store and manage credentials:
```
sudo apt update && sudo apt upgrade -y 

sudo apt install pass gpg
```
2. Generate new GPG key (follow the prompts):
```
gpg --gen-key
```
3. Initialize credential store (replacing GPGKEY with your generated key):
```
pass init GPGKEY
```
4. Install Git Credential Manager:
```
curl -O https://github.com/GitCredentialManager/git-credential-manager/releases/download/v2.0.696/gcmcore-linux_amd64.2.0.696.deb

sudo dpkg -i gcmcore-linux_amd64.2.0.696.deb
```
5. Configure Git Credential Manager:
```
git-credential-manager-core configure
git config --global credential.credentialStore gpg
```
6. Usage:
```
git clone https://github.com/saudi-adhd-society/REPO-NAME.git
```
Enter your username and password when prompted.
It should authenticate automatically.
