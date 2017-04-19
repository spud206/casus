# README
## Casus
### Description
> In Ansible een werkende structuur uitschrijven om een Linux server op te zetten met Nginx en meerdere PHP versies. Er dienen hiermee 50 vhosts met willekeurige domeinnamen te worden aangemaakt. Een vhost kan maatwerk regels bevatten en een keuze voor PHP versie.
### Setup
- Ansible
- Vagrant
- Virtualbox
- Git
- Clone (this) git repository
- in Ansible.cfg change inventory=<inventory directory from repo>
- install private key for root
### Run
- chdir vagrant/Debian2
- vagrant up
- sudo ansible-playbook full_stack.yml

## Customize
### Description
Alle vhosts in nginx_sites hash worden op basis van de site.conf.j2 vertaald in vhost configuraties voor nginx. 
php_versions list bevat alle php versies die geinstalleerd moeten worden. php versies worden vertaald in php-{{ versie }} welke als tag wordt gebruikt om php source te downloaden. 
In de php-{{ version }}.yml in host_vars/{{ inventory-hostname }} dir kunnen evt. versie specifieke vars worden opgeslagen.
