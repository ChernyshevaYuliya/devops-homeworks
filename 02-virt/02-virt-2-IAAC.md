# Домашнее задание Применение принципов IaaC в работе с виртуальными машинами

## Задача 1

### Опишите основные преимущества применения на практике IaaC-паттернов.

Ускорение производства и вывод продукта на рынок
Стабильность среды и устранение дрейфа конфигурации
Быстрая и эффективная разработка
 

### Какой из принципов IaaC является основополагающим?
Основной принцип это идемпотентность -
это свойство объекта или операции, при повторном выполнении которой мы получаем результат идентичный предыдущему и всем последующим выполнениям

## Задача 2

### Чем Ansible выгодно отличается от других систем управление конфигурациями?

Низкий порог входа
А так же не надо ставить агенты для управления на хосты

### Какой, на ваш взгляд, метод работы систем конфигурации более надёжный — push или pull?

Push надежнее, так как исключает ситуацию, что кто-то неправильно исправил и ты это залил себе с помощью pull

## Задача 3

### Установите на личный linux-компьютер(или учебную ВМ с linux):

	>VirtualBox,
	>Vagrant, рекомендуем версию 2.3.4(в более старших версиях могут возникать проблемы интеграции с ansible)
	>Terraform версии 1.5.Х (1.6.х может вызывать проблемы с яндекс-облаком),
	>Ansible.

	VirualBox
	
	```
	Установила 6.1. версию
	```
		
	Vagrant
	
	```
	[Julia@fedora vagrantbentoubuntu]$ vagrant -v
	Vagrant 2.2.19
	```
	
	Ansible
	
	```
	```
	

	Terraform 
	```
		Почему-то не ставится черех yum. Подскажите как поставить из бинарника?
	```


## Задача 4*

Vagrant


Ansible

```
[Julia@fedora vagrantbentoubuntu]$ vagrant provision
==> server1.netology: Running provisioner: ansible...
    server1.netology: Running ansible-playbook...

PLAY [nodes] *******************************************************************

TASK [Gathering Facts] *********************************************************
ok: [server1.netology]

TASK [Create directory for ssh-keys] *******************************************
ok: [server1.netology]

TASK [Adding rsa-key in /root/.ssh/authorized_keys] ****************************
An exception occurred during task execution. To see the full traceback, use -vvv. The error was: If you are using a module and expect the file to exist on the remote, see the remote_src option
fatal: [server1.netology]: FAILED! => {"changed": false, "msg": "Could not find or access '~/.ssh/id_rsa.pub' on the Ansible Controller.\nIf you are using a module and expect the file to exist on the remote, see the remote_src option"}
...ignoring

TASK [Checking DNS] ************************************************************
changed: [server1.netology]

TASK [Installing tools] ********************************************************
ok: [server1.netology] => (item=git)
ok: [server1.netology] => (item=curl)

TASK [Installing docker] *******************************************************
changed: [server1.netology]

TASK [Add the current user to docker group] ************************************
changed: [server1.netology]

PLAY RECAP *********************************************************************
server1.netology           : ok=7    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=1   

[Julia@fedora vagrantbentoubuntu]$ vagrant ssh
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.4.0-91-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Mon 04 Mar 2024 12:59:49 PM UTC

  System load:  0.27               Users logged in:          0
  Usage of /:   13.9% of 30.88GB   IPv4 address for docker0: 172.17.0.1
  Memory usage: 22%                IPv4 address for eth0:    10.0.2.15
  Swap usage:   0%                 IPv4 address for eth1:    192.168.56.11
  Processes:    110


This system is built by the Bento project by Chef Software
More information can be found at https://github.com/chef/bento
Last login: Mon Mar  4 12:57:49 2024 from 10.0.2.2
vagrant@server1:~$ docker version
Client: Docker Engine - Community
 Version:           25.0.3
 API version:       1.44
 Go version:        go1.21.6
 Git commit:        4debf41
 Built:             Tue Feb  6 21:14:17 2024
 OS/Arch:           linux/amd64
 Context:           default

Server: Docker Engine - Community
 Engine:
  Version:          25.0.3
  API version:      1.44 (minimum version 1.24)
  Go version:       go1.21.6
  Git commit:       f417435
  Built:            Tue Feb  6 21:14:17 2024
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.6.28
  GitCommit:        ae07eda36dd25f8a1b98dfbf587313b99c0190bb
 runc:
  Version:          1.1.12
  GitCommit:        v1.1.12-0-g51d5e94
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0
vagrant@server1:~$
```



