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

## P.S. u can also download tailscale android app in ur mobile to check weather servers are online or not
