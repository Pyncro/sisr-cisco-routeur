# READme

Claxton Jordan / Vandenabeele Alan

BTS SIO1
Lycée Monge

Objectif : La mission qui vous est confiée concerne la maison d’édition du projet : « Mise en place de services réseau et web ».

* Il s’agit de mettre en place un accès gratuit à Internet via une borne WiFi placée dans la zone d’accueil du public.

* Les utilisateurs devront créer un compte afin de s’authentifier et permettre l’accès à Internet. Les logs de connexion devront être enregistrés.




 Règles a respecter: Une borne Cisco est mise à disposition de chaque binôme. Elle doit être alimentée **uniquement via PoE**.

pièces fournis:
![clipboard.png](SpoxSnqVZ-clipboard.png)


Missions :
1. Mettre en place un réseau WiFi sur un LAN existant.
2. Un portail captif permettra de s’identifier et/ou de créer un compte pour accéder à Internet.
3. La création de compte devra à minima demander un nom, un prénom et une adresse de courriel.
4. Les logs de connexion devront être enregistrés et comporter à minima, la date, l’horaire et la durée de chaque connexion ainsi que les sites visités.
5. Le portail captif devra permettre l’information des utilisateurs à propos de la collecte de leurs données et de son but, ainsi que recueillir leur accord pour cette collecte.


# 1.Branchement appareils
* Branche la cable console de la port Cisco au porte VGI du PC
* Alimenter un switch de cisco
* Branche un cable ethernet du port Cisco routeur dans un port switch


# 2.Configuration de base
mot de passe du routeur : ``` Ciso```

[config.txt]()

Configurer Telnet sur le point d'accès:

1. ``` EN  ```
2. ```  conf t ```
3. ``` line vty 0 4  ```
4. ``` password cisco  ``` (i took bleach)
5. ``` login  ```
6. ``` exit  ```
7. ``` enable password cisco  ```
8. ```  exit ```

Configurer le point d'accès en réseau ouvert: 
1. ``` EN  ```
2. ```  conf t ```
3. ``` dot11 ssid OPEN-WIFI  ``` name the ssid
4. ``` guest-mode  ```
5. ```  authentication open ```
6. ```  exit ```
7. ```  interface dot11radio 0 ```
8. ``` ssid OPEN-WIFI  ```
9. ``` no shutdown  ```
10. ```  exit ```



![clipboard.png](5yP0dbWLY-clipboard.png)
# 3.Création du portails

jkkj