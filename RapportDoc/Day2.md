# Tâches réalisées

* Installation de pfSense
  * Création de la machine virtuelle
  * Configuration des interfaces

| Zone | Interface | Suffix Mac | Adresse IP |
| ---- | --- | --- | -- |
| WAN | EM0 | `9f` | `193.190.65.84` |
| UZ | EM1 | `a9` | `172.16.0.1` |
| DMZ | EM2 | `b3` | `192.168.40.254` |

* Configurer pfSense
  * Mettre en place les zones
  * Mise en place de la NAT

## Wan

1. Refuser tout le traffic entrant sauf exceptions
1. Autoriser le traffic http(s) (tcp/80, tcp/443) vers le reverse proxy
1. Autoriser le traffic dns (tcp/53, udp/53) vers le SOA

## DMZ

1. Autoriser le traffic vers internet
1. Interdire le traffic vers la UZ sauf exceptions
1. Autoriser le traffic LDAP (tcp/389) vers l'AD

## UZ

1. Autoriser le traffic vers Internet
1. Autoriser le traffic vers la DMZ

# Problèmes rencontrés (énnoncé du problème + solution)

## Infra

Certaines NICs du pfsense n'appartenaient pas au bon réseau, nous avons le temps de recâbler et de reconfigurer calmement les switchs physiques et virtuels.

## Interface web

L'interface web était inaccessible malgré que SSH fonctionnait. Une option avait été mal configurée "`revert http to webConfigurator`", en lisant la doc sur internet, nous avons pu corriger notre erreur et accéder à l'interface.

# Remarques

Il a été important de travailler avec les gens de l'infra pour connaitre le réseau auquel chaque nic était connecté.

# Sources

<https://doc.pfsense.org>
