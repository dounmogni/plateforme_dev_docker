# Utilisation du script

## Étapes :

1. **Lancer une VM avec Vagrant et Podman installé**

Assurez-vous d'avoir un `Vagrantfile` configuré pour installer Podman automatiquement. Exemple minimal :

```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt update
    sudo apt install -y podman
  SHELL
end
```

Lancez la VM avec :

```bash
vagrant up
```

---

2. **Se connecter à la VM**

```bash
vagrant ssh
```

---

3. **Créer un répertoire `/srv/data/` dans la VM**

```bash
sudo mkdir -p /srv/data/
```
4. **Créer une clé ssh  dans la VM**

```bash
ssh-keygen
```
---

5. **Cloner le dépôt Git**

```bash
git clone https://github.com/dounmogni/plateforme_dev_docker.git
cd plateforme_dev_docker
```

---

6. **Lancer le script**

```bash
./new_deploy.sh
```

> 💡 Assurez-vous que le script `new_deploy.sh` est exécutable et configuré correctement pour votre environnement.
