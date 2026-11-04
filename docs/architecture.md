# Architecture cible — NovaCorp (laboratoire)

```text
PC Windows étudiant
└── VMware Workstation Pro (réseau NAT)
    └── VM Proxmox VE : pve01.novacorp.test | 4 vCPU / 8 Go / 80 Go
        ├── vmbr0 -> interface VMware NAT -> accès management 8006
        ├── vmbr1 -> réseau interne isolé 10.10.10.0/24
        ├── VM 100 : web01 Debian  (KVM, si nested VT compatible)
        ├── LXC 200 : app01 Debian + nginx
        ├── LXC 201 : copie restaurée de app01
        └── Template 9000 -> VM 102 srv02 via Cloud-Init
```

**Les ID sont des conventions**, à adapter s'ils sont déjà occupés. **Ne pas** affecter vmbr1 au management et ne pas mettre de passerelle supplémentaire sur son réseau isolé. Les scénarios de stockage s'effectuent dans le disque virtuel de la VM Proxmox, jamais sur le disque Windows hôte.
