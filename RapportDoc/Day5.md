## pfsense

pfsense 2.4.2 sur une VM de CPU:1Ghz et RAM:1Go

## zones

Trois zones ont été créées:
    
1) WAN, directement connecté à internet
2) DMZ, directement connecté à la DMZ (192.168.40.0/24)
3) LAN, directement connecté au réseau "Core-to-Distrib" (172.16.0.0/29) et derrière lequel se trouve les différents LAN de la User-Zone (voir Alias:All_UZ)

![](https://cdn.discordapp.com/attachments/409990901511880704/411454573308280832/unknown.png)

## alias

Dans pfsense, il y a moyen de donner des noms à des IPs ou des réseaux, plusieurs IPs/Réseaux peuvent partager le même alias. À cette manière, tous les LAN de la User-Zone sont enregistrés derrière l'alias "All_UZ".

![](https://cdn.discordapp.com/attachments/409990901511880704/411454738421383169/unknown.png)

## nat

Nous avons de la NAT en Port-forward pour permettre l'extérieur (internet) d'accéder aux services de la DMZ. Des règles de NAT en sortie (UZ/LAN/DMZ vers WAN) permet aux réseaux internes d'avoir leur ip privée nat et ainsi accéder à l'extérieur.

![](https://cdn.discordapp.com/attachments/409990901511880704/411454738421383169/unknown.png)

![](https://media.discordapp.net/attachments/409990901511880704/411455094916120576/unknown.png)

## règles

1) Autoriser les réseaux UZ/LAN/DMZ à sortir sur internet
2) Autoriser le traffic de la DMZ vers la machine AD pour LDAP
2) Interdire l'accès à la UZ/LAN depuis les autres réseaux
3) Interdire l'accès à la DMZ depuis internet sauf exceptions (voir nat)

![](https://media.discordapp.net/attachments/409990901511880704/411454851936026634/unknown.png)

## vpn client-to-site

Creation d'un CA qui nous fournit un certificat auto signe, qui est ensuite utilise avec un serveur OPENVPN pour que les membres puissent se connecter a distance de maniere securisee, afin d'acceder au reseau local de notre entreprise 

![](https://media.discordapp.net/attachments/409990901511880704/411455379135004672/unknown.png)
![](https://cdn.discordapp.com/attachments/409990901511880704/411455311275360267/unknown.png)

## vpn site-to-site

Configuration d'un vpn site to site en utlisant openVPN sur pfSense. La configuration se déroule en plusieurs phases. 
Tous d'abord il faut rajouter une authorité de certification dans l'onglet System > Certificate Manager > CAs qui sera la même que sur le site de Kyoto, à savoir Kyoto_CA_SB. 
Ensuite, il faut rajouter le certificat ainsi que sa clé privée dans l'onglet System > Certificate Manager > Certificates (Kyoto SB). 
Il ne faudra pas oublier de de créer un CRL dans l'onglet System > Certificate Manager > Certificate Revocation.

![](https://cdn.discordapp.com/attachments/409990901511880704/411458120230109185/Cpt1.PNG)
![](https://cdn.discordapp.com/attachments/409990901511880704/411458135375740928/cpt2.PNG)
![](https://cdn.discordapp.com/attachments/409990901511880704/411458305005715456/Cpt3.PNG)


## OSFP

OSPF a été configuré grace au paquet quagga sur pfsense

![](https://cdn.discordapp.com/attachments/409990901511880704/411456247649533952/unknown.png)

## utilisateurs

pour gérer le pfsense et avoir accès au VPN client-to-site nous avons créé des utilisateurs, Chuck possède un certificat qui lui permet de se connecter au vpn.
![](https://cdn.discordapp.com/attachments/409990901511880704/411455987623395337/unknown.png)
