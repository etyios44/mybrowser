# Protection Chrome
## Auteur :  z0S.i0S  - Maj : 07/05/2025

## Liste des versions

cf. https://static.open-scap.org/ssg-guides/ssg-chromium-guide-index.html

Sécurisation de l’anonymat sur Chrome
│
├── 1. Mises à jour et versions majeures
│   ├── 2025 : v124+
│   │   └── Safety Check amélioré
│   │       ├── Analyse automatique des failles de sécurité sur extensions, mots de passe, et autorisations
│   │       ├── Révocation automatique des autorisations inutilisées (géolocalisation, caméra, micro)
│   │       └── Alertes en temps réel sur compromission de données
│   ├── 2024 : v122-v123
│   │   ├── Privacy Sandbox généralisée
│   │   │   ├── Blocage natif des cookies tiers
│   │   │   ├── Remplacement du tracking intersite par des API anonymisées (Topics, Protected Audience, Attribution)
│   │   │   └── Traitement local des données de navigation pour éviter l’envoi d’informations individuelles aux serveurs externes
│   │   └── Autorisations ponctuelles pour les sites web
│   │       └── Accès temporaire à la caméra, au micro ou à la localisation, réinitialisé à chaque session
│   ├── 2019 : v76
│   │   └── API FileSystem disponible en navigation privée
│   │       └── Empêche la détection du mode incognito par les sites via l’accès au stockage local
│   ├── 2012 : v23
│   │   └── Prise en charge de l’en-tête « Do Not Track »
│   │       └── Permet d’indiquer aux sites la volonté de ne pas être suivi (signal non contraignant)
│   └── 2008 : v1.0
│       └── Lancement de Chrome avec mode Incognito
│           └── Séparation complète des sessions, effacement automatique des cookies, historiques et caches à la fermeture
│
├── 2. Navigation privée (Incognito)
│   ├── Séparation des sessions utilisateur (pas d’accès à l’historique ou aux cookies des autres sessions)
│   ├── Aucune donnée de navigation (historique, cookies, cache) conservée à la fermeture de la fenêtre
│   ├── Extensions désactivées par défaut (sauf autorisation explicite)
│   └── Depuis v76 : API FileSystem accessible, rendant la détection du mode privé plus difficile
│
├── 3. Fonctionnalités de confidentialité avancées
│   ├── Privacy Sandbox (v122+, 2024)
│   │   ├── Topics API : Attribution de thèmes d’intérêt au navigateur, partagés de façon agrégée avec les sites, sans historique détaillé
│   │   ├── Protected Audience API : Regroupement des utilisateurs dans des cohortes anonymes pour le ciblage publicitaire, sans identifiant individuel
│   │   ├── Attribution Reporting API : Mesure des conversions (clics, vues) sans suivi individuel, données agrégées et bruitées
│   │   ├── Confidentialité différentielle : Ajout de bruit statistique pour empêcher l’identification d’un utilisateur précis
│   │   └── Traitement sur l’appareil : Calculs et analyses réalisés localement, sans transfert de données brutes vers les serveurs Google
│   ├── Safety Check (v124+, 2025)
│   │   ├── Vérification automatique des mots de passe compromis
│   │   ├── Contrôle de l’état des extensions et des autorisations
│   │   └── Notifications proactives en cas de risque détecté
│   ├── Autorisations ponctuelles (v122+, 2024)
│   │   └── Accès temporaire aux ressources sensibles, révoqué automatiquement après usage ou fermeture de l’onglet
│   ├── Navigation sécurisée
│   │   └── Analyse des URL en temps réel, blocage des sites malveillants via listes noires et serveurs de confidentialité
│   └── Do Not Track (v23+, 2012)
│       └── Signal envoyé aux sites pour demander l’absence de suivi (respect dépend du site)
│
├── 4. Outils complémentaires
│   ├── VPN ou Proxy : Masquage de l’adresse IP réelle, chiffrement du trafic réseau
│   ├── Extensions privacy (uBlock Origin, Privacy Badger) : Blocage des scripts de tracking, des cookies tiers restants, et des fingerprintings
│   └── Changement du moteur de recherche par défaut pour limiter la collecte de données par Google
│
├── 5. Paramètres et bonnes pratiques
│   ├── Se déconnecter du compte Google pour éviter la synchronisation des données de navigation
│   ├── Bloquer ou supprimer régulièrement les cookies et données de site
│   ├── Activer la protection renforcée contre les sites dangereux
│   ├── Utiliser un DNS sécurisé (DNS-over-HTTPS)
│   ├── Désactiver les API de tracking publicitaire dans les paramètres Privacy Sandbox
│   ├── Limiter les autorisations accordées aux sites (caméra, micro, localisation)
│   └── Activer « Toujours utiliser une connexion sécurisée » (HTTPS-Only)
│
└── 6. Limitations et transparence
    ├── Chrome reste lié à l’écosystème Google, collecte de données persistante même en mode privé
    ├── Certaines API de Privacy Sandbox offrent un anonymat relatif mais pas absolu
    └── Popularité du navigateur attire des extensions ou clones malveillants, vigilance requise

