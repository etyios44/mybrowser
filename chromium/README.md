# Protection Chromium
## Auteur :  z0S.i0S  - Maj : 06/05/2025

## Introduction

Chromium est un navigateur web libre développé par l’organisation Chromium Project créée par Google en 2008. Chromium sert de base à plusieurs autres navigateurs, dont certains open-source (Brave…) et d'autres propriétaires (Vivaldi Browser, Google Chrome, SRWare Iron, Yandex Browser, Opera et Opera GX, Microsoft Edge, Arc).

Le moteur de rendu de Chromium est Blink, qui remplace WebKit depuis avril 2013. Des versions GNU/Linux, Mac OS X et Windows existent, et il prend en charge les extensions de Chrome. 

## Vulnérabilités du navigateur Chromium

Les vulnérabilités de Chromium sont répertoriées sous les références CVE-2024-12381 et CVE-2024-12382 . Ces deux vulnérabilités sont liées à des problèmes de sécurité de la mémoire qui pourraient permettre à un attaquant d'exploiter des corruptions de tas via une page HTML spécialement conçue.

## Elements modifiables

cf. https://static.open-scap.org/ssg-guides/ssg-chromium-guide-index.html

|Titre|Description|
|---|---|
Désactiver toutes les extensions par défaut|Les extensions sont développées par des sources tierces et sont conçues pour étendre les fonctionnalités de Google Chromium. Comme une extension peut être créée par n'importe qui, toutes les extensions doivent être interdites par défaut. Pour interdire toutes les extensions, définissez ExtensionInstallBlacklist sur * dans le fichier de configuration des politiques de Chromium.
Empêcher les notifications sur le bureau|Chromium permet par défaut aux sites web d'afficher des notifications sur le bureau. Pour désactiver ce paramètre, définissez DefaultNotificationsSetting sur 2 dans le fichier de configuration des politiques de Chromium.
Activer les vérifications en ligne des certificats OCSP/CRL|Les certificats peuvent être compromis, et Chromium doit vérifier que les certificats dans son magasin sont valides en définissant EnableOnlineRevocationChecks sur true dans le fichier de configuration des politiques de Chromium.
Bloquer les plugins par défaut|Par défaut, les sites web sont autorisés à exécuter automatiquement des plugins. Les utilisateurs doivent être invités à autoriser les plugins en définissant DefaultPluginsSetting sur 3 dans le fichier de configuration des politiques de Chromium.
Activer le fournisseur de recherche par défaut|Par défaut, les utilisateurs peuvent modifier les paramètres du fournisseur de recherche. Pour désactiver cela, définissez DefaultSearchProviderEnabled sur true dans le fichier de configuration des politiques de Chromium.
Définir l'URL du fournisseur de recherche par défaut|Spécifie l'URL du fournisseur de recherche par défaut à utiliser. Pour définir l'URL du fournisseur de recherche par défaut, définissez DefaultSearchProviderName sur https://www.google.com dans le fichier de configuration des politiques de Chromium.
Désactiver les API graphiques 3D|Chromium utilise WebGL pour rendre des graphiques en utilisant le GPU, ce qui permet aux sites web d'accéder au GPU. Cela doit être désactivé en définissant Disable3DAPIs sur true dans le fichier de configuration des politiques de Chromium.
Désactiver la fonction de remplissage automatique|La fonction de remplissage automatique suggère des correspondances possibles lorsque les utilisateurs remplissent des formulaires. Pour désactiver cette fonction, définissez AutoFillEnabled sur false dans le fichier de configuration des politiques de Chromium.
Désactiver la recherche et l'installation automatiques des plugins|Chromium détecte, recherche et installe automatiquement les plugins nécessaires. Cela doit être désactivé en définissant DisablePluginFinder sur true dans le fichier de configuration des politiques de Chromium.
Désactiver le traitement en arrière-plan|Chromium peut être configuré pour fonctionner en permanence et traiter en arrière-plan. Cela doit être désactivé en définissant BackgroundModeEnabled sur false dans le fichier de configuration des politiques de Chromium.
Désactiver l'utilisation des mots de passe en clair|Chromium permet aux utilisateurs d'importer et de stocker des mots de passe en clair. Cela doit être désactivé en définissant PasswordManagerAllowShowPasswords sur false dans le fichier de configuration des politiques de Chromium.
Désactiver le partage d'impression dans le cloud|Chromium dispose de capacités de partage dans le cloud, y compris le partage d'imprimantes connectées au système. Cela se fait via un proxy. Pour désactiver le partage d'imprimantes, définissez CloudPrintProxyEnabled sur false dans le fichier de configuration des politiques de Chromium.
Désactiver la capacité de Chromium à traverser les pare-feu|Chromium a la capacité de contourner et d'ignorer le pare-feu du système. Cette capacité doit être désactivée. Pour désactiver ce paramètre, définissez RemoteAccessHostFirewallTraversal sur false dans le fichier de configuration des politiques de Chromium.
Désactiver la synchronisation des données avec Google|Définissez SyncDisabled sur true dans le fichier de configuration des politiques de Chromium.
Désactiver le mode Incognito|Le mode Incognito permet aux utilisateurs de naviguer en privé, ce qui empêche la surveillance et la validation des habitudes de navigation des utilisateurs. Cette capacité doit être désactivée en définissant IncognitoModeAvailability sur 1 dans le fichier de configuration des politiques de Chromium.
Désactiver les rapports de métriques|Chaque fois que Chromium plante, il envoie ses données d'utilisation et liées aux plantages à Google. Cela doit être désactivé en définissant MetricsReportingEnabled sur false dans le fichier de configuration des politiques de Chromium.
Désactiver la prédiction réseau|Pour désactiver la fonction de prédiction réseau, définissez DnsPrefetchingEnabled sur false dans le fichier de configuration des politiques de Chromium.
Désactiver les plugins obsolètes|Les plugins obsolètes doivent être désactivés en définissant AllowOutdatedPlugins sur false dans le fichier de configuration des politiques de Chromium.
Désactiver le gestionnaire de mots de passe de Chromium|Le gestionnaire de mots de passe de Chromium permet de sauvegarder et d'utiliser des mots de passe dans Chromium. Cela doit être désactivé en définissant PasswordManagerEnabled sur false dans le fichier de configuration des politiques de Chromium.
Désactiver tous les plugins par défaut|Les plugins sont développés en interne ou par des sources tierces et sont conçus pour étendre les fonctionnalités de Google Chromium. Tous les plugins doivent être interdits par défaut. Pour interdire tous les plugins, définissez DisabledPlugins sur * dans le fichier de configuration des politiques de Chromium.
Désactiver les pop-ups|Chromium permet de gérer si des fenêtres pop-up indésirables apparaissent ou non. Pour désactiver les pop-ups, définissez DefaultPopupsSetting sur 2 dans le fichier de configuration des politiques de Chromium.
Désactiver les schémas de protocole non sécurisés et obsolètes|Chaque accès à une URL est géré par le navigateur en fonction du "schéma" de l'URL. Pour désactiver les schémas de protocole non sécurisés et obsolètes, définissez URLBlacklist sur javascript://* dans le fichier de configuration des politiques de Chromium.
Désactiver les mots de passe enregistrés|Désactivez en définissant ImportSavedPasswords sur false dans le fichier de configuration des politiques de Chromium.
Désactiver la suggestion de recherche|Chromium essaie de deviner ce que les utilisateurs recherchent lorsqu'ils saisissent des données de recherche dans la barre de recherche. Cela doit être désactivé en définissant SearchSuggestEnabled sur false dans le fichier de configuration des politiques de Chromium.
Désactiver les cookies de session|Pour désactiver les cookies de session uniquement pour les sites, définissez CookiesSessionOnlyForUrls sur none dans le fichier de configuration des politiques de Chromium.
Désactiver les cookies tiers|Les cookies tiers ne doivent pas être activés. Pour désactiver les cookies tiers, définissez BlockThirdPartyCookies sur true dans le fichier de configuration des politiques de Chromium.
Désactiver le suivi de localisation|Le suivi de localisation est activé par défaut et peut suivre les habitudes de navigation des utilisateurs. Le suivi de localisation doit être désactivé en définissant DefaultGeolocationSetting sur 2 dans le fichier de configuration des politiques de Chromium.
Activer uniquement les plugins approuvés|Une organisation peut avoir besoin d'utiliser des plugins développés en interne ou par des tiers. Tout plugin approuvé par l'organisation doit être activé. Pour activer les plugins approuvés, définissez EnabledPlugins sur la liste des plugins approuvés par l'organisation dans le fichier de configuration des politiques de Chromium.
Activer la sauvegarde de l'historique du navigateur|Les utilisateurs peuvent activer ou désactiver la sauvegarde de l'historique du navigateur dans Chromium. L'historique du navigateur doit être conservé en définissant SavingBrowserHistoryDisabled sur false dans le fichier de configuration des politiques de Chromium.
Activer la recherche cryptée|Spécifie l'URL du moteur de recherche utilisé lors d'une recherche par défaut. L'URL doit contenir la chaîne {searchTerms}. Pour définir l'URL du moteur de recherche, définissez DefaultSearchProviderSearchURL sur https://www.google.com/#q={searchTerms} dans le fichier de configuration des politiques de Chromium.
Activer la fonction de navigation sécurisée|Chromium a la capacité de vérifier les URL pour détecter les logiciels malveillants et le phishing associés aux sites web via la fonction de navigation sécurisée. Cela peut être activé en définissant SafeBrowsingEnabled sur true dans le fichier de configuration des politiques de Chromium.
Activer uniquement les extensions approuvées|Une organisation peut avoir besoin d'utiliser des extensions développées en interne ou par des tiers. Toute extension approuvée par l'organisation doit être activée. Pour activer les extensions approuvées, définissez ExtensionInstallWhitelist sur oiigbmnaadbkfbmpbfijlflahbdbdgdf dans le fichier de configuration des politiques de Chromium. S'il n'y a pas d'extensions approuvées, ExtensionInstallWhitelist doit être défini sur oiigbmnaadbkfbmpbfijlflahbdbdgdf.
Définir le schéma d'authentification HTTP de Chromium|Pour définir le schéma d'authentification HTTP par défaut de Chromium, définissez AuthSchemes sur negotiate dans le fichier de configuration des politiques de Chromium.
Exiger l'autorisation des plugins obsolètes|Chromium doit demander aux utilisateurs une autorisation pour exécuter des plugins obsolètes. Cela peut être activé en définissant AlwaysAuthorizePlugins sur false dans le fichier de configuration des politiques de Chromium.
S'assurer que le fichier de configuration des politiques de Chromium existe|Chromium peut être configuré avec de nombreuses politiques et paramètres. Ces paramètres peuvent être définis de manière à ce qu'un utilisateur ne puisse pas les modifier. Pour empêcher les utilisateurs de définir ou de modifier les paramètres de Chromium, un fichier JavaScript Object Notation (JSON) (extension .json) doit exister dans /etc/chromium/policies/managed.
Définir la page d'accueil par défaut|Lorsqu'un navigateur est démarré, la première page web affichée est la "page d'accueil". Bien que l'utilisateur puisse sélectionner la page d'accueil, la page d'accueil par défaut doit être définie pour afficher une page approuvée. Pour définir la page d'accueil par défaut, définissez HomepageLocation sur about:blank dans le fichier de configuration des politiques de Chromium.
Activer les plugins uniquement pour les URL approuvées|Dans certains cas, les plugins utilisés par des sites web approuvés par l'organisation peuvent être autorisés à être utilisés par ces sites. Configurez les URL approuvées autorisées à exécuter des plugins en définissant PluginsAllowedForUrls sur les URL approuvées par l'organisation dans le fichier de configuration des politiques de Chromium. S'il n'y a pas d'URL approuvées, cela doit être défini sur none.

