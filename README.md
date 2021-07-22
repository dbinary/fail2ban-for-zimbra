# Instalación y Configuración fail2ban para Zimbra 8.X

## Instalación fail2ban
En Centos 7.X o mayor ejecutar

```
# yum install epel-release -y
```

Proceder a Instalar el paquete de fail2ban

```
# yum install fail2ban -y
```


## Configuración

clonar éste repositorio

```
# git clone https://github.com/dbinary/fail2ban-for-zimbra.git
```
copiar jaula 01-zimbra.conf a /etc/fail2ban/jail.d

```
# cp -v 01-zimbra.conf /etc/fail2ban/jail.d/
```
copiar filtro zimbra.conf a /etc/fail2ban/filter.d

```
# cp -v zimbra.conf /etc/fail2ban/filter.d/

```
copiar filtro sasl.conf a /etc/fail2ban/filter.d

```
# cp -v sasl.conf /etc/fail2ban/filter.d/
```
ejemplo de fail2ban.conf

```
[Definition]
loglevel = INFO
logtarget = /var/log/fail2ban.log
syslogsocket = auto
socket = /var/run/fail2ban/fail2ban.sock
pidfile = /var/run/fail2ban/fail2ban.pid
dbfile = /var/lib/fail2ban/fail2ban.sqlite3
dbpurgeage = 86400
```
