---
title: Pack de correctifs cumulés AEM 6.3
description: Notes de mise à jour du pack de correctifs cumulés AEM 6.3.
exl-id: 04969587-a904-44cb-83e0-51707ac6a87f
source-git-commit: e9031f819352f34248c6a458ef5a9101a660fbea
workflow-type: tm+mt
source-wordcount: '15909'
ht-degree: 99%

---

# Notes de mise à jour du pack de correctifs cumulés AEM 6.3 {#release-notes-aem-cumulative-fix-pack}

## Informations sur la version {#release-information}

| **Produit** | Adobe Experience Manager |
|---|---|
| **Version** | 6.3 |
| **Version** | Pack de correctifs cumulés 6.3.3.8 via la [Distribution de logiciels](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq630/cumulativefixpack/aem-6.3.3-cfp-8.0.zip) |
| **Prérequis** | [AEM 6.3 Service Pack 3 (6.3.3.0)](https://helpx.adobe.com/fr/experience-manager/6-3/release-notes/sp3-release-notes.html) |
| **Disponibilité générale** | 5 mars 2020 |

### Pack de correctifs cumulés {#cumulative-fix-pack}

Adobe a introduit un modèle de diffusion unique pour la publication des correctifs. Au lieu de publier des correctifs ad hoc pour chaque problème, Adobe publie désormais un pack de correctifs cumulés (CFP) tous les mois (sous réserve de contrôles de qualité satisfaisants). Un CFP est un module de contenus agrégés contenant plusieurs correctifs. Les CFP comprennent principalement des correctifs de bugs, mais peuvent également inclure des Feature Packs. Ils présentent les avantages suivants par rapport aux correctifs publiés individuellement :

* Cumulatifs par nature (par exemple, un CFP contient les correctifs apportés par le biais de CFP précédents)
* Meilleure assurance qualité
* Installation simplifiée (l’utilisateur installe un CFP en un seul module sans dépendances, hormis le dernier Service Pack)

Pour plus d’informations sur le CFP et sur d’autres types de versions, consultez les [définitions du véhicule de version de maintenance.](https://docs.adobe.com/content/docs/en/aem/6-3/deploy/maintenance-release-vehicle-definitions.html)

## À propos de cette version {#about-the-release}

Le pack de correctifs cumulés 6.3.3.8 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du Service Pack 3 (6.3.3.0) AEM 6.3 de septembre 2018.

Le pack de correctifs cumulés AEM 6.3.3.8 nécessite la présence du Service Pack 3 AEM 6.3. Vous devez donc installer le pack de correctifs cumulés AEM 6.3.3.x après avoir installé le Service Pack 3 AEM 6.3. Pour obtenir des instructions sur l’installation, consultez les [Notes de mise à jour du service Pack 3 d’AEM 6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.20.

>[!CAUTION]
>
>Le fait d’installer le CFP sans avoir validé la compatibilité entre les Feature Packs installés peut entraîner une défaillance du système ou la perte de configurations personnalisées, ce qui nécessiterait une restauration à partir de la sauvegarde pour résoudre le problème.

>[!NOTE]
>
>Pour les instances AEM dont la version est inférieure à 6.3.3.0, Adobe recommande de déployer le SP/CFP via le dossier d’installation pour les clients dont l’instance AEM dispose d’un grand nombre d’utilisateurs.

>[!NOTE]
>
>MongoDB Enterprise 3.6 est pris en charge à partir d’AEM version 6.3.3.1.

## Liste des problèmes {#changes}

Cette section répertorie tous les problèmes et correctifs inclus dans le CFP actuel.

En outre, ce CFP inclut des correctifs fournis dans les [packs de correctifs cumulés](#previous) précédents.

### Ressources {#assets}

* La page Ajouter à la collection n’affiche pas toutes les collections disponibles en mode Carte lors de l’ajout de ressources à la collection (NPR-32537).

### Sites {#sites}

* Lorsque vous sélectionnez un parsys et un composant qu’il contient, et que vous utilisez le raccourci clavier pour supprimer les éléments sélectionnés, l’action supprime à la fois le composant et son parsys parent (NPR-32071).
* Lorsque les propriétés d’une page sont enregistrées, un nœud incorrect est créé (NPR-31774).

### Intégrations {#integrations}

* ReportSuitesServlet est vulnérable aux attaques SSRF (NPR-32162).

### Campaign - Ciblage {#campaign-targeting}

* Le contenu d’un composant modifié dans l’instance Auteur, puis activé, n’est pas visible dans l’instance Publication tant que le composant n’a pas été redémarré **com.day.cq.personalization.impl.TargetedContentManagerImpl** (NPR-32489 et NPR-32232).
* Les performances de Contexthub s’annulent lors de la publication (NPR-31170).

### Brand Portal {#brand-portal}

* Adobe I/O n’est pas intégré à Adobe Experience Manager 6.3 pour Brand Portal (NPR-32056).

### Formulaires {#forms}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

#### Package de modules complémentaires Forms {#forms-add-on-package}

>[!NOTE]
>
>Les modules complémentaires AEM Forms permettent d’harmoniser les fonctionnalités des formulaires avec les Service Packs et les packs de correctifs cumulés AEM. Il est donc impératif d’installer le module complémentaire AEM Forms après avoir installé un Service Pack, un pack de correctifs cumulés ou un Feature Pack AEM.

* Designer : si l’option de balisage est activée, la bordure du sous-formulaire disparaît dans la sortie PDF générée (NPR-32324 et NPR-32545).
* Designer : s’il existe des cellules fusionnées dans un tableau, le test d’accessibilité échoue pour un fichier PDF de sortie converti par le service de sortie à l’aide d’un formulaire XDP (NPR-32068).
* Sécurité des documents : un fichier PDF protégé ne peut pas s’ouvrir hors connexion avec l’option `DisableGlobalOfflineSynchronizationData` définie sur `True` (NPR-32080).

**Problèmes résolus dans la version 6.3.0-0047**

* (JEE uniquement) Vulnérabilités de sécurité critiques (CVE-2021-44228 et CVE-2021-45046) signalées pour Apache Log4j2.

## Correctifs et Feature Packs inclus dans les packs de correctifs cumulés précédents {#previous}

### Pack de correctifs cumulés 6.3.3.7 {#cumulative-fix-pack-1}

Le pack de correctifs cumulés 6.3.3.7 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du Service Pack 3 (6.3.3.0) AEM 6.3 de septembre 2018.

Le pack de correctifs cumulés AEM 6.3.3.7 nécessite la présence du Service Pack 3 AEM 6.3. Vous devez donc installer le pack de correctifs cumulés AEM 6.3.3.x après avoir installé le Service Pack 3 AEM 6.3. Pour obtenir des instructions sur l’installation, consultez les [Notes de mise à jour du service Pack 3 d’AEM 6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html).

### Ressources {#assets-1}

* Les ressources sélectionnées (en mode Colonnes dans l’interface utilisateur tactile) avant de sélectionner l’option de filtre dans la liste déroulante Contenu uniquement, puis de sélectionner l’option déplacement, sont également déplacées (NPR-30693).
* La variable `${extension}` n’est pas rendue dans l’instance de création lors du traitement du workflow (NPR-31694).
* La valeur d’expiration (délai d’activation du cache client) configurée pour le mode hybride de Dynamic Media n’est pas répliquée dans l’environnement de diffusion de Dynamic Media (NPR-31114).
* Les ressources sont répliquées dans l’instance de publication à partir de l’instance de création qui s’exécute sur le déploiement de Dynamic Media Scene7, même après l’utilisation de filtres par défaut (NPR-30856).

### Sites {#sites-1}

* Le chargement des propriétés de page d’une page modèle échoue et une exception NullPointerException est renvoyée. Le problème est résolu par l’ajout de la propriété cq:blueprint (NPR-30901).
* Les configurations de déploiement ne sont pas correctement récupérées à partir de blueprintConfig sur le nœud racine. La désactivation est déclenchée pour les plans directeurs et les live copies. La désactivation ne doit être déclenchée que pour le plan directeur (NPR-30866).
* Lorsqu’un utilisateur déploie une page, la boîte de dialogue de configuration du déploiement affiche des chemins de live copies en double (NPR-30438).
* L’éditeur de texte enrichi (RTE) dédié à la génération de modèles automatique applique inopinément la taille de police en ligne aux éléments (NPR-31283, NPR-30922).
* Impossible de synchroniser la campagne d’Adobe Campaign qui contient le composant d’importateur de conception prêt à l’emploi (NPR-30890).
* L’éditeur de texte enrichi (RTE) ne permet pas d’insérer un tableau incorporé en tant qu’élément de liste (NPR-30878).
* Lorsqu’un utilisateur se concentre sur les champs du rail gauche et utilise un raccourci clavier pour coller du contenu, il colle le contenu du Presse-papiers de l’éditeur de page au lieu du contenu copié à partir des champs du rail gauche (NPR-31173).
* Lorsqu’un utilisateur modifie un fragment de contenu, la variante déjà supprimée du fragment de contenu est restaurée (NPR-31272).
* Le site AEM ne comporte pas l’option permettant de créer une copie de langue (NPR-30690).
* Les actions de l’éditeur de pages ne comportent pas les commandes permettant de déployer des live copies (NPR-30613).

### Communities {#communities}

* Les titres des activités et des notifications sont incohérents (NPR-30940).
* Les rapports d’analyse ne sont pas renseignés dans l’environnement de création AEM, une page vierge s’affiche (NPR-30905).
* La pagination ne fonctionne pas correctement dans les blogs Communities (NPR-30827).

### Foundation {#foundation}

* Les mises à jour de la configuration de la taille de la mémoire tampon pour le service HTTP basé sur Jetty ne sont pas enregistrées (NPR-30925).

### Formulaires {#forms-1}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-1}

>[!NOTE]
>
>Les modules complémentaires AEM Forms permettent d’harmoniser les fonctionnalités des formulaires avec les Service Packs et les packs de correctifs cumulés AEM. Il est donc impératif d’installer le module complémentaire AEM Forms après avoir installé un Service Pack, un pack de correctifs cumulés ou un Feature Pack AEM.

#### Formulaires adaptatifs {#adaptive-forms}

* Les valeurs flottantes calculées à l’aide d’un script ne s’affichent pas correctement dans un formulaire qui fait partie d’une visionneuse de formulaires (NPR-30802).

#### Formulaires HTML5 {#html-forms}

* La génération de l’aperçu HTML5 d’un formulaire XDP affiche un scintillement lors de l’ajout d’instances d’un sous-formulaire (NPR-30908).

### Programme d’installation de Forms JEE {#forms-jee-installer}

#### Services de document {#document-services}

* OutputService affiche une réponse incorrecte après l’application d’un correctif pour résoudre les problèmes en HTML comme en PDF (NPR-31504).

#### Service PDFG {#pdfg-service}

* Le nombre maximal de réutilisations avec la console JMX ne s’affiche pas pour le service HTML2PDF (NPR-30305).

#### Foundation JEE {#foundation-jee}

* Le nombre maximal de réutilisations avec la console JMX ne s’affiche pas pour le service HTML2PDF (NPR-30136).

### Pack de correctifs cumulés 6.3.3.6 {#cumulative-fix-pack-2}

Le pack de correctifs cumulés 6.3.3.6 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du Service Pack 3 (6.3.3.0) AEM 6.3 de septembre 2018.

Le pack de correctifs cumulés AEM 6.3.3.6 nécessite la présence du Service Pack 3 AEM 6.3. Vous devez donc installer le pack de correctifs cumulés AEM 6.3.3.x après avoir installé le Service Pack 3 AEM 6.3. Pour obtenir des instructions sur l’installation, consultez les [Notes de mise à jour du service Pack 3 d’AEM 6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html).

### Ressources {#assets-2}

* L’agrégation vidéo par Dynamic Video renvoie uniquement les 100 premiers éléments sur l’ensemble des résultats. NPR-30441 ; correctif pour CQ-4213561
* Problème de connectivité d’Adobe Smart Tag via Datapower. NPR-30026 : correctif pour CQ-4269457
* Il est impossible d’ouvrir une archive dont le nom contient un symbole de pourcentage (%) à l’aide de l’interface Ressources. NPR-29989 : correctif pour CQ-4270467
* Le traitement des sous-ressources des fichiers PDF volumineux provoque une exception OutOfMemoryError (OOME). NPR-29851 : correctif pour CQ-4269574

### Sites {#sites-2}

* Erreur ContextHub durant l’intégration d’AEM et de Campaign. NPR-30624 : correctif pour CQ-4250790
* Les propriétés des métadonnées « onTime » ou « offTime » enregistrées sur les ressources ne sont pas rappelées si le serveur AEM est redémarré. NPR-30412 : correctif pour CQ-4272784
* Lors de la génération d’une exportation au format CSV, l’ajout de colonnes personnalisées pour l’affichage de liste permet de ventiler le rapport. NPR-30208 : correctif pour CQ-4273344
* Les rapports prêts à l’emploi dans /etc/reports/ ne fonctionnent pas correctement et le graphique de données historiques ne s’affiche pas. NPR-30016 : correctif pour CQ-4220180
* La valeur du paramètre de requête resourceType est copiée dans la valeur d’un attribut de balise HTML encapsulé dans des guillemets doubles. NPR-29832 : correctif pour CQ-4255365

### Communautés {#communities-1}

* Problème de contenu en double avec la console de modération d’AEM Communities. NPR-30667 : correctif pour CQ-4276829

### Traduction {#translation}

* Problème de traduction : seuls quelques composants sont traduits à l’aide de la traduction automatique. NPR-30079 : correctif pour CQ-4273764
* Lors de l’utilisation de la structure de traduction, l’ajout de pages à plusieurs tâches de traduction déclenche une erreur. NPR-29746 : correctif pour CQ-4270953

### Formulaires {#forms-2}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-2}

>[!NOTE]
>
>Les modules complémentaires AEM Forms permettent d’harmoniser les fonctionnalités des formulaires avec les Service Packs et les packs de correctifs cumulés AEM. Il est donc impératif d’installer le module complémentaire AEM Forms après avoir installé un Service Pack, un pack de correctifs cumulés ou un Feature Pack AEM.

#### Formulaires HTML5 {#html-forms-1}

* Lors de l’utilisation de l’option Accès aux ordinateurs de bureau non visuels en mode Navigation pour lire un formulaire HTML5, le navigateur Chrome affiche « graphic » avant chaque graphique vectoriel évolutif (SVG) dans la conception du formulaire. NPR-30451 : correctif pour CQ-4274732

#### Forms - Intégration du serveur principal {#forms-backend-integration}

* Impossible d’afficher le service ou la source de données pour la connexion à la base de données lors de la création du modèle de données de formulaire (FDM). NPR-30108 : correctif pour CQ-4273359

### Programme d’installation de Forms JEE {#forms-jee-installer-1}

#### Forms - Document Services {#forms-document-services}

* Lorsqu’un test de chargement est effectué sur le service HTML en PDF, il échoue avec une erreur et les paramètres de type de fichier sont supprimés du serveur AEM Forms. NPR-30111, NPR-30086 : correctif pour CQ-4271495

### Pack de correctifs cumulés 6.3.3.5 {#cumulative-fix-pack-3}

Le pack de correctifs cumulés 6.3.3.5 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du Service Pack 3 (6.3.3.0) AEM 6.3 de septembre 2018.

Le pack de correctifs cumulés AEM 6.3.3.5 nécessite la présence du Service Pack 3 AEM 6.3. Vous devez donc installer le pack de correctifs cumulés AEM 6.3.3.x après avoir installé le Service Pack 3 AEM 6.3. Pour obtenir des instructions sur l’installation, consultez les [Notes de mise à jour du service Pack 3 d’AEM 6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.17.

### Ressources {#assets-3}

* Mise à jour de l’interface DAM DMGateway pour la prise en charge multipartie S3. NPR-29740 : correctif pour Q-4226303
* Impossible de supprimer un rendu d’image sur une ressource vidéo de la page Détails du fichier. NPR-29417 : correctif pour CQ-4268675
* Le propriétaire ne peut pas créer de dossier privé dans un dossier privé. NPR-29397 : correctif pour CQ-4229830
* Le chargement d’un fichier d’illustration Adobe Illustrator de plus de 2 Go génère une erreur d’espace de tas Java. NPR-29265 : correctif pour CQ-4226217
* Les ressources deviennent inutilisables une fois que le service DAM CQ Mime Type applique le texte pour m3u8. NPR-29259 : correctif pour CQ-4264052
* L’option Créer ne fonctionne pas lors des tentatives de création de collections dans Edge. NPR-29248 : correctif pour CQ-4265699 et CQ-4265438
* Le partage de liens de ressources affiche des cartes grises vierges à la place de certaines ressources du dossier. NPR-29831 : correctif pour CQ-4270187
* Les nouvelles balises ajoutées aux ressources ne sont pas enregistrées et disparaissent des propriétés. Correctif pour CQ-4271931, CQ-4270476

### Sites {#sites-3}

* CoralUI, lorsqu’il est utilisé avec Multifield, stocke le paramètre fileReferenceParameter au niveau du composant et non au niveau de plusieurs champs. NPR-29535 : correctif pour CQ-4266129
* Problème lors de la tentative de comparaison de la version de la page la plus récente et de la version actuelle dans AEM 6.3.3.3. NPR-29532 : correctif pour CQ-4269639
* Le champ de chemin d’accès s’ouvre à la racine, quel que soit le chemin spécifié pour la recherche. NPR-29398 : correctif pour CQ-4268897
* (Fragments d’expérience) FacebookApplication#setUpApp utilise une API obsolète, qui ne fonctionne plus. NPR-29213 : correctif pour CQ-4266630
* Une alerte d’erreur est générée lors de l’ajout de composants à la page WCM lorsque la minification est activée sur l’instance. NPR-29476 : correctif pour CQ-4266197
* Les propriétés vides et les propriétés multiples ne sont pas propagées pas à partir du plan directeur lors du déploiement. La réinitialisation de la live copy avec plan directeur ne fonctionne pas pour les composants. NPR-29252 : correctif pour CQ-4264928, CQ-4264926, CQ-4267722
* La réduction de l’éditeur de texte enrichi à partir du mode plein écran en mode modification de la source entraîne une perte de contenu. NPR-28838 : correctif pour CQ-4260584

### Communautés {#communities-2}

* Les visiteurs et les membres, sans privilèges de modérateur, peuvent voir les publications non approuvées et en attente en collant l’URL. NPR-29726 : correctif pour CQ-4271124
* Un temps de réponse élevé allant jusqu’à 40-50 secondes est observé lors de la connexion de l’utilisateur à la Communauté. NPR-29679 : correctif pour CQ-4269444
* Impossible de réinitialiser le mot de passe lorsque vous êtes connecté avec un nom d’utilisateur et un email différents, car la clé semble être générée avec un nom d’utilisateur et une adresse email permutés. NPR-29281 : correctif pour CQ-4268694

### Fragments d’expérience {#experience-fragments}

* Impossible d’exporter les fragments d’expérience vers la cible lorsque une image dynamique est utilisée. Correctif pour CQ-4269606

### Réplication {#replication}

* Le composant Agent de réplication est exposé à une vulnérabilité qui divulgue des informations sensibles à des utilisateurs non autorisés. NPR-29613 : correctif pour Granite-25070
* Les données fournies par l’utilisateur ne sont pas ignorées lors de la sortie dans le composant `cq/replication/components/agent`, ce qui entraîne une vulnérabilité Cross-site scripting (XSS) par stockage. NPR-29452 : correctif pour CQ-4266263

### Formulaires {#forms-3}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-3}

* Aucun nouveau correctif AEM Forms dans le module complémentaire de Forms.

### Programme d’installation de Forms JEE {#forms-jee-installer-2}

* Aucun nouveau correctif AEM Forms dans le programme d’installation de Forms JEE.

### Lots OSGI et packages de contenu dans 6.3.3.5 {#osgi-bundles-and-content-packages-included-in}

Liste des lots OSGi inclus dans AEM 6.3.3.5

[Obtenir le fichier](assets/do-not-localize/6_5-bundle-list.txt)

Liste des packages de contenu inclus dans AEM 6.3.3.5

[Obtenir le fichier](assets/do-not-localize/content_packages6335.txt)

### Pack de correctifs cumulés 6.3.3.4 {#cumulative-fix-pack-4}

Le pack de correctifs cumulés 6.3.3.4 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du Service Pack 3 (6.3.3.0) AEM 6.3 de septembre 2018.

Le pack de correctifs cumulés AEM 6.3.3.4 nécessite la présence du Service Pack 3 AEM 6.3. Vous devez donc installer le pack de correctifs cumulés AEM 6.3.3.x après avoir installé le Service Pack 3 AEM 6.3. Pour obtenir des instructions sur l’installation, consultez les [Notes de mise à jour du service Pack 3 d’AEM 6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.16.
* Ajout du délai d’expiration du socket et du délai de connexion dans les agents de réplication du Brand Portal.

### Ressources {#assets-4}

* Si vous chargez à nouveau une archive qui porte le même nom, les rendus ne sont pas générés pour les nouvelles ressources traitées. NPR-28643 : correctif pour CQ-4262286
* Le workflow CommandLineProcess échoue lorsque le nom de fichier comprend un guillemet simple. NPR-28805 : correctif pour CQ-4262287
* Les valeurs sont différentes entre la page de collecte et la page de collecte en utilisant le filtre. NPR-28642 : correctif pour CQ-4261405
* CommitFailedException se déclenche lors du chargement de fichiers d’archive zip volumineux. NPR-28528 : correctif pour CQ-4260903
* Échec d’enregistrement des métadonnées du dossier lors de la modification d’un dossier contenant des caractères spéciaux. NPR-28211 : correctif pour CQ-4260401
* Impossible de supprimer les rendus d’image d’une ressource vidéo depuis la page Détails du fichier. NPR-29149 : correctif pour CQ-4266073
* La diffusion vidéo sur un ordinateur de bureau DMS7 à l’aide de DMComponent utilise le téléchargement progressif pour lire la vidéo en mode de publication et ne diffuse pas de vidéo en continu. NPR-28754 : correctif pour CQ-4263732
* Impossible de créer/modifier des paramètres d’image prédéfinis, car la restriction de l’accès à /etc/dam/video/dynamicmedia désactive les fonctionnalités pour les gestionnaires d’images. NPR-28662 : correctif pour CQ-4263022
* Le partage de lien avec des fichiers vidéo codés DMS7 génère des dossiers vides. NPR-28851 : correctif pour CQ-4206743
* La réplication d’AEM vers le Brand Portal est bloquée pendant de longues périodes. NPR-28913 : correctif pour CQ-4254932

### Communautés {#communities-3}

* Impossible d’ouvrir les messages dont les pièces jointes se trouve dans les dossiers Envoyé et Boîte de réception d’Outlook. NPR-28559 : correctif pour CQ-4217072

### Sites {#sites-4}

* Cross-site scripting (XSS) dans SuggestionHandler pour la version 6.3. NPR-28692 : correctif pour CQ-4253821
* Le déploiement profond se termine sans contenir toutes les branches dans la LiveCopy correspondante. NPR-29175 : correctif pour CQ-4239472
* (MSM) Mettez en œuvre LiveCopyIndex à l’aide de oak-index. NPR-29198 : correctif pour CQ-4222472
* Le fichier « coral.js » contient une version vulnérable de la bibliothèque « handlebars.js ». NPR-26973 : correctif pour CQ-4255377
* L’utilisation d’un composant Target avec un conteneur de mises en page et un composant de texte imbriqués renvoie une erreur JavaScript « Impossible de lire la propriété currentPos de null » lors de la modification du texte ou d’un clic sur le conteneur. NPR-29077 : correctif pour CQ-4246594
* (IU tactile) Impossible de mettre à jour en bloc les balises sur les pages qui sont déjà balisées par des balises différentes. NPR-28729 : correctif pour CQ-4262922
* L’ouverture de la variation dans l’affichage de carte provoque une erreur 500. NPR-28611 : correctif pour CQ-4263571
* Le déploiement d’une structure qui a été déplacé dans un gabarit entraîne un cq:moveTarget erroné. NPR-28968 : correctif pour CQ-4265280

### Intégration {#integration}

* (Configurations du service Cloud) La case « hérité de » qui apparaît au niveau racine doit être supprimée. NPR-28771 : correctif pour CQ-4259676
* com.day.cq.personalization.impl.TeaserResourceEventHandler résulte en une boucle infinie et provoque des mises à jour des nœuds lors de la publication. NPR-28561 : correctif pour CQ-4263096
* L’utilisation de l’identifiant Brightedge échoue avec une erreur de connexion. NPR-29167 : correctif pour CQ-4265872
* Problème de compilation dans OfferproxyTandtProvider.java en raison d’une instruction d’importation manquante pour la classe « Resource » : instruction d’importation manquante : import org.apache.sling.api.resource.Resource. NPR-28772

### Commerce {#commerce}

* L’option Trier ne fonctionne pas pour les ressources de la collection Commerce. NPR-28755 : correctif pour CQ-4213622

### Jetty {#jetty}

* Exceptions jetty dans error.log pour toutes les redirections 302 après l’installation de CFP2 en plus de la version 6.3.3. NPR-28606 : prise en charge de CQ-4262844

### IU - Fondation {#ui-foundation}

* Le fait de cliquer sur la balise supprime l’événement mouseup global et la boîte de dialogue est figée en « mode déplaçable ». NPR-28641 : correctif pour CUI-7294

### WCM - MSM {#wcm-msm}

* Le déploiement de PushOnModify pour PageManager déplace les validations à plusieurs reprises depuis deux sessions, provoquant une condition de concurrence. NPR-28880 : correctif pour CQ-4266191

### Vulnérabilité {#vulnerability}

* La structure de protection CSRF ne fonctionne pas avec les formulaires AEM Foundation. NPR-28612 : correctif pour GRANITE-22231

### Formulaires {#forms-4}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

Les principaux aspects pour AEM Forms sont les suivants :

* Option activée pour sélectionner des éléments par page sur la page d’affichage du Jeu de stratégies.
* Ajout de la fonctionnalité Partager la file d’attente pour tous les navigateurs.

### Package de modules complémentaires Forms {#forms-add-on-package-4}

#### Forms - Workflow {#forms-workflow}

* La tâche de réponse de file d’attente partagée ouvre un élément Flash dans l’espace de travail HTML5. NPR-29161 : correctif pour CQ-4266498
* Impossible d’envoyer depuis l’espace de travail si le bouton contient un caractère Umlaut. NPR-29014 : correctif pour CQ-4263172

#### Forms - Document Security {#forms-document-security}

* Activer l’option pour sélectionner des éléments par page sur la page d’affichage du Jeu de stratégies. NPR-29243 : correctif pour CQ-4268567 et CQ-4265132

#### Forms - Document Services {#forms-document-services-1}

* OSGi Forms Assembler ne fonctionne pas avec les fichiers Acrobat. NPR-29049 : correctif pour CQ-4254426

#### Formulaires HTML5 {#html-forms-2}

* Un comportement différent est observé lors de la prévisualisation d’un fichier XDP au format PDF par rapport au même fichier XDP au format HTML dans Designer. NPR-28602 : correctif pour CQ-4260239

### Programme d’installation de Forms JEE {#forms-jee-installer-3}

* Aucun nouveau correctif AEM Forms dans le programme d’installation de Forms JEE.

### Lots OSGI et packages de contenu dans 6.3.3.4 {#osgi-bundles-and-content-packages-included-in-1}

Liste des lots OSGi inclus dans AEM 6.3.3.4

[Obtenir le fichier](assets/do-not-localize/list_of_osgi_bundlesincludedinaem633.4)

Liste des packages de contenu inclus dans AEM 6.3.3.4

[Obtenir le fichier](assets/do-not-localize/list_of_content_packagesincludedinaem633.4)

### Pack de correctifs cumulés 6.3.3.3 {#cumulative-fix-pack-5}

Le pack de correctifs cumulés 6.3.3.3 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du Service Pack 3 (6.3.3.0) AEM 6.3 de septembre 2018.

Le pack de correctifs cumulés AEM 6.3.3.3 nécessite la présence du Service Pack 3 AEM 6.3. Vous devez donc installer le pack de correctifs cumulés AEM 6.3.3.x après avoir installé le Service Pack 3 AEM 6.3. Pour obtenir des instructions sur l’installation, consultez les [Notes de mise à jour du service Pack 3 d’AEM 6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.16.
* Modification de la pagination de la liste des paramètres de stratégie, limitée à 50 enregistrements par page.
* Rep ajouté : mise en cache dans les nœuds ignorables de l’écouteur de synchronisation des utilisateurs d’AEM Communities sur les instances de publication.
* Ajout d’un libellé aria pour le bouton d’affichage sous forme de liste ou de cartes.
* Inclut un caractère d’échappement pour la virgule lors de toute recherche.
* Prise en charge des ressources de synthèse pour la stratégie de contenu.

#### Ressources {#assets-5}

* Impossible de télécharger plusieurs fichiers de type .jp2,.max,.oft,.msg. NPR-28002 : correctif pour CQ-4210856
* Les paramètres de publication d’ImageServer ne se répliquent pas vers une diffusion hybride. NPR-28329 : correctif pour CQ-4253030

#### Communautés {#communities-4}

* Activation de la navigation au clavier pour les composants d’activation d’AEM Communities lors de la publication. NPR-27739 : correctif pour CQ-4253856
* Activation de la navigation au clavier pour déclencher la lecture du contenu. NPR-27738 : correctif pour CQ-4254026
* Ajout d’un libellé aria pour le bouton d’affichage sous forme de liste ou de cartes. NPR-27736 : correctif pour CQ-4254027
* (Rétroportage) Rep ajouté : mettre en cache dans les nœuds ignorables du module d’écoute de synchronisation des utilisateurs d’AEM Communities sur les instances de publication. NPR-27841 : correctif pour CQ-4247234
* Les caractères spéciaux sont précédés d’un caractère d’échappement (\) dans la zone de recherche au niveau de l’interface utilisateur. NPR-27839 : correctif pour CQ-4259757
* Erreur lors de la recherche de caractères tels que (, +, ? dans la recherche rapide. NPR-28212 : correctif pour CQ-4260969
* Impossible de supprimer les commentaires dans le contenu créé par l’utilisateur à l’aide de l’API. NPR-28075 : correctif pour CQ-4260534
* Les commentaires publiés sur la page suivante sont surlignés en jaune lorsqu’un nouveau commentaire est publié. NPR-28148 : correctif pour CQ-4259681
* Impossible d’ouvrir les messages dont les pièces jointes se trouve dans les dossiers Envoyé et Boîte de réception de Outlook. NPR-28559 : correctif pour CQ-4217072

#### Sites {#sites-5}

* L’exécution de la purge de version dans AEM 6.3 provoque la répétition constante d’un avertissement dans les journaux. NPR-27750 ; correctif pour CQ-4206870
* Le plug-in de style n’est pas pris en charge dans le mode plein écran de l’éditeur de texte enrichi. NPR-27622 : correctif pour CQ-4258674
* La liste « loaderPromises » n’est pas effacée une fois le cadre de contenu chargé dans editor.js. NPR-27768 : correctif pour CQ-4205337
* Impossible de définir la stratégie de modèle sur les parsys imbriqués sans la définir dans le composant parent. NPR-27987 : correctif pour CQ-4246095
* L’explorateur de composants n’analyse pas les entrées utilisateur et peut donc générer des erreurs JavaScript. NPR-27986 : correctif pour CQ-4247590
* La page apparaît vide lorsque l’utilisateur tente de modifier le fragment de contenu. NPR-27669
* La mise en surbrillance de l’annotation disparaît dès que l’utilisateur clique sur l’annotation. BPR-27196 : correctif pour CQ-4254423

#### Intégration {#integration-1}

* ResourceResolver ne résout pas plusieurs domaines pour le composant Target. NPR-28265 : correctif pour CQ-107847
* L’annulation de l’héritage de LiveCopy ne fonctionne pas correctement sur les conteneurs ciblés, car aucune action n’est affichée. NPR-28129 : correctif pour CQ-4259813

#### Réplication {#replication-1}

* DispatcherFlushRules interrompt la réplication dans 6.3.3.1. NPR-28150 : correctif pour CQ-4261401

#### Campaign - Ciblage {#campaign-targeting-1}

* Exception NullPointerException dans TargetedContentManager. Correctif pour CQ-4263485

#### Social - SCORM {#social-scorm}

* Supprimez la référence au cloud SCORM (Shareable Content Object Reference Model) dans le lecteur. Correctif pour CQ-4260779

#### DAM - Général {#dam-general}

* Le téléchargement via l’e-mail de partage de liens renvoie un fichier zip vide/corrompu. Correctif pour CQ-4259686

#### MAC - Intégration de Test&amp;Target {#mac-test-target-integration}

* La configuration de l’option Composant Target n’est pas disponible pour les audiences autres que l’audience par défaut. Correctif pour CQ-4261370

#### Traduction {#translation-1}

* Activez la prise en charge du service MS Translator dans AEM 6.3 après la mise à niveau de MS Translator vers l’API v3.0. NPR-28365 : correctif pour CQ-4259096

### Formulaires {#forms-5}

### Package de modules complémentaires Forms {#forms-add-on-package-5}

#### Forms - Workflow {#forms-workflow-1}

* Impossible de générer les formulaires PDF dans l’espace de travail HTML5. NPR-28059 : correctif pour CQ-4260373

#### Forms - Document Services {#forms-document-services-2}

* Impossible d’afficher les jeux de stratégies au-delà des 1 000 premiers répertoriés dans la vue Jeux de stratégies de la console d’administration. NPR-28060, NPR-26047 : correctif pour CQ-4249865
* Une exception est générée avec le nom java.lang.IllegalArgumentException message:Aucune constante d’énumération com.adobe.internal.pdfm.docbuilder.signature.PathValidationFailureReason.SIGNED_IN_FUTURE empêchant l’exécution du workflow de courte durée. NPR-28652

#### Forms - Formulaires adaptatifs {#forms-adaptive-forms}

* L’ajout et la suppression d’éléments dans la liste déroulante ne se met pas à jour lors de la vérification des éléments de case à cocher. NPR-28224 : correctif pour CQ-4252834

### Forms - Programme d’installation JEE {#forms-jee-installer-4}

* Aucun nouveau correctif AEM Forms dans le programme d’installation de Forms JEE.

### Lots OSGI et packages de contenu dans 6.3.3.3 {#osgi-bundles-and-content-packages-included-in-2}

Liste des lots OSGi inclus dans AEM 6.3.3.3

[Obtenir le fichier](assets/do-not-localize/6333_bundle_list.txt)

Liste des packages de contenu inclus dans AEM 6.3.3.3

[Obtenir le fichier](assets/do-not-localize/content_package_list_6333.txt)

### Pack de correctifs cumulés 6.3.3.2 {#cumulative-fix-pack-6}

Le pack de correctifs cumulés 6.3.3.2 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du Service Pack 3 (6.3.3.0) AEM 6.3 de septembre 2018.

Le pack de correctifs cumulés AEM 6.3.3.2 nécessite la présence du Service Pack 3 AEM 6.3. Vous devez donc installer le pack de correctifs cumulés AEM 6.3.3.x après avoir installé le Service Pack 3 AEM 6.3. Pour obtenir des instructions sur l’installation, consultez les Notes de mise à jour du service Pack 3 d’AEM 6.3.

Les principaux aspects du pack de correctifs cumulés AEM sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.15.
* Ajout de la prise en charge de l’onglet Règles et de son application dans le dossier Ressources du Schéma de métadonnées du dossier.
* Prise en charge de la pagination activée pour la page de liste des groupes sur    publish.
* Activation de la configuration de la notification unreadCount avec n’importe quel nombre. Valeur par défaut définie sur 20.
* Correctifs dans le vérificateur de liens externes.

#### Ressources {#assets-6}

* La liste déroulante en cascade n’est pas prise en charge dans les listes déroulantes dynamiques. NPR-27044 ; correctif pour CQ-4252564
* Amélioration de la requête d’utilisation de la fonction ExpiryNotification. NPR-26999 : correctif pour CQ-4251188
* Migration des règles du Schéma de métadonnées vers le Schéma de métadonnées du dossier. NPR-27771 : rétroportage pour CQ-4257737, CQ-4257735, CQ-4259822
* L’ajustement de références de ressources ne parvient pas à mettre à jour les références des ressources qui font partie de Sling ResourceCollections. NPR-26759 : correctif pour CQ-4252605
* Le téléchargement via l’e-mail de partage de liens renvoie un fichier zip vide/corrompu. NPR-27997 : correctif pour CQ-4259686
* Le codage vidéo hybride ne s’achève pas et aucune miniature n’est créée. NPR-27122 : correctif pour CQ-4255080

#### Sites {#sites-6}

* La suspension de la page parente supprime le type de mixin cq : LiveRelationship de la page manquante. NPR-26996 : correctif pour CQ-4254113
* (Vérificateur de lien externe) Les liens internes apparaissent rompus sur les différentes pages, mais cela ne fonctionne pas pour les liens externes. NPR-27481 : correctif pour CQ-4257780
* L’héritage de la configuration du service Cloud échoue lors de la modification d’autres propriétés de page. NPR-27311 : correctif pour CQ-4256785
* Exception Pointeur nul lors de l’utilisation d’un formulaire de Composants    formulaire avec un formulaire Foundation. NPR-27333 : correctif pour CQ-4249176
* L’éditeur de texte enrichi supprime la balise alt vide. NPR-26938 : correctif pour CQ-4253267
* (IU classique) Problèmes de performances avec le listener...selectionchanged...en cas de listes déroulantes multiples. NPR-27115 : correctif pour CQ-4237215
* En cas de combinaison de l’éditeur de texte enrichi avec plusieurs champs, l’erreur « Uncaught TypeError: fieldAPI.getName is not a function at foundation.js » se produit. NPR-27146 : correctif pour CQ-4253155, CQ-4259967
* L’accent/curseur reste sur l’éditeur de texte enrichi même lorsque vous cliquez sur un bouton radio dans le navigateur Safari. NPR-27144 : correctif pour CQ-4249635
* La page apparaît vide lorsque l’utilisateur tente de modifier le fragment de contenu. NPR-27669
* Impossible de créer une version pour les fragments d’expérience. NPR-27689 : correctif pour CQ-4259009

#### Intégration {#integration-2}

* com.day.cq.personalization.impl.BrandsRetriever parcourt l’arbre entier pour recueillir les marques disponibles. NPR-27060 : correctif pour CQ-4255790
* Les actions cq  : ne sont pas prises en compte pour un composant ciblé. NPR-27616 : correctif pour CQ-4257497

#### Sling {#sling}

* Lorsque data-sly-use est utilisé avec des classes portant le même nom, un code non conforme est généré. NPR-27282 : correctif pour Sling-7581

#### Commerce {#commerce-1}

* Mise à jour vers Apache Felix Http Jetty 4.0.6. NPR-26472 : correctif pour Granite-22916

#### DAM - Client DM {#dam-dm-client}

* Une image ne s’affiche pas après avoir spécifié des points d’arrêt dans le composant de média dynamique. Correctif pour CQ-4256168

#### DAM - DMServices {#dam-dmservices}

* MixedMediaSet avec la vidéo associée ne se synchronise pas correctement. Correctif pour CQ-4251650
* La vidéo ne s’exécute pas dans l’éditeur de paramètres prédéfinis de la visionneuse pour la visionneuse de supports variés. Correctif pour CQ-4251442

#### DAM - Général {#dam-general-1}

* Le lien vers le modèle de fragment de contenu est manquant après l’application du patch SP3. Correctif pour CQ-4259029

#### DAM - IU {#dam-ui}

* Problèmes affectant l’interface utilisateur du schéma de métadonnées de dossier après l’installation de SP3. Correctif pour CQ-4257737

#### Communautés {#communities-5}

* Ajout de la prise en charge de la pagination pour la liste des groupes lors de la publication. NPR-26953 : correctif pour CQ-4246525
* La notification du nombre non lu ne peut pas être définie sur plus de 21. NPR-27496 : correctif pour CQ-4252829
* La limite des abonnements utilisateur est limitée à 1000. NPR-27615 : correctif pour CQ-4254689
* Erreur observée lors du chargement d’une pièce jointe autre qu’une image (par exemple .pdf) dans le forum. NPR-27375 : correctif pour CQ-4257753
* Le lien pour les réponses ne fonctionne pas lors d’un clic sur une ligne. NPR-24556 : correctif pour CQ-4256138
* Les relations avec le contenu créé par l’utilisateur (UGC) ne sont pas supprimées lors de la suppression de l’UGC. NPR-27631 : correctif pour CQ-4258706
* Impossible de rechercher par valeur d’adresse dans la recherche par mot-clé si la communauté est définie avec le fournisseur de ressources de stockage de base de données (DSRP). NPR-27652 : correctif pour CQ-4253261
* Un clic sur l’icône de la corbeille sur l’image après la confirmation de suppression supprime définitivement la pièce jointe. NPR-27340 : correctif pour CQ-4255150
* Les publications et les réponses du forum sont ajoutées au haut de la deuxième page et, une fois actualisées, la publication se déplace à l’emplacement correct en haut de la première page. NPR-27341 : correctif pour CQ-4247338
* Le libellé de statut d’achèvement de la ressource Scorm d’activation apparaît vide dans l’interface utilisateur. NPR-27152 : correctif pour CQ-4249994
* Si l’option « Autoriser les privilégiés » est arrivée, les membres privilégiés ne devraient pouvoir composer que pour les utilisateurs qui sont membres de la communauté. NPR-27901 : correctif pour CQ-4251235

#### Soutenance {#sustenance}

* Les journaux d’activité du gestionnaire de packages doivent être extraits dans un fichier journal distinct. NPR-27323 : correctif pour Granite-14866

#### Traduction {#translation-2}

* La prévisualisation de la traduction ne fonctionne pas avec l’exemple de contenu we.retail. NPR-27170 : correctif pour CQ-4241179

* Correctifs proactifs de connexion à la plateforme. NPR-26961
* L’option Enregistrer et fermer dans les propriétés de la page ne revient pas sur la page    page appropriée dans AEM WAR avec Tomcat. NPR-27567 : correctif pour Granite-23671

* Une fois enregistré, le texte saisi est perdu grâce à la fonction sourceEdit. Correctif pour CQ-4259273

### Formulaires {#forms-6}

### Package de modules complémentaires Forms {#forms-add-on-package-6}

#### Forms - Document Security {#forms-document-security-1}

* Problème d’exécution simultanée avec le SDK client JEE. NPR-27572 : correctif pour CQ-4247156

#### Forms - Document Services {#forms-document-services-3}

* La création d’un modèle de données de formulaire basé sur SOAP échoue dans WebSphere. NPR-27692 : correctif pour CQ-4253702

#### Forms - Formulaires adaptatifs {#forms-adaptive-forms-1}

* Vulnérabilité aux injections XML avec les formulaires AEM. NPR-27863 : correctif pour CQ-4257315
* Le composant Conteneur AEM Forms devient invisible lorsque le mauvais formulaire est configuré dans la page de sites et que la case à cocher « Les formulaires couvrent toute la largeur de la page » est activée. NPR-25972 : correctif pour CQ-4239287, CQ-4249133

### Programme d’installation de Forms JEE {#forms-jee-installer-5}

#### Foundation JEE {#foundation-jee-1}

* La création d’un modèle de données de formulaire basé sur SOAP échoue dans WebSphere. NPR-27692 : correctif pour CQ-4253702

#### Lots OSGI et packages de contenu inclus {#osgi-bundles-and-content-packages-included}

Liste des lots OSGi inclus dans AEM 6.3.3.2

[Obtenir le fichier](assets/do-not-localize/63332bundle_list.txt)

Liste des packages de contenu inclus dans AEM 6.3.3.2

[Obtenir le fichier](assets/do-not-localize/6332content_package.txt)

### Pack de correctifs cumulés 6.3.3.1 {#cumulative-fix-pack-7}

Le pack de correctifs cumulés 6.3.3.1 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du Service Pack 3 (6.3.3.0) AEM 6.3 de septembre 2018.

Le pack de correctifs cumulés AEM 6.3.3.1 nécessite la présence du Service Pack 3 AEM 6.3. Vous devez donc installer le pack de correctifs cumulés AEM 6.3.3.x après avoir installé le Service Pack 3 AEM 6.3. Pour obtenir des instructions sur l’installation, consultez les [Notes de mise à jour du service Pack 3 d’AEM 6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.14.
* Amélioration des performances des prédicats et de la recherche.
* Correction d’un problème dans la gestion des FormData pour la valeur par défaut.
* Mise à niveau de FormBuilder vers la dernière version de Handlebars.
* Ajout du servlet de configuration pour la configuration de modification du RTE en mode boîte de dialogue.
* Ajout de la prise en charge des champs composites.
* Activation/désactivation d’éléments de barre d’outils de l’éditeur de texte enrichi avec une stratégie de contenu pour la boîte de dialogue de modification.

#### Ressources {#assets-7}

* Si le découplage du répertoire de stockage global de documents est activé, le workflow de mise à jour du fichier de gestion des ressources numériques (DAM) ne lie plus les références. NPR-26135 : correctif pour CQ-4250933
* La décompression d’une archive créée par l’étape unarchiver avec un dossier qui comporte un % dans son nom ne s’ouvre pas. NPR-26275 : correctif pour CQ-4251482
* Le caractère guillemet simple empêche la mise à jour des métadonnées. NPR-26808 : correctif pour CQ-4254305
* (Omni-recherche) Problème de performances lors de la recherche au sein d’une collection. NPR-26714 : correctif pour CQ-4253408
* L’utilisation de GQLConverter avec une recherche de texte intégral contenant les lettres « OR » dans le texte est traitée de manière incorrecte. NPR-26564 : correctif pour CQ-4247362
* Le partage d’un lien de ressource à partir d’un système multi-client préfixe l’ID du client, formant une URL non valide. NPR-26482 : correctif pour CQ-4253540
* Désactivation de « Chemin d’accès au dossier racine de l’entreprise » dans l’interface utilisateur de configuration du cloud Dynamic Media. NPR-26361 : correctif pour CQ-4249505
* L’importation des fichiers RAW .mos dure trop longtemps. NPR-26296 : correctif pour CQ-4250661
* Le partage de liens de ressources ne permet pas d’ajouter plusieurs utilisateurs internes avec un identifiant numérique d’utilisateur. NPR-26206 : correctif pour CQ-4251466
* Corruption des fichiers zip compressés avec l’algorithme deflate64. NPR-26793 : correctif pour CQ-4253995
* Le workflow de génération de miniatures ne fonctionne pas correctement pour les fichiers PDF complexes, ce qui entraîne l’affichage de miniatures où une partie de l’image est manquante. NPR-26057 : correctif pour CQ-4250944
* Problème d’utilisation de la mémoire du tas lors de la génération de miniatures. NPR-25545 : correctif pour CQ-4246960
* La création d’un grand nombre de relations dans une ressource provoque des erreurs. NPR-26309 : correctif pour CQ-4250708
* L’option « Supprimer le rendu » ne fonctionne pas et renvoie une erreur « rien à supprimer ». NPR-26007 : correctif pour CQ-4213414
* Impossible de supprimer les valeurs par défaut des champs à plusieurs valeurs. NPR-25116 : correctif pour CQ-4247856
* (DM Hybrid) La réplication de catalogue échoue dans AEM 6.3.2 avec Dynamic Media. NPR-26406 : correctif pour CQ-4251306

#### Sites {#sites-7}

* Rétroportage proactif des correctifs de sites. NPR-26963
* Les balises sont créées deux fois lorsqu’il existe une différence de type de casse entre le Titre et Nom. NPR-26877 : correctif pour CQ-4254134
* Les fonctions de l’éditeur de texte enrichi dans la boîte de dialogue Modifier ne sont pas contrôlées par les stratégies. NPR-27059, NPR-26750 : correctif pour CQ-4241130
* Questions de caching ou de non caching de segment.js dans le contexte du client. NPR-26622 : correctif pour CQ-4253486
* L’activation de la règle de segmentation (/etc/segmentation) pour les règles enfants en mode classique provoque la suppression de la publication. NPR-26601 : correctif pour CQ-4253588
* L’ajout d’un « caractère spécial » fait défiler la boîte de dialogue de l’éditeur de texte enrichi jusqu’en haut. NPR-26435 : correctif pour CQ-4249869
* (IU tactile) La barre d’outils devient inutilisable avec plusieurs éditeurs de texte enrichi lorsque l’on passe du mode plein écran à une boîte de dialogue flottante. NPR-25652 : correctif pour CQ-4206008
* La promotion d’un lancement de plusieurs pages crée plusieurs versions pour chaque page. NPR-26810 : correctif pour CQ-4254663
* Les opérations de déplacement de balises ne sont pas reprises dans    des balises de modèle de fragment de contenu structuré. NPR-26801 : correctif pour CQ-4251805
* (IU tactile) L’annulation de la publication de la page enfant depuis l’éditeur de page ne fonctionne pas après un changement du nom de la page dans le plan directeur. NPR-26774 : correctif pour CQ-4254175
* La page dont la publication est annulée ne fonctionne pas avec les références. NPR-26749 : correctif pour CQ-4254372
* Pour créer une variante en tant que live copy, l’utilisateur doit actualiser la page afin d’en refléter les données. NPR-26663 : correctif pour CQ-4254328
* (IU classique) En revenant aux propriétés de la page, l’image miniature n’utilise plus l’héritage et disparaît de l’administrateur du site et du sidekick. L’image apparaît comme vide. NPR-26562 : correctif pour CQ-4252346
* Lorsqu’une version d’une page est créée et qu’une comparaison est déclenchée, les nœuds de /content/  versionshistory sont répertoriés dans la liste des live copies du plan directeur. NPR-26506 : correctif pour CQ-4243957
* Les URL dans l’éditeur d’administration des fragments d’expérience ne permettent pas les superpositions. NPR-26318 : correctif pour CQ-4252156

#### Plateforme {#platform}

* Fuite de session dans ReplicationEventListener avec des événements de test. NPR-25937 : correctif pour CQ-4251090
* La réplication utilise le jeton expiré pour OAuth, ce qui entraîne plusieurs erreurs. NPR-25894 : correctif pour GRANITE-22388

#### Intégration {#integration-3}

* Le TSDK intégré à AEM échoue lors d’une mise à niveau vers Handlebars 4 en raison de l’utilisation de modèles incompatibles. NPR-26699 : correctif pour CQ-4248974
* La publication d’une page avec une nouvelle ressource désactive la page enfant de l’instance de publication sans notification. NPR-24869 : correctif pour CQ-4247832
* La réplication utilise un jeton expiré pour    oauth. NPR-25984 : correctif pour Granite-22388

#### Réplication {#replication-2}

* Le transport HTTP peut faire fuiter des sessions ouvertes. Correctif pour Granite-17434
* Exceptions dans les journaux lorsque plusieurs agents de réplication accèdent simultanément au nœud de jetons d’accès. NPR-26964 : correctif pour GRANITE-23276, GRANITE-23155

#### ContextHub {#contexthub}

* Le fichier « coral.js » contient une version vulnérable de la bibliothèque « handlebars.js ». Correctif pour CQ-4255377

#### DAM - Client DM {#dam-dm-client-1}

* La suppression d’une copie d’une ressource d’image rend la ressource d’image d’origine inutilisable. Correctif pour CQ-4251648
* Téléchargement redondant de contenu d’image supplémentaire à partir des serveurs S7. Correctif pour CQ-4248770

#### Granite {#granite}

* Le fournisseur OAuth d’AEM n’effectue pas de recherche non sensible à la casse. NPR-26133 : correctif pour GRANITE-22650
* Le programme de validation de package ne valide pas les packages inclus dans CFP/SP. NPR-26775 : correctif pour Granite-22825

#### Communautés {#communities-6}

* Problème de délimiteur affectant les résultats de recherche. NPR-27051 : correctif pour CQ-4248939
* Remplace la valeur de la liste déroulante de Dallas à Virginia dans Adobe Storage Resource Provider. NPR-26936 : correctif pour CQ-4254434
* Activation de la prise en charge de la recherche de titre localisée dans SocialTagManager. NPR-26932 : correctif pour CQ-4250276
* Les images en pièce jointe n’affichent pas de miniature lors de la création d’une publication sur un forum. NPR-26380 : correctif pour CQ-4253105
* Le plug-in Coller à partir de Word ne parvient pas à charger plus d’une image. NPR-26728 : correctif pour CQ-4253638
* Impossible de filtrer le contenu de la page de modération. NPR-26697 : correctif pour CQ-4213766
* (Vulnérabilité de sécurité) Prise de contrôle du compte en raison d’une mauvaise configuration de JWT. NPR-26440 : correctif pour CQ-4253314
* La récupération des données du fournisseur de ressources de stockage Adobe est lente. NPR-26237 : correctif pour NPR-24152
* La page de composition des messages privés se comporte de manière erratique et laborieuse. NPR-26120 : correctif pour CQ-4250923
* La notification « Tout marquer comme lu » ne marque que les 10 premiers comme non lus sans actualisation de la page. NPR-27036 : correctif pour CQ-4254058
* Pagination des sections des commentaires de Communities et comportement de chargement de page. NPR-27030 : correctif pour CQ-4251228
* (Recherche dans le forum) Le bouton Précédent saute la page et revient à forum.html. NPR-26949 : correctif pour CQ-4254804
* Le nombre de notifications pour messages non lus ne dépasse pas 21. NPR-26947 : correctif pour CQ-4251251
* (Tâche SearchScheduledPosts) Ajout du commutateur activer/désactiver dans ConfigMgr. NPR-26924 : correctif pour CQ-4250463
* Le chemin d’accès du contexte Tomcat (/aempublish) est perdu lorsque l’on fait défiler la page Affectations. NPR-26919 : correctif pour CQ-4254345
* Exception NullPointerException lors de la création d’un groupe et d’un membre. NPR-26778 : correctif pour CQ-4248095
* Le contenu que le modérateur a désépinglé et a décidé de ne pas mettre en vedette ne fonctionne pas avec le principe de responsabilité unique (SRP) de MySQL. NPR-26767 : correctif pour CQ-4251520
* Problèmes de fonctionnalité de recherche avec certains caractères. NPR-26726 : correctif pour CQ-4247744
* Activez les liens profonds pour l’interface utilisateur de modération et les ressources d’activation. NPR-26705 : correctif pour CQ-4251381
* Problème de recherche dans le composant de forum. NPR-26577 : correctif pour CQ-4251303
* La recherche en utilisant conjointement le prénom et le nom dans les messages Communities ne renvoie pas les résultats attendus. NPR-26377 : correctif pour CQ-4253150
* La pagination ne se met pas à jour lors de la suppression des réponses. NPR-26327
* La suppression de la publication fonctionne, mais provoque une erreur sur la console et la publication reste visible dans l’interface utilisateur. NPR-26292 : correctif pour CQ-4252803
* La pagination ne se met pas à jour de manière dynamique et la liste des réponses continue de s’allonger. NPR-26145 : correctif pour CQ-4251586
* Les paramètres du groupe ne se chargent pas dans un groupe qui contient de 50 000 à 100 000 utilisateurs. NPR-25642 : correctif pour CQ-4238426
* Échec du lecteur de ressources du catalogue pour les chemins d’accès au contexte. NPR-25640 : correctif pour CQ-4238426
* (Recherche dans le forum) - Les liens paginés vers des fils qui contiennent beaucoup de publications ne fonctionnent pas dans les notifications. Correctif pour CQ-4254202
* La console de modération affiche uniquement 5 entrées avec Firefox. Correctif pour CQ-4254128
* Les groupes ne sont pas visibles lors de la création d’un site. NPR-27148 : correctif pour CQ-4251788
* Exception NullPointer lors de l’ajout d’un groupe et de membres aux paramètres de rôles et de l’autorisation du membre privilégié dans la fonction blog. NPR-21732, NPR-27176 : correctif pour CQ-4255909
* La modification du site et l’ajout de membres aux paramètres de rôles renvoie une exception NullPointer. NPR-27132 : correctif pour CQ-4255909

#### Interface utilisateur {#user-interface}

* Correctifs proactifs de la connexion à la plateforme. NPR-26961
* (Multichamp) Permet aux éléments composites d’avoir des noms personnalisés. NPR-26493 : correctif pour Granite-20568
* Le mode Colonnes n’est pas mis à jour après le collage d’une page tant que celle-ci n’a pas été actualisée. NPR-26030 : correctif pour CQ-4236346
* Correctifs proactifs de granite.ui.commons. NPR-26960
* Correctifs proactifs de granite.ui.content. NPR-26959
* Correctifs proactifs du journal CQ/experience. NPR-26943
* Rétroportages proactifs de l’interface utilisateur de Foundation. NPR-26942
* (IE11) « NaN » s’affiche dans le champ numérique lors de la saisie d’une valeur négative. NPR-26701 : correctif pour CQ-100826
* (Coral. Multichamp) Les champs multiples imbriqués utilisent un modèle incorrect pour créer les éléments. NPR-25649 : correctif pour CUI-6743
* Mettez à jour les clientlibs granite coralui2 et coralui3 pour supprimer Handlebars de la compilation. NPR-25606 : correctif pour Granite-22116

### Formulaires {#forms-7}

### Package de modules complémentaires Forms {#forms-add-on-package-7}

#### Forms - Document Security {#forms-document-security-2}

* Exceptions de survol de clé principale dans les journaux du serveur pour les clés inactives. NPR-26748 : correctif pour CQ-4253705
* Impossible de créer ou de modifier les paramètres de filigrane de Document Security. NPR-26267, NPR-26129 : correctif pour CQ-4250234

#### Forms - Document Services {#forms-document-services-4}

* Validation PDF/A non valide avec « validate PDF/A ». NPR-25934 : Correctif pour CQ-4248558

#### Forms - Communication interactive {#forms-interactive-communication}

* Les aperçus PDF et HTML de la lettre sont visibles et fonctionnels dans la même fenêtre lorsqu’un module modifiable est modifié, enregistré, puis que l’aperçu PDF est ouvert/fermé. NPR-26770 : correctif pour CQ-4253217

#### Forms - Workflow {#forms-workflow-2}

* L’espace de travail se bloque par intermittence et affiche les points de départ à plusieurs reprises. NPR-26461 : correctif pour CQ-4253439
* Une exception ESAPI est générée dans les journaux lorsque des accolades sont utilisées dans le nom de la tâche. Correctif pour CQ-4256627
* Une exception de type NullPointer est rapportée lorsque le point de départ associé au formulaire adaptatif/visionneuse de formulaires non prérempli est ouvert. Correctif pour CQ-4256124
* Impossible d’envoyer l’email à l’aide du paramètre global. NPR-26163 : correctif pour CQ-111110
* Impossible d’ouvrir l’espace de travail après l’application du fichier axis.jar. NPR-26131 : correctif pour CQ-4251126
* Le bouton Actualiser ne parvient pas à synchroniser les dernières données du serveur vers les formulaires adaptatifs. Correctif pour CQ-4255670
* La définition d’un modèle de recherche à partir de l’interface utilisateur d’administration, puis l’utilisation de ce modèle pour rechercher la tâche dans l’espace de travail AEM Forms renvoie une exception. Correctif pour CQ-4255649
* Les détails du suivi des workflows sous les applications dont le nom contient des parenthèses ne s’affichent pas dans l’espace de travail HTML. Correctif pour CQ-4242101
* L’enregistrement des modifications sur l’écran des préférences de l’espace de travail HTML renvoie une exception. Correctif pour CQ-4241485
* L’approbation en bloc est défaillante après installation de la dernière version de JEE. Correctif pour CQ-4241486
* Le brouillon de tâche/point de départ échoue sur la dernière version du serveur JEE 6.4. Correctif pour CQ-4241484
* Définissez le paramètre Date().getTime().toString pour initialiser la session au lieu de Date.toString(). Correctif pour CQ-4241483
* Lors de l’ouverture de /lc/ws, une exception de caractères vulnérables est observée dans le paramètre HTML. Correctif pour CQ-4241481

#### Vulnérabilité {#vulnerability-1}

* Vulnérabilité au cross-site scripting (XSS) par stockage dans l’onglet Remarques du gestionnaire de formulaires. NPR-27157 : correctif pour CQ-4255556

### Programme d’installation de Forms JEE {#forms-jee-installer-6}

#### Foundation JEE {#foundation-jee-2}

* Examen du code pour l’API Enterprise Security. Correctif pour CQ-4255638
* Échec du chargement de esapi.properties en tant que ressource de chargeur de classe dans WAS9. Correctif pour CQ-4255631
* Un clic sur « Ajouter une authentification » lors de la Configuration du domaine renvoie une erreur. Correctif pour CQ-4255634
* Forms JEE prend en charge l’authentification mutuelle PKCS#11. NPR-21372
* Correction des problèmes signalés dans l’analyse du code statique de Core. Correctif pour CQ-104446
* Le déploiement de adobe.livecycle.weblogic.ear et adobe.livecycle.websphere.ear échoue lors de l’exécution de LCM. Correctif pour CQ-4255629, CQ-4255630
* Messages d’erreur non valides dans la Gestion des applications. NPR-23289 : correctif pour CQ-4233163, CQ-4255636
* Un clic sur « Ajouter une authentification » lors de la Configuration du domaine produit une erreur. Correctif pour CQ-4255634

#### Forms - Connecteur JEE {#forms-jee-connector}

* Correction des problèmes signalés dans l’analyse du code statique de Connector. NPR-22260

#### Service PDFG {#pdfg-service-1}

* Erreur org.jgroups.Message dans les journaux après la mise à niveau de LiveCycle vers AEM 6.2 Forms. NPR-26795 : correctif pour CQ-4220415
* AEM Forms - Erreur lors de la migration des styles. Correctif pour CQ-4251969
* Correction des problèmes signalés dans le rapport d’analyse du code statique de PDFG. NPR-23251 : correctif pour CQ-4213930

#### Lots OSGI et packages de contenu dans 6.3.3.1 {#osgi-bundles-and-content-packages-included-in-3}

Liste des lots OSGi inclus dans AEM 6.3.3.1

[Obtenir le fichier](assets/do-not-localize/63sp3cfp1bundlelist.txt)

Liste des packages de contenu inclus dans AEM 6.3.3.1

### Pack de correctifs cumulés 6.3.2.2 {#cumulative-fix-pack-8}

Le pack de correctifs cumulés AEM 6.3.2.2 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du Service Pack 2 (6.3.2.0) AEM 6.3 d’avril 2018.

Le pack de correctifs cumulés AEM 6.3.2.2 nécessite la présence du Service Pack 2 AEM 6.3. Vous devez donc installer le pack de correctifs cumulés AEM 6.3.2.x après avoir installé le Service Pack 2 AEM 6.3. Pour obtenir des instructions sur l’installation, consultez les [Notes de mise à jour du service Pack 2 d’AEM 6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp2-release-notes.html).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.11.
* Activation des sous-ressources et de la visionneuse de ressources multipage sur le Brand Portal.
* Modification de la longueur du type de champ, définie sur 255, pour prendre en charge tous les types MIME possibles pour les différents types de pièces jointes.
* Configuration d’un message d’erreur du serveur lorsqu’une image enfreint les critères de chargement.
* Ajout de la prise en charge de STARTTLS dans Day CQ Mail Service.
* Mise à jour vers les dernières versions de cq-wcm-content et com.adobe.cq.launches.it.serverside.
* Mise à jour de com.adobe.granite.ui.coralui3-rte vers la dernière version publiée.
* S’assure que la condition de rendu renvoie un résultat sain si expressionResolver est nul.
* Coral.ColumnView : ajout de la prise en charge de Maj.+clic.

### Ressources {#assets-8}

* Le champ Groupe d’utilisateurs fermé (CUG) du dossier de ressources ne rappelle pas le groupe « tout le monde ». NPR-23163 : correctif pour CQ-4239377
* La requête de recherches enregistrées dans une collecte dynamique ne renvoie pas tous les résultats. NPR-23243 : correctif pour CQ-4240355
* (ExpiryNotificationJobImpl) Optimisation de la requête existante. NPR-23330 : correctif pour CQ-4205249
* (Profil des métadonnées) Les valeurs de balise standard définies au moment de la création ne sont pas disponibles après l’enregistrement. NPR-23370 : correctif pour CQ-4235458
* (IU tactile) Impossible de déplacer plusieurs ressources en raison d’une erreur JS. NPR-23395 : correctif pour CQ-4241279
* La disparité entre la taille du téléchargement et les informations affichées est source de confusion pour les utilisateurs. NPR-23418 : correctif pour CQ-4242774
* Le type MIME extrait pour l’extension de fichier LSR et SKETCH est incorrect et entraîne un téléchargement de fichier non valide. NPR-23644 : correctif pour CQ-4243260
* (Firefox/Chrome) Impossible de télécharger les ressources dans la page Partage de ressources. NPR-23963 : correctif pour CQ-4244391
* Les facettes de recherche de l’administrateur des ressources disparaissent dans les panneaux de recherche après prévisualisation. NPR-23964 : correctif pour CQ-4244410
* L’annulation de la publication du formulaire de recherche supprime complètement le formulaire de recherche par défaut. NPR-23291 : correctif pour CQ-4241382
* (Brand Portal) La recherche dans le prédicat du répertoire devrait être filtrée lors de la réplication. NPR-23292 : correctif pour CQ-4241385
* L’action Publier dans l’interface utilisateur du Brand Portal n’est pas disponible. NPR-23293 : correctif pour CQ-4241161
* Le bouton Publier/Annuler la publication sur le Brand Portal ne devrait pas être disponible pour les fragments de contenu. NPR-23318 : correctif pour CQ-4245086
* (Brand Portal) Activation de la création de sous-ressources lors de la publication d’une ressource. NPR-23331 : correctif pour CQ-4242018
* Les requêtes Dynamic Media n’utilisent pas le client commun proxy/HTTP. NPR-10727 : correctif pour CQ-45695, CQ-88800
* Impossible d’annoter la ressource vidéo MP4 de rendu unique dans Dynamic Media S7 (DMS7). NPR-22046 : correctif pour CQ-4215912
* Les données EmbedXMP sont toujours définies comme « actives » pour le workflow de génération Ptiff. NPR-22903 : correctif pour CQ-4234498
* Problèmes d’affichage/de sélection du rendu dynamique en présence d’un grand nombre de paramètres d’image prédéfinis. NPR-23151 : correctif pour CQ-4217511
* Problème avec la vidéo de codage Dynamic Media - Modification / Nouveau téléchargement du lanceur. NPR-23237 : correctif pour CQ-4240260
* Correctif de gestion des proxys pour le transfert HTTP dans Dynamic Media S7. NPR-24001 : correctif pour CQ-244140

### Sites {#sites-8}

* Des disparités affectant le créateur de requêtes provoquent une traduction xPath différente entre les versions 6.2 et 6.3. NPR-23245 : correctif pour CQ-4240396
* L’onglet Miniature de la propriété de page ne fonctionne pas lorsqu’on agrandit la boîte de dialogue. NPR-22844 : correctif pour CQ-4241474
* Les parsys provoquent une défaillance qui affecte la largeur d’image du périphérique de l’émulateur et coupe (place hors-cadre) tout composant qui y est ajouté. NPR-22926 : correctif pour CQ-4238224
* Lors de l’exécution de plusieurs lancements, le lancement est promu dans Auteur mais les modifications ne sont pas répliquées sur le serveur de publication en raison de l’absence d’autorisations de réplication. NPR-22934 : correctif pour CQ-4234746
* Une page verrouillée par un utilisateur au cours de la première session peut être modifiée par un autre utilisateur au cours d’une autre session. NPR-23057 ; correctif pour CQ-4199017
* Correction de l’option de réorganisation en mode Liste. NPR-23065 : correctif pour CQ-4239321
* (Éditeur de page) L’image d’un composant d’image disparaît lors de la réouverture de la boîte de dialogue. NPR-23156 : correctif pour CQ-4239978
* L’éditeur de modèles affiche uniquement 20 modèles ou dossiers et ne charge pas les autres lorsque l’on fait défiler la page vers le bas. NPR-23185 : correctif pour CQ-4238483
* (IU classique) Une erreur est générée lors du déplacement ou du changement de nom des pages. NPR-23213 : correctif pour CQ-4240971
* Impossible de modifier ou de créer des segments ContextHub. NPR-23218 : correctif pour CQ-4226948
* (Éditeur de texte enrichi) - L’opération Remplacer modifie le format d’un mot. NPR-23271 : correctif pour CQ-4239677
* Le bouton Déploiement est manquant dans l’onglet Plan directeur pour les variantes XF. NPR-23320 : correctif pour CQ-4240404
* L’UI classique ne permet pas de modifier le CUG pour des raisons d’obsolescence. NPR-24122 : correctif pour 4241823
* Correctif proactif visant a prévenir les promotions de contenu indésirables. NPR-24387 : correctif pour 4244993
* Après l’ajout d’environ 80 fragments dans un dossier dans Assets, le déclenchement du workflow à partir de la console de chronologie rencontre des erreurs. NPR-23393 ; correctif pour CQ-4211216
* Impossible de faire glisser des images dans la boîte de dialogue de l’éditeur de texte enrichi depuis l’outil de recherche de contenu. NPR-23403 : correctif pour CQ-4242094
* Erreur « Valeur du sélecteur de récursivité non valide » lors de la migration d’un composant d’AEM 6.0 vers AEM 6.2. NPR-23532 : correctif pour CQ-4241258
* (Éditeur de texte enrichi) Des info-bulles affichent le nom variable du plug-in au lieu du nom lisible du plug-in. NPR-23550 : correctif pour CQ-4243269
* Impossible d’enregistrer la boîte de dialogue avec la liste déroulante de sélection requise dans la version mobile/tablette. NPR-23904 : correctif pour CQ-4243096
* Les options du système de style apparaissent sur toutes les pages après l’installation de la version 6.3.2.1. NPR-23972 : correctif pour CQ-4244394
* L’UI classique ne permet pas de modifier le CUG pour des raisons d’obsolescence. NPR-24122 : correctif pour 4241823
* Correctif proactif visant a prévenir les promotions de contenu indésirables. NPR-24387 : correctif pour 4244993
* Les références aux ressources ne sont pas mises à jour lorsque les ressources sont déplacées. NPR-23208 : correctif pour CQ-4239879

### Plateforme {#platform-1}

* La collecte dynamique n’affiche pas les résultats après l’enregistrement en cas d’utilisation du prédicat de balises dans la facette de recherche. NPR-23401 : correctif pour Granite-21278
* Patch pour jQuery 1.12.4 de clientlib afin d’inclure un correctif de sécurité. NPR-24128 : correctif pour Granite-20058
* Les traductions d’internationalisation ne sont pas mises à jour, sauf si le lot est redémarré. NPR-23193 : correctif pour Sling-7190
* Résolveur de ressources non fermé dans ReplicationEventListener. NPR-23240 : correctif pour CQ-4241350
* Prise en charge de STARTTLS dans « Day CQ Mail Service ». NPR-23941 : correctif pour CQ-4240397
* Le nom de la balise de plainte JCR doit être renseigné automatiquement en fonction du titre de la balise. NPR-24173 : correctif pour CQ-4199411

### Intégration {#integration-4}

* (Target) Les campagnes ne sont pas activées lors de l’utilisation du type d’API au format XML. NPR-23199 : correctif pour CQ-4240936****
* La réplication de référence de configuration échoue avec la structure de dossiers intermédiaire. NPR-23485 : correctif pour CQ-4242751

### Vulnérabilité {#vulnerability-2}

* L’intégration de Salesforce est vulnérable aux attaques SSRF (Server Side Request Forgery). NPR-24289 : correctif pour CQ-424527
* Cross-site scripting (XSS) dans les liens des Projets de l’IU d’administration. NPR-23272 : correctif pour CQ-4241795

### WCM - Composants Foundation {#wcm-foundation-components}

* Le tableau Foundation est vulnérable au cross-site scripting par stockage. NPR-23214 : correctif pour CQ-4240760

### Traduction {#translation-3}

* Propriétés de la copie dynamique non supprimées lors de la création de copies de langue. NPR-23123 : correctif pour CQ-4230641

### Interface utilisateur {#user-interface-1}

* DatePicker ne prend pas en charge la définition manuelle d’un conseil de type externe par un champ masqué. La modification de l’indicateur de type génère une erreur de conversion. NPR-23371 : correctif pour Granite-21194
* Coral.ColumnView : ajout de la prise en charge de Maj.+clic. NPR-23404 : correctif pour Granite-13338
* La sélection de RT n’est pas validée en cas de sélection d’un élément ayant une valeur vide. NPR-23405 : correctif pour Granite-21283
* (OMEGA) Rapport « Fonctionnalité » en anglais seulement. NPR-23990 : correctif pour Granite-21231
* Correctifs de l’API Coral.Autocomplete. NPR-23516

### Granite {#granite-1}

* Les connexions de suivi des clients Apache Http et une utilisation élevée du tas provoquent le blocage du serveur AEM. NPR-23906 : correctif pour Granite-21056

### Commerce {#commerce-2}

* La sortie Json de la campagne ne contient pas la racine du contexte du servlet. NPR-23733 : correctif pour CQ-4243827

### Communautés {#communities-7}

* La recherche sur les communautés échoue pour quelques mots. NPR-23256 : correctif pour CQ-4240717
* Impossible d’affecter des groupes pour le problème de rôle des gestionnaires de communauté. NPR-23317 : correctif pour CQ-4241233 : CQ-4221399
* Problèmes de création de ressource avec un nom de ressource similaire. NPR-23319 : correctif pour CQ-4240700
* (ContextPath) La ventilation de la fonctionnalité de messagerie échoue pour les configurations Jetty et rencontre une erreur lors de la recherche de membres du groupe dans la liste des membres du groupe de communautés. NPR-23336 : correctif pour CQ-4241519, CQ-4242080
* Le chargement d’une image vers un forum Communities n’apparaît pas dans Adobe Storage Resource Provider (ASRP). NPR-23397 : correctif pour CQ-4242497
* Les idées supprimées s’affichent sous la forme de liens actifs dans les activités. NPR-23406
* imsmanifest.xml ne peut pas être chargé lorsque AEM s’exécute avec la racine du contexte. NPR-23483 : correctif pour CQ-4242193
* Vulnérabilités de sécurité dans une ancienne version de Handlebars. NPR-23518 : correctif pour CQ-4243055
* Le service Tunnel ne fonctionne pas. NPR-23543 : correctif pour CQ-4242217
* Les problèmes affectant les composants Communities lorsqu’on y accède par l’intermédiaire du répartiteur et de la dynamique sling incluent l’activation. NPR-23586 : correctif pour CQ-4242360, CQ-4241522
* Lorsque vous recherchez un terme de recherche qui génère de nombreux résultats par le biais de la recherche, puis que vous saisissez un nouveau terme de recherche, la pagination ne se réinitialise pas. NPR-23739 : correctif pour CQ-4222593
* Problèmes lors de    recherches dans le composant de forum. NPR-23838 : correctif pour CQ-4243770
* (Marquage de la modération dans Communities) L’autorisation en bloc des messages marqués ne fonctionne pas. NPR-23845 : correctif pour CQ-4243962
* Le texte du bouton Trier n’affiche pas la valeur sélectionnée    malgré la sélection de l’ordre de tri par défaut. NPR-23881 : correctif pour CQ-4243375
* Les notifications par web et par email ne sont pas déclenchées en raison d’un échec d’envoi du message aux groupes. NPR-23934 : correctif pour CQ-4242880
* Aucun détail sur les utilisateurs de l’indicateur et les motifs ne s’affiche lorsqu’on utilise la configuration DSRP. NPR-23973 : correctif pour CQ-4243205
* Les motifs de marquage des utilisateurs dont le marquage a été annulé restent visibles. NPR-23974 : correctif pour CQ-4243822
* Le fait de joindre deux fois deux fichiers portant le même nom à une publication de formulaire entraîne une erreur du serveur. NPR-24166 : correctif pour CQ-4244367
* Impossible de stocker les pièces jointes dont le type MIME comporte plus de 15 caractères à l’aide du DSRP (Database Storage Resource Developer). NPR-24174
* Lorsqu’une image qui enfreint les critères de chargement est glissée et déposée dans le texte de la publication, une erreur du serveur est générée et un message d’erreur générique s’affiche. NPR-24243
* Correctifs de plusieurs problèmes côté serveur affectant AEM Communities. NPR-23971 : correctif pour CQ-4243144, CQ-4242145, CQ-4243365, CQ-4244098
* Correctifs de plusieurs problèmes affectant Adobe Social. NPR-24242 : correctif pour CQ-4245054, CQ-4245120, CQ-4245296

### Campagne {#campaign}

* La sortie Json de la campagne ne contient pas la racine du contexte du servlet. NPR-23733 : correctif pour CQ-4243827

### MSM {#msm}

* Lors du déploiement de la page, la copie dynamique n’affiche pas les propriétés temporelles d’activation/désactivation héritées du gabarit. NPR-23873 : correctif pour CQ-4243431
* L’opération LiveCopy n’ignore pas les nœuds enfants des composants supprimés. NPR-23058 : correctif pour CQ-4211662

### Déchargement {#offloading}

* Demande de mécanisme de nettoyage des ressources des instances de traitement, après un traitement ou régulièrement. NPR-23638 : correctif pour Granite-21337

## Formulaires {#forms-8}

### Package de modules complémentaires Forms {#forms-add-on-package-8}

#### Formulaires adaptatifs {#adaptive-forms-1}

* Déplacement de ReCaptchaConfigService vers un package interne. Correctif pour CQ-4217459
* Le champ numérique ne respecte pas la valeur minimale. NPR-23967 : correctif pour CQ-4244830
* Prise en charge de la fonctionnalité Multi Shard dans l’intégration des formulaires adaptatifs avec Adobe Sign. NPR-23383

#### Intégration du serveur principal {#backend-integration}

* (FDM)(WebService) Prise en charge du concept d’extensions de WSDL dans l’analyseur WSDL. NPR-23640, NPR:23236: correctif pour 4205821
* Inclusion de SDLInvokerParams dans le SDK client du module complémentaire de Forms. NPR-23157

### Programme d’installation de Forms JEE {#forms-jee-installer-7}

#### Process Management {#process-management}

* Impossible d’ouvrir l’espace de travail après l’application du nouveau fichier axis.jar. NPR-23316
* LiveCycle vulnérable aux attaques XSS sur PMAdmin. NPR-23267
* Après la mise à niveau vers AEM Forms 6.1, l’espace HTML se bloque lors de l’accès à la liste des tâches pour des utilisateurs spécifiques. NPR-23943

#### Base {#core}

* Forms JEE prend en charge l’authentification mutuelle PKCS#11. NPR-21372

#### Service PDFG {#pdfg-service-2}

* Le service Paper Capture se bloque en cas de traitement simultané de plusieurs fichiers TIFF (d’environ 50 ko). NPR-23556

#### Concepteur Forms {#forms-designer}

* Output du serveur AEM Forms - Description alternative manquante pour les annotations. NPR-22207
* Ajout de la prise en charge de PDF/UA aux formulaires XML générés via Designer et Output Service. NPR-23132

### Lots OSGI et packages de contenu dans 6.3.2.2 {#osgi-bundles-and-content-packages-included-in-4}

Liste des lots OSGi inclus dans AEM 6.3.2.2

[Obtenir le fichier](assets/do-not-localize/6_3_2_2_bundle-list.txt)

Liste des packages de contenu inclus dans AEM 6.3.2.2

[Obtenir le fichier](assets/do-not-localize/6_3_2_2_content_packagelist.txt)

### Pack de correctifs cumulés 6.3.2.1 {#cumulative-fix-pack-9}

Le pack de correctifs cumulés AEM 6.3.2.1 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du Service Pack 2 (6.3.2.0) AEM 6.3 d’avril 2018.

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.10.
* Amélioration du rendu des composants Parsys dans l’interface utilisateur classique.
* Mise à jour des lots de modèles sling afin d’inclure le correctif de jeu de caractères.
* La publication sur le Brand Portal est désormais asynchrone pour tous les types de ressources.
* Mise à jour de coralui-component-richtexteditors.git de 0.1.15 à 0.1.16
* Correctifs de la fonctionnalité d’affichage/masquage des composants déroulants.
* Activation de la symétrie d’image pour le composant Image de base.
* Mise à jour des lots  http felix pour activer les attributs de session.

* Suppression de cache=true sur les modèles Sling en raison de problèmes de consommation de mémoire.

### Ressources {#assets-9}

* Lors de la modification du titre ou de l’image miniature dans les paramètres du dossier de ressources, le groupe d’origine et les autorisations du dossier sont remplacés. NPR-22171 : correctif pour CQ-4216080
* L’interface utilisateur renvoie la fausse erreur « Échec de la publication sur Brand Portal. », alors que la tâche est ajoutée à la file d’attente de réplication et que les ressources sont publiées sur le Brand Portal. NPR-22179 : correctif pour CQ-4205273
* (IU tactile) Emplacement de chargement par défaut des ressources en mode Colonnes. NPR-22465 : correctif pour CQ-4237057
* AEM renvoie une erreur StackOverflow lors de la tentative de copie d’un schéma de ressources de /conf/global vers /conf/  mytenant. NPR-22489 : correctif pour CQ-4235875
* La décompression d’une archive ZIP échoue en présence d’un espace à la fin du nom du dossier. NPR-22522 : correctif pour CQ-4238036
* Le tri à l’aide de la colonne Titre du fichier ne fonctionne pas pour les résultats de la recherche. NPR-22908 : correctif pour CQ-4239076
* Les vidéos YouTube sont balisées avec le chemin d’accès complet au lieu du nom de la balise lui-même. NPR-22976 : correctif pour CQ-4238669
* La réorganisation des dossiers situés sous un dossier réorganisable n’est pas conservée. NPR-23125 : correctif pour CQ-4231761
* HTTP 504 : erreur de dépassement du délai d’expiration de la passerelle lors d’une tentative de partage de collections à l’aide d’un partage de lien. NPR-21928 : correctif pour CQ-4234507
* Les métadonnées des mots-clés PDF ne sont pas correctement extraites et modifiées lorsqu’un fichier PDF comporte plusieurs mots-clés. Pour résoudre ce problème, la propriété des métadonnées du champ Objet a été supprimée pour les ressources PDF. Vous pouvez toutefois modifier le schéma de métadonnées pour ajouter un champ de texte à plusieurs valeurs pour le champ Objet. NPR-21972 : correctif pour 4215741****
* Les ressources incorrectes sont supprimées si le dossier sélectionné est modifié entre l’affichage des deux fenêtres contextuelles. NPR-21980 : correctif pour CQ-4233675
* (DAM) Plusieurs vulnérabilités aux attaques cross-site scripting (XSS) lors d’un ajout à l’assistant de collection. NPR-22432 : correctif pour CQ-4327086
* Le téléchargement des ressources échoue lors de l’utilisation de la gestion des droits numériques dans Assets dans Safari. Les utilisateurs ne peuvent pas télécharger de ressources comportant une clause de non-responsabilité et de longs noms de fichier. NPR-22747 : correctif pour CQ-4236460 et CQ-4235274
* Le partage public devient l’option par défaut lors de la publication de ressources sur le Brand Portal. NPR-21931 : correctif pour CQ-4218816

### Sites {#sites-9}

* Le nouvel élément de la boîte de réception Workflow affiche le chemin de page au lieu du titre de la page. NPR-21634 : correctif pour CQ-4230672
* Les composants de structure modifiables perdent les noms de classe CSS nécessaires pour la grille réactive lors de la modification. NPR-21741 : correctif pour CQ-4232374
* (IU tactile) Plusieurs vulnérabilités aux attaques cross-site scripting (XSS) pour les composants HTL. NPR-21899 : correctif pour CQ-4232511
* Impossible de modifier le type de ressource d’image de média mixte du fragment de contenu. NPR-21907 : correctif pour CQ-4233401
* Le mode plein écran du RTE pour la boîte de dialogue de l’IU tactile masque les plug-ins RTE. NPR-22034 : correctif pour CQ-4235457
* (IU tactile) L’éditeur de texte enrichi supprime tous les attributs autres que id de la balise &lt;a>. NPR-22044 : correctif pour CQ-4234133
* L’empilement de plusieurs parsys en raison de requêtes longues (plus de 6) provoque un ralentissement d’AEM. NPR-22134 : correctif pour CQ-4233904
* Impossible de modifier les autorisations sur les nœuds dont le nom contient le caractère « deux points ». NPR-22136 : correctif pour CQ-4236221
* (IU classique) La sortie de l’éditeur de texte enrichi html ajoute &#39;list-position-style: inside;&#39; à titre de style intégré à la balise &lt;ul>. NPR-22145 : correctif pour CRTE-114
* TreeNode est défini par défaut sur l’attribut nom lorsque le texte est vide. NPR-22146 : Correctif pour CQ-4234724 / CQ-4236300
* Problèmes de flux RSS, port -1 à AEM 6.3. NPR-22176 : correctif pour CQ-4233339
* (IU classique) Le raccourci de collage de texte (Ctrl+V) ne fonctionne pas pour le composant Texte (texte enrichi) prêt à l’emploi. NPR-22224 : correctif pour CQ-4236224
* Le filtrage de Tagfield ne fonctionne pas comme prévu lors de la saisie du texte. NPR-22236 : correctif pour CQ-4236655
* (Éditeur de page) Lors du collage de données textuelles dans le composant Zone cliquable, le composant Texte est également collé. NPR-22264 : correctif pour CQ-4236230
* Le champ Télécharger le fichier de la boîte de dialogue entraîne des problèmes lors de l’envoi de la boîte de dialogue. NPR-22464 : correctif pour CQ-4222192
* Le déplacement sans autorisation de réplication lance une requête de workflow d’activation si la page déplacée ou ses référents ne peuvent pas être activés. NPR-22467 : correctif pour CQ-4211765
* Problèmes de performances lors du chargement d’une page avec des audiences importantes (2000+). NPR-22478 ; correctif pour CQ-4209567
* Problèmes de persistance lorsque les boutiques ContextHub remplacent le calque de persistance par défaut lors de l’initialisation. NPR-22479 : correctif pour CQ-4218399
* Le lancement avec plusieurs pages ne publie pas de sous-pages sur les serveurs de publication si l’option « Inclure les sous-pages » n’est pas activée dans la    première racine de contenu. NPR-22482 : correctif pour CQ-4237818
* (IU tactile) La suppression des lancements via la console d’interface utilisateur classique rend toutes les pages non modifiables. NPR-22491 : correctif pour CQ-4225074
* Problèmes liés au composant Image en présence d’un espace supplémentaire dans la    boîte de dialogue. NPR-22528 : correctif pour CQ-4238183
* Lors de l’ouverture du composant à l’aide du mode    inlide, les plug-ins chargés précédemment ne sont pas visibles la deuxième fois. NPR-22591 : correctif pour CQ-4236850
* La suppression d’un lancement dans un lancement imbriqué entraîne l’abandon des sous-lancements. NPR-22621 ; correctif pour CQ-4202639
* (Sidekick de l’IU classique) L’onglet Workflow est désactivé lorsque la page est en phase de verrouillage du processus. NPR-22722 : correctif pour CQ-4237557
* Après avoir retourné une image ajoutée au composant image sur une page, les modifications ne sont pas enregistrées et    l’image d’origine est affichée sur la page. La prise en charge du rendu a été ajoutée au composant image de base via [https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/pull/141](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/pull/141). NPR-22801 : correctif pour CQ-4221539
* Lorsque l’utilisateur tente de supprimer l’ancre existante du menu d’ancrage, la fenêtre du composant de l’éditeur de texte enrichi se ferme et les modifications ne sont pas enregistrées. NPR-22802 : correctif pour CQ-4238167
* Le filtre d’omni-recherche n’affiche pas toutes les actions dans la console Sites. NPR-22804 : correctif pour CQ-4239007
* Problème avec le Copier/Coller dans l’IU tactile avec le Presse-papiers du système d’exploitation et le Presse-papiers AEM interne. NPR-22807 : correctif pour CQ-4220383
* Incohérence dans la mise en surbrillance de l’extrait renvoyée par Lucene Search. NPR-22879 : correctif pour CQ-4238513
* L’activation d’une page avec    les instances de publication désactivées produit un statut vert au lieu de passer au jaune. NPR-22927 : correctif pour CQ-4236310
* (StyleSystem) Un saut s’applique à la position de l’écran lors de la sélection du style dans la fenêtre contextuelle. NPR-23183 : correctif pour CQ-4238867
* (Gérer la publication) Le passage au mois suivant du calendrier nécessite plusieurs clics. NPR-23508 : correctif pour CQ-4242732

### Plateforme {#platform-2}

* La servlet Sling Exporter n’exporte pas correctement les caractères japonais. NPR-22153 : correctif pour CQ-4228920
* Verrouillage du planificateur au démarrage. NPR-22440 : correctif pour Sling-7004
* Impossible de synchroniser des groupes entre deux instances de publication. NPR-21943 : correctif pour Granite-19564
* Problèmes de performance avec le résolveur de session/ressources partagées org.apache.sling.i18n. NPR-23390 : correctif pour Sling-7543

### Intégration {#integration-5}

* Résolveur de ressources non fermé dans com.day.cq.analytics.sitecatalyst. NPR-22323 : correctif pour CQ-4236515
* TargetContentImpl ralentit AEM pendant les requêtes longues. NPR-22361 : correctif pour CQ-4236907
* Le moteur Target (mbox.js, at.js) n’utilise pas d’URL mal formées et utilise des URL contenant deux-points qui peuvent rencontrer des problèmes avec certains déploiements. NPR-22366 : correctif pour CQ-4237854
* Lorsque vous fournissez un at.js ou mbox.js personnalisé, le script d’inclusion est écrit sur la page sous forme de texte au lieu de balises HTML. NPR-22441 : correctif pour CQ-4203691
* En mode Target, les auteurs peuvent modifier un composant hérité du plan directeur sans annuler l’héritage. NPR-22751 : correctif pour CQ-4237907
* L’élément PersonalizationDataSource renvoie une exception NullPointerException en raison d’une absence du nœud de contenu    jcr : content node. NPR-22850 : correctif pour CQ-4222122
* Le ciblage AEM échoue lors de l’utilisation d’une langue    autre qu’anglaise. NPR-22917 : correctif pour CQ-4218213
* Il manque des ressources connexes en cas de publication d’une page avec du contenu ciblé. NPR-23064 : correctif pour CQ-4227119
* Les utilisateurs ne peuvent pas voir les valeurs de paramètre statique de test dans l’appel mbox qui s’affiche lors du test avec AT.js comme bibliothèque cliente dans la configuration cloud. NPR-21930 : correctif pour CQ-4234520

### Composants WCM-Foundation {#wcm-foundation-components-1}

* iParsys crée le décalage de position après avoir décoché la case Annuler/Désactiver l’héritage. NPR-21905 : correctif pour CQ-4230951
* La fonctionnalité Afficher/Masquer du composant déroulant de formulaire ne fonctionne pas comme prévu. NPR-22327 : correctif pour CQ-4222853
* Le composant CAPTCHA a été abandonné pour une meilleure sécurité. Si vous utilisez le composant CAPTCHA, le message « Le composant Captcha est obsolète et ne doit plus être utilisé. » s’affiche après l’installation de la version 6.3.2.1 ou ultérieure. Le composant AEM peut être personnalisé de manière à inclure reCAPTCHA pour une meilleure sécurité. NPR-22151 : correctif pour CQ-4220052

### WCM - Éditeur de page {#wcm-page-editor}

* Les scripts intersites (XSS) se reflètent lors de l’utilisation d’un sélecteur non valide. Correctif pour CQ-4270397

### Traduction {#translation-4}

* Étude des problèmes liés à la fonctionnalité Aperçu. NPR-22114 : correctif pour CQ-4223753

### Interface utilisateur {#user-interface-2}

* Problèmes avec le sélecteur de mois du calendrier Coral lorsque la plage de dates « min » et « max » est définie. NPR-22716 : correctif pour CUI-7187
* (IU classique) Le composant affiche les valeurs par défaut même si le service de modèle de données de formulaire associé est défini sur un champ vide. NPR-22272 : correctif pour GRANITE-19744

### Granite {#granite-2}

* Problèmes de stabilité affectant l’instance de publication AEM de partage de ressources, provoqués par des fuites de mémoire. NPR-22205, NPR-23178 : correctif pour Sling-5668, Sling-7292 et Sling-7470.
* L’ID de service instable ne doit pas être utilisé pour les noms d’attributs de session. NPR-22821 : correctif pour Granite-21059
* Lorsqu’une session gérée par tableau blanc http est invalidée, la session du conteneur est également invalidée si celle-ci ne comporte aucun autre attribut de session. NPR-23059 : correctif pour FELIX-5819
* Une partie de la configuration OSGi de LogbackManager peut être absente au démarrage. NPR-23060 : correctif pour Granite-19791

### Commerce {#commerce-3}

* Activation de la création de workflow dans le menu Fragments d’expérience. NPR-22347 : correctif pour CQ-4221661
* Erreurs de fragments d’expérience reproductibles sur WeRetail. NPR-21958 : correctif pour CQ-4220061
* L’activation d’une page contenant un fragment d’expérience supprimé renvoie une exception NullPointerException. NPR-23179 : correctif pour CQ-4239939

### Projets {#projects}

* (Projet multilingue) Le projet ne répertorie pas les tâches de traduction pour plus de 19 langues. NPR-22498 : correctif pour CQ-4229978

### Workflow {#workflow}

* (IU classique) L’activation ou la désactivation d’un lanceur de workflow entraîne un comportement erroné. NPR-22907 : correctif pour CQ-4239153

## Formulaires {#forms-9}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

Les principaux aspects pour AEM Forms sont les suivants :

* Ajout de la prise en charge du type d’entrée HTML5.
* Correction de l’authentification de base des en-têtes SOAP.
* Ajout de la prise en charge de l’attribut de titre pour l’hyperlien.
* Activation de l’identifiant PDF/UA dans l’arborescence d’accessibilité de Forms Designer.
* Activation de l’authentification de certificat pour les utilisateurs de Workbench.
* Ajout de la prise en charge de la création de fichiers PDF conformes à la norme PDF/A-2a ou PDF/A-3a.

### Package de modules complémentaires Forms {#forms-add-on-package-9}

#### IU d’administration Forms {#forms-admin-ui}

* Le mot de passe est visible en texte brut lors de l’inspection du champ de mot de passe pour les pages de configuration des connecteurs ECM. NPR-22508 : correctif pour CQ-4236065

#### Service Forms {#forms-service}

* Lorsque SSL est activé, les événements Envoyer et Abandon ne fonctionnent pas avec les analyses de formulaire. NPR-22637 ; correctif pour CQ-4237973

#### Gestion des utilisateurs {#user-management}

* Impossible de synchroniser LDAP en raison d’une version de cglib-nodep incorrecte. NPR-22493 : correctif pour CQ-4234099

#### Formulaires adaptatifs {#adaptive-forms-2}

* Les fonctions personnalisées de l’éditeur de règles ajoutent un supplément ; après l’appel de fonction, la validation échoue même si la fonction personnalisée renvoie « true ». NPR-22481 : correctif pour CQ-4235499
* Quel que soit le modèle de date sélectionné, le composant Sélecteur de date ne suit pas le modèle lors de l’affichage des messages de validation minimum et maximum. NPR-22444 : correctif pour CQ-4236269
* Le format de date envoyé dans « Envoyer la demande » doit correspondre au modèle fourni dans le composant Sélecteur de date. NPR-22384
* Le nombre maximal de caractères spécifié pour un champ de texte de formulaire adaptatif n’est pas honoré sur les périphériques Samsung sous Android 6.0. NPR-22363, NPR-22364 : correctif pour CQ-4235205
* (Microsoft Edge) (IE11) Le composant Champ de texte de formulaire adaptatif avec champ multiligne affiche la valeur par défaut « Null » au lieu d’être vide. NPR-22284 : correctif pour CQ-69107
* Le codage d’entrée SOAP UTF-8 dans les formulaires adaptatifs renvoie des erreurs avec des pages tronquées. NPR-20105 : correctif pour CQ-4222669
* Le composant Conteneur AEM Forms n’est pas disponible pour modification une fois qu’un formulaire incorrect est configuré dans la page de sites. Correctif pour CQ-4237456
* Les tests de développement échouent lorsqu’ils sont exécutés sur des serveurs JEE. Correctif pour CQ-4222082
* Échec des tests AF sur les serveurs JEE en raison de problèmes de minification dans le framework Calvin. Correctif pour CQ-4217220

#### Forms Manager {#forms-manager}

* (Firefox) Impossible de mettre à jour les propriétés de schéma XML des formulaires adaptatifs, car les options du document d’enregistrement (DOR) ne sont pas présélectionnées dans la page des propriétés. NPR-22298 : correctif pour CQ-4237402
* Les formulaires qui sont modifiés après la publication de la page ne sont pas republiés lors de la publication du site. NPR-23013 : correctif pour CQ-4236566

#### Intégration du serveur principal {#backend-integration-1}

* L’authentification de base prête à l’emploi pour les services SOAP ne fonctionne pas pour l’authentification de base dans l’intégration FDM. NPR-23238 : correctif pour CQ-4241308

#### Correspondence Management {#correspondence-management}

* Les fichiers XDP prêts à l’emploi, lorsqu’ils sont utilisés dans la lettre et prévisualisés, affichent le contenu chevauché avec le pied de page. Correctif pour CQ-4212414

#### Incohérence affectant le service assembleur {#assembler-service}

* entre les rapports Acrobat DC et AEM concernant l’erreur de vérification de la conformité PDF/A-1b. NPR-22051, NPR-22050 : correctif pour CQ-4226128, CQ-4227671

### Programme d’installation de Forms JEE {#forms-jee-installer-8}

#### Workbench {#workbench}

* Activation de l’authentification de certificat pour les utilisateurs de Workbench. NPR-20644 : correctif pour CQ-4214486
* Le téléchargement du journal du serveur à l’aide de Workbench fonctionne uniquement pour un serveur et non pour l’autre serveur. NPR-21079 : correctif pour CQ-4229842

#### Gestion des processus {#process-management-1}

* (Espace de travail HTML) Problèmes de taille d’écran avec les barres de défilement. NPR-23288
* (Espace de travail HTML) Les points de départ du workflow ne sont pas triés dans un ordre alphanumérique. NPR-22841 : correctif pour CQ-4238944
* (Espace de travail HTML) Les données de préparation sont déclenchées à la fermeture du formulaire dans l’espace de travail. NPR-21127 : correctif pour CQ-4224574
* (Espace de travail HTML) Lors de l’appel d’un workflow qui nécessite des remarques avec des descriptions longues, le bouton de développement des remarques ne fonctionne pas. Correctif pour CQ-4241488

#### Base {#core-1}

* Erreur rencontrée au démarrage lors du lancement du planificateur. NPR-22990
* Correctif visant à empêcher les navigateurs de stocker les informations d’identification saisies dans les formulaires HTML. NPR-21762 : correctif pour CQ-4206543
* Les problèmes signalés dans l’analyse de code statique de base doivent être résolus. Correctif pour CQ-104446

#### Service PDFG {#pdfg-service-3}

* PDF Generator ne parvient pas à produire des documents PDF avec les niveaux de signets spécifiés. NPR-22921, NPR-22285 : correctif pour CQ-4230562
* Ajout de la prise en charge de la création de fichiers PDF conformes à la norme PDF/A-2a ou PDF/A-3a. NPR-23021 : correctif pour CQ-4214172

#### Concepteur Forms {#forms-designer-1}

* Il manque l’identifiant PDF/UA lors de l’enregistrement au format PDF depuis le Concepteur. NPR-23137
* Les objets de chemin d’accès, par exemple : les bordures, les soulignements et les hyperliens ne sont pas balisés lors de l’enregistrement au format PDF depuis le Concepteur. NPR-23136
* L’objet image ne comporte aucun cadre de sélection lorsqu’il est enregistré au format PDF depuis le Concepteur. NPR-23134
* Les hyperliens en ligne définis dans le Concepteur ne sont pas balisés et ne contiennent pas de texte de remplacement lors de l’enregistrement au format PDF depuis le Concepteur. NPR-23133
* L’ouverture du package de données XML avec le Concepteur d’AEM Forms 6.3 supprime le formatage XHTML de la source XML. NPR-21178 : correctif pour LC-3917046

#### Installation de LCM {#install-lcm}

* Mise à jour de Jsafe Jars vers Cryptoj 6.1.3.1 dans le programme d’installation et LCM. NPR-21370

#### Service Signatures {#signatures-service}

* Exception rencontrée lors de la tentative de signature/certification numérique d’un document PDF via HSM. NPR-21154 : correctif pour CQ-4226978

### Lots OSGI et packages de contenu dans 6.3.2.1 {#osgi-bundles-and-content-packages-included-in-5}

Liste des lots OSGi inclus dans AEM 6.3.2.1

[Obtenir le fichier](assets/do-not-localize/bundle-list_002_.txt)

Liste des packages de contenu inclus dans AEM 6.3.2.1

[Obtenir le fichier](assets/do-not-localize/content_package_comparison.txt)

Le pack de correctifs cumulés 6.3.1.2 consiste en une mise à jour importante comprenant plusieurs correctifs internes et clients apportés depuis la disponibilité générale du Service Pack 1 (6.3.1.0) AEM 6.3 d’octobre 2017.

Les principaux aspects du pack de correctifs cumulés AEM sont les suivants :

* Modification de l’interface utilisateur pour prendre en charge la mise en œuvre de la fonctionnalité CUG dans l’AEM Assets.
* Correction de problèmes d’interface utilisateur sur la page de vérification des licences pour une meilleure expérience.
* Activation de la prise en charge des tâches du workflow OSGi dans l’application AEM Forms.

### Ressources {#assets-10}

* Modification de l’interface utilisateur pour prendre en charge la mise en œuvre de la fonctionnalité CUG dans l’AEM Assets. NPR-19485
* Le chargement d’une ressource en tant que nœud enfant direct de soi-même à l’aide de l’IU tactile provoque un problème. La ressource est chargée en tant qu’enfant direct de la ressource précédemment sélectionnée. NPR-19736
* Le prédicat de plage de dates et le prédicat de plage ne fonctionnent pas lors du chargement d’une recherche/collecte dynamique enregistrée. NPR-19844 : correctif pour CQ-4220808
* L’instance d’AEM est ralentie lorsque plusieurs ressources (plus de 4) sont publiées sur Brand Portal. NPR-20009 : correctif pour CQ-4213426
* Impossible de télécharger des ressources avec des espaces à partir de la page de vérification de licence. NPR-20067 : correctif pour CQ-4216557
* Problèmes de traitement lors du chargement de fichiers PSB avec plusieurs calques alpha. NPR-20250 : correctif pour CQ-4220869
* Les utilisateurs ne peuvent pas télécharger des fichiers qui possèdent des noms de fichier longs et des clauses de non-responsabilité définies. NPR-20254
* ProductAssetsUploader laisse les fichiers temporaires du cache JAVA dans le dossier TEMP Java. NPR-20256 : correctif pour CQ-4221801
* Remplacement du code de comparaison de version par du code propriétaire Adobe en raison de problèmes de licence. NPR-20272 : correctif pour CQ-4223758
* Les métadonnées d’une propriété de chaîne, documentNumber, s’affichent sous la forme d’une date, alors qu’il doit s’agir d’un nombre. NPR-20291 : correctif pour CQ-4223991
* L’extraction de texte est bloquée pour un fichier PDF corrompu. NPR-20416 : correctif pour CTG-4150375
* Les fichiers compressés contenant des ressources dont les noms sont incompatibles avec UTF-8 ne sont pas correctement téléchargés. NPR-20420 : correctif pour CQ-4219961
* Un nombre trop élevé de caractères dans l’omni-recherche provoque le blocage du serveur AEM. NPR-20434 : correctif pour CQ-4223602
* Le défaut de métadonnées de l’API de ressources DAM rompt les API xmp-write-back. NPR-20607 : correctif pour CQ-4220455
* Problèmes de performances lors de l’ajout d’utilisateurs à des collections. NPR-20699 : correctif pour CQ-4225733
* La publication sur le Brand Portal à partir d’AEM ne devrait pas être autorisée pour les ensembles de médias dynamiques. NPR-20320 : correctif pour CQ-4221147
* Les vidéos contenant des espaces et accents ne produit aucune vidéo pour la page Rendus. NPR-19961 : correctif pour CQ-4221014
* Résolution de plusieurs problèmes de gestion de dossiers avec les API Ressources. NPR-20569
* AEM Dynamic Media Classic (anciennement Scene7) ne parvient pas à synchroniser les ressources à partir du serveur AEM lorsque le chemin de destination dans la configuration du service cloud pointe vers un sous-dossier du chemin racine. CQ-4228265
* Groupe d’emails d’apache commons `{org.apache.commons/commons-email/1.5}` a été ajouté en remplacement de `{com.day.commons.osgi.wrapper/com.day.commons.osgi.wrapper.commons-email/1.2.0-0002}`.

### Sites {#sites-10}

* Problèmes de droits d’administrateur : impossible de supprimer les membres des groupes d’utilisateurs fermés des propriétés de la page. NPR-20631
* Le nom saisi du workflow doit être disponible dans la case Notification lors de la publication de la page via Gestion de la publication. NPR-20046 : correctif pour CQ-4221586
* L’application de texte stylisé sur deux lignes dans l’éditeur de texte enrichi, puis leur fusion au sein d’un même paragraphe supprime les plages de style. NPR-20110 : correctif pour CQ-4223051
* Les modifications apportées aux propriétés des champs dans plusieurs onglets de la boîte de dialogue de modification des propriétés ne sont parfois pas enregistrées. NPR-20286
* Balise inattendue à la fin du contenu collé dans le fragment de contenu. NPR-20413 : correctif pour CQ-4224014
* Mise en œuvre d’un mécanisme dans Adobe Campaign pour récupérer la stratégie d’une ressource de contenu à partir d’une ressource de ciblage externe. NPR-20667
* Le plug-in Richtext ne fonctionne pas pour les barres en ligne et en plein écran dans l’IU tactile multichamp. NPR-20973

### Campagne {#campaign-1}

* Les espaces réservés ne sont pas visibles dans une page qui contient plusieurs composants parsys. NPR-20436 ; correctif pour CQ-4215000

### Commerce {#commerce-4}

* Les fragments d’expérience ne s’affichent pas correctement dans Internet Explorer 11. NPR-20161 : correctif pour CQ-4223319
* Dans les workflows de commerce, une image vierge est automatiquement insérée lors de la création d’une variante basée sur un produit principal avec plusieurs images. NPR-20068 : correctif pour CQ-4222048
* Le filtrage par balises sur les pages de collection dans la console de produits ne fonctionne pas. NPR-20292 : correctif pour CQ-4224023

### Communautés {#communities-8}

* Les résultats de recherche ne correspondent pas au composant searchresult. NPR-20070 : correctif pour CQ-4220913
* Les notifications par e-mail ne sont déclenchées pour aucune des activités liées au modérateur sur les composants publiés. NPR-20122
* Une pagination vierge sans résultat s’affiche pour les utilisateurs anonymes de la communauté. NPR-20136 : correctif pour CQ-4220738
* Configuration du déclencheur d’alerte lorsqu’un UGC est détecté comme indésirable ou lorsqu’un utilisateur publie sur un site prémodéré. NPR-20274 : correctif pour CQ-96850
* Correction de plusieurs problèmes dans les pages des sites AEM Communities, dont des redirections incorrectes et des problèmes d’actualisation des pages. NPR-20344
* CommunityUserOperationExtension déclenche une exception d’attribution de classe. NPR-20532 : correctif pour CQ-4224385
* Après la création d’un site Communities, les utilisateurs ne peuvent plus l’ouvrir à partir du plan de site, car le chemin d’accès au contexte n’est pas ajouté en préfixe à l’URL. NPR-20730

### Intégration {#integration-6}

* Migration des informations d’identification Analytics existantes vers l’authentification WSSE. NPR-19962 : correctif pour CQ-4218071
* La réactivation du segment après toute modification échoue et renvoie une erreur. NPR-20054 : correctif pour CQ-4218401
* La configuration du service cloud Search&amp;Promote ignore la méthode de récupération de formulaire, ce qui la rend inutilisable sur l’instance de création. NPR-20447 : correctif pour CQ-4206076
* Une définition de filtre ambiguë dans le package de contenu entraîne le remplacement des chemins d’accès lorsque la fonction Search&amp;Promote est installée. NPR-20808

### Mobile On-Demand {#mobile-on-demand}

* Les propriétés des métadonnées des fichiers de type TXT s’affichent dans différents éditeurs de métadonnées chaque fois que leurs propriétés sont affichées. NPR-20239

### Plateforme {#platform-3}

* Résolution d’une exception de résolveur de ressources non fermé. NPR-19749 : correctif pour Granite - 19143
* Demande d’affichage des cartes personnalisées au côté des contrôles d’intégrité par défaut dans le tableau de bord des opérations. NPR-20145
* Le calque d’annotation de l’éditeur de page ne fonctionne pas correctement dans Internet Explorer 11. NPR-20222 : correctif pour CQ-4222818
* Fuite de session lors de la définition de l’agent utilisateur en tant qu’administrateur dans l’agent de réplication. NPR-20578
* La variable requestAttributes n’est pas désactivée pour les autres instructions data-sly-resource. NPR-20639 : correctif pour 4226206
* Correction de problèmes liés aux requêtes Curl Head pour les ressources prêtes à l’emploi dans AEM. NPR-20781 : correctif pour CQ-4221520

### Projets {#projects-1}

* Le chargement de différents projets à partir de la console Projets prend plus de temps. NPR-20314
* L’installation d’AEM 6.3.0.1 supprime le keystore de l’utilisateur de dam-update-service. NPR-20018
* Dans certains déploiements personnalisés, les utilisateurs qui tentent de sélectionner un cessionnaire dans le module addTask prennent plus de temps pour remplir la liste dans le sélecteur d’utilisateurs. NPR-20283 : correctif pour CQ-4224193

### Interface utilisateur {#user-interface-3}

* Le champ de couleur est défini sur « Toujours obligatoire » malgré les attributs de la boîte de dialogue. NPR-19702
* La barre de défilement ne s’affiche pas pour le composant multi-champ en plein écran dans Internet Explorer 11. NPR-20261 : correctif pour CQ-4219782
* Les requêtes antérieures ne sont pas abandonnées si des requêtes consécutives sont déclenchées, ce qui entraîne des résultats incorrects. NPR-20398 : correctif pour GRANITE-19306

### Workflow {#workflow-1}

* Les utilisateurs ne sont pas informés des tâches de workflow qu’ils reçoivent dans leur boîte de réception. NPR-20213 : correctif pour CQ-4221639
* Le sélecteur d’utilisateurs de Granite prêt à l’emploi ne charge aucun utilisateur lorsque l’on clique sur la liste déroulante de la boîte de dialogue à l’étape Participant du modèle de workflow. NPR-20236

## Formulaires {#forms-10}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms {#forms-add-on-package-10}

#### Formulaires adaptatifs {#adaptive-forms-3}

* La prise en charge de l’expression d’agrégation pour les panneaux répétés est absente. NPR-20861
* La liste déroulante affiche la dernière valeur stockée, même si le service de modèle de données de formulaire associé ne renvoie aucune valeur. NPR-20710
* Impossible de modifier les règles existantes avec des contraintes booléennes dans l’éditeur de règles. NPR-21128

#### Portail des formulaires {#form-portal}

* Le profil HTML s’affiche pour un formulaire adaptatif, même si son type de ressource n’est pas XDP. NPR-20079

#### Intégration du serveur principal {#backend-integration-2}

* Impossible de définir la valeur du composant commutateur entre vrai et faux. NPR-21111

#### Workflow OSGI {#osgi-workflow}

* La gestion des envois de workflow répertorie uniquement dix applications. CQ-4230193

#### Formulaires HTML5 {#html-forms-3}

* Le nom d’un objet de formulaire XDP, comme un sous-formulaire, s’affiche sous forme d’info-bulle lorsqu’il n’est pas défini dans les configurations d’accessibilité. NPR-20523

### Programme d’installation de Forms JEE {#forms-jee-installer-9}

#### Gestion des processus {#process-management-2}

* Le point de départ FormSetPrefillApp ne préremplit pas les champs de la visionneuse de formulaires dans l’application AEM Forms. NPR-20950

#### Forms - AEM (LiveCycle) {#forms-aem-livecycle}

* Installation de la dernière bibliothèque CTJPEG2K pour résoudre une vulnérabilité de sécurité critique. Cela a un impact sur les modules XMLFM (AEM et IfBA), RM et PDFG. NPR-20625 : NPR-21337.

### Feature Packs inclus {#feature-packs-included}

#### Application AEM Forms {#aem-forms-app}

* Activation de la prise en charge des tâches du workflow OSGi dans l’application AEM Forms. CQ-4222638

### Lots OSGI et packages de contenu dans 6.3.1.2 {#osgi-bundles-and-content-packages-included-in-6}

Liste des lots OSGi inclus dans AEM 6.3.1.2

[Obtenir le fichier](assets/do-not-localize/6_3_1_2-bundle-list.txt)

Liste des packages de contenu inclus dans AEM 6.3.1.2

[Obtenir le fichier](assets/do-not-localize/6_3_1_2-content-package-list.txt)
Le pack de correctifs cumulés 6.3.1.1 consiste en une mise à jour importante comprenant plusieurs correctifs internes et clients apportés depuis la disponibilité générale du Service Pack 1 (6.3.1.0) AEM 6.3 d’octobre 2017.

Les principaux aspects du pack de correctifs cumulés AEM sont les suivants :

* Activation de l’action Publier sur le Brand Portal pour le formulaire de schéma de métadonnées par défaut.
* Changement de comportement lors de l’affichage des titres sur la carte d’image pour les images ayant une propriété dc: title définie sur String [] (multichamp).
* Remplacement du rendu côté serveur de l’heure par le composant fondation-time.
* Activation de la publication de balises à partir d’AEM dans le Brand Portal depuis la console tagadmin/tagging.
* L’API JSON publiée consomme des fragments de contenu.
* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.5.

### Ressources {#assets-11}

* Le mappage de deux champs possédant la même propriété avec différents types de champ de propriété génère une erreur interne. NPR-19462 : HF pour CQ-4216828
* dc: title et dc: description ne bascule pas vers une valeur multichamp dans    crx /de. NPR-19570 : HF pour CQ-4209086
* La visionneuse dynamique charge le rendu vidéo de la qualité la plus faible pour tester l’expérience de lecture vidéo en mode création. NPR-19004
* Le rendu dynamique ne peut pas être téléchargé pour les ressources qui incluent des espaces dans leur nom. NPR-19433 : correctif pour CQ-4211738
* Impossible de charger la liste complète des pages/ressources en mode Colonnes avec Chrome. NPR-19566 : correctif pour CQ-4214248
* L’option Publier sur le Brand Portal n’est pas disponible lors de la sélection d’un schéma, d’une facette de recherche ou d’un paramètre prédéfini. NPR-19550
* Lors de la sélection d’une ressource en mode Colonnes et d’un clic sur Modifier, la page renvoie une erreur. NPR-20301 : correctif pour CQ-4224052
* L’affichage Expiration des ressources est désactivé en cas de chevauchement de fuseaux horaires positifs et négatifs. NPR-20329 : correctif pour CQ-4219333

### Campagne {#campaign-2}

* Les composants du curseur de campagne n’apparaissent pas lorsque l’expérience par défaut est sélectionnée pour une campagne. NPR-19213

### Intégration {#integration-7}

* Le fichier at.js personnalisé n’est pas publié lorsqu’il est utilisé avec l’utilisateur anonyme. NPR-19542 : correctif pour CQ-4219592
* Le champ Moteur de ciblage dans l’assistant de configuration est défini sur ContextHub (AEM) au lieu d’Adobe Target. NPR-19320 : HF pour CQ-4218465
* La section Audience est corrompue lors de la création de l’expérience. NPR-19110
* La boîte de dialogue de ciblage ne s’affiche pas en mode ciblage lorsqu’un module cible est modifié et enregistré plusieurs fois. NPR-19144 : correctif pour CQ-4216708
* Les propriétés d’accès des articles sont mal configurées dans Adobe Digital Publishing Solution dans l’IU classique. NPR-19367
* Comportement incorrect du pliage automatique lors de la personnalisation des offres via Campaign si les utilisateurs ont accès à plusieurs zones. NPR-19290 : correctif pour CQ-4218029

### Sites {#sites-11}

* Les valeurs de la liste déroulante des champs multicomposites ne sont pas renseignées à nouveau en raison d’une modification du code dans Sidekick.js après la mise à niveau de l’instance vers AEM 6.1SP2-CFP3. NPR-19450 : HF pour CQ-4194771
* WCMMode.EDIT ne fonctionne pas pour les composants ciblés en mode création. NPR-19387
* L’API JSON publiée consomme des fragments de contenu. NPR-19500
* La fonctionnalité gras, italique et souligné ne fonctionne pas pour les champs d’éditeur de texte enrichi dans la boîte de dialogue de création. NPR-19670 : NPR-19718 : correctif pour CQ-4219088

### Mobile On-Demand {#mobile-on-demand-1}

* Problèmes de rendu avec la console d’article AEM, provoquant des ralentissements en cas d’utilisation d’images en taille réelle. NPR-19088

### Traduction {#translation-5}

* Impossible de générer un aperçu pour les projets de traduction. NPR-19289

### Sécurité {#security}

* Erreur de connexion SSL. Impossible d’établir une connexion sécurisée au serveur. NPR-19628

### Communautés {#communities-9}

* Le courrier est déclenché lors de la publication de contenu sur des sites prémodérés. NPR-20008
* Les notifications par e-mail ne fonctionnent pour aucune des activités liées au modérateur sur les composants publiés. NPR-19767 : HF pour CQ-4218060

### Plateforme {#platform-4}

* Problèmes de stabilité liés au déploiement du serveur de production AEM. NPR-19707
* Les taglibs personnalisées qui font référence aux balises implémentées en tant que script sont introuvables après la mise à niveau vers AEM 6.3. NPR-19087
* Correctifs de bugs HTL pour AEM 6.3.1. NPR-19161
* Le champ de texte enrichi n’est pas modifiable dans les composants multi-champs. NPR-19604 : correctif pour Granite-16755
* Le service Modèle d’email Adobe ajoute des balises aux modèles utilisateur personnalisés. NPR-19190
* Correctif pour Oak 1.6.5. NPR-19148

### Commerce {#commerce-5}

* Le bouton Démarrer le workflow après avoir sélectionné un éditeur de variation XF reste sans effet. NPR-19642 : correctif pour CQ-4207796

### Projets {#projects-2}

* Les éditeurs de projet ne peuvent pas copier/coller de ressources dans le dossier de ressources du projet. NPR-19619: Correctif pour CQ-4215321

### Gestion de contenu web {#web-content-management}

* Dans l’écran de déploiement, les cases à cocher correspondant aux pages de copie dynamique ne peuvent pas être cochées ni décochées. NPR-19518
* La modification en masse des propriétés des pages ne peut pas être utilisée correctement, car tous les onglets et champs peuvent être modifiés en masse. NPR-19451
* Les propriétés de la barre d’outils et les propriétés d’alignement des images n’apparaissent pas lors de la modification d’une image dans l’IU classique. NPR-19488 : HF pour CQ-4217914

### Interface utilisateur {#user-interface-4}

* Avec le navigateur Google Chrome, les utilisateurs ne peuvent pas charger la liste complète des pages/ressources en utilisant le mode Colonnes dans l’interface tactile. NPR-19566 : correctif pour CQ-4214248

### Brand Portal {#brand-portal-1}

* Impossible de publier des ressources depuis AEM avec des commentaires et des annotations. NPR-19590 : correctif pour CQ-4218386
* Activation de la publication de balises à partir d’AEM dans Brand Portal depuis la console tagadmin/tagging. NPR-20271 : correctif pour CQ-4223948
* Correction du champ « activé » dans l’IU de configuration du service cloud du Brand Portal. Correctif pour CQ-4211101
* La réplication de formulaires de recherche échoue. Correctif pour CQ-4220080

## Formulaires {#forms-11}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms {#forms-add-on-package-11}

#### Formulaires adaptatifs {#adaptive-forms-4}

* Le workflow Envoyer vers JEE ne renvoie pas le paramètre de sortie côté JEE vers AEM et renvoie l’erreur « Ignorer car la valeur n’est pas primitive ». NPR-20265
* Les formulaires adaptatifs n’autorisent pas le format PDF en tant que pièce jointe dans Safari. NPR-19625
* RestoreGuideState remplace la carte customcontextproperty. CQ-4222877
* Lors de la configuration de Google reCaptcha à l’aide du service Cloud, dans les environnements qui nécessitent la configuration de org.apache.http.proxyconfigurator pour les connexions externes, les appels POST ne semblent pas passer par PROXY. NPR-20454
* Les formulaires adaptatifs basés sur des schémas XSD envoient des valeurs XML erronées pour les champs numériques des installations dont les paramètres régionaux comportent un séparateur décimal autre que « . », ce qui entraîne des erreurs. NPR-20444
* Les paramètres de proxy définis pour la « Configuration du proxy des composants HTTP Apache » ne sont pas respectés lors d’une requête HTTP à un serveur tiers. Problèmes de délai d’expiration de connexion à l’aide des appels HTTP GET ou POST. NPR-20457, NPR-20456, NPR-20455, NPR-20451

#### Intégration de données Forms {#forms-data-integration}

* Les caractères UTF-8 en sortie du service SOAP ne sont pas correctement copiés dans les champs de formulaires adaptatifs pour les langues autres que l’anglais. NPR-20238 : NPR-20103

#### Correspondence Management {#correspondence-management-1}

* Un copier-coller de contenu depuis un fichier Word perd la couleur et la police de son contenu dans l’éditeur de texte. NPR-19521

#### Services d’assemblage {#assembler-services}

* Incohérence entre les résultats d’Acrobat et d’AEM lors de la vérification de la conformité d’un document au format PDFA-1b. NPR-19280

#### Workflow {#workflow-2}

* Étape de signature du workflow doit permettre aux appels http de se connecter via le proxy. NPR-20529

#### Formulaires HTML5 {#html-forms-4}

* Ajout de la prise en charge de l’événement preSubmit. NPR-20604

### Programme d’installation de Forms JEE {#forms-jee-installer-10}

#### Gestion des processus {#process-management-3}

* Les onglets de pièces jointes, de notes et de détails du processus ne fonctionnent pas dans l’espace de travail lorsque le formulaire est agrandi/réduit et enregistré en tant que brouillon ou transféré. NPR-20243
* Le champ de texte multiligne (TextArea) ne conserve pas de nouveau caractère de ligne ni de saut de ligne dans le texte après l’envoi des données dans l’espace de travail HTML. NPR-20085

#### Rapports de workflow {#process-reporting}

* Les rapports de workflow ne récupèrent pas correctement les données en raison d’une exception NullPointerException. NPR-19759

>[!NOTE]
>
>Installation du package intégré LiveCycle répertorié dans l’article [Versions d’AEM Forms](aem-forms-releases.md) pour résoudre le problème.

#### Services standard {#standard-services}

* docConvertor ne prend pas en charge l’aplatissement des transparences dans les PDF et ne parvient pas à produire un fichier PDF/A. NPR-16228 : Correctif pour CQ-4214488

#### Base {#core-2}

* Lorsque l’on arrête le serveur AEM Forms qui exécutant en configuration de grappe sur l’application JBoss, le serveur d’applications est déconnecté de la base de données. Cela peut conduire à des problèmes de corruption de données. NPR-19724

### Feature Packs inclus {#feature-packs-included-1}

* Le champ déroulant schéma des métadonnées ne peut pas être défini comme obligatoire car la validation obligatoire des champs est absente pour les ressources. NPR-17882 : FP pour CQ-4208373

### Lots OSGI et packages de contenu dans 6.3.1.1 {#osgi-bundles-and-content-packages-included-in-7}

Liste des lots OSGi inclus dans AEM CFP 6.3.1.1

[Obtenir le fichier](assets/do-not-localize/bundle-list.txt)

Liste des packages de contenu inclus dans AEM CFP 6.3.1.1

[Obtenir le fichier](assets/do-not-localize/content-package-list.txt)

Le pack de correctifs cumulés 6.3.0.2 consiste en une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale d’AEM 6.3 en avril 2017.

Les principaux aspects du pack de correctifs cumulés AEM sont les suivants :

* Auditabilité du contrôle d’accès des utilisateurs
* Inclut la version 1.6.2 du référentiel intégré (Apache Jackrabbit Oak)
* Résolution des problèmes de résolveur de ressources non fermé
* Simplification de la configuration pour les services de contenu dynamique
* Résolution des problèmes de validation des fragments de contenu
* Amélioration des capacités de modification des schémas de métadonnées sur les périphériques hybrides
* Résolution des problèmes de synchronisation au niveau du composant dans les live copies
* Les pages riches en contenu sont plus faciles à utiliser en mode Colonnes
* Amélioration de la conformité à la convention d’appellation des pages pour les pages comportant des titres longs
* Amélioration de l’expérience de personnalisation des campagnes dans l’IU tactile
* Correction de divers problèmes de superposition de projet

### Plateforme {#platform-5}

* Correctif pour Oak 1.6.2. NPR-16993
* En cas d’ouverture de l’omni-recherche à l’aide d’un filtre, le chemin d’accès n’est plus défini. NPR-17398 : correctif pour CQ-4204870
* Conditions requises pour la vérification des modifications des autorisations d’utilisateur dans AEM. NPR-17061
* Persistance des connexions à DM Cloud Services, ce qui entraîne des exceptions « Trop de fichiers ouverts ». CQ-4211407

### Ressources {#assets-12}

* Problèmes d’utilisation de la configuration des services de contenu dynamique à l’aide de différentes options. NPR-18200 : correctif pour CQ-4201557
* Fuite de ressources dans les flux binaires vers la banque de données S3. NPR-18041 : correctif pour CQ-4209506
* Une erreur se produit lorsqu’un fichier texte codé en ASCII/UTF-8 est chargé vers AEM Assets et la création des miniatures échoue. NPR-18006 : CFP pour CQ-4209345
* Le schéma de métadonnées par défaut entraîne l’échec de la validation des fragments de contenu. NPR-17769 : correctif pour CQ-4211111
* Résolveur de ressources non fermé dans com.day.cq.dam.s7dam.common.analytics.impl.SiteCatalystReportRunner. NPR-17598 : CFP pour CQ-4209018
* Demande de création de plusieurs agents de réplication pour la publication de ressources sur le Brand Portal. NPR-17189
* La tâche de révision des ressources sous le dossier en langue japonaise ne fonctionne pas. CQ-4204782
* Une exception NullPointerException se produit lorsqu’une ressource est déplacée depuis sa page de propriétés. CQ-4204251
* AEM ne parvient pas à suivre les références ultérieures à une ressource dans la page de propriétés s’il est lié plusieurs fois à un document InDesign. CQ-4204186
* Problèmes liés à l’ajout de nouveaux onglets dans le formulaire de schéma de métadonnées lorsqu’il est modifié dans Chrome sur des périphériques hybrides. CQ-4201810
* Lorsque des ressources en double sont chargées, l’option (supprimer/conserver) est appliquée à tous les fichiers, même s’ils ne sont pas sélectionnés dans la boîte de dialogue des doublons détectés. CQ-4201673
* Une exception NullPointerException se produit en cas de déplacement d’un dossier de ressources contenant plus de 150 références entrantes. CQ-4200981
* Dans le cas d’un dossier de ressources téléchargé, si un conflit survient lors de l’extraction du contenu du fichier ZIP, l’option par défaut s’affiche sous la forme Créer une version plutôt que Conserver les deux. CQ-97800
* Les utilisateurs disposant d’autorisations en lecture seule sur l’application ne peuvent pas prévisualiser le contenu à partir de la gestion de contenu d’AEM Mobile. NPR-17486 : CFP pour CQ-4209690
* Le bouton Créer un catalogue ne fonctionne pas en mode Colonnes dans la console Catalogue. CQ-4209952

### Sites {#sites-12}

* Problèmes affectant l’incorporation de composants image/vidéo via l’attribut data-sly-resource. NPR-18182 : CFP pour CQ-4212100
* Les composants localisés modifiés ne retrouvent pas leur forme d’origine lorsque l’héritage est réappliqué à une LiveCopy. NPR-18172 : correctif pour CQ-4211379
* Problèmes de navigation dans une page riche en contenu en mode Colonnes dans l’IU tactile. NPR-17799 : correctif pour CQ-4199611
* Résolveur de ressources non fermé dans `com.day.cq.wcm.core.impl.VersionManagerImpl`. NPR-17789 : CFP pour CQ-4211152
* Le nom de page n’est pas généré conformément à la convention pour les titres de pages longs. NPR-17633 : correctif pour CQ-4209056
* Problèmes de création de page dans l’IU tactile d’AEM 6.3 déployée sur Jboss EAP 6.4. NPR-17589 : correctif de CQ-4210137
* Le fournisseur de statut de workflow verrouille l’instance lorsque des groupes imbriqués sont présents. NPR-17556 : demande CFP pour CQ-4202056
* Résolveur de ressources non fermé dans les objets suivants :

   * `com.day.cq.wcm.undo.impl.BinaryValueManagerImpl` NPR-17497 : CFP pour CQ-4208673
   * `com.day.cq.commons.impl.ThumbnailProviderManagerImpl` NPR-17495 : CFP pour CQ-4208668
   * `com.day.cq.wcm.workflow.impl.WcmWorkflowServiceImpl` NPR-17494 : CFP pour CQ-4208669
   * `com.day.crx.delite.impl.AuthHttpContext` NPR-17493 : CFP pour GRANITE-17404

### Intégrations {#integrations-1}

* Résolution des erreurs du composant de recherche AEM qui peuvent se produire lorsque le client HTTP AEM Day 3.1 OSGI est configuré avec un proxy qui requiert une authentification Digest. NPR 18128 : correctif pour NPR-18029
* Problèmes de personnalisation des campagnes et des expériences associées via l’IU classique. NPR-18127 : correctif pour CQ-4211559
* Lors de la définition d’une marque/zone sur la page racine d’un site, un héritage annulé ne peut pas être restauré pour les zones des sous-pages. NPR-17753 : correctif pour CQ-4210139

### Workflow {#workflow-3}

* Dans un workflow non transitoire, les modifications apportées à l’historique des workflow et aux métadonnées avant une étape de workflow externe ne sont pas conservées. NPR-17848 : correctif pour GRANITE-17757
* Les valeurs des champs de la boîte de dialogue de workflow ne sont pas conservées dans le nœud de la tâche. NPR-17734 : correctif pour CQ-4210369
* Une erreur de date non analysable se produit lors de la modification de la tâche à partir de la boîte de réception. CQ-4208749

### Projets {#projects-3}

* Correction de divers problèmes de superposition de projet. NPR-17733
* La restructuration des capsules dans le module Projets le rend moins configurable. CQ-4209859
* Le chemin d’accès des ressources est modifié et défini sur les sites localisés respectifs lorsque de l’ajout de pages à la tâche de traduction. CQ-4206007

### Sécurité {#security-1}

* Problèmes de chargement d’images d’avatar pour les utilisateurs LDAP. NPR-16561
* Demande d’utilisation d’une version mise à niveau de org.apache.sling.servlets.post servlet (2.3.22) dans l’API Apache Sling pour prévenir une vulnérabilité XSS. NPR-18963

## Formulaires {#forms-12}

Les correctifs d’AEM Forms sont fournis par le biais du module complémentaire Forms et d’autres programmes d’installation de patchs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

Les principaux aspects pour AEM Forms sont les suivants :

* Correctifs dans les modules de texte de Correspondance Management, les aperçus de lettres et le lancement programmatique de l’IU de création de correspondance.
* Correctifs pour la validation PDF/A-1b, la conversion de fichiers d’image volumineux en PDF et de documents PDF en japonais dans PDF Generator.
* Correctifs d’utilisation pour Correspondence Management, Document Security et le workflow des formulaires.
* Ajout de la prise en charge de la capture des événements de contrôle pour le champ de signature Griffonnage.

### Package de modules complémentaires Forms {#forms-add-on-package-12}

**Correspondence Management**

* Lors de la modification d’un fragment Correspondence Management, l’éditeur de texte affiche les conditions en ligne à côté du texte traité. CQ-4211930
* Lors de la création d’une lettre Correspondence Management, la description de la lettre n’est pas enregistrée. NPR-18089
* Une marge supplémentaire au-dessus et au-dessous d’une liste à puces apparaît dans l’éditeur de texte, mais pas dans le rendu HTML et PDF. NPR-18126
* Lors d’un envoi HTML à l’aide de la méthode POST, échec du lancement de l’IU de création de correspondance. NPR-18202
* Lorsqu’un module de texte est enregistré et qu’une expression du module de texte ne contient aucune balise d’expression d’ouverture ou de fermeture, aucun message d’erreur ne s’affiche. Le module de texte affiche un message d’erreur et n’effectue pas le rendu dans la lettre. NPR-18535
* Lors de l’ajout de nouveau contenu ou lorsque la touche Entrée est enfoncée, une balise div est ajoutée au module de texte. NPR-18240

**Assembler**

* Lors de la validation d’un document PDF pour conformité à la norme PDF/A-1b, AEM Forms renvoie une erreur de validation : PDFA_CONTENT_003_DEVICE_DEPENDENT_COLOR_USED. Le document PDF ne renvoie pas l’erreur lorsqu’il est validé avec Adobe Preflight et des logiciels tiers. NPR-18011
* Lors de la validation de documents PDF pour la conformité à la norme PDF/A-1b, AEM Forms renvoie une erreur de validation : le champ de formulaire a plusieurs apparences. Les documents PDF sont conformes à la norme PDF/A-1b. NPR-18013

**Dossier de contrôle**

* Lors de la sélection de fichiers à traiter à l’aide d’un workflow, durant création d’un dossier de contrôle, la liste déroulante de sélection de modèle de workflow apparaît tronquée. NPR-17566

**Formulaires HTML5**

* AEM Forms ne capture pas les événements de contrôle pour le champ de signature Griffonnage. NPR-15286

**Forms Manager**

* L’interface utilisateur AEM Forms répertorie toutes les ressources dans le premier ordre le plus ancien. Les utilisateurs ne sont pas en mesure de réorganiser les ressources dans le premier ordre le plus récent. NPR-18450

**Référence API Java**

Ajout de JavaDocs pour la classe com.adobe.livecycle.content. NPR-18468

### Programme d’installation de Forms JEE {#forms-jee-installer-11}

**PDF Generator**

* Le service PDF Generator ne parvient pas à convertir des images de plus de 100 Mo en documents PDF. Réf. CQ-4208628
* Lors de l’utilisation du service PDF Generator avec une reconnaissance optique des caractères japonais, le fichier PDF généré est inversé. NPR-17602

**Process Management**

* La variable TaskContext n’est pas renseignée pour les workflow AEM Forms. NPR-18199

**Document Security**

* Microsoft Excel et Microsoft PowerPoint prennent beaucoup plus de temps pour ouvrir les documents protégés par AEM Document Security Extension for Microsoft Office. CQ-4212358
* Lors de la création d’une nouvelle stratégie, s’il existe une stratégie portant le même nom qu’une stratégie existante, une erreur interne se produit au niveau du serveur. NPR-18247

## Feature Packs inclus {#feature-packs-included-2}

* Conditions requises pour la vérification des modifications des autorisations d’utilisateur dans AEM. NPR-17061

Le pack de correctifs cumulés AEM 6.3.0.1 consiste en une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale d’AEM 6.3 en avril 2017. Les principaux aspects du pack de correctifs cumulés AEM sont les suivants :

* Améliorations dans les domaines suivants :

   * Composants Fragments de contenu, Sites, Éditeur de texte enrichi, Éditeur de règles et Éditeur de modèles
   * Révision sociale et connexion sociale à Facebook
   * Configuration et démarrage des tâches de traduction
   * Temps de réponse pour l’accès aux notifications dans les communautés de réseaux sociaux
   * Affichage des tâches de révision dans le référentiel DAM

* Fournit une option de validation dans le gestionnaire de modules pour la détection des conflits entre superposition et CFP

## Instructions de téléchargement relatives aux CFP via la Distribution de logiciels {#download-instructions-for-cfp-via-package-share}

Vous pouvez télécharger le package CFP directement à partir de la [distribution de logiciels](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) ou effectuer les étapes suivantes :

1. Ouvrez la [Distribution de logiciels](https://experience.adobe.com/downloads). Vous avez besoin d’un Adobe ID pour vous connecter à la Distribution de logiciels.
1. Appuyez sur **[!UICONTROL Adobe Experience Manager]** disponible dans le menu d’en-tête.
1. Appuyez sur le nom du package, sélectionnez **[!UICONTROL Accepter les termes du contrat de licence utilisateur final]**, puis appuyez sur **[!UICONTROL Télécharger]**.

## Instructions d’installation {#installation-instructions}

Cette section décrit les exigences et les étapes à suivre pour installer le CFP.

### Avant l’installation {#before-you-install}

>[!NOTE]
>
>Les Feature Packs facultatifs fournis par Adobe dépendent de la version et du pack de correctifs cumulés. Si vous avez installé un Feature Pack, contactez [l’équipe d’assistance clientèle d’AEM](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html) pour valider sa compatibilité avec le pack de correctifs cumulés pour AEM 6.3.

>[!NOTE]
>
>Il est recommandé de valider chaque nouveau package d’installation avant d’essayer d’installer le package. La pré-validation analyse et signale les erreurs détectées avant l’installation et avertit les utilisateurs de ces erreurs de manière proactive.
>
>Vous pouvez accéder à la documentation de l’option Valider à l’adresse[https://docs.adobe.com/content/docs/fr-FR/aem/6-3/administer/content/package-manager.html#Package%20Validator](https://docs.adobe.com/content/docs/fr-FR/aem/6-3/administer/content/package-manager.html#Package%20Validator)

* AEM 6.3.3.0 est une condition préalable à l’installation du CFP. Consultez la [documentation de mise à niveau](https://docs.adobe.com/docs/en/aem/6-3/deploy/upgrade.html) pour obtenir des instructions détaillées sur la mise à niveau d’une installation AEM vers AEM 6.3.
* Pour un déploiement en grappe utilisant RDBMK ou MongoDB, le package CFP peut être installé sur n’importe quelle instance de création utilisant le gestionnaire de modules.
* Avant d’installer le pack de correctifs cumulés, veillez à prendre un instantané ou à effectuer une sauvegarde de votre instance AEM.
* La désinstallation du CFP n’est pas prise en charge.

### Ajout de nouveaux enregistreurs {#adding-new-loggers}

Pour configurer la journalisation au niveau du débogage et récupérer un journal d’activité lors de l’installation de SP/CFP, procédez comme suit :

* Vous pouvez ajouter un nouvel enregistreur à l’emplacement par défaut [http://localhost:4502/system/console/slinglog](http://localhost:4502/system/console/slinglog) avec les propriétés suivantes :

   * Niveau de consignation : débogage
   * Additif : faux
   * Fichier journal : logs/activity.log
   * Enregistreur : org.apache.jackrabbit.vault.packaging.impl.ActivityLog

Le fichier activité.log sera créé dans le dossier crx -quickstart /logs.

### Installer le pack de correctifs cumulés par le biais de la distribution de logiciels {#install-the-cumulative-fix-pack-via-package-share}

Procédez comme suit pour installer le pack de correctifs cumulés sur une instance AEM 6.3 existante :

1. Cliquez sur le lien [Distribution de logiciels](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/cumulativefixpack/aem-6.4.8-cfp-2.0.zip) pour télécharger le package.

1. Ouvrez [Package Manager](http://localhost:4502/crx/packmgr/index.jsp) et cliquez sur **[!UICONTROL Télécharger le package]** pour télécharger le package.

1. Sélectionnez le nom du package et cliquez sur **[!UICONTROL Installer]**.

### Installation automatique {#automatic-installation}

Le CFP peut être automatiquement installé dans une instance en cours d’exécution de la manière suivante :

* Placez le package dans `../crx-quickstart/install` pendant l’exécution du serveur. Le package est automatiquement installé.
* Utilisez l’[API HTTP du gestionnaire de modules](https://helpx.adobe.com/fr/experience-manager/6-3/sites/administering/using/package-manager.html) (veillez à utiliser `cmd=install&recursive=true`) afin d’installer le package imbriqué.

### Validation de l’installation {#validate-installation}

1. La page Informations sur le produit (`/system/console/  productinfo`) doit maintenant afficher la chaîne de version mise à jour « Adobe Experience Manager, Version 6.3.3.8. » sous Produits installés.
1. Tous les lots OSGI sont ACTIFS ou FRAGMENT dans la console OSGI (utiliser la console web : `/system/console/bundles`).

>[!NOTE]
>
>Une fois l’installation du package réussie, un message d’information s’affiche sur les journaux d’erreur pour indiquer que le package de contenu a bien été installé, par exemple « **AEM 6.3.3-Cumulative-Fix-Pack-7** installé avec succès ».

>[!NOTE]
>
>Depuis AEM 6.3.3.1, le niveau de journal dans Jackrabbit FileVault est passé d’INFO à DEBUG pour la plupart des messages. Pour obtenir les journaux d’installation d’un package de contenu installé sur AEM 6.3.3.1 ou une version ultérieure, activez le niveau de journal DEBUG pour org.apache.jackrabbit.vault.packagings.impl.

### Installation d’AEM Forms {#install-aem-forms}

>[!NOTE]
>
>Ignorez cette section si vous n’utilisez pas AEM Forms.

#### Installation du module complémentaire AEM Forms {#install-forms}

1. Vérifiez que vous avez installé le package CFP AEM 6.3.3.x.
1. Téléchargez le module complémentaire Forms correspondant répertorié dans les [versions AEM Forms](aem-forms-releases.md) pour votre système d’exploitation.
1. Installez le module complémentaire Forms comme décrit dans la section [Installation des modules complémentaires AEM Forms](https://helpx.adobe.com/fr/experience-manager/6-3/forms/using/installing-configuring-aem-forms-osgi.html).

#### Installation du package de lots AEM Forms JEE {#install-aem-forms-jee-bundles-package}

Les correctifs dans AEM Forms JEE sont fournis dans un programme d’installation distinct. Pour plus d’informations sur l’installation d’un CFP pour AEM Forms sur JEE, reportez-vous à [Installation d’un CFP pour AEM Forms JEE](install-cfp-aem-forms-jee.md).

#### Programme d’installation du Concepteur Forms {#designer-installer}

1. Pour installer la mise à jour, exécutez le fichier Designer 6.2.0_&lt;Langue>_Cumulative_QF.msp.
1. Sur l’écran de bienvenue, cliquez sur **Mettre à jour**. L’installation démarre.
1. Une fois l’installation terminée, cliquez sur **Terminer**.

## Paramètres de configuration pour AEM Forms JEE (JBoss EAP) {#configuration-settings-for-aem-forms-jee-jboss-eap}

>[!NOTE]
>
>Si vous installez la version 6.3.3.0 ou ultérieure, procédez comme suit pour configurer les paramètres du serveur d’applications JBoss. Si vous installez la version 6.3.3.0 sur un serveur AEM Forms qui s’exécute sur des serveurs d’applications Oracle WebLogic ou IBM WebSpehere, aucune configuration supplémentaire n’est nécessaire. Pour plus d’informations, reportez-vous aux [Notes de mise à jour d’AEM 6.3.3.0](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html).

## Mises à jour de configuration pour l’intégration de Search&amp;Promote {#configuration-updates-for-search-promote-integration}

Avec le pack de correctifs cumulés AEM 6.3.0.2 et les versions ultérieures, la configuration OSGi utilisée pour l’intégration de Search&amp;Promote est la **configuration du proxy des composants HTTP Apache**. La configuration du proxy du client HTTP 3.1 Day Commons n’est plus utilisée.

## Problèmes connus {#known-issues}

* Les erreurs et avertissements suivants peuvent survenir lors de l’installation du CFP AEM 6.3.3.x et peuvent être ignorés en toute sécurité :

   * *WARN* [OsgiInstallerImpl] org.apache.jackrabbit.vault.packl.impl.InstallHookProcessorImpl Hook /META-INF/vault/hooks/cloudservices-wfchangeinstallhook-0.0.2-jar-with-dependencies.jar a généré une exception d’environnement d’exécution.
   * *ERROR* [OsgiInstallerImpl] com.adobe.cq.social.cq-social-jcr-provider [com.adobe.cq.social.provider.jcr.impl.SpiSocialJcrResourceProviderImpl(2174)] Délai d’attente de la fin de la désinscription. CQ-4209974.
   * Service org.apache.sling.engine.impl.SlingRequestProcessorImpl ServletResolver manquant, impossible de traiter les demandes, envoi de l’état 503
   * com.day.cq.wcm.mobile.core.MobileUtil isMobileResource : impossible de vérifier la ressource [/bin/receive], gestionnaire de pages indisponible
   * org.apache.sling.servlets.resolver.internal.SlingServletResolver : l’appel du gestionnaire d’erreurs a généré une erreur.
   * org.apache.sling.servlets.resolver.internal.SlingServletResolver Erreur originale nulle
   * org.apache.sling.engine.impl.DefaultErrorHandler Échec du gestionnaire d’erreurs : java.io.IOException
   * *ERROR* [FelixDispatchQueue] com.day.cq.dam.cq-dam-core FrameworkEvent ERROR (org.osgi.framework.ServiceException : la fabrique de services a renvoyé une valeur « null ». (Composant : com.day.cq.dam.handler.standard.ps.PostScriptHandler))

**Brand Portal**

* À partir de la version 6.3.1.2, le bouton Publier sur le Brand Portal pour les collectes dynamiques a été supprimé.

**Interface utilisateur**

>[!NOTE]
>
>Au cas où vous seriez concerné par l’un de ces deux problèmes, contactez le [service d’assistance clientèle d’AEM](https://helpx.adobe.com/marketing-cloud/contact-support.html).

* Une utilisation intensive du processeur est observée en raison du nombre élevé de requêtes dans la fonctionnalité de recherche d’administrateurs. NPR-24229
* PathField n’est pas sélectionné dans pathBrowser lors de la réouverture du composant. NPR-24177

## Paramètres de configuration requis pour NPR-27692 {#configuration-settings-required-for-npr}

>[!NOTE]
>
>Ce paramètre de configuration s’applique à CFP 6.3.3.2 et versions ultérieures. Il vous demande de mettre à jour les propriétés de délégation de démarrage dans le fichier de propriétés `sling`.

Pour mettre à jour manuellement les modifications apportées à adobe- livecycle - cq -author.ear/ cq .war, procédez comme suit :

* Arrêtez le serveur AEM.
* Accédez à adobe-livecycle-cq-author.ear/cq.war
* Ouvrez adobe-livecycle-cq-author.ear/cq.war/WEB-INF/web.xml pour le modifier :

   * mettez à jour la valeur **sling.bootdelegation.ibm** param-name avec :

      * com.ibm.xml.*,com.ibm.crypto.pkcs11impl.provider,com.ibm.pkcs11,com.ibm.pkcs11.nat
   * Après la modification ci-dessus, init-param doit apparaître comme suit :

      * &lt;init-param>\
         &lt;param-name>sling.bootdelegation.ibm&lt;/param-name> &lt;param-value>com.ibm.xml.*,com.ibm.crypto.pkcs11impl.provider,com.ibm.pkcs11,com.ibm.pkcs11.nat&lt;/param-value>\
         &lt;/init-param>


* Désinstallez le fichier EAR précédent du serveur d’applications WebSphere et installez le fichier EAR mis à jour en suivant les étapes décrites à la section 10.2 de[https://helpx.adobe.com/fr/pdf/aem-forms/6-3/install-single-server-websphere.pdf](https://helpx.adobe.com/fr/pdf/aem-forms/6-3/install-single-server-websphere.pdf)
* Enregistrez le fichier et redémarrez le serveur. [https://helpx.adobe.com/fr/pdf/aem-forms/6-3/install-single-server-websphere.pdf](https://helpx.adobe.com/pdf/aem-forms/6-3/install-single-server-websphere.pdf)

## Paramètres de configuration requis pour NPR-23208 {#configuration-settings-required-for-npr-1}

>[!NOTE]
>
>Ce paramètre de configuration s’applique aux versions 6.3.2.2 et ultérieures. Il vous demande de mettre à jour manuellement les stratégies de listes de contrôle d’accès (ACL) via CRX-DE, car les listes de contrôle d’accès ne sont pas mises à jour via l’installation du CFP en raison de la variable « merge_preserve » acHandling.

**Documentation pour l’ajout manuel de stratégies de liste de contrôle d’accès**

Pour mettre à jour les stratégies ACL, ajoutez les contrôles d’accès ci-dessous via CRX-DE :

`1)` Chemin d’accès &quot;/content&quot;\
`a)` Principal : reference-adjustment-service\
Type : Allow\
Privilèges : jcr:read , jcr:modifyProperties\
Restrictions : rep:glob=&quot;/*/jcr:content&quot;\
`b)` Principal : reference-adjustment-service\
Type : Allow\
Privilèges : jcr:read , jcr:modifyProperties\
Restrictions : rep:glob=&quot;/*/jcr:content/*&quot;

`2)` Chemin d’accès &quot;/content/usergenerated&quot;\
`a)` Principal : reference-adjustment-service\
Type : Allow\
Privilèges : jcr:write

`3)` Chemin d’accès &quot;/etc.&quot;\
`a)` Principal : reference-adjustment-service\
Type : Allow\
Privilèges : jcr:read , jcr:modifyProperties\
Restrictions : rep:glob=&quot;/*/jcr:content&quot;\
`b)` Principal : reference-adjustment-service\
Type : Allow\
Privilèges : jcr:read , jcr:modifyProperties\
Restrictions : rep:glob=&quot;/*/jcr:content/*&quot;

## Paramètres de configuration requis pour NPR-19450 {#configuration-settings-required-for-npr-2}

>[!NOTE]
>
>Ce paramètre de configuration s’applique à CFP 6.3.1.1 et versions ultérieures.

**Configurez la propriété CQ.PAGE_PROPERTIES_MAX_RECURSION_LEVEL.**

La propriété contrôle la profondeur maximale de la sous-arborescence du nœud sous le nœud de page ` /  jcr   :content`, jusqu’à ce que les nœuds présents dans le référentiel soient utilisés pour obtenir les propriétés de la page. Tout nœud situé sous la profondeur spécifiée dans cette propriété est ignoré.

La valeur par défaut est 1. Cette valeur peut être    remplacée en appliquant le fichier constants.js (`/libs/cq/ui/widgets/source/constants.js`) sans commenter la propriété CQ.PAGE_PROPERTIES_MAX_RECURSION_LEVEL et lui affecter la valeur requise (profondeur maximale sous la propriété / jcr  :content de la page jusqu’à laquelle les données des propriétés de la page sont stockées).

**Si l’utilisateur doit créer plusieurs variantes de pages afin que le nombre de nœuds sous le nœud de la page /  jcr   :content soit supérieur à 1 000, procédez comme suit pour modifier la configuration :**

* Configuration de la propriété JSON Max results d’Apache Sling
* Get Servlet à l’aide de `/system/console/  configMgr`
* Définissez sa valeur sur un nombre supérieur à 1 000 (valeur par défaut actuelle) de sorte que ce nombre soit supérieur au nombre total de nœuds dans le sous-arbre / jcr  :content jusqu’à la profondeur configurée comme ci-dessus.

Cela permet au servlet Sling GET de renvoyer tous les nœuds requis.

## Uber Jar {#uber-jar}

Uber Jar pour 6.3.3.8 est disponible dans le [Référentiel Adobe Public Maven](https://repo.adobe.com/nexus/content/groups/public/com/adobe/aem/uber-jar/6.3.3.8/).

Pour utiliser Uber Jar dans un projet Maven, reportez-vous à l’article [Comment utiliser Uber Jar](https://helpx.adobe.com/fr/experience-manager/6-3/sites/developing/using/ht-projects-maven.html) et incluez la dépendance suivante dans votre projet POM :

```TXT
<dependency>
      <groupId>com.adobe.aem</groupId>
      <artifactId>uber-jar</artifactId>
      <version>6.3.3.8</version>
      <classifier>apis</classifier>
      <scope>provided</scope>
</dependency>
```

## Fonctionnalités supprimées / obsolètes {#deprecated}

Cette section répertorie les fonctionnalités qui ont été supprimées ou désignées comme obsolètes dans AEM 6.3.

| Zone | Fonctionnalité | Remplacement | Version |
|----|-----|-----|-----|
| Intégration des Ressources et d’Adobe Creative Cloud | [Le partage de dossiers AEM vers Creative Cloud](https://helpx.adobe.com/fr/experience-manager/6-3/sites/administering/using/creative-cloud.html) a été introduit dans AEM 6.2 afin de permettre aux créatifs d’accéder aux ressources depuis AEM. Adobe Asset Link, nouvelle fonctionnalité proposée dans l’application Creative Cloud, offre une expérience utilisateur améliorée et un accès plus puissant aux ressources d’AEM directement à partir de Photoshop, InDesign et Illustrator.<br /> Adobe n’apportera pas d’améliorations supplémentaires à la fonctionnalité de partage de dossiers. Bien que cette fonctionnalité soit incluse dans AEM, il est vivement conseillé aux clients d’utiliser la solution de remplacement. | Adobe Asset Link ou l’application de bureau. Pour plus d’informations, reportez-vous à l’article [Intégration d’AEM Creative Cloud](https://helpx.adobe.com/fr/experience-manager/6-3/assets/using/aem-cc-integration-best-practices.html). | AEM 6.3.3.x |

## Lots OSGi et packages de contenu inclus {#osgi-bundles-and-content-packages-included-1}

Les documents texte suivants répertorient les lots OSGi et les packages de contenu inclus dans le CFP :

* [Liste des lots OSGi inclus dans AEM 6.3.3.8](assets/do-not-localize/list_of_osgi_bundlesincludedin6338.txt)

* [Liste des packages de contenu inclus dans AEM 6.3.3.8](assets/do-not-localize/list_of_content_packageincludedin6338.txt)

>[!MORELIKETHIS]
>
>* [Versions et mises à jour d’AEM](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/aem-releases-updates.html?lang=fr)
>* [Page des correctifs AEM 6.3](https://helpx.adobe.com/fr/experience-manager/kb/aem63-available-hotfixes.html)
>* [Notes de mise à jour d’AEM 6.3](https://docs.adobe.com/docs/en/aem/6-3/release-notes.html)
>* [Page de produits AEM ](http://www.adobe.com/fr/solutions/web-experience-management.html)
>* [Documentation d’AEM 6.3](https://docs.adobe.com/content/docs/en/aem/6-3.html)
>* Abonnement aux [mises à jour de produits prioritaires d’Adobe](https://www.adobe.com/subscription/priority-product-update.html)

