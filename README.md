# Borg Backup Server

Dockerized version of Borg Backup Server based on alpine image. For more information refer to: https://www.borgbackup.org/

## Usage

```
# docker create \
  --name borgbackup \
  -p <sshport>:22 \
  -v <path to datadir>:/backups \
  -v <path-to-ssh-keys>:/home/borg/.ssh \
  paintenzero/borgserver
# docker start borgbackup
```

### Note


After creating the container you will need to start the container add your own public keys. Create _authorized_keys_ file to <path-to-ssh-keys>. Recommended content of the _authorized_keys_:
```
command="borg serve --restrict-to-repository /backups" ssh-rsa AAAA....
```
