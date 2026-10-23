# 🖥️ **Mon serveur personnel sous Linux Mint**
<br><br>
## **Présentation**
<br>
Conception et administration d'un serveur DIY
sous Linux Mint, dédié à l'auto-hébergement,
au stockage, à l'automatisation et à
l'intelligence artificielle locale.

<br>
## **1. Configuration matérielle**
<br>
Mon serveur repose sur une configuration PC assemblée et évolutive, adaptée à l'auto-hébergement et à l'exécution de modèles d'intelligence artificielle en local.

| Composant | Configuration |
|---|---|
| Processeur | AMD Ryzen 5 4500 — 6 cœurs / 12 threads |
| Carte mère | ASUS PRIME B450M-A II |
| Mémoire vive | 16 Go DDR4 — extension prévue |
| Carte graphique | AMD Radeon RX 6600 XT — 8 Go VRAM |
| Disque système | SSD NVMe WD_BLACK — 1 To |
| Système d'exploitation | Linux Mint 22.3 |

Cette architecture me permet de faire évoluer indépendamment la mémoire, le processeur, le stockage et la carte graphique, sans dépendre d'un matériel NAS propriétaire.

<br><br>
## **2. Système d'exploitation**
<br>
🐧 Linux Mint 22.3 — Une solution libre, stable et polyvalente

Pour mon serveur personnel, j'ai choisi Linux Mint 22.3, une distribution GNU/Linux basée sur Ubuntu LTS.

Contrairement aux systèmes d'exploitation spécialisés dans le stockage, comme TrueNAS ou Unraid, Linux Mint me permet de disposer d'un environnement généraliste, entièrement personnalisable et adapté à de multiples usages.

Ce choix repose sur plusieurs critères :

- **Open source** : utilisation d'un système libre, sans licence commerciale obligatoire.

- **Stabilité** : une base Ubuntu LTS bénéficiant de mises à jour de sécurité et d'un support à long terme.

- **Polyvalence** : possibilité d'utiliser simultanément des applications classiques, des services réseau, des conteneurs Docker et des outils d'intelligence artificielle.

- **Compatibilité matérielle** : prise en charge d'une grande variété de composants et de périphériques.

- **Administration** : accès complet au système via le terminal, SSH et les outils d'administration Linux.

- **Évolutivité** : liberté d'installer, modifier ou supprimer des services selon mes besoins.
  
<br>
⚙️ **Administration et gestion du système**

L'administration du serveur repose sur plusieurs outils et technologies :

|Technologie|Utilisation|
|---|---|
|APT|Installation et mise à jour des logiciels|
|systemd|Gestion des services et démarrage automatique|
|SSH|Administration distante sécurisée|
|UFW|Gestion des règles du pare-feu|
|Docker / Docker Compose|Déploiement et isolation des applications|
|Bash|Scripts de maintenance et d'automatisation|
|Cron|Planification des tâches récurrentes|
|RustDesk|Accès et assistance à distance|
<br>
🔐 **Sécurité et maîtrise des données**

L'un des objectifs principaux de cette installation est de conserver le contrôle de mon infrastructure et de mes données.

Je privilégie une approche Local-First, dans laquelle les applications et les données sont hébergées localement chaque fois que cela est possible.

Cette démarche permet notamment de :

- Limiter la dépendance aux fournisseurs de services cloud.

- Conserver les données personnelles sur une infrastructure maîtrisée.

- Contrôler les services actifs et les accès réseau.

- Adapter les règles de sécurité aux besoins réels.

- Maintenir les applications et les services indépendamment les uns des autres.
<br>
🎯 **Pourquoi Linux Mint plutôt qu'Ubuntu Server ou Debian ?**

Ubuntu Server et Debian auraient également été des choix pertinents pour cette installation.

Cependant, j'ai privilégié Linux Mint pour conserver un environnement graphique complet, tout en disposant des outils d'administration et des fonctionnalités serveur de Linux.

Cette approche facilite certaines opérations de maintenance, l'utilisation d'applications graphiques et les expérimentations locales, sans renoncer à l'administration en ligne de commande.

Mon objectif n'était pas simplement de construire un NAS, mais de disposer d'une véritable plateforme Linux polyvalente, capable d'évoluer avec mes projets.

<br><br>
## **3. Architecture et stockage**
<br>
🖥️ **Une architecture DIY modulaire et évolutive**

Mon serveur repose sur une architecture PC classique, assemblée et configurée pour répondre à mes besoins en stockage, auto-hébergement, automatisation et intelligence artificielle locale.

Contrairement à un NAS traditionnel dont le nombre de baies est généralement fixé dès l'achat, cette architecture permet une évolution progressive des capacités matérielles.

L'objectif est de disposer d'une infrastructure polyvalente, évolutive et indépendante d'un écosystème propriétaire.

Cette approche offre plusieurs avantages :

- **Évolutivité matérielle** : ajout ou remplacement de disques, contrôleurs de stockage, mémoire RAM et autres composants.

- **Liberté logicielle** : choix des systèmes de fichiers et des outils de gestion des données.

