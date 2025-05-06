# Protection FireFox
## Auteur :  z0S.i0S  - Maj : 06/05/2025

## Introduction

Lorsque vous visitez une page web, votre navigateur envoie volontairement des informations sur sa configuration, telles que les polices disponibles, le type de navigateur et les add-ons. Si cette combinaison d'informations est unique, il peut être possible de vous identifier et de vous suivre sans utiliser de cookies.

## Test du niveau de sécurité de la configuration du navigateur

Pour tester son niveau de trace sur Internet :

```txt
cf. https://coveryourtracks.eff.org/
```

## Liste de versions 

Sécurisation de l’anonymat sur Firefox
│
├── 1. Mises à jour et versions majeures
│   ├── 2025 : v138
│   │   └── Derniers correctifs de sécurité et protections anti-pistage renforcées
│   ├── 2022 : v102
│   │   └── Total Cookie Protection activée par défaut pour tous
│   ├── 2021 : v89
│   │   └── Total Cookie Protection étendue à la navigation privée
│   ├── 2021 : v86
│   │   └── Total Cookie Protection disponible en mode strict
│   ├── 2019 : v70
│   │   └── Tableau de bord vie privée, blocage renforcé des traqueurs et fingerprinting
│   ├── 2013 : v23
│   │   └── Blocage du contenu mixte (protection contre attaques Man-in-the-middle)
│   └── 2004 : v1.0
│       └── Lancement de Firefox, priorité à la vie privée et à la sécurité
│
├── 2. Navigation privée (toutes versions)
│   ├── Efface historique, cookies, données à la fermeture
│   ├── Blocage des traqueurs et cookies tiers renforcé (v70+)
│   └── Total Cookie Protection en navigation privée (v89+)
│
├── 3. Fonctionnalités de confidentialité
│   ├── Enhanced Tracking Protection (v69+)
│   │   ├── Blocage traqueurs, cookies tiers, cryptominers, fingerprinters
│   ├── Total Cookie Protection (v86+ mode strict, v89+ navigation privée, v102+ par défaut)
│   ├── Tableau de bord vie privée (v70+)
│   ├── Blocage du contenu mixte (v23+)
│   ├── DNS over HTTPS (v78+)
│   ├── HTTPS-Only Mode (v91+)
│   ├── ECH (Encrypted Client Hello) (v118+)
│   └── SmartBlock (v87+)
│
├── 4. Outils complémentaires
│   ├── VPN, Proxy
│   ├── Extensions privacy (uBlock Origin, Privacy Badger, Cookie AutoDelete)
│   └── Attention à l’unicité du fingerprint avec trop d’extensions
│
├── 5. Paramètres et bonnes pratiques
│   ├── Désactiver télémétrie (Menu > Paramètres > Vie privée)
│   ├── Gérer autorisations sites (caméra, micro, localisation)
│   ├── Effacer régulièrement les données de navigation
│   └── Personnalisation avancée via about:config
│
└── 6. Transparence et open source
    ├── Code source auditable
    ├── Corrections rapides via bug bounty
    └── Mises à jour régulières des politiques de confidentialité


cf. https://www.mozilla.org/en-US/firefox/releases/

## Fichier de profil

cf. https://kb.mozillazine.org/User.js_file

Un fichier **user.js** est une autre méthode de modification des préférences, recommandée uniquement pour les utilisateurs avancés. Sauf si vous avez besoin d'un fichier user.js pour un usage spécifique, vous devez utiliser à la place **about:config**. Le fichier user.js n'existe pas par défaut.

```sh
about:support => permet de localiser le fichier profil
```
Références de fichiers durcis :
- https://github.com/arkenfox/user.js
- https://github.com/pyllyukko/user.js

## Elements modifiables

