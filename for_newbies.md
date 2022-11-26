## learn about SSH
______
+ create a key pair on your private computer
```
ssh-keygen
```
Next you after you choose directory to save your keys you should see this:
```
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /root/.ssh/id_rsa
Your public key has been saved in /root/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:NYzzfXL/WN0f1exs0uxcJuRDPUeZ3BrbsUFKos7Azy0 root@vm3766978
The key's randomart image is:
+---[RSA 3072]----+
|           . . . |
|      .  o. o + +|
|       oo.+  ..*o|
|        *+.o   O=|
|        SE..o BoB|
|          .  B **|
|              =.&|
|               @=|
|              . =|
+----[SHA256]-----+

```
+ See your public key
```
cat ~/.ssh/id_rsa.pub
```
+ Enter output to server
```
echo your_pub_key >> ~/.ssh/authorized_keys
```
+ Set permissions
```
chmod -R go= ~/.ssh
```
And now you can connect to server where you drop your pub_key, I repeat you must make ssh_keys on server from there you need to open ssh tunnel to server where you drop yoour pub_key.

### Ok, next it is create User without root permissions
____
+ add user(username choose yours)
```
adduser username
```
+ add group for user(you must choose everything, but i choose sudo) 
```
usermod -aG sudo username
```
+ set directory for your pub_key
```
cd /home/username
mkdir .ssh
nano .ssh/authorized_keys
```
+ connect to your user 
```
ssh username@78.47.166.77
```
### Set authentication and root login
____
Login to your server
```
sudo nano /etc/ssh/sshd_config
```
Those parameters should look like this:
```
PermitRootLogin no
PasswordAuthentication no
```
To actually activate these changes, we need to restart the sshd service:
```
sudo systemctl restart ssh
```
## SET UFW
Start by checking the status of ufw.
```
sudo ufw status
```
Sets the default to allow outgoing connections, deny all incoming except ssh and 26656(Change if you don’t use standard port). Limit SSH login attempts
```
sudo ufw default allow outgoing
sudo ufw default deny incoming
sudo ufw allow ssh/tcp
sudo ufw limit ssh/tcp
sudo ufw allow 26656,26660/tcp
sudo ufw enable
```
Congratulation!  You can feel more secure from now on.