- **Maintenance simplifiée** : remplacement individuel des composants défectueux.

- **Optimisation des ressources** : adaptation du matériel aux services réellement utilisés.

- **Maîtrise des coûts** : possibilité de réutiliser des composants existants et d'effectuer les évolutions progressivement.
<br>
💾 **Organisation du stockage**

J'ai choisi de séparer le stockage système des espaces destinés aux données et aux applications.

**SSD NVMe — Système et applications**

Le système d'exploitation Linux Mint est installé sur un SSD NVMe WD_BLACK de 1 To.

Ce disque accueille notamment :

- Le système d'exploitation et ses composants.

- Les logiciels et outils d'administration.

- Les applications et services installés localement.

- Les environnements d'exécution nécessaires à l'intelligence artificielle.

- Les fichiers et configurations des services, selon leur emplacement d'installation.

Le NVMe offre des débits élevés et une faible latence, particulièrement intéressants pour le démarrage du système, le chargement des applications et les accès fréquents aux fichiers.

**Disques de données — Stockage et auto-hébergement**

Les disques de données sont utilisés pour les besoins de stockage du serveur, notamment :

Les bibliothèques multimédias.

Les documents et fichiers personnels.

Les données persistantes des applications Docker.

Les archives et espaces de sauvegarde.

Les fichiers utilisés par les différents services auto-hébergés.

Cette séparation logique facilite l'organisation des données et permet d'envisager des évolutions de capacité sans réinstaller le système d'exploitation.
<br>
<br>
🔄 **Redondance et protection des données**

Pour la gestion des disques, je privilégie une approche simple et compréhensible, fondée sur des disques indépendants ou des volumes en miroir lorsque la disponibilité des données le justifie.

Le RAID 1, par exemple, permet de conserver une copie identique des données sur deux disques.

En cas de panne de l'un des disques, les données restent accessibles depuis l'autre, sous réserve du bon fonctionnement du volume.

Cette méthode présente plusieurs avantages :

- Une architecture relativement simple à administrer.

- Une bonne tolérance à la panne d'un disque dans un miroir à deux disques.

- Une reconstruction ne nécessitant pas de calcul de parité.

- Une organisation adaptée à des besoins de stockage ciblés.

En contrepartie, un miroir de deux disques ne fournit qu'une capacité utile équivalente à celle du plus petit disque.

Je préfère cette approche aux configurations à parité lorsque la simplicité de maintenance et de récupération constitue ma priorité.

**Il est toutefois essentiel de distinguer redondance et sauvegarde : un RAID 1 ne protège pas contre la suppression accidentelle, les erreurs logicielles, les ransomwares ou la destruction de l'ensemble du matériel.**
<br><br>
🔧 **Une capacité d'extension sans limitation de licence**

L'un des principaux avantages de mon architecture est de ne pas dépendre d'une licence logicielle déterminant le nombre de disques autorisés.

L'ajout de nouveaux supports de stockage dépend principalement :

- Du nombre de ports SATA et d'emplacements M.2 disponibles.

- Des possibilités d'extension PCIe.

- De la capacité de l'alimentation électrique.

- De l'espace disponible dans le boîtier.

- Des limites techniques du système et des contrôleurs utilisés.

Il est donc possible d'augmenter progressivement la capacité de stockage sans devoir remplacer l'ensemble de l'infrastructure.
<br>

🌐 **Une architecture orientée Local-First**

Mon installation s'inscrit dans une démarche Local-First, consistant à privilégier l'hébergement et le traitement des données directement sur mon infrastructure.

Les services peuvent communiquer sur le réseau local, sans nécessiter systématiquement une connexion à des plateformes cloud.

Cette approche permet de conserver davantage de contrôle sur les données, les applications et leur disponibilité.
<br><br>
🎯 **Objectif de cette architecture**

Mon objectif est de maintenir une infrastructure capable d'évoluer avec mes besoins, sans dépendre d'un matériel NAS spécialisé ou d'un système de licence limitant les extensions.

**Je privilégie une architecture modulaire, administrable et réparable, dans laquelle chaque composant peut évoluer indépendamment.**

Ce choix constitue également un excellent support d'apprentissage pour approfondir mes compétences en administration Linux, gestion du stockage, maintenance matérielle et infrastructure système.

<br><br>
## **4. Applications et services hébergés**
<br>
🐳** Une infrastructure polyvalente basée sur Docker**

Mon serveur Linux Mint ne se limite pas au stockage de fichiers. Il constitue une plateforme d'auto-hébergement sur laquelle fonctionnent plusieurs applications et services destinés à différents usages.

J'utilise principalement Docker et Docker Compose pour déployer, organiser et administrer mes applications.

La conteneurisation permet notamment de :

- Isoler les applications et leurs dépendances.

- Simplifier le déploiement et les mises à jour.

- Centraliser les configurations dans des fichiers YAML.

- Gérer les volumes persistants pour conserver les données.

- Redémarrer automatiquement les services après une interruption.

- Faciliter la migration et la restauration des applications.

