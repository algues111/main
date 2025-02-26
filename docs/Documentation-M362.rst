.. role:: raw-m2r(raw)
   :format:


Module 362 : Mettre en service les systèmes vocaux et vidéo complexes
=====================================================================



.. image:: https://upload.wikimedia.org/wikipedia/commons/a/a2/3CX_Logo_-_Wiki.png
   :align: right
   :height: 32px

3CX
----------

Qu'est-ce que 3CX ?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

3CX est une **solution de communications virtuelle** qui permet aux entreprises de gérer leurs appels téléphoniques, leur messagerie instantanée, leur vidéoconférence ainsi que tous les services que pourrait proposer un PBX classique, grâce à différentes installations et forfaits.

12 millions d'utilisateurs l'utilisent chaque jour, le placant donc sans souci sur le podium des leaders mondiaux de la téléphonie !

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/3cx-paccueil.png
   :align: center

----

Licences
^^^^^^^^^^^^^^^^^^^^

Pour avoir une vue d'ensemble plus concrète de ce que propose 3CX en tant que service ou système, il est important de connaître les différentes licences proposées par l'entreprise du même nom.
Le choix de la licence est une décision importante dans la solution que vous proposerez à votre client, car certaines fonctionnalités ne seront pas disponibles selon la licence choisie.

Il est donc recommandé de suivre les formations 3CX et de passer la certification gratuite disponible avec ce lien : https://portal.3cx.com/customer/certification

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/3cx-licences.png
   :align: center


.. warning:: 
   Le principal défaut de la licence FREE réside dans le fait que les MàJ ne sont pas possibles sauf si vous payez pour une upgrade après 5-6 versions env.


*Remarque : nombre de canaux int. / ext. réunis*




----

Différents types d'installation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

:raw-m2r:`<br>`

.. image:: https://imgs.search.brave.com/t5Gh4h12EKJUKsBYlQEidsH_O2SyxBPQABqSv3rnPxU/rs:fit:860:0:0/g:ce/aHR0cHM6Ly9icmFu/ZHNsb2dvcy5jb20v/d3AtY29udGVudC91/cGxvYWRzL2ltYWdl/cy9kZWJpYW4tbG9n/by5wbmc
   :align: right
   :height: 32px

Linux
~~~~~~~~~~~~~~

:raw-m2r:`<br>`

Chez 3CX, le principal avantage de leur système est leur **OS basé sur Debian** qui est **optimisé pour leur PBX virtuel.**

L'installation s'avère simple si l'on est familiarisé avec le milieu de la virtualisation sous linux.

:raw-m2r:`<u>Voici les prérequis matériels pour l'installation de 3CX sur Debian : </u>`

**Votre machine a besoin d'au moins 1 cœur de processeur dédié et de 2Go de RAM. Si vous hébergez vous-même votre machine et que votre hébergeur utilise une unité centrale partagée, vous avez besoin de 2 cœurs !**

Passez en revue les spécifications matérielles suggérées afin d'allouer du temps d'unité centrale et des ressources de mémoire vive supplémentaires en fonction des critères suivants :


* Nombre d'appels simultanés gérés par le système.
* Nombre d'utilisateurs actifs - 100 sessions actives du client Web sont plus exigeantes que 100 appels occasionnels via des téléphones IP.
* L'utilisation de l'enregistrement des appels - le système est sollicité pour le mixage audio et le stockage des fichiers.

..

   3CX peut être installé sur n'importe quel système fonctionnant sous Debian 12. Si vous souhaitez faire une installation barebone, assurez-vous que le matériel fonctionne avec Debian 12 et que le fournisseur du matériel vous aidera en cas de problème. Nous ne pouvons pas vous aider à résoudre les problèmes liés à l'installation de Debian 10 sur du matériel " barebone ".

   Ne configurez pas de réseau virtuel, d'interface VPN ou d'option TeamViewer VPN sur l'hôte 3CX.


Pour les autres prérequis liés à la virtualisation, au réseau etc... Je vous invite à vous référer à leur documentation complète disponible avec le lien ci-dessous :

**https://www.3cx.fr/docs/manuel/installation-debian-linux-ipbx/**

Voici aussi le lien pour le téléchargement de l'iso linux de 3CX :

**https://downloads-global.3cx.com/downloads/debian10iso/debian-amd64-netinst-3cx.iso**

.. image:: https://lh7-us.googleusercontent.com/dnv4yC4v_g33UFLJcYGuXi3QmSsWkMeu_Iir9wF8EmmyCZTKqkXkgFiIYQfmL_WMYjxXJoSGsAFnsz2kkg3GRqR_GmU9pxCSW8YbKFS63S5mnrrJkDrqopNUzxvNp9oaYDly7gzf0vpt7Ug
   :align: center


