# steps to remote access using tailscale
***note:- step 1,2,3 to be done on both machines host and client***

## 1. install curl on both machine

```bash
sudo apt install curl
```

## 2. install tailscales:- copy and paste this link 

```bash
curl -fsSL https://tailscale.com/install.sh | sh
```

## 3. start the tailscale 

```bash
sudo tailscale up
```

* it will ask to visit a link to verify mail

* right click on the link and select open link

* then login via gmail

* mail should be same for both remote and server

## 4. check the ip of the tailscale vpn on host server
```bash
tailscale ip -4 
```
## check if tailscale is on 
```bash
tailscale status
```

***installation is done***

## 5. open terminal on client system and type this
```bash
ssh <username@IP>
```
***username is from host machine what u hav created and ip of the host machine from above `tailscale ip -4 ` output***

* click yes

* enter the login password of the host server

***all done u are now in host server***


*replace username and ip with ur host machine username and ip*


## P.S. u can also download tailscale android app in ur mobile to check weather servers are online or not


# transfer files between host and client server
## using sftp protocol (secure file transfer protocol)
```bash
sftp <username@ip>
```
*a prompt shell is opened named as sftp*

## basic commands inside sftp prompt
- ***for host machine***
  - `ls` to list out the items in current directory
  - `pwd` to check present working directory
  - `cd <directory> ` to change the directory
  - `exit` to exit sftp session
- ***for uploading files to host machine***
  - `put <filename>` to upload the file in host machine from remote machine
  - `mput <filename>` to upload multiple files in host machine from remote machine
- ***for downloading files from host machine***
  - `get <filename> ` to download the file from the host machine to remote machine
  - `mget <filename> ` to download the multiple files from the host machine to remote machine
 
## for larger files use rsync
### for downloading host pc file to client machine
- `rsync -avz source destination`
  - `-a` preserves permissions
  - `-v` verbose mode :- show details
  - `-z` compress data during transfer
- example
  - ` rsync -avz <username@IP>:/home/ubuntu/Downloads/viv.txt ~/Downloads/`
      
### for uploading local client files to host pc
- `rsync -avz destination source`
- example
  - `rsync -avz ~/Downloads/viv2.txt <username@IP>:/home/ubuntu/Downloads/ `

### check the status of the tailscale 
```bash
sudo systemctl status tailscaled
```

### to restart the tailscale 
```bash
sudo systemctl restart tailscale
```
### to update the certificates and openssl
```bash
sudo apt update
sudo apt install --reinstall ca-certificates
sudo apt install openssl curl
```

