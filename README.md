Repo for exercise "8.4 Работа с Roles"; Ansible roles Playbook
---
## Репозиторий Playbook для выпонения ДЗ "8.4 Работа с Roles" - Захаров Сергей Николаевич

Приложены файлы:
* Файл `site.yml` перечисляет а также задает порядок выполнения ролей в плейбуке
```yml
---
- name: Assert elasticrole
  hosts: all
  roles:
    - elasticsearch_roles
    - kibana_roles
    - filebeat_roles              
```

* Файл `requirements.yml` позволяет с помощью команды `ansible-galaxy` загрузить и установить директории с файлами для ролей плейбука
```yml
---
- src: git@github.com:zakharovnpa/elasticsearch_roles.git
  scm: git
  version: "v1.0.0"
  name: elasticsearch_roles
- src: git@github.com:zakharovnpa/kibana_roles.git
  scm: git
  version: "v1.0.0"
  name: kibana_roles
- src: git@github.com:zakharovnpa/filebeat_roles.git
  scm: git
  version: "v1.0.0"
  name: filebeat_roles
```
