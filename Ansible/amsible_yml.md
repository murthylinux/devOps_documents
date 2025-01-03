# Ansible Playbooks:
```
---
- name: Install and configure
  hosts: webservers
  become: yes

  tasks:
  - name: Install Apache (httpd)
  	yum:
  	  name: httpd
  	  stage: present
  - name: Install Apache (httpd)
  	service:
  	  name: httpd
  	  stage: present

```
```
# Install Nginx
---
- name: Install Nginx
  hosts: webserver
  become: yes

  tasks: 
  - name: Install Nginx
    yum: 
      name: nginx
      state: present
```