## Détail des modifications 

Bien sûr ! Voici comment réaliser chaque action sur Chrome, étape par étape, sans références externes :

---

## 1. Désactiver Discover by Google
- Ouvrez un nouvel onglet.
- Si des suggestions Discover apparaissent, cliquez sur les options ou paramètres de la page pour masquer les contenus recommandés.
- Si l’option n’existe pas, ignorez cette étape (Discover est surtout sur mobile).

## 2. Désactiver tous les services Google
- Ouvrez les **Paramètres**.
- Accédez à « Vous et Google » puis « Synchronisation et services Google ».
- Désactivez toutes les options disponibles, telles que :
  - Connexion à Chrome
  - Amélioration des fonctionnalités Chrome
  - Amélioration des suggestions de recherche
  - Amélioration des recherches et de la navigation
  - Touch to Search (si présent)

## 3. Changer le moteur de recherche
- Allez dans **Paramètres > Moteur de recherche**.
- Choisissez DuckDuckGo dans la liste.
- Pour Brave ou Mojeek, cliquez sur « Gérer les moteurs de recherche », puis ajoutez manuellement le moteur souhaité et définissez-le par défaut.

## 4. Confidentialité et sécurité
- Dans **Paramètres**, ouvrez la section « Confidentialité et sécurité ».
- Passez en revue chaque sous-menu pour activer les options de protection maximale.

## 5. Bloquer tous les cookies tiers
- Dans « Confidentialité et sécurité », ouvrez « Cookies et autres données de site ».
- Sélectionnez « Bloquer les cookies tiers ».

## 6. Désactiver toutes les options publicitaires Privacy Sandbox
- Dans « Confidentialité et sécurité », ouvrez « Privacy Sandbox ».
- Désactivez toutes les options liées à la publicité, aux thèmes, suggestions et mesures d’annonces.

## 7. Désactiver l’envoi du signal Do Not Track
- Dans « Cookies et autres données de site », trouvez l’option « Envoyer une demande "Do Not Track" » et désactivez-la.

## 8. Désactiver le préchargement
- Dans « Cookies et autres données de site », repérez l’option de préchargement des pages.
- Sélectionnez « Aucun préchargement ».

## 9. Désactiver la navigation sécurisée
- Dans « Confidentialité et sécurité », ouvrez « Sécurité ».
- Choisissez l’option sans protection.

## 10. Toujours utiliser HTTPS
- Dans « Sécurité », activez l’option « Toujours utiliser une connexion sécurisée ».

## 11. Utiliser un DNS sécurisé
- Dans « Sécurité », activez « Utiliser un DNS sécurisé ».
- Choisissez un fournisseur DNS sécurisé dans la liste ou saisissez l’adresse d’un fournisseur de confiance.

## 12. Bloquer les permissions dans les paramètres de site
- Dans « Confidentialité et sécurité », ouvrez « Paramètres des sites ».
- Pour chaque catégorie, sélectionnez « Bloquer » :
  - Localisation
  - Caméra
  - Microphone
  - Contenu intégré
  - Capteurs de mouvement
  - Presse-papiers
  - Utilisation de l’appareil
  - Connexion tierce partie (si disponible)
  - Vérification automatique (si disponible)

## 13. Désactiver les services Google spécifiques
- Retournez dans « Synchronisation et services Google ».
- Désactivez :
  - Autoriser la connexion à Chrome
  - Aide à l’amélioration des fonctionnalités Chrome
  - Améliorer les suggestions de recherche
  - Améliorer les recherches et la navigation
  - Touch to Search (si présent)

---

**Conseils supplémentaires :**
- Pensez à supprimer régulièrement l’historique et les cookies.
- Utilisez des mots de passe forts et uniques.
- Vérifiez régulièrement les permissions accordées aux sites.

## Automatision de ces contrôles** de confidentialité et sécurité dans Chrome

