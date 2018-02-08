# Tâches réalisées

* Réinstallation de pfSense avec la version 2.4.2

* Reconfiguration du pfSense
 
* Mise en place de l'OSPF

* Mise en place d'openVPN client-to-site

* Mise en place du VPN site-to-site # AFAIRE !

* Debuggage

# Problèmes rencontrés (énnoncé du problème + solution)

## Problème au niveau de la version du pfSense et impossibilité d'installer le package Quagga OSPF

La version du pfSense installée par la team deployment était dépassée et l'update ne passait pas (elle n'allait pas jusqu'au bout). Nous avons donc téléchargé une version de pfSense plus récente pour pouvoir installer le package Quagga et mettre en place l'OSPF.

## openVPN

## Problème au niveau d'une règles du firewall

Ajout de règles : 

* 

Ajout des logs au niveau des règles du firewall pour le LAN

# Motivations des technologies/infrastructures utilisées

# Remarques éventuelles

# Sources

<https://www.cyberciti.biz/faq/freebsd-setup-default-routing-with-route-command/netstat-freebsd-routing-table/>

<https://www.sparklabs.com/support/kb/article/setting-up-an-openvpn-server-with-pfsense-and-viscosity/>

<https://doc.pfsense.org>

<https://www.freebsd.org>
