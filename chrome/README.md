# Protection Chrome

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