### **Résumé des paramètres automatisables par stratégie ou registre**

| Contrôle                                   | Automatisable par stratégie/registre |
|--------------------------------------------|:------------------------------------:|
| Désactiver Discover/Google Services        | Oui                                 |
| Changer moteur de recherche                | Oui                                 |
| Bloquer cookies tiers                      | Oui                                 |
| Désactiver Privacy Sandbox/Ads             | Oui                                 |
| Désactiver Do Not Track                    | Oui                                 |
| Désactiver préchargement                   | Oui                                 |
| Désactiver Safe Browsing                   | Oui                                 |
| Forcer HTTPS                               | Oui                                 |
| DNS sécurisé                              | Oui                                 |
| Permissions site (caméra, micro, etc.)     | Oui                                 |
| Désactiver Chrome sign-in                  | Oui                                 |

Pour **automatiser les contrôles de confidentialité et sécurité de Chrome sous Linux**, voici les méthodes principales :

---

## 1. **Utiliser les politiques Chrome (policies)**
- Chrome sous Linux supporte la gestion centralisée via des fichiers de politique JSON placés dans `/etc/opt/chrome/policies/managed/` (ou `/etc/chromium/policies/managed/` pour Chromium).
- Créez un fichier, par exemple :  
  `/etc/opt/chrome/policies/managed/privacy.json`
- Insérez-y les règles souhaitées, par exemple :

```json
{
  "BlockThirdPartyCookies": true,
  "SafeBrowsingEnabled": false,
  "SearchSuggestEnabled": false,
  "AlternateErrorPagesEnabled": false,
  "DnsOverHttpsMode": "secure",
  "DnsOverHttpsTemplates": "https://dns.nextdns.io/votre_id",
  "DefaultSearchProviderEnabled": true,
  "DefaultSearchProviderName": "DuckDuckGo",
  "DefaultSearchProviderSearchURL": "https://duckduckgo.com/?q={searchTerms}",
  "DefaultSearchProviderSuggestURL": "https://duckduckgo.com/ac/?q={searchTerms}",
  "ForceGoogleSafeSearch": false,
  "URLBlacklist": ["chrome://signin/"],
  "PasswordManagerEnabled": false,
  "SigninAllowed": false,
  "MetricsReportingEnabled": false,
  "SpellCheckServiceEnabled": false,
  "AutofillAddressEnabled": false,
  "AutofillCreditCardEnabled": false,
  "CookiesAllowedForUrls": [],
  "CookiesBlockedForUrls": ["*"],
  "HttpsOnlyMode": true,
  "PrivacySandboxAdMeasurementEnabled": false,
  "PrivacySandboxAdTopicsEnabled": false,
  "PrivacySandboxSiteEnabledAdsEnabled": false
}
```
- Redémarrez Chrome pour appliquer les politiques.

---

## 2. **Déploiement par scripts Bash**
- Vous pouvez automatiser la création et la mise à jour des fichiers de politique avec un script bash :

```bash
sudo mkdir -p /etc/opt/chrome/policies/managed
sudo tee /etc/opt/chrome/policies/managed/privacy.json > /dev/null <<EOF
{
  "BlockThirdPartyCookies": true,
  "SafeBrowsingEnabled": false,
  ...
}
EOF
```
- Ajoutez ce script à vos procédures d’installation, d’image système ou de post-installation.

---

## 3. **Gestion des permissions site**
- Les politiques peuvent aussi contrôler les permissions comme caméra, micro, géolocalisation, etc. Exemple :

```json
"DefaultGeolocationSetting": 2,    // 2 = Bloquer
"DefaultCameraSetting": 2,
"DefaultMicrophoneSetting": 2,
"DefaultClipboardSetting": 2,
"DefaultSensorsSetting": 2,
```

---

## 4. **Automatisation avancée**
- Pour des déploiements sur parc, utilisez des outils comme Ansible, Puppet ou SaltStack pour distribuer et maintenir ces fichiers sur tous les postes Linux.

---

## 5. **Pour vérifier les politiques appliquées**
- Tapez dans la barre d’adresse :  
  `chrome://policy`
- Vous verrez la liste des politiques actives.

---

**Résumé** :  
Sous Linux, l’automatisation des contrôles de confidentialité et sécurité de Chrome passe par la gestion des politiques via fichiers JSON dans `/etc/opt/chrome/policies/managed/`. Cette méthode est robuste, centralisée, et adaptée aussi bien à un usage personnel qu’en entreprise.
