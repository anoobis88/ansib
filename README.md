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
* dedicated_user: "{{domain_user}}"  -- пользователь отдельно добавляющийся в realm permit, можно не определять (группа Linux Admin добавляется по-умолчанию, hardcode)


Для роли ubuntu_default_deploy:
* ntp_servers: "ntp.office.sspk.spb.ru ru.pool.ntp.org"  -- адреса ntp серверов, можно не определять (будут использованы сервера ru.pool.ntp.org)


Для роли ubuntu_zabbix_agent2:
* zabbix_server: rover-zbx.infra.adc.spb -- адрес zabbix сервера


Для роли ubuntu_distribute_ca:
* rootca_path -- место публикации сертификата корневого ЦС
