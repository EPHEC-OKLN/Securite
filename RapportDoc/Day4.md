# Tâches réalisées

* Réinstallation de pfSense avec la version 2.4.2

* Reconfiguration du pfSense
 
* Mise en place de l'OSPF

* Mise en place d'openVPN client-to-site

# Mise en place du VPN site-to-site 

* Installation du package quagga-OSPF & pfSense-pkg-openvpn-client-export

* Création d'une CRL (control revocation list)

* Debuggage

# Problèmes rencontrés (énnoncé du problème + solution)

## Problème au niveau de la version du pfSense et impossibilité d'installer le package Quagga OSPF

La version du pfSense installée par la team deployment était dépassée et la mise à jour ne fonctionnait pas (freeze complet du par-feu pendant 30 minutes). Nous avons donc téléchargé et installé une version de pfSense plus récente pour pouvoir installer le package Quagga et mettre en place l'OSPF.

## openVPN

TODO

## User-zone sans accès internet

Un oubli de notre part dans les règles du par-feu a ralenti de plusieurs dizaines de minutes l'équipe chargé de l'infra réseau. Les règles en place n'autorisaient que le traffic venant du réseau "Core-to-Distrib" (172.16.0.0/29) et n'autorisait pas les réseaux relayés par les Switch L3 "User-Zone" (VLAN 10, 20, 30, 50). Une règle supplémentaire a été ajoutée pour les autoriser après que l'équipe infra ait trouvé la source du problème.

# Motivations des technologies/infrastructures utilisées

## Quagga

Nous avons choisi d'utiliser le paquet freebsd Quagga pour OSPF pour sa bonne intégration avec pfsense

# Sources

<https://www.cyberciti.biz/faq/freebsd-setup-default-routing-with-route-command/netstat-freebsd-routing-table/>

<https://www.sparklabs.com/support/kb/article/setting-up-an-openvpn-server-with-pfsense-and-viscosity/>

<https://doc.pfsense.org>

<https://www.freebsd.org>

<https://www.adrienfuret.fr/2016/08/04/pfsense-vpn-l2tpipsec/>

<https://doc.pfsense.org/index.php/VPN_Capability_IPsec#Configuring_the_VPN_Tunnel>
