Для работы с ролями требуются следующие переменные (deploy.yml можно рассматривать как пример): 

<br>

Общие: 
* domain: office.sspk.spb.ru  -- домен, обязательная переменная
* proxy_address -- адрес прокси, можно не определять


Для доступа к серверу:
* ansible_become: True
* ansible_become_method: sudo
* ansible_user
* ansible_password
* ansible_become_password


Для ввода в домен: 

* domain_user
* domain_pass
* dedicated_user: "{{domain_user}}"  -- пользователь отдельно добавляющийся в realm permit и sudoers, можно не определять
* admins_group  -- группа добавляющаяся в realm permit и sudoers

Для роли ubuntu_default_deploy:
* ntp_servers: "ntp.office.sspk.spb.ru ru.pool.ntp.org"  -- адреса ntp серверов, можно не определять (будут использованы сервера ru.pool.ntp.org)


Для роли ubuntu_zabbix_agent2:
* zabbix_server: rover-zbx.infra.adc.spb -- адрес zabbix сервера
* zabbix_version -- версия zabbix, по умолчанию - 5.0


Для роли ubuntu_distribute_ca:
* rootca_path -- место публикации сертификата корневого ЦС

Для роли ubuntu_docker:
* docker_compose_version -- версия docker-compose (только v1), по умолчанию - 1.29.2
