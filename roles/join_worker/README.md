JOIN_WORKER
=========

Роль разработана для автоматизации добавления Worker ноды в кластер.
Для выполнения роли должны быть установлены kubelet, kubeadm, kubectl.
Поддерживаемые OS: Ubuntu 16.04+


Пример использования
----------------

Вы можете подключить роль к плейбуку вот так:

    - hosts: all
      tasks:
        - include_role:
            name: join_worker
          tags:
            - join_worker