Certains services, notamment les outils d'intelligence artificielle, sont également installés directement sur le système lorsque cela répond mieux à leurs besoins matériels ou logiciels.
<br><br>
🤖 **4.1. Intelligence artificielle locale**

L'intelligence artificielle constitue l'un des axes importants de mon infrastructure.

Mon objectif est de pouvoir exécuter différents modèles de langage et développer des agents IA spécialisés, directement sur mon propre matériel.

|Application|Fonction|
|---|---|
|Ollama|Exécution et gestion de modèles de langage locaux|
|Open WebUI|Interface web pour interagir avec les modèles IA|
|llama.cpp|Exécution et expérimentation de modèles avec accélération matérielle|
|Service mémoire SQLite|Stockage local d'informations destinées aux agents IA|

J'expérimente notamment avec des modèles tels que Qwen, Mistral et Gemma.

L'utilisation de ma carte graphique AMD Radeon RX 6600 XT permet d'accélérer certains traitements grâce à son GPU et à ses 8 Go de mémoire vidéo.

Cette architecture me permet d'expérimenter différents usages :

Assistants conversationnels locaux.

Génération et analyse de code informatique.

Analyse de documents.

Automatisation de tâches.

Développement d'agents IA spécialisés.

Communication entre les modèles IA et les services auto-hébergés.

L'objectif est de conserver la maîtrise de mes données et de limiter le recours aux services d'intelligence artificielle hébergés dans le cloud.
<br><br>
⚙️ **4.2. Automatisation et orchestration**

**n8n — Automatisation des processus**

J'utilise n8n pour concevoir et exécuter des workflows automatisés.

Cet outil permet de relier différents services, API et applications à travers une interface visuelle.

Les usages envisagés ou expérimentés comprennent :

- L'automatisation de tâches récurrentes.

- La communication entre applications.

- L'intégration de modèles IA locaux.

- Le traitement et la transmission de données.

- La création de workflows associant plusieurs agents et outils.

L'auto-hébergement de n8n me permet de conserver le contrôle sur son environnement d'exécution et les données traitées.
<br><br>
📚 **4.3. Documentation et productivité**

**BookStack — Base documentaire personnelle**

BookStack est une application de gestion documentaire auto-hébergée.

Je l'utilise pour disposer d'un espace structuré permettant d'organiser des informations techniques, des procédures et des documentations.

Ses fonctionnalités comprennent :

- Organisation des documents en livres, chapitres et pages.

- Édition des contenus depuis une interface web.

- Recherche dans la documentation.

- Gestion des utilisateurs et des permissions.

- Stockage des informations dans une base MariaDB.

Cette solution complète mon utilisation de GitHub, davantage orientée vers la documentation publique de mes projets.
<br><br>
🎵 **4.4. Services multimédias**

Mon serveur héberge également plusieurs applications permettant de gérer et de diffuser des contenus multimédias sur mon réseau local.

|Application|Fonction|
|---|---|
|Plex|Organisation et diffusion de bibliothèques vidéo|
|Navidrome|Serveur de streaming musical personnel|
|PsySonic|Accès aux services musicaux compatibles Subsonic|
|MeTube|Interface web de gestion de téléchargements vidéo|
|Pinchflat|Automatisation et organisation de téléchargements vidéo|
|Spotify Downloader|Gestion de téléchargements audio|

Ces services me permettent de centraliser mes bibliothèques et d'y accéder depuis différents équipements.

Ils constituent également un terrain d'expérimentation pour la gestion des volumes Docker, des permissions Linux, des montages de disques et des accès réseau.
<br><br>
🔎 **4.5. Recherche et services web**

**SearXNG — Moteur de recherche auto-hébergé**

SearXNG est un métamoteur de recherche open source qui agrège les résultats de plusieurs moteurs.

Son auto-hébergement permet de disposer d'une interface de recherche personnalisable et de limiter la dépendance à une interface de recherche commerciale unique.

Il peut également être intégré à des outils d'automatisation ou à certains assistants IA.
<br><br>
🔐 **4.6. Administration et accès distant**

L'administration de mon infrastructure repose sur plusieurs outils complémentaires.

|Outil|Utilisation|
|---|---|
|SSH|Administration du serveur en ligne de commande|
|RustDesk|Accès graphique à distance|
|UFW|Configuration du pare-feu Linux|
|systemd|Gestion et supervision des services système|
|Docker Compose|Gestion des applications conteneurisées|
|Cron|Exécution planifiée de scripts et de sauvegardes|

Cette organisation permet de gérer les applications, consulter les journaux, contrôler les services et intervenir sur le serveur sans nécessiter systématiquement un accès physique.
<br><br>
🧩 **4.7. Une architecture en constante évolution**

L'un des avantages de cette infrastructure est sa capacité à accueillir de nouveaux services sans nécessiter la mise en place d'un serveur physique supplémentaire pour chaque application.

Docker facilite cette approche modulaire : chaque application peut disposer de ses propres dépendances, paramètres et volumes de données.

L'ensemble constitue un environnement d'expérimentation permettant d'approfondir plusieurs domaines techniques :

Administration Linux et gestion des services.

Conteneurisation et orchestration d'applications.

