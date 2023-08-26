>[DOC link of md formatting file](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
# Tableau Server Installation, Backup & Restoration

## 1. Download File onto the server
[Login](https://www.tableau.com/support/releases/server) and generate the Download link (.deb only):

    cd /data
    wget <PLACE LINK HERE:https://downloads.tableau.com/esdalt/2023.1.4/tableau-server-2023-1-4_amd64.deb>
    ls
---
## 2. Update, Upgrade and Install

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get -y install gdebi-core
    sudo gdebi -n tableau-server-<Downloaded_filename>_amd64.deb

---

## 3. Setup the 'tableau' user
If we have **user: tableau** already on server, Kindly skip this step.

    sudo useradd tableau -g tableau
    sudo passwd tableau

---

## 4. Ownership to directory

    sudo chown tableau:tableau /data
---
