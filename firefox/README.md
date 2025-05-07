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

Pour **automatiser les contrôles de confidentialité et sécurité dans Firefox sous Linux**, il existe plusieurs méthodes robustes et adaptées à différents contextes :

---

## 1. **Utiliser les politiques d’entreprise (policies.json)**

- Créez le dossier :  
  `/etc/firefox/policies/`
- Ajoutez un fichier `policies.json` contenant vos règles, par exemple :

```json
{
  "policies": {
    "DisableTelemetry": true,
    "BlockAboutConfig": false,
    "Cookies": {
      "Behavior": "reject_trackers"
    },
    "SearchBar": "separate",
    "DefaultSearchEngine": "DuckDuckGo",
    "SafeBrowsing": {
      "Enabled": false,
      "MalwareProtection": false,
      "PhishingProtection": false
    },
    "DNSOverHTTPS": {
      "Enabled": true,
      "ProviderURL": "https://dns.nextdns.io/votre_id"
    },
    "ExtensionSettings": {
      "*": {
        "installation_mode": "allowed"
      }
    },
    "Permissions": {
      "Camera": "block",
      "Microphone": "block",
      "Location": "block",
      "Notifications": "block",
      "Clipboard": "block",
      "Sensors": "block"
    },
    "SSLVersionMin": "tls1.2",
    "SSLVersionMax": "tls1.3",
    "HttpsOnlyMode": true
  }
}
```
- Redémarrez Firefox pour appliquer les politiques.

---

## 2. **Configurer via user.js (par profil ou globalement)**

- Placez un fichier `user.js` dans le dossier du profil Firefox (`~/.mozilla/firefox/xxxxxx.default/`).
- Exemple de lignes à inclure :

```js
// Bloquer cookies tiers
user_pref("network.cookie.cookieBehavior", 1);
// Désactiver le préchargement
user_pref("network.prefetch-next", false);
// Désactiver Safe Browsing
user_pref("browser.safebrowsing.enabled", false);
user_pref("browser.safebrowsing.malware.enabled", false);
// Toujours utiliser HTTPS
user_pref("dom.security.https_only_mode", true);
// DNS-over-HTTPS
user_pref("network.trr.mode", 2);
user_pref("network.trr.uri", "https://dns.nextdns.io/votre_id");
// Désactiver WebRTC
user_pref("media.peerconnection.enabled", false);
// Désactiver la télémétrie
user_pref("toolkit.telemetry.enabled", false);
user_pref("datareporting.healthreport.uploadEnabled", false);
// Bloquer accès caméra/micro/localisation/notifications
user_pref("permissions.default.camera", 2);
user_pref("permissions.default.microphone", 2);
user_pref("permissions.default.geo", 2);
user_pref("permissions.default.desktop-notification", 2);
```

---

## 3. **Fichiers de configuration avancés**
- Pour verrouiller certains réglages, utilisez :
  - `/etc/firefox/syspref.js` (pour des valeurs par défaut ou verrouillées)
  - `autoconfig.js` et `mozilla.cfg` pour des configurations avancées ou des scripts de verrouillage.

---

## 4. **Déploiement automatisé**
- Utilisez des outils comme Ansible, Puppet, SaltStack ou un simple script bash pour copier et maintenir ces fichiers sur tous les postes Linux.

---

## 5. **Vérification et priorités**
- Les réglages via `policies.json` prennent le dessus sur `mozilla.cfg` et `user.js`.
- Pour vérifier les politiques actives, tapez :  
  `about:policies`  
  dans la barre d’adresse de Firefox.

---

**Résumé** :  
- Placez un fichier `policies.json` dans `/etc/firefox/policies/` pour appliquer des politiques globales.
- Pour des réglages plus fins ou spécifiques à un profil, utilisez `user.js`.
- Automatisez la distribution de ces fichiers via des outils de gestion de configuration ou des scripts.
- Cette approche permet de contrôler efficacement la confidentialité et la sécurité de Firefox sur Linux, de façon centralisée et reproductible.


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