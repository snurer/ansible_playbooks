# Ansible Playbook Exercies

This repository includes simple ansible playbooks to exercise modules and commands.  

## Automation

Use these playbooks to automate the following actions for Centos7:

## Install and start Apache

```bash
yum install httpd -y
systemctl enable httpd
systemctl start apache
```

## Copy file from /etc/passwd to /tmp/copy_passwd

```
cp /etc/passwd /tmp/copy_passwd
```

## Create a directory under /tmp

```
mkdir /tmp/test-ansible
```

## Install and Start yum-cron

```
yum install yum-cron -y
systemctl enable yum-cron
systemctl start yum-cron
```

## Ensure NTP is installed and running

```
yum install ntp -y
systemctl enable ntpd
systemctl restart ntpd
```

Feel free to clone and work on the playbooks.