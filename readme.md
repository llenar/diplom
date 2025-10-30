# Задача

Ключевая задача — разработать отказоустойчивую инфраструктуру для сайта, включающую мониторинг, сбор логов и резервное копирование основных данных. 
Инфраструктура должна размещаться в Yandex Cloud и отвечать минимальным стандартам безопасности: запрещается выкладывать токен от облака в git. 
Используйте [инструкцию](https://cloud.yandex.ru/docs/tutorials/infrastructure-management/terraform-quickstart#get-credentials).

# [Полное задание к дипломной работе:](https://github.com/netology-code/sys-diplom/tree/diplom-zabbix)

# [Nginx](http://158.160.189.220)

# [Zabbix](http://89.169.189.22/zabbix/) (Логин: Admin / Пароль: zabbix)

# [ElasticSearch](http://158.160.23.169:5601)


# Выполнение работы
# Terraform
Скачиваем последней версии Terraform из [зеркала](https://hashicorp-releases.yandexcloud.net/terraform) Яндекс.

Поднимаем инфраструктуру в Yandex Cloud используя terraform.

Указываем token id, cloud id и folder id через задание переменных текущего сеанса в консоли подставляя свои id в команды.

```
export YC_TOKEN=
export YC_CLOUD_ID=
export YC_FOLDER_ID=
```
Перед началом применения нашей конфигурации необходимо инициализировать провайдера и установить плагин AWS. Это можно сделать с помощью команды:

```
terraform init
```
<img width="754" height="214" alt="terraform init" src="https://github.com/user-attachments/assets/004751bf-be01-4764-9f47-bd4f85b7e936" />



Далее проверяем правильность конфигурации командой terraform plan.
```
terraform plan
```
Запускаем процесс поднятия инфраструктуры командой terraform apply.
```
terraform apply
```

<img width="682" height="588" alt="terraform apply" src="https://github.com/user-attachments/assets/3691a026-936f-46f0-8843-c107d7785dba" />

<img width="1280" height="371" alt="vm" src="https://github.com/user-attachments/assets/4e6a360c-d0c4-4f95-b8c8-15382722465a" />

# Yandex Cloud

### Выполнение Target Group

<img width="1188" height="604" alt="image" src="https://github.com/user-attachments/assets/08825197-e1b5-451d-a5b7-5b6b16eb4f3c" />

### Выполнение Backend

<img width="1258" height="593" alt="image" src="https://github.com/user-attachments/assets/8c31fbad-64bf-49cc-a185-b0b06c33e5a3" />

Выполнение http-router

<img width="1155" height="605" alt="image" src="https://github.com/user-attachments/assets/7778c3f9-190a-443d-8a09-f127eff86598" />


Выполнение balancer

<img width="1206" height="726" alt="image" src="https://github.com/user-attachments/assets/ad63c343-8a4b-46c4-82c1-55c09387f7a2" />



# Ansible

Устанавливаем Ansible
```
apt install ansible
```

<img width="888" height="326" alt="ansible" src="https://github.com/user-attachments/assets/6b6c1917-1d64-459f-85f9-151980638965" />

# Установка [Nginx](http://158.160.189.220)

<img width="1011" height="361" alt="nginxyml" src="https://github.com/user-attachments/assets/8dbc1177-768c-454e-980f-8e5348a56214" />

### Протестируйте сайт curl -v 158.160.189.220:80

<img width="785" height="543" alt="image" src="https://github.com/user-attachments/assets/03070dc3-aac6-4d62-b9fe-9ddc21a5f16e" />


<img width="709" height="515" alt="nginx html" src="https://github.com/user-attachments/assets/736fc33a-1a0b-4d9b-81d0-b06e8f5c5795" />

# [Zabbix](http://89.169.189.22/zabbix/) (Логин: Admin / Пароль: zabbix)

### Установка Zabbix Server

<img width="997" height="582" alt="zabbix server" src="https://github.com/user-attachments/assets/bd5cbb44-b214-40b6-b1e6-f42042d92684" />

<img width="1635" height="812" alt="zabbix login" src="https://github.com/user-attachments/assets/81ee1029-4acd-48f1-87a3-8b32767abb62" />

### Установка Zabbix-agent

<img width="1119" height="419" alt="zabbix agent" src="https://github.com/user-attachments/assets/777b798c-faa5-4f9e-aced-da9c6829a537" />

### Проверка статуса Zabbix-agent

<img width="1147" height="587" alt="zabbix agent status" src="https://github.com/user-attachments/assets/664f4e14-bec0-4241-b42b-010756ece6f0" />

### Добавление Zabbix-agent в Zabbix-server
<img width="1696" height="560" alt="ZabbixServerHost" src="https://github.com/user-attachments/assets/b30c353a-26e3-4f16-9836-faabcfb90d1a" />

<img width="1854" height="907" alt="zabbixServer dashboard" src="https://github.com/user-attachments/assets/eee79a85-e1e8-41c2-8288-fcd1637b84bf" />

# Установка ElasticSearch

<img width="1259" height="361" alt="elactic" src="https://github.com/user-attachments/assets/74ea1568-f247-4e95-b4b1-b5fd0a65a04d" />

### Проверка статуса ElasticSearch

<img width="1277" height="513" alt="elastic status" src="https://github.com/user-attachments/assets/50f9f136-5194-48a9-9a96-90d28f93e109" />

# Установка Kibana

<img width="1138" height="326" alt="kibana" src="https://github.com/user-attachments/assets/41ea71fd-54da-4214-b6c5-c71573a82ae6" />

### Проверка статуса Kibana
<img width="1274" height="256" alt="kibana status" src="https://github.com/user-attachments/assets/37a14b2a-ffef-4c94-9967-7d4454d90ed5" />

### Проверка логов Kibana
<img width="1273" height="349" alt="kibana log" src="https://github.com/user-attachments/assets/547afd13-c0f9-458a-baca-a5344d7308dc" />

<img width="1870" height="978" alt="kibana site" src="https://github.com/user-attachments/assets/1123442f-4f7d-461e-b8df-ba7aaacd9cd3" />

# Установка Filebeat

<img width="1280" height="414" alt="filebeat" src="https://github.com/user-attachments/assets/4aad47d0-e361-4194-8a58-fc5cdba3f32d" />

### Проверка статуса Filebeat
<img width="1522" height="276" alt="web-2 filebeat status" src="https://github.com/user-attachments/assets/85584fdf-b045-4782-9b86-dbf6a0b9fbfd" />

### Проверка логов Filebeat
<img width="1873" height="982" alt="filebeat site" src="https://github.com/user-attachments/assets/3a9dc700-996d-42af-bbf2-89a0a26ed8ce" />
