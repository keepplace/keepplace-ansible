### Setup local environment

``` bash
brew install ansible libressl vagrand virtualbox ssh-copy-id
```

### Add your key to remote server
``` bash
ssh-copy-id ...
```


### Login and and manually install some dependenices
```bash
sudo apt-get update 
sudo apt-get install build-essential checkinstall python 
```

### Update inventory and env_vars/base.yml with your settings

### Run ansible tasks against your server
``` bash
ansible-playbook -i inventory main.yml -u root
```