Gestion des réseaux et des ports.

Gestion des volumes et de la persistance des données.

Automatisation et scripting.

Déploiement de modèles d'intelligence artificielle.

Maintenance, diagnostic et résolution d'incidents.
<br><br>
🎯**Objectif de cette infrastructure**

Mon objectif est de disposer d'un environnement informatique autonome, polyvalent et évolutif, capable de répondre à mes besoins personnels tout en constituant un véritable laboratoire technique.

Au-delà des applications hébergées, cette infrastructure me permet de mettre en pratique et de développer continuellement mes compétences en systèmes, réseaux, Linux, Docker et automatisation.

<br><br>
## **5. Sauvegarde et synchronisation**
<br>
💾 **Une stratégie de protection des données locale et maîtrisée**

La sauvegarde des données constitue un élément essentiel de mon infrastructure.

Mon objectif est de conserver la maîtrise de mes fichiers, des configurations de mes applications et de mes données personnelles, tout en limitant la dépendance aux solutions de stockage cloud.

Pour cela, je privilégie une approche reposant sur plusieurs principes :

- Sauvegarde locale : conservation des données sur des supports que je contrôle.

- Automatisation : utilisation de scripts et de tâches planifiées pour limiter les interventions manuelles.

- Simplicité : privilégier des mécanismes compréhensibles, faciles à maintenir et à restaurer.

- Indépendance : utiliser des outils libres et des formats de fichiers accessibles.

- Évolutivité : adapter la stratégie de sauvegarde à l'évolution des services et des volumes de données.

Cette organisation s'inscrit dans ma démarche Local-First, qui privilégie le traitement et la conservation des données sur une infrastructure personnelle.
<br><br>
🔄 **5.1. Syncthing — Synchronisation des fichiers**

Syncthing est une solution open source permettant de synchroniser des fichiers directement entre plusieurs équipements.

Contrairement aux services de synchronisation cloud traditionnels, Syncthing ne nécessite pas de serveur central appartenant à un fournisseur externe.

Ses principales fonctionnalités comprennent :

- Synchronisation automatique entre plusieurs appareils.

- Communication chiffrée entre les équipements.

- Synchronisation bidirectionnelle ou unidirectionnelle selon la configuration.

- Détection des modifications de fichiers.

- Gestion des conflits et possibilité de conserver différentes versions des fichiers.

- Fonctionnement sur un réseau local, avec possibilité de synchronisation à distance.

Syncthing constitue ainsi une solution intéressante pour maintenir des fichiers cohérents entre plusieurs machines Linux, Windows ou d'autres équipements compatibles.

Point important : la synchronisation ne remplace pas une sauvegarde. Une suppression ou une modification accidentelle peut également être propagée aux autres appareils.

La gestion des versions et les sauvegardes indépendantes restent donc nécessaires pour protéger les données.
<br><br>
🐳 **5.2. Sauvegarde des applications Docker**

Les applications conteneurisées nécessitent une attention particulière concernant la conservation de leurs données.

Contrairement aux conteneurs eux-mêmes, qui peuvent être recréés à partir de leurs images, les données persistantes doivent être protégées.

Les éléments concernés comprennent notamment :

- Les fichiers compose.yaml et les configurations Docker.

- Les volumes persistants.

- Les bases de données.

- Les paramètres des applications.

- Les fichiers et documents générés par les services.

Cette distinction entre conteneurs et données persistantes facilite la maintenance, les mises à jour et la restauration des applications.

Pour les bases de données, une sauvegarde cohérente nécessite généralement un export adapté ou un mécanisme garantissant leur intégrité, plutôt qu'une simple copie de fichiers pendant leur utilisation.
<br><br>
📚 **5.3. BookStack — Sauvegardes automatisées et chiffrées**

Mon installation BookStack repose sur une architecture Docker associant l'application à une base de données MariaDB.

Pour protéger cette documentation, j'ai mis en place un mécanisme de sauvegarde automatisée.

Caractéristiques de cette sauvegarde :

|Élément|Configuration|
|---|---|
|Application|BookStack|
|Base de données|MariaDB|
|Environnement|Docker|
|Automatisation|Cron|
|Fréquence|Quotidienne|
|Heure d'exécution|23 h 30|
|Protection|Sauvegarde chiffrée|

L'objectif est de conserver les informations nécessaires à la restauration de la documentation en cas de dysfonctionnement, de mauvaise manipulation ou de perte de données.

Cette automatisation permet également de limiter les oublis liés aux sauvegardes manuelles.
<br><br>
🗄️ **5.4. Stockage et redondance**

Pour la protection des données, je privilégie une organisation simple, fondée sur des disques indépendants et, lorsque cela est pertinent, des volumes en miroir RAID 1.

Le RAID 1 permet de maintenir les données accessibles en cas de panne d'un disque dans un miroir fonctionnel.

Cependant, la redondance n'est pas une sauvegarde.

