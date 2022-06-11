# Ansible Role: Containerd

Роль устанавливает containerd.io указаной версии и hold'ит ее. Отключает SWAP и закидывает модули ядра, необходимые для нод Kubernetes.

## Role Variables

    containerd_version: 1.4.3-2
    docker_apt_repository: "deb [arch=amd64] https://download.docker.com/linux/{{ ansible_distribution | lower }} {{ ansible_distribution_release }} stable"
    docker_apt_ignore_key_error: true
    docker_apt_gpg_key: https://download.docker.com/linux/{{ ansible_distribution | lower }}/gpg

## Example Playbook

```yaml
- hosts: all
  roles:
    - containerd
```

