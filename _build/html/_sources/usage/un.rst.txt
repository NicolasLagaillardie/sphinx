PixLed
======

Origines du projets
-------------------

Le projet consiste en la création d'une matrice de LED de dimensions 32x16 permettant l'affichage de diverses animations ainsi que du texte dans le cadre des soirées de campagne BDE d'une des listes candidates.

Déroulement
-----------

Projet initial
**************

Le projet initial se décompose comme suit :
    - Construction de la matrice de LED avec ses 512 led RGB (!), un cadre en bois, ainsi qu'une surface semi opaque et diffusante en Plexiglass. Les leds utilisés sont des LED adressables types rubans de leds. (https://cdn-shop.adafruit.com/product-files/1138/SK6812+LED+datasheet+.pdf)
    - Pilotage basique du ruban de LED directement depuis le microcontroleur (Arduino Nano) grâce à la librairie d'Adafruit NeoPixel : https://learn.adafruit.com/adafruit-neopixel-uberguide/arduino-library-use
    - Envoie d'animation à la matrice de LED via le port USB de l'Arduino, depuis un PC ou une Raspberry Pi, notamment grâce à l'utilisation du logiciel OpenSource Glediator : http://www.solderlab.de/index.php/software/glediator
Bien que divers problèmes aient raisonablement fait leur apparition au cours de chaque étape, comme dans tout projet, le plus important fut sans doute l'impossibilité d'utiliser Glediator, en raison de l'incompatibilité du logiciel avec nos LED RGB**W** (Red Green Blue + White), Glediator ayant seulement été conçu pour les LED RGB. Alors que la recherche de logiciels équivalents pouvant supporter les LED RGBW s'avère rapidement infructueuse, une solution évidente s'impose : nous devons (et nous allons!) coder notre propre application de génération d'animations et de pilotage de matrice de LED **RGBW** (et par extension RGB également).

Première version
****************

Pour des raisons d'expériences et d'affinités, Java à été choisi comme language de développement, un de nos membres ayant déjà une certaine expérience avec le développement d'interfaces graphiques en Java.
En deux semaines, une première application est disponible. Executable facilement depuis un PC, elle permet :
    - De générer diverses animations basiques, parmis lesquelles du texte défilant, une *pluie de pixels*, ou l'affichage de cercle concentrique multicolores.
    - De prévisualiser l'animation en cours.
    - De la transmettre au panneau via un port USB.
Avec les finitions en parallèle d'un point de vue matériel et programmation de l'Arduino, cette première version de l'application nous a permis d'obtenir un premier panneau de led fonctionnel et simple d'utilisation, qui correspondait à nos attentes initiales.
Dans la foulée de son utilisation durant la campagne BDE, des fonctionnalités telles que la possibilité de générer des boucles d'animations sont ajoutées.

Et après?
*********

De multiples animations ont été conçues. L'interface graphique a également été améliorées.

Futur
-----

Les objectifs futurs peuvent être classés comme suit, par ordre d'importance :
    - Développement d'autres animations
    - Algorithme permettant d'exploiter de manière optimal la led blanche des led RGBW
    - Support Bluetooth
    - Inclusion de GIF
    - Mémoire interne permettant de sauvegarder les configurations/boucles d'animations de l'utilisateur
    - Réalisation d'un spectrogramme
    - Interconnexion de panneaux dans diverses configurations (d'un point de vue taille et formes), objectif à la fois software et hardware
    - Adaption Android/Appli Web
    - Jeux
    - Interactions avec l'utilisateur de type accéléromètre/écran tactile/Kinnect...
    - ...
La distribution du logiciel en tant qu'application de contrôle de matrices de LED DIY, à la façon de Glediator mais plus moderne et supportant le RGBW, est envisagé au cours des prochaines itérations.
Le code source est déjà disponible à partir du répertoire GitHub : https://github.com/PaulBreugnot/RGBWMatrixController

A noter qu'aucune documentation n'est disponible pour le moment....................................