|Solution|Objectif principal|
|---|---|
|RAID 1|Maintenir la disponibilité en cas de panne d'un disque|
|Sauvegarde indépendante|Permettre la récupération de données perdues ou altérées|
|Syncthing|Synchroniser des fichiers entre équipements|
|Sauvegarde chiffrée|Protéger la confidentialité des copies de données|
|Versionnement|Retrouver une version antérieure d'un fichier|

Je préfère privilégier des solutions simples à administrer plutôt que des architectures complexes utilisant systématiquement des mécanismes de parité.

Le choix dépend toutefois de l'importance des données, de leur volume et des besoins de disponibilité.
<br><br>
🔐 **5.5. Sécurité et confidentialité des sauvegardes**

La protection des données ne se limite pas à leur duplication.

Une stratégie de sauvegarde doit également prendre en compte :

- La confidentialité : chiffrement des archives contenant des données sensibles.

- L'intégrité : vérification de la validité des sauvegardes.

- La disponibilité : conservation de copies accessibles en cas d'incident.

- La séparation : limitation des risques qu'un incident sur le serveur affecte toutes les copies.

- La restauration : capacité à récupérer effectivement les données et les configurations.

Une sauvegarde n'est réellement utile que si elle peut être restaurée.

C'est pourquoi les tests de restauration constituent une étape importante dans la fiabilisation d'une infrastructure.
<br><br>
📈 **5.6. Évolutions envisagées**

Plusieurs améliorations peuvent renforcer progressivement cette organisation :

- Centraliser les journaux d'exécution des sauvegardes.

- Mettre en place des notifications en cas d'échec.

- Définir une politique de rétention des archives.

- Automatiser les contrôles d'intégrité.

- Effectuer des tests de restauration périodiques.

- Conserver une copie supplémentaire sur un support indépendant ou déconnecté.

- Étendre les sauvegardes automatisées aux autres applications critiques.

L'objectif à terme est de se rapprocher d'une stratégie 3-2-1 : trois copies des données, sur deux types de supports, dont une copie conservée hors site.

Cette approche reste un objectif d'amélioration et non une configuration que je considère comme déjà entièrement déployée.
<br><br>
🎯 **Objectif de cette organisation**

Je cherche à construire une stratégie de sauvegarde fiable, automatisée, compréhensible et adaptée à mes besoins, sans complexité inutile.

L'utilisation de Syncthing, Docker, Cron et de sauvegardes chiffrées me permet d'expérimenter différents mécanismes de protection des données.

Cette démarche contribue également au développement de mes compétences en administration Linux, scripting, gestion du stockage et maintenance des systèmes.

<br><br>
## **6. Administration et sécurité**
<br>
🔐 **Une infrastructure administrée et sécurisée sous Linux**

L'administration et la sécurité constituent deux aspects essentiels de mon serveur personnel sous Linux Mint.

Contrairement à un NAS clé en main, cette installation me donne un contrôle direct sur le système d'exploitation, les services, les utilisateurs, les permissions et les communications réseau.

Mon objectif est de maintenir une infrastructure stable, sécurisée, accessible à distance et facilement maintenable, tout en conservant la maîtrise de son fonctionnement.

Cette démarche repose sur plusieurs principes :

- Administration centralisée : gestion des applications et services depuis le système Linux.

- Contrôle des accès : gestion des comptes, des permissions et des services accessibles.

- Sécurisation réseau : utilisation d'un pare-feu et limitation des ports exposés.

- Maintenance préventive : mises à jour, surveillance et vérification du fonctionnement des services.

- Automatisation : utilisation de scripts et de tâches planifiées pour réduire les interventions répétitives.

- Local-First : priorité aux communications locales et limitation des dépendances aux services cloud.
<br><br>
🖥️ **6.1. Administration locale et distante**

L'administration du serveur s'effectue à travers plusieurs méthodes complémentaires.

|Outil|Fonction|
|---|---|
|Terminal Linux|Administration du système et diagnostic|
|SSH|Administration distante en ligne de commande|
|RustDesk|Accès graphique et maintenance à distance|
|systemd|Gestion des services système|
|APT|Gestion des paquets et mises à jour|
|Bash|Scripts d'administration et d'automatisation|

**Administration en ligne de commande**

Le terminal Linux permet d'effectuer les principales opérations d'administration :

- Vérification de l'utilisation du processeur et de la mémoire.

- Consultation de l'espace disque disponible.

- Gestion des processus et des services.

- Analyse des journaux système.

- Installation et mise à jour des logiciels.

- Gestion des utilisateurs et des permissions.

- Diagnostic des problèmes matériels ou logiciels.

L'administration à distance avec SSH permet d'intervenir sur le serveur depuis une autre machine du réseau, sans nécessiter d'accès physique.

**Accès graphique avec RustDesk**

RustDesk constitue une solution complémentaire pour les opérations nécessitant un environnement graphique.

Cet outil permet notamment de prendre le contrôle du bureau Linux à distance, d'intervenir sur des applications graphiques et de réaliser certaines opérations de maintenance.

Il représente une alternative intéressante aux solutions de bureau distant propriétaires, notamment grâce à ses possibilités d'auto-hébergement.
<br><br>
🛡️ **6.2. Pare-feu et sécurité réseau**

