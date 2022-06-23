# k8s-ipvs
Роль создана для подготовки ноды Kubernetes к переходу на ipvs.

# Переход на ipvs
После того как все ноды прошли процесс подготовки меняем в ConfigMap kube-proxy (namespace kube-system) параметр mode: ipvs, strictARP: true. Перегружаем все поды kube-proxy и проверяем лог
```bash
kubectl logs [kube-proxy pod] | grep "Using ipvs Proxier"
```

**Поддерживает**:  
Debian 18.04+  
**Тестирование**: 
Для тестирования используются yamllint, ansible-lint, vagrant.
Команда для запуска тестов.
```bash
molecule test
```

Если запускаете первый раз: 
- установите molecule и yamllint
- python3 -m pip install molecule
- python3 -m pip install python-vagrant

Подключение роли через ansible-galaxy
---

Пример использования
----------------

Вы можете подключить роль к плейбуку вот так:

```yaml

  hosts: all
  tasks:
    - name: "Include k8s-ipvs"
      include_role:
        name: "k8s-ipvs"
```
