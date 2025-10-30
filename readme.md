# Задача

Ключевая задача — разработать отказоустойчивую инфраструктуру для сайта, включающую мониторинг, сбор логов и резервное копирование основных данных. 
Инфраструктура должна размещаться в Yandex Cloud и отвечать минимальным стандартам безопасности: запрещается выкладывать токен от облака в git. 
Используйте [инструкцию](https://cloud.yandex.ru/docs/tutorials/infrastructure-management/terraform-quickstart#get-credentials).

# [Полное задание к дипломной работе:](https://github.com/netology-code/sys-diplom/tree/diplom-zabbix)

# [Nginx](http://158.160.189.220)

# [Zabbix](http://89.169.189.22/zabbix/) (Логин: Admin / Пароль: zabbix)

# [ElasticSearch](http://158.160.23.169:5601)



# Выполнение работы
# Terraform и Ansible
Скачиваем последней версии Terraform из [зеркала](https://hashicorp-releases.yandexcloud.net/terraform) Яндекс.

Поднимаем инфраструктуру в Yandex Cloud используя terraform

в целях безопасности указываем token id, cloud id и folder id через задание переменных текущего сеанса в консоли подставляя свои id в команды

```
export YC_TOKEN=
export YC_CLOUD_ID=
export YC_FOLDER_ID=
```
Далее проверяем правильность конфигурации командой terraform plan сверяем что все верно и запускаем процесс поднятия инфраструктуры командой terraform apply
<img width="682" height="588" alt="terraform apply" src="https://github.com/user-attachments/assets/3691a026-936f-46f0-8843-c107d7785dba" />


<img width="888" height="326" alt="ansible" src="https://github.com/user-attachments/assets/6b6c1917-1d64-459f-85f9-151980638965" />