La sécurisation des communications réseau repose notamment sur UFW (Uncomplicated Firewall), l'interface simplifiée de gestion du pare-feu Linux.

UFW permet de définir les règles autorisant ou bloquant les connexions entrantes et sortantes.

Son utilisation facilite :

- Le contrôle des ports accessibles.

- La limitation des services exposés.

- L'autorisation des connexions nécessaires aux applications.

- La réduction de la surface d'attaque du serveur.

- L'adaptation des règles aux évolutions de l'infrastructure.

Les applications auto-hébergées utilisent différents ports réseau, notamment pour leurs interfaces web et leurs API.

L'objectif est de n'autoriser que les communications réellement nécessaires.

Un point de vigilance concerne Docker : les ports publiés par les conteneurs peuvent contourner certaines règles UFW classiques. Leur exposition doit donc être contrôlée également au niveau de Docker, des interfaces d'écoute et du pare-feu réseau.
<br><br>
👤 **6.3. Gestion des utilisateurs et des permissions**

Linux dispose d'un système de permissions permettant de contrôler l'accès aux fichiers, répertoires et ressources.

Cette gestion repose notamment sur :

- Les comptes utilisateurs.

- Les groupes Linux.

- Les droits de lecture, d'écriture et d'exécution.

- Les propriétaires des fichiers et répertoires.

- L'élévation temporaire des privilèges avec sudo.

Ces mécanismes sont particulièrement importants pour les applications Docker qui utilisent des répertoires du système hôte.

Une mauvaise configuration des permissions peut provoquer des erreurs d'accès, empêcher l'écriture des données ou exposer inutilement certains fichiers.

Je privilégie donc une organisation dans laquelle chaque application dispose des accès nécessaires à son fonctionnement, sans lui attribuer systématiquement des privilèges élevés.
<br><br>
🐳 **6.4. Administration et maintenance Docker**

Docker occupe une place importante dans mon infrastructure.

L'administration des conteneurs comprend plusieurs opérations :

- Déploiement et configuration des applications.

- Gestion des fichiers Docker Compose.

- Création et gestion des volumes persistants.

- Configuration des ports et réseaux.

- Consultation des journaux d'exécution.

- Redémarrage et mise à jour des services.

- Vérification de l'état des conteneurs.

- Sauvegarde des configurations et des données.

La séparation entre les applications conteneurisées et le système hôte facilite leur maintenance.

Cependant, la conteneurisation ne constitue pas à elle seule une garantie de sécurité.

Il reste nécessaire de contrôler les privilèges des conteneurs, les montages de volumes, les secrets applicatifs, les images utilisées et les services exposés sur le réseau.
<br><br>
📊 **6.5. Surveillance et diagnostic**

L'administration d'un serveur nécessite de pouvoir identifier rapidement les dysfonctionnements.

Pour cela, Linux fournit plusieurs outils de diagnostic.

|Commande|Utilisation|
|---|---|
|htop|Surveillance des processus et ressources|
|free -h|Consultation de l'utilisation de la RAM|
|df -h|Vérification de l'espace disque|
|lsblk|Identification des disques et partitions|
|systemctl|Gestion et état des services|
|journalctl|Consultation des journaux système|
|docker ps|Vérification des conteneurs|
|docker logs|Consultation des journaux Docker|
|ss -tuln|Identification des ports réseau en écoute|

Ces outils permettent notamment de diagnostiquer :

- Un service qui ne démarre plus.
- Une application inaccessible.
- Une saturation de la mémoire.
- Un espace disque insuffisant.
- Un problème de permissions.
- Une erreur de configuration réseau.
- Un conteneur Docker en échec.

Cette approche permet de comprendre l'origine d'un problème plutôt que de simplement redémarrer l'ensemble du serveur.
<br><br>
🔄 **6.6. Mises à jour et maintenance**

La maintenance du serveur comprend la gestion des mises à jour du système et des applications.

Sous Linux Mint, le gestionnaire de paquets APT permet de maintenir les composants logiciels issus des dépôts à jour.

Pour les applications Docker, les mises à jour nécessitent généralement de récupérer les nouvelles images et de recréer les conteneurs concernés, tout en préservant leurs données persistantes.

Une maintenance maîtrisée implique également :

- La vérification de la compatibilité des nouvelles versions.
- La sauvegarde préalable des données importantes.
- La consultation des journaux après une intervention.
- Le contrôle du bon fonctionnement des services.
- La possibilité de restaurer une configuration précédente en cas de problème.

Je privilégie une démarche progressive afin de limiter les interruptions de service.
<br><br>
⚙️ **6.7. Automatisation des tâches d'administration**

L'automatisation constitue un autre aspect important de mon installation.

L'utilisation de Bash, Cron et systemd permet de simplifier certaines opérations récurrentes.

Un exemple concret est la sauvegarde automatisée de BookStack, exécutée quotidiennement à 23 h 30.

Cette approche peut également être appliquée à :

- La vérification de l'état des services.
- La rotation et l'archivage des journaux.
- La maintenance des fichiers temporaires.
- La vérification de l'espace disque.
- Le contrôle des sauvegardes.
- L'envoi de notifications en cas d'anomalie.

