# rules to get files transfer between host and client machine
## using SCP (secure copy protocol)
* to copy a file from remote to local
```bash
scp username@IP:/path/to/remote/file /local/path
```
* to copy a file from local to remote
```bash
scp /local/path/file username@IP:/path/to/remote/directory/
```

## 1 way
### access via rsync 
``` bash
rsync -avz user@tailscale-ip:/remote/path /local/path
```
* if u want to see the real time progress of the transfer use `--progress` flag
```bash
rsync -avz --progress user@tailscale-ip:/remote/path /local/path
```