:raw-m2r:`<br>`

*Premier lancement de l'iso de 3CX*

Choisissez ce que vous préférez en fonction de vos habitudes d'installation de distributions Linux.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/3cx-linux.png
    :align: center
    :height: 470px


:raw-m2r:`<br>`

*Attendre que l'installation s'effectue et choisir les options correspondantes à vos besoins (FQDN...)*

----

:raw-m2r:`<br>`

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/3cx-CLI.png
    :align: center

:raw-m2r:`<br>`

Lorsque votre VM aura redémarré et que vous aurez cette interface de disponible, je vous conseille d'installer 3CX avec votre navigateur web comme support visuel.

:raw-m2r:`<br>`

..

   L'installation en CLI étant réservée aux utilisateurs aguerris de 3CX, je ne le vous recommanderais seulement si vous nécessitez de paramètres spéciaux/avancés.


:raw-m2r:`<br>`
:raw-m2r:`<br>`

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/conf-3cx1.png

:raw-m2r:`<u>Ici, 3 options sont disponibles : </u>`


* *Upload a new configuration file create on 3CX*
* *Restore a backup*
* *Install without config file (legacy, not recommended)*

Nous utiliserons la 3ème option pour cette installation.

:raw-m2r:`<br>`

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/conf-3cx2.png

:raw-m2r:`<br>`

Cette étape nous permet de configurer les différents ports utilisés par les services de 3CX.

..

   Si seulement votre instance 3CX tourne sur votre VM, je vous conseille de laiser les ports par défaut proposer par le wizard d'installation.

   Dans le cas contraire, utilisez des ports qui ne sont pas utilisés par d'autres services!



.. tip::
   Pour manager vos systèmes ainsi que vos licences 3CX, vous pouvez accéder à l'url ci-dessous : https://portal.3cx.com/customer/systems/

:raw-m2r:`<br>`

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/licence.png

:raw-m2r:`<br>`


----

.. image:: https://upload.wikimedia.org/wikipedia/commons/2/2a/Windows_Logo_2012-2015.png
    :align: right
    :height: 32px


Windows
~~~~~~~

Il est aussi possible d'héberger votre PBX 3CX sous l'OS Windows.


.. warning::

   Cependant, cela nécessitera des connaissances avancées, car vous vous retrouverez face à des contraintes plus récurrentes que sur Linux.

   Par exemple, lors des MàJ Windows, il est possible que l'état du Firewall Windows Defender se réinitialise et donc efface les règles de traffics entrants/sortants permettant au 3CX et aux téléphones liés de fonctionner correctement.

De plus, Windows est par défaut plus vulnérable que Linux, de par son architecture et car il est l'OS le plus répandu !

Lorsque l'installation est terminée, on peut remarquer dans le fichier hosts de notre OS Windows que 3CX a rajouté cette ligne :

  ``127.0.0.1 arthur.3cx.ch``

Cette dernière permet, lorsque nous tapons l'URL en question dans notre navigateur, que notre ordinateur pointe vers notre adresse loopback.

Attention, cela se produit seulement si vous précisez que vous n'avez pas votre propre configuration DNS pour le serveur 3CX.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/3cx-hosts.png


.. seealso::
   Un manuel complet du PBX 3CX est disponible sur ce lien :
   https://www.3cx.fr/docs/manuel/avance/


----

Interface
^^^^^^^^^^^^^^^^^^^^^^

Web interface (admin)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Après avoir terminé la configuration du 3CX, vous pourrez accéder à l'URL correspondante à l'installation de votre 3CX (\ *ici arthur.3cx.ch:5001*\ ), et ainsi vous logger avec les identifiants administrateur précédemment choisis.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/3cx-login.png

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/dashboard.png


:raw-m2r:`<br>`

Après s'être identifiés, nous débarquons sur l'interface admin.

Pour avoir une ligne entrante et sortante opérationnelle, il est nécessaire de configurer un trunk SIP.
3CX prend en charge plusieurs opérateurs en Suisse, notamment sipcall...

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/sip-trunk.png

:raw-m2r:`<br>`