## Default Settings

cf. https://github.com/ungoogled-software/ungoogled-chromium/blob/master/docs/default_settings.md

Vanilla Chromium settings are not often changed by ungoogled-chromium, however there are some exceptions.  
Below is a list of the documented changes to the default Chromium settings.

Setting | New State | Location
-- | -- | --
Allow sites to check if you have payment methods saved | Disabled | chrome://settings/payments
Ask where to save each file before downloading | Enabled | chrome://settings/downloads
Auto sign-in | Disabled | chrome://settings/passwords
Block third-party cookies | Enabled | chrome://settings/cookies
Continue running background apps when Chromium is closed | Disabled | chrome://settings/system
Hyperlink auditing (\<a ping>) | Disabled | NA
Link Doctor | Disabled | NA
Offer to save passwords | Disabled | chrome://settings/passwords
Payment autofill | Disabled | chrome://settings/payments
Preload pages | Disabled | chrome://settings/cookies
Search suggestions | Disabled | chrome://settings/syncSetup
Show bookmark bar | Enabled | chrome://settings/appearance
WebRTC IP handling policy | Disable Non-Proxied UDP | `--webrtc-ip-handling-policy`

## Liste des versions

```sh
Sécurisation de l’anonymat sur Chromium
│
├── 1. Mises à jour et versions majeures
│   ├── 2025 : v124+
│   │   └── Correctifs de sécurité récents, alignement sur les API Privacy Sandbox (blocage cookies tiers, nouvelles API publicitaires)
│   ├── 2024 : v122-v123
│   │   ├── Privacy Sandbox intégré (API Topics, Attribution, Protected Audience)
│   │   └── Améliorations sur la gestion des autorisations ponctuelles (caméra, micro, localisation)
│   ├── 2019 : v76
│   │   └── API FileSystem accessible en navigation privée (empêche la détection du mode incognito via cette API)
│   ├── 2012 : v23
│   │   └── Support de l’en-tête Do Not Track (signal volontaire de non-suivi)
│   └── 2008 : v1.0
│       └── Lancement du projet Chromium, navigation privée dès la première version
│
├── 2. Navigation privée (Incognito)
│   ├── Séparation stricte des sessions utilisateur (pas d’accès à l’historique ou aux cookies des autres fenêtres)
│   ├── Effacement automatique des cookies, historiques, cache, données de formulaire à la fermeture
│   ├── Extensions désactivées par défaut (sauf activation manuelle)
│   ├── Depuis v76 : API FileSystem disponible, rendant la détection du mode privé plus difficile
│   └── Limites : l’adresse IP et l’activité réseau restent visibles pour les sites et le FAI
│
├── 3. Fonctionnalités de confidentialité avancées
│   ├── Privacy Sandbox (v122+, 2024)
│   │   ├── Topics API : attribution de thèmes d’intérêt, partagés de façon agrégée, sans historique détaillé
│   │   ├── Protected Audience API : ciblage publicitaire sans identifiant individuel, regroupement en cohortes anonymes
│   │   ├── Attribution Reporting API : mesure des conversions sans suivi individuel, données agrégées et bruitées
│   │   └── Traitement local des données de navigation (moins de fuite vers les serveurs externes)
│   ├── Do Not Track (v23+, 2012)
│   │   └── Signal envoyé aux sites pour demander l’absence de suivi (non contraignant)
│   ├── Navigation sécurisée
│   │   └── Vérification des URL sur listes noires (mode standard : envoi de hash partiel à Google ; mode renforcé : envoi complet)
│   └── Gestion des autorisations ponctuelles (v122+, 2024)
│       └── Accès temporaire à la caméra, micro, localisation, réinitialisé à chaque session
│
├── 4. Outils complémentaires
│   ├── VPN ou Proxy : masque l’IP réelle, chiffre le trafic réseau
│   ├── Extensions privacy (uBlock Origin, Privacy Badger) : blocage des scripts de tracking, cookies tiers restants, fingerprinting
│   └── Changement du moteur de recherche par défaut pour limiter la collecte de données
│
├── 5. Paramètres et bonnes pratiques
│   ├── Ne pas activer la synchronisation Google (pas de transmission des favoris, historiques, mots de passe)
│   ├── Bloquer ou supprimer régulièrement cookies et données de site
│   ├── Restreindre les autorisations accordées aux sites (caméra, micro, localisation)
│   ├── Utiliser un DNS sécurisé (DNS-over-HTTPS)
│   ├── Désactiver les API de tracking publicitaire dans Privacy Sandbox
│   └── Supprimer régulièrement historique et caches
│
├── 6. Limitations et transparence
│   ├── Chromium envoie tout de même des requêtes à Google (mises à jour, extensions, Safe Browsing)
│   ├── Pas de collecte de crash reports ni de statistiques d’usage par défaut, mais certains modules contactent Google
│   ├── Pas de mise à jour automatique : il faut télécharger manuellement les nouvelles versions pour rester protégé
│   ├── Sandbox de sécurité parfois désactivée selon les distributions ou compilations
│   └── Projets dérivés comme Ungoogled Chromium suppriment les connexions résiduelles à Google
```