# ansible_role_docker

Roles para instalar docker y docker-compose en equipos con linux.

Testeado con Vagrant + qemu + ubuntu_22.04 + ansible_2.15

---

### Descripción

La idea del proyecto es automatizar vía ansible la instalación de [docker](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository) y [docker-compose](https://docs.docker.com/compose/install/standalone/) para pruebas de laboratorio, el repo cuenta con 4 roles:

1. docker
2. docker-compose
3. nginx
4. portainer

### Dependencias

* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html)
* [Vagrant](https://developer.hashicorp.com/vagrant/install) (opcional)

### Uso

```
git clone https://github.com/pgraffigna/ansible_role_docker.git
cd ansible_role_docker
ansible-playbook main.yml
```

### Extras
* Archivo de configuración (Vagrantfile) para desplegar una VM descartable con ubuntu-22.04 con libvirt como hipervisor.

### Uso Vagrant
```
vagrant up
vagrant ssh
```