L'objectif est de réduire les tâches répétitives tout en conservant une visibilité sur les opérations effectuées.
<br><br>
🔒 **6.8. Améliorations de sécurité envisagées**

La sécurisation d'une infrastructure est un processus continu.

Plusieurs améliorations peuvent être envisagées pour renforcer progressivement mon installation :

- Généraliser l'authentification SSH par clé et désactiver l'authentification par mot de passe après validation.
- Renforcer le contrôle des ports publiés par Docker.
- Mettre en place une surveillance automatisée des services.
- Centraliser les journaux importants.
- Ajouter des alertes en cas de dysfonctionnement.
- Vérifier régulièrement les permissions des applications.
- Sécuriser davantage les interfaces d'administration.
- Mettre en place des tests périodiques de restauration.
- Étudier la segmentation réseau pour isoler certains services.

Ces évolutions permettraient d'améliorer la disponibilité, la traçabilité et la sécurité globale du serveur.
<br><br>
🎯 **Objectif de cette administration**

Mon objectif est de disposer d'une infrastructure Linux que je peux administrer, maintenir, diagnostiquer et faire évoluer de manière autonome.

Au-delà de l'hébergement d'applications, ce serveur constitue un véritable environnement pratique pour développer mes compétences en :

- Administration des systèmes Linux.
- Gestion des utilisateurs et des permissions.
- Sécurité des services et des communications réseau.
- Déploiement et maintenance Docker.
- Supervision et diagnostic.
- Automatisation et scripting.
- Résolution d'incidents techniques.

Cette expérience s'inscrit directement dans mon parcours de développement de compétences en administration systèmes et réseaux (TSSR) et dans mon intérêt pour la cybersécurité.

<br><br>
## **7. Évolutions envisagées**
<br>
🚀 **Une infrastructure conçue pour évoluer**

L'un des principaux avantages de mon serveur DIY est sa capacité à évoluer progressivement en fonction de mes besoins, sans nécessiter le remplacement complet de la machine.

Initialement orienté vers le stockage et l'auto-hébergement, mon serveur s'est progressivement transformé en une plateforme polyvalente intégrant des applications Docker, des outils d'automatisation et de l'intelligence artificielle locale.

Plusieurs évolutions matérielles et logicielles sont envisagées afin d'améliorer ses performances, sa fiabilité et ses possibilités d'utilisation.
<br><br>
🧠 **7.1. Augmentation de la mémoire RAM**

Mon serveur dispose actuellement de 16 Go de mémoire DDR4.

Cette capacité reste suffisante pour de nombreux services auto-hébergés, mais l'utilisation simultanée de plusieurs applications, conteneurs Docker et modèles d'intelligence artificielle peut rapidement augmenter les besoins.

Une extension à 64 Go de RAM est envisagée.

Les objectifs sont notamment :

- Améliorer le fonctionnement simultané des applications.
- Disposer de davantage de mémoire pour les conteneurs Docker.
- Faciliter l'exécution de modèles IA nécessitant une partie de la mémoire système.
- Limiter les risques de saturation et l'utilisation du swap.
- Conserver une marge pour les futurs services.

Cette évolution nécessitera également de vérifier la compatibilité des barrettes, leur fréquence de fonctionnement et la stabilité de l'ensemble.
<br><br>
🎮 **7.2. Évolution de la carte graphique pour l'IA locale**

Le serveur utilise actuellement une AMD Radeon RX 6600 XT disposant de 8 Go de VRAM.

Cette carte permet déjà d'exécuter différents modèles d'intelligence artificielle en local, notamment avec Ollama et llama.cpp.

Cependant, la quantité de mémoire vidéo constitue une limite pour les modèles de langage plus volumineux.

Mon objectif est d'évoluer vers une carte graphique disposant idéalement de 24 Go de VRAM.

Plusieurs solutions sont étudiées, notamment :

- NVIDIA GeForce RTX 3090 — 24 Go.
- Intel Arc Pro B60 — 24 Go.
- D'autres cartes offrant un bon compromis entre mémoire vidéo, performances, consommation électrique et compatibilité Linux.

Cette évolution permettrait notamment :

- D'exécuter des modèles de langage plus volumineux.
- De réduire le recours à la mémoire RAM pour certains modèles.
- D'améliorer les performances d'inférence.
- D'augmenter la taille des contextes exploitables selon les modèles.
- D'expérimenter davantage de solutions d'intelligence artificielle générative.

Le choix définitif dépendra des performances réelles sous Linux, de la compatibilité avec les moteurs d'inférence utilisés et du budget disponible.
<br><br>
🤖**7.3. Développement d'une architecture multi-agents IA**

L'un de mes projets les plus importants consiste à développer une architecture d'intelligence artificielle locale composée de plusieurs agents spécialisés.

L'objectif n'est pas simplement d'exécuter un modèle conversationnel, mais de créer un ensemble de services capables de coopérer et d'interagir avec mon infrastructure.

Plusieurs agents sont envisagés :