Ci-dessus, nos 2 trunks sont déjà configurés. Nous pouvons cependant plonger dans leur configuration afin de comprendre les paramètres incontournables :

   - Nom du trunk
   - Nom ou IP du registrar
   - Proxy sortant
   - Nombre d'appels simultanés
   - Type d'authentification
   - ID d'authentification (user ID)
   - Mot de passe
   - Routage (que l'on verra plus loin dans la documentation)


.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/telco1a.png


.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/telco1b.png




Web Interface (client)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Il est possible d'accéder à l'interface webclient et ainsi d'avoir des fonctionnalités UCC proposées par 3CX :

Cela inclut :

   - Chats
   - Chats de groupe
   - Meetings (avec caméra, micro, partage d'écran/app...)
   - Historique des appels
   - Cahier de contacts
   - Boîte de messagerie vocale

Tout est accessible depuis le menu latérale de gauche :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/webclient.png

:raw-m2r:`<br>`

Chats & Chats de groupe
**************************

L'interface des chats est assez rudimentaire mais efficace. 
Elle permet de partager des fichiers, faire des listes à puces...

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/webclient-chat.png


:raw-m2r:`<br>`


Meetings
********************

3CX permet notamment de faire des conférences en ligne, grâce à une interface intuitive et pratique.
Pour pouvoir profiter pleinement de toutes ces fonctionnalités, il est nécessaire d'accorder l'accès au micro et webcam à votre navigateur web.

Durant ces conférences, il est possible de partager son écran et de donner la main à un des collaborateurs présents dans la réunion.
Partager des fichiers et écrire dans un chat dédié est aussi possible !

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/webclient-meeting.png

:raw-m2r:`<br>`

Historique des appels
******************************

Affichage de l'historique des appels entrants et sortants passés.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/callhistory.png


:raw-m2r:`<br>`

Cahier de contacts
******************************


Un cahier des contacts existe, donnant la possibilité d'enregistrer des fiches contacts.
Pour aller plus loin, une intégration LDAP est même possible pour télécharger l'annuaire depuis un serveur LDAP. (disponible pour la licence 3CX Pro)

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/phonebook.png


:raw-m2r:`<br>`

Boîte de messagerie vocale
******************************

Comme son nom l'indique, la boîte de messagerie vocale permet d'écouter les messages vocaux laisser par les appelants.

Réseau & Téléphonie
----------------------

Généralités Réseau
^^^^^^^^^^^^^^^^^^^^^^^^

DECT : Digital Enhanced Cordless Telecommunications
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La tehnologie DECT est un standard de communication téléphonique sans-fil.

Ses caractéristiques sont les suivantes :

   - Longue portée (jusqu'à 50 m à l'intérieur, jusqu'à 300 m à l'extérieur)
   - Haut niveau de sécurité contre les interceptions
   - Très bon rendement énergétique
   - Gamme de fréquences distincte qui ne dépend pas du WiFi
   - Meilleure qualité sonore qu'avec les normes précédentes
   - Application polyvalente
   - Possibilité d'utiliser plusieurs combinés en même temps
   - Appels internes gratuits
   - Les combinés peuvent être utilisés sur plusieurs stations de base
   - Les combinés multi-fournisseurs peuvent être utilisés sur les stations de base
   - Changement automatique de station de base (handover)


.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/dect-yealink.png
   :height: 300px


:raw-m2r:`<br>`

**Bande de fréquence :** de 1880 à 1920MHz

- Divisé en 2 plages distinctes :
   - 1880-1900 : émission
   - 1900-1920 : réception

- Chaque plage contient 12 canaux
- 8 canaux pour la communication
- 4 canaux pour la signalisation

- TDM dans chaque canal permettant 10 personnes par canal, ce qui revient à 80 communications en simultanées maximum.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/bande-dect.png


:raw-m2r:`<br>`

**Différence DECT VS SIP-DECT**


Gestion des canaux : 

DECT : Central téléphonique agissant en tant qu'OMM (Office manager mobile) et gèrant la partie sans-fil via un protocole propriétaire.

SIP DECT : Antennes liées au switch, avec une antenne master (OMM), autres antennes slave, protocole LLDP (broadcast)


Schéma réseau d'une installation DECT incluant à la fois une base numérique et une base IP :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/schema-dect-digital-ip.png

*Source : avaya.com*

.. seealso::

   Ce dernier provient du document pdf suivant, étant la propriété intellectuelle d'Avaya :

   https://ipofficekb.avaya.com/businesspartner/ipoffice11_1fr/mergedProjects/manuals/install/IP%20Office%20DECT%20R4%20Installation%20Guide_fr.pdf




.. warning::

   Le broadcast est désactivé par défaut sur les switchs CISCO et sur d'autres marques, **bloquant donc le broadcast du LLDP**. 
   Ceci crée des **problèmes de connexions** des terminaux aux antennes SIP DECT.
   Il est alors vivement recommandé **d'autoriser les trames broadcast** sur le switch.

Connection DECT :

2 fils, DSI (mitel), propriétaire...

Connexion SIP DECT :

Connexion au PBX via SIP puis configuration XML envoyée par le serveur


ATA : Analogic terminal adapter
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Le principe de l'ATA est en réalité très simple ; il permet de convertir un signal analogique en un signal numérique et inversement.
Cela permet donc de connecter un ancien téléphone analogique ou un FAX à un réseau numérique (souvent IP).

Cependant la méthode de conversion est différente pour le FAX (protocole T.38), il est alors simportant de choisir minutieusement l'ATA que nous installons.

Un ATA comporte en général minimum 2 ports RJ11 pour les appareils analogiques ainsi qu'un port RJ45 pour le connecter au réseau IP.
Les plus sophistiqués d'entre eux peuvent aussi être dotés de la capacité d'être alimenté en PoE et d'avoir un port RJ45 pour le WAN directement par exemple.

Voici une photo d'un ATA relativement classique :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/ata.png
   :height: 230px


:raw-m2r:`<br>`

.. seealso::

   Ce sujet est abordé dans le module M114 de 1ère année, je vous invite donc à vous référer à ces liens pour plus d'informations au sujet du PCM30 / MIC !

   - https://fr.wikipedia.org/wiki/Modulation_par_impulsions_et_codage
   - https://www.chireux.fr/mp/TIPE/ADS/Modulation_telephonie.pdf
   - https://www.universalis.fr/media/principe-de-la-modulation-par-impulsions-et-codage-v22n0038/


Schéma réseau d'une installation IP / SIP intégrant des appareils analogiques :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/schema-sip-ata.png





Attention aux recommandations des fournisseurs

----



Exigences réseau
^^^^^^^^^^^^^^^^^

Ce chapitre se base sur le cours 07-Exigences Réseau du cockpitprofessionnel.ch

Latence
*********

La durée d’exécution des paquets vocaux est un critère essentiel pour la qualité vocale. On s’intéresse ici au délai total entre la parole de l’émetteur et l’écoute du récepteur (délai de bout en bout).

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/latence.png

:raw-m2r:`<br>`

Gigue (Jitter)
***************************

Il désigne la différence de délai de transmission de bout en bout entre différents paquets d'un même flux de paquets lors d'une transmission d'un système à l'autre.
Il s'agit en réalité d'une variation de lantence.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/jitter.png

:raw-m2r:`<br>`

Perte de paquets
***************************
Un paquet vocal contient seulement 20 à 30 ms de paroles, ce qui correspond environ à une syllabe. Un codec doit pouvoir compenser jusqu’à 5% de perte de données, ce qui n’est pas entendu lors d’une conversation téléphonique.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/pertedepaquets.png


Erreurs possibles
******************

Si ces exigences de réseau ne sont pas tenues, les erreurs suivantes peuvent apparaître:

   - Conversation entrecoupées

   - Retards de paroles

   - Durée prolongée de l’établissement de la connexion

   - Volume de la conversation trop faible



Fonctions de réseau
^^^^^^^^^^^^^^^^^^^^^

PoE (Power over Ethernet)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La norme IEEE 802.3af, aussi appelée PoE, permet, initialement, de faire passer une alimentation en courant continu d'une puissance de max. 15,4W avec une tension d'environ 48V, en plus des données avec un débit de 100Mbit/s à 1Gbit/s.
Aujourd'hui la norme initiale a évolué (avec le PoE+, et PoE++), permettant de faire passer plus de courant, et donc d'alimenter des appareils de plus en plus gourmands en énergie !

Tableau des normes PoE à voir ci-dessous :   


.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/normes-poe.png
    :alt: normes-poe


----

LLDP (Link Layer Discovery Protocol)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Le protocole LLDP (Link Layer Discovery Protocol) est un protocole de découverte des voisins de couche 2 qui permet aux périphériques d'annoncer des informations sur eux-mêmes à leurs voisins directement connectés au même réseau.
Ces informations sont également enregistrées dans des banques de données d’informations de gestion (MIB) locales.
Sur les appareils compatibles LLDP, un agent LLDP est installé, ce dernier émettant des annonces de toutes les interfaces physiques, à intervalles réguliers ou lors de modifications.

Voici quelques-unes des informations qui peuvent être recueillies par LLDP (seules des informations minimales sont obligatoires) :

   - Nom et description du système

   - Nom et description du port

   - Nom et identifiant du VLAN

   - Adresse de gestion du réseau IP

   - Capacités de l’appareil (par exemple, commutateur, routeur ou serveur)

   - Informations sur l’adresse MAC et la couche physique

   - Informations sur l’alimentation

   - Informations d’agrégation de liens

En téléphonie IP, ce sont principalement les classes PoE nécessaires, l’ID VLAN et les paramètres QoS qui sont transmis. 
Cette option **devrait être activée sur les terminaux et sur les switchs Ethernet.**


 .. seealso::
   Ce protocole étant complexe et n'étant pas l'objet central de cette documentation, je vous invite à vous renseigner sur ce site :
   https://www.noction.com/blog-francais/decouverte-peers-bgp-lldp


STUN (Simple Traversal of UDP over NAT)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ce système permet la connexion d'appareils à distance à travers du NAT.
Pour de la VoIP, cela inclut PAR appareil :

   - 1 port SIP 
   - 10 ports RTP

Cela fonctionne mais demande **beaucoup de temps** et est **très complexe** à mettre en place à grande échelle

Cette solution est en générale **non recommandée** par les opérateurs.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/stun_binding.png

*Source : nexcom.fr*


.. seealso::
   Le site ci-dessous explique bien et de manière précise le STUN, je vous invite donc à vous y référer si intéressé !
   https://www.nexcom.fr/stun-la-base/


SBC (Session Board Controller)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Le SBC permet de garantir le fonctionnement et la qualité du service de l'opérateur jusqu'à leur SBC qui se situe à l'intérieur de notre réseau.

Il permet notamment de :

   - Sécuriser les communications
   - Gérer la QoS (différencier les appels d'urgences par exemple)
   - D'agir en tant qu'intermédiaire entre les réseaux et ainsi garantir l'interopérabilité des protocoles de communication

Puisqu'une image vaut plus que 1000 mots, vous trouverez ci-dessous un schéma réseau intégrant un SBC :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/SBC.jpg

*Source : Napsis.fr*

:raw-m2r:`<br>`


Schéma de principe du fonctionnement d'un SBC :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/large.png

:raw-m2r:`<br>`

Généralités Téléphonie
^^^^^^^^^^^^^^^^^^^^^^^^

Codecs audio
~~~~~~~~~~~~~~~~

Le choix du codec dépend des paramètres suivants:

   - Qualité vocale souhaitée
   - Bande passante disponible et taux de perte de paquets
   - Prise en charge par les appareils terminaux, PBX et le fournisseur SIP


G711
***********

Le G711 ou encore PCM30 / MIC, est le codec audio par défaut utilisé dans la téléphonie classique.

Les caractéristiques du codec G.711 sont les suivantes :

- Bande de fréquences : 300-3400Hz
- Fréquence d’achantillonnage de 8 khz
- Débit fixe de 64 kbits/s (échantillons de 8 bits x 8 kHz)
- Délai de compression de 0,125 ms (sans aucun délai d’anticipation)

MOS :

- Mesure de qualité en conditions idéales : 4,45 en G.711 Loi-A
- Mesure de qualité en condition dégradées :  4,11 en G.711 Loi-A

.. note::
   Les MOS ci-dessus sont basés sur le site https://w3tel.com/documentation-voip/codecs/g-711/ 

Pour tout appel passant par IP, une initiation de communications est procédé par le protocole SIP.
Ce dernier pourrait être comparable au fonctionnement du TCP, mais à la couche 7 du modèle OSI.




Capture wireshark d'une conversation en G711 (flux RTP):

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/rtp-conf-payload-G711.png

:raw-m2r:`<br>`


Comme escompté, nous remarquons que la discussion transite du téléphone 192.168.1.122 en passant par le serveur 3CX 192.168.1.120 .

La première chose qui est importante à souligner, est que les paquets utilisent le protocole de transport UDP (couche OSI 4) pour naviguer à travers le réseau, réduisant donc la latence potentielle de la conversation.

Étant donné que le trafic est d'interne à interne, il n'est par défaut pas chiffré, laissant le payload contenu dans le RTP visible en clair.
Il est donc tout à fait possible à partir d'un fichier d'un logiciel tel que Wireshark, d'écouter une conversation à partir de la conversation RTP !

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/i2i-call-RTP-voice-recording.png 




G722
*******

Aussi désigné comme la HD de l'audio, le G722 (ADPCM) est un codec avec une large bande fréquence. Il est donc beaucoup plus agréable de téléphoner avec celui-ci car le timbre de voix est bien moins altéré.


Les caractéristiques du codec G.722 sont les suivantes :

- Bande de fréquences : 50-7000Hz
- Fréquence d'échantillonnage : 16 kHz
- Débit fixe : 64 kbps
- Délai de compression : Non spécifié

MOS :

- Mesure de qualité en conditions idéales : MOS (Mean Opinion Score) similaire pour G.722 et G.711
- Mesure de qualité en conditions dégradées : MOS (Mean Opinion Score) similaire pour G.722 et G.711

Voici un graphique comparatif pour les bandes de fréquence du G711 et du G722 :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/g711-g722-frequency-response.jpg
    :alt: graph-g711-g722

:raw-m2r:`<br>`

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/rtp-conf-payload-G722.png

:raw-m2r:`<br>`

G729
*********

Ce codec (CS-ACELP), permet de téléphoner avec un débit réduit et dans des conditions réseau défavorables.
Sa qualité est donc moindre car son délai de compression est élevé.
Les discussions ont un timbre "métallique" voire "robotique".

Nous remarquerons d'ailleurs que sur la capture wireshark ci-dessous, le volume du payload contenu dans le paquet RTP est bien inférieur à celui des 2 précédents codecs.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/rtp-conf-payload-G729.png

:raw-m2r:`<br>`

Les caractéristiques du codec G.729 sont les suivantes :

- Bande de fréquences : 300-3400Hz
- Fréquence d'échantillonnage : 8 kHz
- Débit fixe : 8Kbps
- Délai de compression : 15ms

MOS :

- Mesure de qualité en conditions idéales : MOS (Mean Opinion Score) 4,04 en G.729a
- Mesure de qualité en conditions dégradées : MOS (Mean Opinion Score) 3,51 en G.729a





SIP trunk
~~~~~~~~~~

Un SIP trunk permet une liaison entre le réseau privé et le réseau public de téléphonie. 
Plus concrètement, cette liaison permet d'émettre et recevoir des appels vers/depuis l'extérieur.

Un SIP trunk peut se louer par mois ou à l'utilisation à la minute par exemple.
Il se présente souvent comme un compte, avec un nom d'utilisateur, un mot de passe ainsi que l'IP du registrar.

Ce dernier est un serveur d'authentification, vérifiant les credentials des clients.


.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/sip-trunk-schema.png

*Source : ringcentral.com*





DTMF
~~~~

Les touches DTMF (Dual-tone multi-frequency) usent d'une combinaison de fréquences pour composer un numéro de téléphone et interagir avec des serveurs vocaux interactifs.
Les fréquences utilisées sont situées entre 770Hz et 1633MHz.

Elles sont normalisées et spécifiées par la recommandation Q.23 de :abbr:`l'UIT (Union internationnale des Télécommunications)`. 

.. seealso::
   Un tableau interactif des touches DTMF est disponible sur la page suivante : https://fr.wikipedia.org/wiki/Code_DTMF



IVR 
~~~~~

L'IVR (Interactive Voice Responder) est un répondeur interagissant avec les appelants via des **menus vocaux** et des **messages préenregistrés.**
Il est donc possible **d'orienter ces personnes** vers les services dont ils ont besoin **automatiquement.**

Chez 3CX, le menu de configuration se présente de la sorte :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/ivr.png

:raw-m2r:`<br>`


Pour une entreprise, cet outil est très précieux car il permet d'optimiser au préalable le temps des collaborateurs et ainsi d'économiser de l'argent.
Configurer un IVR est donc une tâche à ne pas négliger !






----


Exercices
-----------


Exercice 1
^^^^^^^^^^^^^^^^^

Demande
~~~~~~~~~~~~~~~~~~~

**Exercice 1: Création d’un numéro d’assistance**

L’accessibilité téléphonique du service clientèle de Cardinal Bier Import AG doit être améliorée. À l’heure actuelle, le numéro principal n’est desservi que par une seule personne. Récemment, une application de Customer Releationship Management a été installée. Désormais, les commandes, réclamations ou autres demandes des clients sont enregistrées électroniquement. Une équipe de 4 collaboratrices a été formée. La répartition des appels au sein de cette équipe doit être définie. Créez une solution de téléphonie pour le service clientèle de Cardinal Bier Import AG. Vous disposez d’une instance vPBX de Peoplefone ou d’autres installations. Lisez les exigences de l’entreprise et établissez une configuration.

**Besoins en téléphonie du service clientèle**

:raw-m2r:`<u>Exigences auxquelles doit satisfaire le numéro principal:</u>`


* Horaires d’ouverture du lundi au vendredi de 8h00 à 18h00 et le samedi de 8h00 à 17h00
* Saisie de tous les jours fériés catholiques légaux pour le site de Fribourg, pour les 12 prochains mois.
* IVR pour allemand, français et anglais en amont

Formez des groupes pertinents. Les appels doivent être répartis de manière séquentielle au sein du groupe. Il doit y avoir passage d’un groupe à un autre, si personne ne répond ou si la ligne est occupée. L’appel passera sur messagerie et signalera qu’aucun collaborateur n’est libre, seulement aucune personne ne répond. Les équipes parlant les langues officielles du canton reçoivent un numéro d’appel externe et les collaboratrices peuvent passer des appels externes sur lle téléphone IP avec ce numéro ou avec le numéro principal.

Les textes de message suivants peuvent être repris dans le fichier ZIP ou vous pouvez en enregistrer vous-même:


* HPN_AB_FeiertagFerien.wav
* HPN_AB_keinMitarbeiterFrei.wav
* HPN_AB_Oefffnungszeiten.wav
* IVR_Ansage.wav

Fichiers WAV
Le texte parlé des fichiers WAV ne doit pas correspondre à 100% à la problématique de cet exercice.
Les utilisateurs suivants doivent être enregistrés:


* Meier Anna, parle allemand, français
* Müller Janine, parle allemand, anglais
* Angeloz Marie, parle français
* Ducrest Sophie, parle français, anglais

Mission par groupe de 2 ou 4:


* Tracez le Call Flow pour le numéro principal (modèles disponibles dans le chapitre 10 du module 361)
* Configurez l’installation en fonction des exigences

Testez l’installation et consignez les tests dans un protocole

Workflow 
~~~~~~~~~~~~~~~~~~~~~~

La chose la plus importante à faire dans un exercice tel quel, est de dessiner un schéma de principe très simple, à la main de préférence.

Cela permet de visualiser au mieux la demande et de pouvoir poser des questions au client si les indications ne sont pas claires !

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/schema-ex1.png

:raw-m2r:`<br>`

La demande est désormais plus compréhensible, nous allons donc maintenant procéder à la configuration de notre PBX virtuel !

En supposant que le SIP trunk et que les règles entrantes / sortantes sont déjà configurées, je vous propose de commencer par les utilisateurs :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/users1.png

:raw-m2r:`<br>`

*Cependant, pour avoir une idée de comment se configure une règle sortante, je vous invite à accéder au lien suivant : https://www.3cx.fr/docs/manuel/avance/#h.y5la85hz60l*

:raw-m2r:`<br>`

.. note::

   Pour l'exercice, seuls 2 téléphones IP Yealink étaient à disposition ; ils seront configurés pour les utilisateurs 100 et 101.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/users1.png

:raw-m2r:`<br>`

Configuration Janine :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/janine.png

:raw-m2r:`<br>`

Les champs obligatoires à remplir lors de la création de l'utilisateur sont les suivants :


* Extension
* Prénom
* Nom
* Adresse Mail

Par la suite, il est nécessaire de **configurer les groupes d'appels** en fonction des **langues parlées** par les collaborateurs :
Nous allons donc ici configurer 3 groupes :

   - Groupe allemand (810)
   - Groupe francais (820)
   - Groupe anglais (830)

Dans les paramètres de chacun des groupes, il est **important** de sélectionner la **sonnerie en parallèle (sonne tous)** dane le but d'éviter le cas suivant :

Imaginons que nous configurions la sonnerie à la suite 1 à 1 (Janine puis Anna dans l'ordre).
Un client appelle le groupe allemand, mais Janine est absente ou alors cette dernière a juste pris une pause café de 5 minutes.
Dans ce cas-là, le client tombera directement sur la messagerie de Janine sans passer par Anna, qui elle, est bien présente.

Cela pourrait présenter un inconvénient majeur pour les collaborateurs et créer une frustration côté client.

Voici pour exemple la configuration du groupe allemand :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/groupe-appel-810.png

:raw-m2r:`<br>`

Tout de suite après, nous pouvons créer un IVR :

En premier temps, nous choisissons le nom de l'IVR, son n° d'extension, son type, le message pré-enregistré ainsi que la langue des directives vocales.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/ivr-config1.png

:raw-m2r:`<br>`

Après cela, nous définissons comment chaque touche agit :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/ivr-config2.png

:raw-m2r:`<br>`

Ici, nous voulons que la touche n°1 appelle le groupe allemand, que la n°2 appelle le groupe francais et que la n°3 appelle le groupe anglais.
En cas de non réponse, l'appelant se verra redirigé vers la messagerie vocale de l'extension n°299 "occupé".

Il est nécessaire de **répéter cette configuration pour chaque groupe d'appel.**

Voici la configuration de l'utilisateur 299 "occupé" :

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/occupé.png

:raw-m2r:`<br>`

Maintenant, créons les règles lorsque le bureau est fermé ou lorsque le jour en question est férié / chômé :

Il est possible de le faire pour un **SIP trunk**, une **règle entrante** ou encore dans les **paramètres généraux de 3CX.**
Ici, nous avons choisi la 3ème option.


.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/férié.png

:raw-m2r:`<br>`

Désormais, il ne manque plus que définir le routage dans le SIP Trunk pour définir où seront redirigés les utilisateurs en fonction des 2 cas précédemment cités.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/trunk-routage.png

:raw-m2r:`<br>`


Il ne manque plus que la configuration des terminaux pour que l'installation soit opérationnelle.

Tout d'abord, il est nécessaire d'accéder au menu de téléconfiguration de l'utilisateur et de rentrer le modèle de l'appareil ainsi que son adresse MAC.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/tel-config.png

:raw-m2r:`<br>`

Après cela, il faut enregistrer le nom d'utilisateur et le mot de passe que vous rentrerez dans le menu d'auto-provisioning du poste IP fixe.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/id-tel.png

:raw-m2r:`<br>`

Le plus simple est d'accéder à la web interface de chaque terminal IP et de saisir le lien de provisionning dans le menu correspondant afin que le PBX s'occupe seul de la configuration.

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/provision.png

:raw-m2r:`<br>`

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/T46-3cx.png

:raw-m2r:`<br>`

Après avoir redémarré nos terminaux, notre installation est fin prête à être testée et déployée pour l'exercice !!


----


Exercice 2
^^^^^^^^^^^^^^^^^

1 - NAT / PAT avec installation app natel externe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Workflow de l'exercice :

Dépannage 3CX

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/depannage-3cx.png


:raw-m2r:`<br>`

Vous avez la possibilité à travers ce menu de définir si oui ou non le serveur 3CX agit en tant qu'intermédiaire pour les appels.
Ici, cela nous sera utile afin de nous simplifier la tâche, au lieu de configurer un port de mirroring sur le switch par exmple.

La prochaine étape sera de créer la règle NAT/PAT dans le routeur / firewall du réseau (ici Centro Business 2.0 Swisscom)
Nous accédons donc à la web interface administrateur de ce dernier :menuselection:`Réseau --> Port Forwarding --> Create new rule`.

- Port TCP 5001 (HTTPS)
- Port TCP/UDP 5090 (Tunnel 3CX)

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/natpat-swisscom-ex2.png

:raw-m2r:`<br>`

A la suite de cette configuration, nous pouvons télécharger l'application 3CX sur notre téléphone.

.. warning::


   Sur Android, l'application **nécessite** le GSF afin d'afficher les notifications d'appels entrants.
   Dans le cas contraire, vous ne pourrez pas répondre aux appels, mais serez en mesure d'en passer (appels sortants).

Précision faite, il est temps d'installer l'application sur notre appareil !

- Rendez-vous dans votre :menuselection:`gestionnaire de paquets / applications préféré --> Tapez "3CX" dans la barre de recherche --> Installez l'application`. 
- Ensuite, lisez et acceptez les conditions d'utilisation de l'app.
- Pour finir, scannez le QR code que vous trouvez dans la configuration de votre utilisateur 3CX.


.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/install-android.png
      

:raw-m2r:`<br>`

Vous êtes désormais connecté à votre compte, vous permettant donc de passer des appels et d'envoyer des messages dans le service de chat 3CX.

:raw-m2r:`<u>Schéma réseau de la connexion : </u>`

.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/schema-app-qr.png


2 - 1 App + 1 Webclient en interne avec Wireshark
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Après avoir vu comment fonctionnaientt les communications SIP / RTP, il est nécessaire de comprendre comment se passent les communications passant à travers des applications ou par WebRTC.

Pour illustrer cela, rien de mieux qu'une capture wireshark accompagnée d'un petit schéma réseau.d


.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/udp-stream.png

:raw-m2r:`<br>`

Avant que la communication commence entre les appareils, un handshake TLS1.2 est initié afin d'échanger les clés nécessaires au chiffrement de la communication.

.. danger::

   Il est important de noter qu'un chiffrement **TLS 1.2 min.** est recommandé pour **garantir l'intégrité et la confidentialité** de la communication.


Voici comment se passe un handshake TLS :


.. image:: https://raw.githubusercontent.com/algues111/docs-cfc/main/docs/source/images/M362/tls-ssl-handshake.png

:raw-m2r:`<br>`

.. admonition:: Lien utile

   TLS / SSL protocols  : https://www.cloudflare.com/fr-fr/learning/ssl/what-happens-in-a-tls-handshake/



3 - 2 Téléphones SIP avec Wireshark (comparaison G711/G722/G729 )
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Concernant cet exercice, je vous invite à vous rediriger vers la section discutant des codecs audio, car les captures Wireshark ont été prises lors de cet exercice.