- "Firefox Preferences" ou "**about:preferences#privacy**" :
  - Général : Firefox est votre navigateur par défaut
    - Onglets :
      - À l’ouverture d’un lien, d’une image ou d’un média dans un nouvel onglet, basculer vers celui-ci immédiatement : ${\color{red}OFF}$
      - Extensions X : ${\color{red}OFF}$
      - Activer les onglets conteneurs  : ${\color{green}ON}$
    - Fichiers et applications :
      - Enregistrer les fichiers :  ${\color{green}ON}$
      - Lire le contenu protégé par des DRM : ${\color{green}ON}$
    - Mises à jour de Firefox  :
      - Vérifier l’existence de mises à jour, mais vous laisser décider de leur installation
    - Performances : 
      - Utiliser les paramètres de performance recommandés : ${\color{green}ON}$ (cf "**about:memory**" et "**about:processes**")
    - Navigation :
      - Lancer la recherche lors de la saisie de texte : ${\color{red}OFF}$
      - Activer les contrôles pour l’incrustation vidéo: ${\color{green}ON}$ 
      - Contrôler la lecture des médias via le clavier, un casque ou l’interface virtuelle : ${\color{green}ON}$ 
      - Recommander des extensions en cours de navigation :  ${\color{red}OFF}$
      - Recommander des fonctionnalités en cours de navigation : ${\color{red}OFF}$
    - Paramètres réseau :
      - Configuration manuelle du proxy :  => Burp
        - Proxy HTTP : 127.0.0.1
        - Port : 8000
  - Accueil :
    - Nouvelles fenêtres et nouveaux onglets :
      - Page d’accueil et nouvelles fenêtres : Page vide
      - Nouveaux onglets : Page vide
    - Contenu de la Page d’accueil de Firefox :
      - Recherche web : ${\color{green}ON}$ 
      - Raccourcis : ${\color{red}OFF}$
      - Articles recommandés : ${\color{red}OFF}$
      - Activité récente : ${\color{red}OFF}$
    - Recherche :
      - Moteur de recherche par défaut  : Duckduckgo
      - Suggestions de recherche : 
        - Afficher les suggestions de recherche : ${\color{red}OFF}$
        - Afficher les recherches récentes : ${\color{red}OFF}$
    - Vie privée :
      - Protection renforcée contre le pistage : Personnalisée
        - Cookies : Cookies de pistage intersites et isolation des autres cookies intersites
        - Contenu utilisé pour le pistage : dans toutes les fenêtres
        - Mineurs de cryptomonnaies : ${\color{green}ON}$ 
        - Détecteurs d’empreinte numérique connus : ${\color{green}ON}$ 
        - Détecteurs d’empreinte numérique suspectés :  dans toutes les fenêtres
      - Mots de passe  :
        - Proposer d’enregistrer les mots de passe : ${\color{red}OFF}$
        - Afficher des alertes pour les mots de passe de sites concernés par des fuites de données : ${\color{red}OFF}$
        - Utiliser un mot de passe principal : ${\color{red}OFF}$
      - Remplissage automatique :
        - Enregistrer et remplir automatiquement les adresses  : ${\color{red}OFF}$
      - Historique :
        - Toujours utiliser le mode de navigation privée : ${\color{green}ON}$
      - Permissions :
        - Bloquer les fenêtres popup : ${\color{green}ON}$
        - Prévenir lorsque les sites essaient d’installer des modules complémentaires : ${\color{green}ON}$
      - Collecte de données par Firefox et utilisation : 
        - Envoyer des données techniques et d’interaction à Mozilla : ${\color{red}OFF}$
        - Envoyer un ping quotidien d’utilisation à Mozilla : ${\color{red}OFF}$
        - Envoyer automatiquement les rapports de plantage : ${\color{red}OFF}$
      - Préférences publicitaires des sites web :
        - Autoriser les sites web à effectuer des mesures publicitaires en respectant la vie privée : ${\color{red}OFF}$
      - Sécurité :
        - Protection contre les contenus trompeurs et les logiciels dangereux :
          - Bloquer les contenus dangereux ou trompeurs : ${\color{green}ON}$
        - Certificats : 
          - Interroger le répondeur OCSP pour confirmer la validité de vos certificats : ${\color{red}OFF}$
          - Autoriser Firefox à faire automatiquement confiance aux certificats racines tiers que vous installez : ${\color{green}ON}$
        - Mode HTTPS uniquement :
          - Activer le mode HTTPS uniquement dans toutes les fenêtres : ${\color{green}ON}$
        - DNS via HTTPS : 
          - Activer le DNS via HTTPS en utilisant : Protection maximale
      - Synchronisation : ${\color{red}OFF}$

- about:addons :
  - Extensions : 
    - Autoriser les mises à jour automatiques : ${\color{red}OFF}$
  - Thèmes :
    - Autoriser les mises à jour automatiques : ${\color{red}OFF}$
  - Plugins : 
    - Autoriser les mises à jour automatiques : ${\color{red}OFF}$

- "**about:config**" : variable selon  version du navigateur. 

<u>Nota :</u> Chercher par mot clé pour retrouver les paramètres en rapport. Recherches générales : "stream", "update","extensions", "privacy"
  
  - StartUp Settings : like "browser"
  - Geolocation : like "geo"
  - Language / Locale : like "local"
  - Auto-updates / Recommendations : like "update"
  - Telemetry : like "telemetry"
  - Studies : like "studies"
  - Crash Reports : like "crash"
  - Captive Portal Detection / Network Checks : like "detection"
  - Safe Browsing : like "safe"
  - Network: DNS, Proxy, IPv6 : like "dns" 
  - Search Bar: Suggestions, Autofill : like "search"
  - Passwords : like "passw"
  - Disk Cache / Memory : like "disk"
  - HTTPS / SSL/TLS / OSCP / CERTS : like "http" 
  - Headers / Referers : like "head"
  - Audio/Video: WebRTC, WebGL, DRM : like "web" 
  - Downloads : like "down"
  - Cookies : like "cook"
  - UI Features : like "ui"
  - Extensions : like "extension"
  - Shutdown Settings : like "shutdown"
  - Fingerprinting (RFP) : like "finger"

## Extensions

- User-Agent : 
  - [User Agent Switcher](https://addons.mozilla.org/fr/firefox/addon/uaswitcher/)
  - [Modify Header Value](https://addons.mozilla.org/fr/firefox/addon/modify-header-value/)
- canvas fingerprinting : 
  - [canvas fingerprinting](https://fr.wikipedia.org/wiki/Canvas_fingerprinting)
  - [canvas fingerprinting](https://addons.mozilla.org/fr/firefox/addon/canvas-fingerprint-defender/)
- empreinte WebGL :
  - [empreinte WebGL](https://addons.mozilla.org/fr/firefox/addon/webgl-fingerprint-defender/)
- anti-tracking :
  - [uBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/)
- Browser Leak Tests :
    - [coveryourtracks](https://coveryourtracks.eff.org/)
    - [amiunique](https://www.amiunique.org/)
    - [browserleaks](https://browserleaks.com/)
    - [arkenfox](https://arkenfox.github.io/TZP/tzp.html)
    - [Firefox Lightbeam](https://github.com/mozilla/lightbeam-we), équivalent de **chrome://discards** => donne l'activité du navigateur avec les extensions activées et les pages affichées

## Parts de marché des  navigateurs

![alt text](image.png)