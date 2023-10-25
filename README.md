# package-management-installation

## Change host-name for ubuntu on wsl:


When using WSL, you must create a configuration file to change the hostname. 
Use your editor to create a */etc/wsl.conf* file.

```
sudo vi/vim /etc/wsl.conf
```

## Once the config file opens, add the following lines:

```
[network]
hostname = <your-new-hostname>
generateHosts = false
```
- The `generateHosts = false` ensures WSL will not automatically generate a hosts file.

- This allows us to use the new hostname and overwrite the existing one. 
- Your configuration file should match the one below except for the hostname. 
- In our case, we are setting our new hostname to be <desired-hostname>.
Next, change the `/etc/hosts` file to ensure we have the same hostname for our Ubuntu. 

Run the command below.
```
sudo vi/vim /etc/hosts
```
- Once the file opens, locate every instances of the previous hostname and replace it with your new hostname. 
- In our case, we have our hostname as **DESKTOP-PTV7941** which we will replace for this case.
- Ensure you replace it with the hostname you defined in the `/etc/wsl.conf` file.
- After all the proccess up, you can restart wsl. First open your powershell or your command prompt.
```
wsl --shutdown
```
and then 
```
wsl --status
```
