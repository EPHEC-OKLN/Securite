# Tâches réalisées
On s'est concertés pour décider les technologies nécéssaires au bon fonctionnement du projet. Pour le moment on q choisis 3 technologies :

*pfSense* qui sera la veritable plaque tournante pour la sécurité de notre infra

*OpenVPN client-to-site* pour la liaison VPN client-to-site

*VPN IPSec site-to-site* pour la liaison VPN site-to-site
# Problèmes rencontrés (énnoncé du problème + solution)

# Motivations des technologies/infrastructures utilisées
pfSense

    OpenSource, portable, puissant, dispose de nombreuses fonctionnalités

OpenVPN 
    
    Portabilité crosse plateforme
    Bonne stabilité
    Possibilité d'évolution (pouvoir s'adapter à la charge)
    Installation relativement simple
    Support pour les IP dynamiques et le NAT
    Possède une interface de management pour pouvoir le contrôler à distance ou centralement.
    Sécurisé (support du X509 PKI, SSL, TLS, ...)
    ...
    
IPSEC

    techno très répendue, safe, et qu'on a apris en cours avec Schalkwijk 

    
    
# Remarques éventuelles

# Sources (Important !)

### IPSec
Infrastructure réseau base de Laurent Schalkwijk (cours de 2TI)

### pfSense
https://forum.pfsense.org/index.php?topic=76015.0

### OpenVPN avec pfSense
https://doc.pfsense.org/index.php/OpenVPN_Remote_Access_Server
https://openvpn.net/index.php/open-source/documentation/howto.html
https://forum.pfsense.org/index.php?topic=76015.0

### Pourquoi OpenVPN
https://openvpn.net/index.php/open-source/335-why-openvpn.html

