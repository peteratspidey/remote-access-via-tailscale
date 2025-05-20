# steps to remote access using tailscale
## first install curl

```bash
sudo apt install curl
```

# to install tailscales copy and paste this link 

```bash
curl -fsSL https://tailscale.com/install.sh | sh
```

## start the tailscale 

```bash
sudo tailscale up
```

*it will ask to visit a link to verify mail*

*mail should be same for both remote and server*

*right click on the link and select open link*

*then login via gmail*

*check the ip of the tailscale vpn on host server machine*
```bash
tailscale ip -4 
```


## open terminal on client system and type this
```bash
ssh <username@IP>
```
*click yes *
*enter the login password of the host server*

***all done***
