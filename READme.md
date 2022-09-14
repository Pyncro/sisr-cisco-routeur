# Internet routeur


Objectif : La mission qui vous est confiée concerne la maison d’édition du projet : « Mise en place de services réseau et web ».

* Il s’agit de mettre en place un accès gratuit à Internet via une borne WiFi placée dans la zone d’accueil du public.

* Les utilisateurs devront créer un compte afin de s’authentifier et permettre l’accès à Internet. Les logs de connexion devront être enregistrés.




Règles a respecter: Une borne Cisco est mise à disposition.Elle doit être alimentée **uniquement via PoE**.


Routeur cisco
![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/SpoxSnqVZ-clipboard.jpeg)

Missions :
1. Mettre en place un réseau WiFi sur un LAN existant.
2. Un portail captif permettra de s’identifier et/ou de créer un compte pour accéder à Internet.
3. La création de compte devra à minima demander un nom, un prénom et une adresse de courriel.
4. Les logs de connexion devront être enregistrés et comporter à minima, la date, l’horaire et la durée de chaque connexion ainsi que les sites visités.
5. Le portail captif devra permettre l’information des utilisateurs à propos de la collecte de leurs données et de son but, ainsi que recueillir leur accord pour cette collecte.


# 1.Branchement
* Branche la cable console de la port Cisco au porte VGI du PC
* Alimenter un switch de cisco
* Branche un cable ethernet du port Cisco routeur dans un port switch


# 2.Configuration de base
mot de passe du routeur : ``` Ciso```

[config.txt]()

Configurer Telnet sur le point d'accès:

1. ``` EN  ```
2. ``` conf t ```
3. ``` line vty 0 4  ```
4. ``` password bleach  ``` 
5. ``` login  ```
6. ``` exit  ```
7. ``` enable password bleach  ```
8. ``` exit ```

Configurer le point d'accès en réseau ouvert: 
1. ``` EN  ```
2. ``` conf t ```
3. ``` dot11 ssid DARLING  ``` name the ssid
4. ``` guest-mode  ```
5. ``` authentication open ```
6. ``` exit ```
7. ``` interface dot11radio 0 ```
8. ``` ssid DARLING  ```
9. ``` no shutdown  ```
10. ```exit ```


![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/IMG_4761.PNG)

# 3.Choix d'opérateurs
Ceux-ci sont tous des opérateurs libres qui peuvent gérer le réseau du routeur.


 Sophos Xg Firewall: ![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/xgfirewall.jpeg)
 
 Pfsense:
 ![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/pfsense.jpeg)

 OPNsense:
 
 ![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/OPNsense.png)


⚠️Ils ne peuvent pas être exécutés en tant qu'application, ils doivent être installés sur un ordinateur ou une boîte virtuelle pour fonctionner comme une machine à part.


# 4.Installing OPNsense


Pour ce tutoriel, nous allons utiliser OPNsense sur la machine virtuelle. Virtual Box.
https://opnsense.org/download/

![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/view.PNG)

login: root
password: opnsense

veuillez noter que le clavier par défaut dans l'opérateur est anglais (QWERTY)

![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/qwerty%20Petite.jpeg)

lorsque vous arrivez au menu, -

![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/h1.PNG)

-Entrer ces commandes pour l'interface 1:


>n 
>
>n
> 
>em0
>
>em1
>
>(press enter)

Après avoir implémenté avec succès vos ports, appliquez une adresse IP de votre choix.

![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/lanwan.PNG)
Pour l'interface 2:

>
>1
>
>n
>
>192.168.8.27
>
>16
>
>n
>
>n
>
>(enter nothing
>
>n


# 4.Partie client
Après avoir entré l'adresse IP fournie par Opensense, vous serez invité à entrer votre Username et mot de passe:

Username: root

Password: opnsense

![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/webguilog.png)


Après votre connexion,vous aurrez accès à tous les paramètres et tous les appareils connectés auront un accès Wi-Fi.
![images](https://github.com/Pyncro/sisr-cisco-routeur/blob/main/blob/main/webgui.png)
◊le projet se termine ici, to be continued.

✅ WiFi access

❌ Portail captif

❌ logs

❌ Collècte des données


# Da Rulez

https://www.lenetexpert.fr/mise-a-disposition-dun-acces-internet-au-public-quelles-precautions/ 



