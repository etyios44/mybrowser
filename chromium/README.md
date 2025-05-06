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
Disable All Extensions by Default|Extensions are developed by third party sources and are designed to extend Google Chromium's functionality. As an extension can be made by anyone, all extensions should be blacklisted from installation by default. To blacklist all extensions, set the ExtensionInstallBlacklist to * in the Chromium policy file.
Prevent Desktop Notifications|Chromium by default allows websites to display notifications on the desktop. To disable this setting, set DefaultNotificationsSetting to 2 in the Chromium policy file.
Enable Online OCSP/CRL Certificate Checks|Certificates can become compromised, and Chromium should check that the certificates in its store are valid by setting EnableOnlineRevocationChecks to true in the Chromium policy file.
Block Plugins by Default|By default, websites are allowed to automatically run plugins. Users should be prompted to allow plugins to execute plugins by setting DefaultPluginsSetting to 3 in the Chromium policy file.
Enable the Default Search Provider|By default users, can change search provider settings. To disable this, set DefaultSearchProviderEnabled to true in the Chromium policy file.
Set the Default Search Provider's URL|Specifies the URL of the default search provider that is to be used. To set the URL of the default search provider, set DefaultSearchProviderName to https://www.google.com in the Chromium policy file.|
|Disable the 3D Graphics APIs|Chromium uses WebGL to render graphics using the GPU which allows website access to the GPU. This should be disabled by setting Disable3DAPIs to true in the Chromium policy file.
Disable the AutoFill Feature|The AutoFill feature suggests possible matches when users are filling in forms. To disable the AutoFill feature, set AutoFillEnabled to false in the Chromium policy file.
Disable Automatic Search And Installation of Plugins|Chromium will automatically detect, search, and install plugins as required. This should be disabled by setting DisablePluginFinder to true in the Chromium policy file.
Disable Background Processing|Chromium can be set to run at all times and process in the background. This should be disabled by setting BackgroundModeEnabled to false in the Chromium policy file.
Disable Use of Cleartext Passwords|Chromium allows users to import and store passwords in cleartext. This should be disabled by setting PasswordManagerAllowShowPasswords to false in the Chromium policy file.
Disable Cloud Print Sharing|Chromium has cloud sharing capabilities including sharing printers connected to the system. This is done via a proxy. To disable printer sharing, set CloudPrintProxyEnabled to false in the Chromium policy file.
Disable Chromium's Ability to Traverse Firewalls|Chromium has the ability to bypass and ignore the system firewall. This ability should be disabled. To disable this setting, set RemoteAccessHostFirewallTraversal to false in the Chromium policy file.
Disable Data Synchronization to Google|SyncDisabled to true in the Chromium policy file.
Disable Incognito Mode|Incognito Mode allows users to browse in private which prevents monitoring and validating user browsing habits. This capability should be disabled by setting IncognitoModeAvailability to 1 in the Chromium policy file.
Disable Metrics Reporting|Whenever Chromium crashes, it sends its usage and crash-related data to Google. This should be disabled by setting MetricsReportingEnabled to false in the Chromium policy file.
Disable Network Prediction|To disable the network prediction feature, set DnsPrefetchingEnabled to false in the Chromium policy file.
Disable Outdated Plugins|Outdated plugins should be disabled by setting AllowOutdatedPlugins to false in the Chromium policy file.
Disable Chromium Password Manager|Chromium Password Manager allows the saving and using of passwords in Chromium. This should be disabled by setting PasswordManagerEnabled to false in the Chromium policy file.
Disable All Plugins by Default|Plugins are developed internally or by third party sources and are designed to extend Google Chromium's functionality. All plugins should be blacklisted from installation by default. To blacklist all plugins set DisabledPlugins to * in the Chromium policy file.
Disable Popups|Chromium allows you to manage whether or not unwanted pop-up windows appear. To disable pop-ups, set DefaultPopupsSetting to 2 in the Chromium policy file.
Disable Insecure And Obsolete Protocol Schemas|Each access to a URL is handled by the browser according to the URL's "scheme". The "scheme" of a URL is the section before the ":". The term "protocol" is often mistakenly used for a "scheme". The difference is that the scheme is how the browser handles a URL and the protocol is how the browser communicates with a service. To disable insecure and obsolete protocol schema, set URLBlacklist to javascript://* in the Chromium policy file.
Disable Saved Passwords|Disable by setting ImportSavedPasswords to false in the Chromium policy file.
Disable Search Suggestion|Chromium tries to guess what users are searching for when users enter search data in the search Omnibox. This should be disabled by setting SearchSuggestEnabled to false in the Chromium policy file.
Disable Session Cookies|To disable session only cookies sites, set CookiesSessionOnlyForUrls to none in the Chromium policy file.
Disable 3rd Party Cookies|Third party cookies should be be enabled. To disable third party cookies, set BlockThirdPartyCookies to true in the Chromium policy file.
Disable Location Tracking|Location tracking is enabled by default and can track user's browsing habits. Location tracking should be disabled by setting DefaultGeolocationSetting to 2 in the Chromium policy file.
Enable Only Approved Plugins|An organization might need to use an internal or third party developed plugins. Any organizationally approved plugin should be enabled. To enable approved plugins, set EnabledPlugins to the list of organizationally approved plugins in the Chromium policy file.
Enable Saving the Browser History|Users can enable or disable the saving of browser history in Chromium. Browser history should be retained by setting SavingBrowserHistoryDisabled to false in the Chromium policy file.
Enable Encrypted Searching|Specifies the URL of the search engine used when doing a default search. The URL should contain the string {searchTerms}. To set the URL of the search engine, set DefaultSearchProviderSearchURL to https://www.google.com/#q={searchTerms} in the Chromium policy file.
Enable the Safe Browsing Feature|Chromium has the capability to check URLs for known malware and phishing associated with websites through the Safe Browsing Feature. This can be enabled by setting SafeBrowsingEnabled to true in the Chromium policy file.
Enable Only Approved Extensions|An organization might need to use an internal or third party developed extension. Any organizationally approved extenstion should be enabled. To enable approved extensions, set ExtensionInstallWhitelist to oiigbmnaadbkfbmpbfijlflahbdbdgdf in the Chromium policy file. If there are no approved extensions, ExtensionInstallWhitelist should be set to oiigbmnaadbkfbmpbfijlflahbdbdgdf.
Set Chromium's HTTP Authentication Scheme|To set the default Chromium's HTTP Authentication Scheme, set AuthSchemes to negotiate in the Chromium policy file.
Require Outdated Plugins to be Authorized|Chromium should prompt users for authorization to run outdated plugins. This can be enabled by setting AlwaysAuthorizePlugins to false in the Chromium policy file.
 Ensure the Chromium Policy Configuration File Exists|Chromium can be configured with numerous policies and settings. These settings can be set so that a user is unable to edit or change them. To prevent users from setting or changing Chromium settings, a JavaScript Object Notation (JSON) file (contains the .json extension) must exist in /etc/chromium/policies/managed.
Set the Default Home Page|When a browser is started the first web page displayed is the "home page". While the home page can be selected by the user, the default home page needs to be defined to display an approved page. To set the default home page, set HomepageLocation to about:blank in the Chromium policy file.
Enable Plugins for Only Approved URLs|In some cases, plugins utilized by organizationally approved websites may be allowed to be used by those websites, configure the approved URLs allowed to run plugins by setting PluginsAllowedForUrls to organizationally approved URLs in the Chromium policy file. If there are no approved URLs, this should be set to none

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
