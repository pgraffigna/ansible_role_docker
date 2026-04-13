# Ansible Role Docker

Playbook Ansible para automatizar la instalación de Docker, Docker Compose y Portainer en entornos Linux.

Testeado con Vagrant + QEMU + Ubuntu 24.04 + Ansible 2.15.

---

## Descripción

Este repositorio contiene roles Ansible para automatizar la instalación y configuración de:
- **Docker**: Motor de contenedores
- **Docker Compose**: Herramienta para definir y ejecutar aplicaciones multi-contenedor
- **Portainer**: Interfaz gráfica para gestionar Docker

## Herramientas utilizadas

- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html) - Motor de automatización
- [Docker](https://docs.docker.com/engine/install/ubuntu/) - Plataforma de contenedores
- [Docker Compose](https://docs.docker.com/compose/install/standalone/) - Orquestación de contenedores
- [Portainer](https://docs.portainer.io/) - Gestión visual de Docker
- [Vagrant](https://developer.hashicorp.com/vagrant/install) + QEMU - Entorno de pruebas (opcional)

## Estructura del proyecto

```
ansible_role_docker/
├── main.yml                  # Playbook principal
├── inventory                 # Inventario de hosts
├── ansible.cfg               # Configuración de Ansible
├── vars_main.yml             # Variables globales
├── Vagrantfile               # Configuración de VM para pruebas
├── README.md
├── roles/
│   ├── docker/               # Rol: instalación de Docker y Docker Compose
│   │   ├── defaults/
│   │   │   └── main.yml
│   │   └── tasks/
│   │       └── main.yml
│   └── portainer/            # Rol: instalación de Portainer
│       ├── files/
│       │   └── docker-compose.yml.j2
│       └── tasks/
│           └── main.yml
└── .gitignore
```

## Despliegue en entornos Linux

### Requisitos previos

1. Instalar Ansible y la colección de Docker:
```bash
ansible-galaxy collection install community.docker
```

### Ejecución

1. Clonar el repositorio:
```bash
git clone https://github.com/pgraffigna/ansible_role_docker.git
cd ansible_role_docker
```

2. Configurar el inventario en el archivo `inventory` con las IPs de los servidores objetivo.

3. Ejecutar el playbook:
```bash
ansible-playbook main.yml
```

## Entorno de pruebas con Vagrant

Para probar en una máquina virtual con Ubuntu 22.04:

```bash
vagrant up
vagrant ssh
```

Esto despliega una VM descartable con Libvirt/QEMU para validar el funcionamiento del playbook.

---

## Dependencias

- Ansible
- Colección `community.docker`
- Vagrant (opcional, solo para pruebas)