|Agent IA |Fonction envisagée|
|---|---|
|Assistant généraliste | Questions, recherches et tâches quotidiennes|
|Agent programmation | Assistance au développement et analyse de code|
|Agent Home Assistant|Analyse et génération de configurations YAML|
|Agent documentaire|Lecture, extraction et analyse de documents|
|Agent OSINT|Assistance à la recherche d'informations publiques|
|Agent trading|Analyse de données financières et génération de rapports|
|Agent recettes|Recherche et organisation de recettes de cuisine|
|Agent programme TV / Cinéma|Recherche et diffusion de programmes personnalisés|

L'architecture s'appuie sur plusieurs composants déjà présents sur mon serveur :

- Ollama : exécution des modèles de langage.
- Open WebUI : interface de communication.
- n8n : automatisation et orchestration de workflows.
- SQLite : stockage local d'informations et de mémoires.
- Python : développement de services, d'API et de modules spécialisés.

Le développement est réalisé progressivement, avec une approche modulaire : chaque fonctionnalité est conçue, testée et validée avant l'intégration de la suivante.

À terme, l'objectif est de disposer d'un assistant personnel évolutif, capable d'utiliser différents outils tout en conservant les traitements et les données localement autant que possible.
<br><br>
🖼️ **7.4. Génération d'images et de contenus multimédias**

Une autre évolution envisagée concerne l'intégration d'outils d'intelligence artificielle générative dédiés aux images.

L'objectif est de disposer d'une interface locale permettant de :

- Générer des images à partir de descriptions textuelles.
- Modifier ou améliorer des images existantes.
- Expérimenter différents modèles de diffusion.
- Exploiter l'accélération GPU.
- Conserver les fichiers et traitements sur le serveur.

Des solutions telles que InvokeAI ou ComfyUI font partie des outils étudiés.

Ces usages restent secondaires par rapport aux modèles conversationnels et aux agents IA, mais représentent un axe d'expérimentation intéressant.
<br><br>
💾 **7.5. Extension des capacités de stockage**

Mon architecture permet d'envisager l'ajout progressif de nouveaux disques selon l'évolution des besoins.

Les principales pistes sont :

- Augmenter la capacité destinée aux fichiers et aux bibliothèques multimédias.

- Séparer davantage les données des applications et les archives.

- Adapter les volumes aux besoins des services Docker.

- Améliorer l'organisation des sauvegardes.

- Étudier l'utilisation de volumes en miroir pour les données nécessitant une meilleure disponibilité.

L'objectif est de conserver une architecture simple à administrer, sans imposer systématiquement des configurations RAID complexes.

Les extensions resteront conditionnées aux possibilités matérielles de la carte mère, du boîtier, de l'alimentation et des éventuels contrôleurs supplémentaires.
<br><br>
🔐 **7.6. Renforcement de la sécurité et de la supervision**

L'évolution de l'infrastructure doit également s'accompagner d'une amélioration progressive de sa sécurité et de sa fiabilité.

Plusieurs axes sont envisagés :

- Mise en place d'une supervision centralisée des ressources et des services.
- Alertes en cas d'indisponibilité d'une application.
- Surveillance de l'état des disques et des températures.
- Renforcement du contrôle des accès réseau.
- Amélioration de la gestion des sauvegardes et des restaurations.
- Documentation des procédures de maintenance.
- Sécurisation des communications entre applications et agents IA.

L'objectif est de pouvoir détecter plus rapidement les anomalies, faciliter les interventions et limiter les interruptions de service.
<br><br>
📚 **7.7. Documentation et partage d'expérience**

Enfin, une évolution importante de ce projet concerne sa documentation.

À travers GitHub, je souhaite conserver une trace structurée des différentes étapes de construction et d'administration de mon infrastructure.

Cette documentation permettra notamment de présenter :

- Les choix matériels et logiciels.
- Les architectures mises en place.
- Les procédures d'installation et de configuration.
- Les difficultés rencontrées et leurs résolutions.
- Les évolutions réalisées.
- Les compétences techniques mobilisées.

Cette démarche s'inscrit dans une volonté de partager mes expérimentations, de contribuer à la communauté open source et de valoriser mes compétences en administration systèmes et réseaux.
<br><br>
🎯 **Vision à long terme**

Mon objectif est de faire évoluer progressivement ce serveur vers une plateforme personnelle d'auto-hébergement et d'intelligence artificielle locale, performante, sécurisée et aussi autonome que possible.

Ce projet représente bien plus qu'un simple serveur domestique.

Il constitue un environnement d'apprentissage permanent dans lequel je peux expérimenter, développer, administrer et maintenir des services réels.

Chaque évolution est l'occasion d'approfondir mes connaissances en Linux, réseaux, stockage, Docker, automatisation, programmation et intelligence artificielle.

Cette approche correspond pleinement à ma volonté de développer mes compétences dans les métiers de l'administration systèmes et réseaux, avec une ouverture vers la cybersécurité.

*Ce projet est évolutif. Cette documentation sera mise à jour au fil des améliorations matérielles, des nouveaux services déployés et des expérimentations réalisées.*
