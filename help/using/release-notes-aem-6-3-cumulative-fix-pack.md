---
title: Pack de correctifs cumulés AEM 6.3
description: Notes de mise à jour du pack de correctifs cumulatif AEM 6.3.
exl-id: 04969587-a904-44cb-83e0-51707ac6a87f
source-git-commit: 53803f61394144ed81367a5c050814223fc6d565
workflow-type: ht
source-wordcount: '17347'
ht-degree: 100%

---

# Notes de mise à jour du pack de correctifs cumulés AEM 6.3 {#release-notes-aem-cumulative-fix-pack}

## Informations sur la version {#release-information}

| **Produit** | Adobe Experience Manager |
|---|---|
| **Version** | 6.3 |
| **Version** | Pack de correctifs cumulés 6.3.3.8 via la [Distribution de logiciels](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq630/cumulativefixpack/aem-6.3.3-cfp-8.0.zip) |
| **Prérequis** | [Pack de services 3 d’AEM 6.3 (6.3.3.0)](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions) |
| **Disponibilité générale** | 5 mars 2020 |

### Pack de correctifs cumulés {#cumulative-fix-pack}

Adobe a introduit un modèle de diffusion unique pour la publication des correctifs. Au lieu de publier des correctifs ad hoc pour chaque problème, Adobe publie désormais un pack de correctifs cumulés (CFP) tous les mois (sous réserve de contrôles de qualité satisfaisants). Un CFP est un package de contenu agrégé pour plusieurs correctifs. Les CFP comprennent principalement des correctifs de bugs, mais peuvent également inclure des Feature Packs. Ils présentent les avantages suivants par rapport aux versions individuelles des correctifs :

* Cumulatif par nature (par exemple, un CFP contient des correctifs apportés par le biais de CFP précédents)
* Amélioration de l’assurance qualité
* Installation simplifiée (l’utilisateur installe un CFP en un seul package sans dépendances, hormis le dernier Service Pack)

Pour plus d’informations sur le CFP et sur d’autres types de versions, consultez les [définitions du véhicule de version de maintenance.](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions)

## À propos de cette version {#about-the-release}

Le pack de correctifs cumulatif 6.3.3.8 apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du pack de services 3 (6.3.3.0) pour AEM 6.3 de septembre 2018.

Le pack de correctifs cumulatif 6.3.3.8 pour AEM nécessite la présence du pack de services 3. Vous devez donc installer le pack de correctifs cumulatif 6.3.3.x pour AEM après avoir installé le pack de services 3 pour AEM 6.3. Pour obtenir des instructions sur l’installation, reportez-vous aux notes de mise à jour du [pack de services 3 pour AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.20.

>[!CAUTION]
>
>Le fait d’installer le pack de correctifs cumulatif (CFP) sans avoir validé la compatibilité entre les packs de fonctionnalités installés peut entraîner une défaillance du système ou la perte de configurations personnalisées, ce qui nécessite une restauration à partir de la sauvegarde pour résoudre le problème.

>[!NOTE]
>
>Pour les instances AEM dont la version est inférieure à 6.3.3.0, Adobe recommande de déployer le SP/CFP via le dossier d’installation pour la clientèle dont l’instance AEM dispose d’un grand nombre d’utilisateurs et d’utilisatrices.

>[!NOTE]
>
>MongoDB Enterprise 3.6 est pris en charge à partir de la version 6.3.3.1 d’AEM.

## Liste des problèmes {#changes}

Cette section répertorie tous les problèmes et correctifs inclus dans le CFP actuel.

En outre, ce CFP inclut des correctifs fournis dans les [packs de correctifs cumulés](#previous) précédents.

### Ressources {#assets}

* La page Ajouter à la collection n’affiche pas toutes les collections disponibles dans la vue Carte lors de l’ajout de ressources à la collection (NPR-32537).

### Sites {#sites}

* Lorsque vous sélectionnez un parsys et un composant qu’il contient, puis que vous utilisez le raccourci clavier pour supprimer les éléments sélectionnés, l’action supprime à la fois le composant et son parsys parent (NPR-32071).
* Lorsque les propriétés d’une page sont enregistrées, un nœud incorrect est créé (NPR-31774).

### Intégrations {#integrations}

* ReportSuitesServlet est vulnérable aux attaques SSRF (NPR-32162).

### Campaign - Ciblage {#campaign-targeting}

* Le contenu d’un composant modifié puis activé dans l’instance de création n’est pas visible dans l’instance de publication tant que le composant n’a pas été redémarré **com.day.cq.personalization.impl.TargetedContentManagerImpl** (NPR-32489 et NPR-32232).
* Les performances de ContextHub font l’objet d’un crash lors de la publication (NPR-31170).

### Brand Portal {#brand-portal}

* Adobe Developer n’est pas intégré à Adobe Experience Manager 6.3 pour Brand Portal (NPR-32056).

### Formulaires {#forms}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

#### Package de modules complémentaires Forms {#forms-add-on-package}

>[!NOTE]
>
>Les packages de modules complémentaires AEM Forms permettent d’harmoniser les fonctionnalités de formulaires avec les packs de services AEM et les packs de correctifs cumulatifs AEM. Il est donc impératif d’installer le package de modules complémentaires AEM Forms après avoir installé un pack de services AEM, un pack de correctifs cumulatifs AEM ou un pack de fonctionnalités AEM.

* Designer : si l’option de balisage est activée, la bordure du sous-formulaire disparaît dans la sortie PDF générée (NPR-32324 et NPR-32545).
* Designer : s’il existe des cellules fusionnées dans un tableau, le test d’accessibilité échoue pour un fichier PDF de sortie converti par le service de sortie à l’aide d’un formulaire XDP (NPR-32068).
* Sécurité des documents : un fichier PDF protégé ne peut pas s’ouvrir hors connexion avec l’option `DisableGlobalOfflineSynchronizationData` définie sur `True` (NPR-32080).

**Problèmes résolus dans la version 6.3.0-0047**

* (JEE uniquement) Vulnérabilités de sécurité critiques (CVE-2021-44228 et CVE-2021-45046) signalées pour Apache `Log4j2`.

## Correctifs et Feature Packs inclus dans les packs de correctifs cumulés précédents {#previous}

### Pack de correctifs cumulés 6.3.3.7 {#cumulative-fix-pack-1}

Le pack de correctifs cumulatif 6.3.3.7 pour AEM apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du pack de services 3 (6.3.3.0) pour AEM 6.3 de septembre 2018.

Le pack de correctifs cumulatif 6.3.3.7 pour AEM nécessite la présence du pack de services 3 pour AEM 6.3. Vous devez donc installer le pack de correctifs cumulatif 6.3.3.x pour AEM après avoir installé le pack de services 3 pour AEM 6.3. Pour obtenir des instructions sur l’installation, reportez-vous aux notes de mise à jour de la section [Pack de services 3 pour AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions).

### Ressources {#assets-1}

* Les ressources sélectionnées (dans la vue Colonnes dans l’interface d’utilisation tactile) avant de sélectionner l’option de filtre dans la liste déroulante Contenu uniquement, et lorsque l’option de déplacement est ensuite sélectionnée, sont également déplacées (NPR-30693).
* La variable `${extension}` n’est pas rendue dans l’instance de création lors du traitement du workflow (NPR-31694).
* La valeur d’expiration (délai d’activation du cache client) configurée pour le mode hybride de Dynamic Media n’est pas répliquée dans l’environnement de diffusion de Dynamic Media (NPR-31114).
* Les ressources sont répliquées dans l’instance de publication à partir de l’instance de création qui s’exécute sur le déploiement de Dynamic Media Scene7, même après l’utilisation de filtres par défaut (NPR-30856).

### Sites {#sites-1}

* Le chargement des propriétés de page d’une page principale échoue et une exception NullPointerException est renvoyée. Le problème est résolu lors de l’ajout de la propriété `cq:blueprin`t (NPR-30901).
* Les configurations de déploiement ne sont pas correctement récupérées à partir de blueprintConfig sur le nœud racine. La désactivation est déclenchée pour les plans directeurs et les live copies. Seul le plan directeur fait l’objet d’un déclenchement de désactivation (NPR-30866).
* Lorsqu’un utilisateur ou une utilisatrice déploie une page, la boîte de dialogue de configuration du déploiement affiche les chemins de Live Copy en double (NPR-30438).
* L’éditeur de texte enrichi (RTE) dédié à la génération de modèles automatique applique inopinément la taille de police en ligne aux éléments (NPR-31283, NPR-30922).
* Impossible de synchroniser la campagne dans Adobe Campaign contenant le composant d’importateur de conception prêt à l’emploi (NPR-30890).
* L’éditeur de texte enrichi (RTE) ne permet pas d’insérer un tableau incorporé en tant qu’élément de liste (NPR-30878).
* Un utilisateur ou une utilisatrice place son curseur dans les champs du rail de gauche et utilise un raccourci clavier pour coller du contenu. Cette action colle le contenu du Presse-papiers de l’éditeur de la page au lieu du contenu copié à partir des champs du rail de gauche (NPR-31173).
* Lorsqu’un utilisateur ou une utilisatrice modifie un fragment de contenu, la variante déjà supprimée du fragment de contenu est restaurée (NPR-31272).
* Le site AEM ne crée pas de copie de langue (NPR-30690).
* Les actions de l’éditeur de page n’ont pas les commandes pour déployer les Live Copies (NPR-30613).

### Communities {#communities}

* Les titres des activités et des notifications sont incohérents (NPR-30940).
* Les rapports Analytics ne sont pas renseignés dans l’environnement de création AEM. Une page vierge s’affiche à la place (NPR-30905).
* La pagination ne fonctionne pas correctement dans les blogs Communities (NPR-30827).

### Foundation {#foundation}

* Les mises à jour de la configuration de la taille de la mémoire tampon pour le service HTTP basé sur Jetty ne sont pas enregistrées (NPR-30925).

### Formulaires {#forms-1}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-1}

>[!NOTE]
>
>Les packages de modules complémentaires AEM Forms permettent d’harmoniser les fonctionnalités de formulaires avec les packs de services AEM et les packs de correctifs cumulatifs AEM. Il est donc impératif d’installer le package de modules complémentaires AEM Forms après avoir installé un pack de services AEM, un pack de correctifs cumulatifs AEM ou un pack de fonctionnalités AEM.

#### Formulaires adaptatifs {#adaptive-forms}

* Les valeurs flottantes calculées à l’aide d’un script ne s’affichent pas correctement dans un formulaire qui fait partie d’une visionneuse de formulaires (NPR-30802).

#### Formulaires HTML5 {#html-forms}

* La génération de l’aperçu HTML5 d’un formulaire XDP affiche un scintillement lors de l’ajout d’instances d’un sous-formulaire (NPR-30908).

### Programme d’installation de Forms JEE {#forms-jee-installer}

#### Services Acrobat {#document-services}

* OutputService affiche une réponse incorrecte après l’application d’un correctif pour résoudre les problèmes de conversion de HTML en PDF (NPR-31504).

#### Service PDFG {#pdfg-service}

* Le nombre maximal de réutilisations avec la console JMX ne s’affiche pas pour le service HTML2PDF (NPR-30305).

#### Foundation JEE {#foundation-jee}

* Le nombre maximal de réutilisations avec la console JMX ne s’affiche pas pour le service HTML2PDF (NPR-30136).

### Pack de correctifs cumulés 6.3.3.6 {#cumulative-fix-pack-2}

Le pack de correctifs cumulatif 6.3.3.6 pour AEM apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du pack de services 3 (6.3.3.0) pour AEM 6.3 de septembre 2018.

Le pack de correctifs cumulatif 6.3.3.6 pour AEM nécessite la présence du pack de services 3 pour AEM 6.3. Vous devez donc installer le pack de correctifs cumulatif 6.3.3.x pour AEM après avoir installé le pack de services 3 pour AEM 6.3. Pour obtenir des instructions sur l’installation, reportez-vous aux notes de mise à jour de la section [Pack de services 3 pour AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions).

### Ressources {#assets-2}

* L’agrégation vidéo par Dynamic Video renvoie uniquement les 100 premiers éléments dans l’ensemble de résultats. NPR-30441 : correctif pour CQ-4213561
* Problème de connectivité du balisage intelligent d’Adobe via DataPower. NPR-30026 : correctif pour CQ-4269457
* Il est impossible d’ouvrir via l’interface d’Assets un dossier d’archive décompressée dont le nom contient un symbole de pourcentage (%). NPR-29989 : correctif pour CQ-4270467
* Le traitement des sous-ressources de fichiers PDF volumineux entraîne une exception OutOfMemoryError (OOME). NPR-29851 : correctif pour CQ-4269574

### Sites {#sites-2}

* Erreur ContextHub durant l’intégration d’AEM et de Campaign. NPR-30624 : correctif pour CQ-4250790
* Les propriétés des métadonnées « onTime » ou « offTime » enregistrées sur les ressources ne sont pas rappelées si le serveur AEM est redémarré. NPR-30412 : correctif pour CQ-4272784
* Lors de la génération d’un export au format CSV, l’ajout de colonnes personnalisées pour la vue Liste altère le bon fonctionnement du rapport. NPR-30208 : correctif pour CQ-4273344
* Les rapports prêts à l’emploi dans /etc/reports/ ne fonctionnent pas correctement et le graphique de données historiques ne s’affiche pas. NPR-30016 : correctif pour CQ-4220180
* La valeur du paramètre de requête resourceType est copiée dans la valeur d’un attribut de balise HTML encapsulé entre guillemets. NPR-29832 : correctif pour CQ-4255365

### Communities {#communities-1}

* Problème de duplication de contenu avec la console de modération d’AEM Communities. NPR-30667 : correctif pour CQ-4276829

### Traduction {#translation}

* Problème de traduction : seuls quelques composants sont traduits à l’aide de la traduction automatique. NPR-30079 : correctif pour CQ-4273764
* Lors de l’utilisation du framework de traduction, l’ajout de pages à plusieurs tâches de traduction déclenche une erreur. NPR-29746 : correctif pour CQ-4270953

### Formulaires {#forms-2}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-2}

>[!NOTE]
>
>Les packages de modules complémentaires AEM Forms permettent d’harmoniser les fonctionnalités de formulaires avec les packs de services AEM et les packs de correctifs cumulatifs AEM. Il est donc impératif d’installer le package de modules complémentaires AEM Forms après avoir installé un pack de services AEM, un pack de correctifs cumulatifs AEM ou un pack de fonctionnalités AEM.

#### Formulaires HTML5 {#html-forms-1}

* Lors de l’utilisation de l’option Accès aux ordinateurs de bureau non visuels en mode Navigation pour lire un formulaire HTML5, le navigateur Chrome affiche « graphic » avant chaque graphique vectoriel évolutif (SVG) dans la conception du formulaire. NPR-30451 : correctif pour CQ-4274732

#### Forms - Intégration du serveur principal {#forms-backend-integration}

* Impossible d’afficher le service/la source de données pour la connexion à la base de données lors de la création du modèle de données de formulaire (FDM). NPR-30108 : correctif pour CQ-4273359

### Programme d’installation de Forms JEE {#forms-jee-installer-1}

#### Forms - Services Acrobat {#forms-document-services}

* Lorsqu’un test de charge est effectué sur le service HTML vers PDF, il échoue et produit une erreur, et les paramètres de type de fichier sont supprimés du serveur AEM Forms. NPR-30111, NPR-30086 : correctif pour CQ-4271495

### Pack de correctifs cumulés 6.3.3.5 {#cumulative-fix-pack-3}

Le pack de correctifs cumulés 6.3.3.5 pour AEM apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du pack de services 3 (6.3.3.0) pour AEM 6.3 de septembre 2018.

Le pack de correctifs cumulatif 6.3.3.5 pour AEM nécessite la présence du pack de services 3 d’AEM 6.3. Vous devez donc installer le pack de correctifs cumulatif 6.3.3.x pour AEM après avoir installé le pack de services 3 pour AEM 6.3. Pour obtenir des instructions sur l’installation, reportez-vous aux notes de mise à jour du [pack de services 3 pour AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.17.

### Ressources {#assets-3}

* Mise à jour de l’interface de gestion des ressources numériques DMGateway pour la prise en charge multipartie S3. NPR-29740 : correctif pour Q-4226303
* Impossible de supprimer un rendu d’image dans une ressource vidéo à partir de la page Détails de la ressource. NPR-29417 : correctif pour CQ-4268675
* Le ou la propriétaire ne peut pas créer de dossier privé dans un dossier privé. NPR-29397 : correctif pour CQ-4229830
* Le chargement d’un fichier d’illustration Adobe Illustrator de plus de 2 Go génère une erreur d’espace de tas Java™. NPR-29265 : correctif pour CQ-4226217
* Les ressources deviennent inutilisables lorsque le service de type MIME DAM CQ applique le texte pour m3u8. NPR-29259 : correctif pour CQ-4264052
* L’option Créer ne fonctionne pas lors de la tentative de création de collections dans Edge. NPR-29248 : correctif pour CQ-4265699 et CQ-4265438
* Le partage de liens de ressources affiche des cartes grises vierges à la place de certaines ressources du dossier. NPR-29831 : correctif pour CQ-4270187
* Les nouvelles balises ajoutées aux ressources ne sont pas enregistrées et disparaissent des propriétés. Correctif pour CQ-4271931, CQ-4270476

### Sites {#sites-3}

* CoralUI, lorsqu’il est utilisé avec des champs multiples, stocke le fileReferenceParameter au niveau du composant et non au niveau du champ multiple. NPR-29535 : correctif pour CQ-4266129
* Problème lors de la tentative de comparaison entre la version actuelle de la page avec celle la plus récente sur AEM 6.3.3.3. NPR-29532 : correctif pour CQ-4269639
* Le champ de chemin d’accès s’ouvre au chemin racine, quel que soit le chemin d’accès spécifié pour la recherche. NPR-29398 : correctif pour CQ-4268897
* (Fragments d’expérience) FacebookApplication#setUpApp utilise une API obsolète qui ne fonctionne plus. NPR-29213 : correctif pour CQ-4266630
* Une alerte d’erreur est générée lors de l’ajout de composants à la page de gestion de contenu web lorsque la minimisation est activée sur l’instance. NPR-29476 : correctif pour CQ-4266197
* Les propriétés vides et les propriétés multiples ne sont pas propagées pas à partir du plan directeur lors du déploiement. La réinitialisation de la Live Copy avec le plan directeur ne fonctionne pas pour les composants. NPR-29252 : correctif pour CQ-4264928, CQ-4264926, CQ-4267722
* La minimisation de l’éditeur de texte enrichi à partir du mode plein écran en mode d’édition de la source entraîne une perte de contenu. NPR-28838 : correctif pour CQ-4260584

### Communities {#communities-2}

* Les visiteurs et les membres, sans privilèges de modérateur, peuvent voir les publications non approuvées et en attente en collant l’URL. NPR-29726 : correctif pour CQ-4271124
* Un temps de réponse élevé allant jusqu’à 40-50 secondes est observé lors de la connexion de l’utilisateur à la Communauté. NPR-29679 : correctif pour CQ-4269444
* Impossible de réinitialiser le mot de passe lorsque vous êtes connecté avec un nom d’utilisateur et un email différents, car la clé semble être générée avec un nom d’utilisateur et une adresse email permutés. NPR-29281 : correctif pour CQ-4268694

### Fragments d’expérience {#experience-fragments}

* Vous ne pouvez pas exporter les fragments d’expérience vers la cible lorsqu’une image intelligente est utilisée. Correctif pour CQ-4269606

### Réplication {#replication}

* Le composant Agent de réplication est exposé à une vulnérabilité qui divulgue des informations sensibles à des utilisateurs et des utilisatrices non autorisés. NPR-29613 : correctif pour Granite-25070
* Les données fournies par les utilisateurs et les utilisatrices ne comprennent pas de séquence d’échappement dans la sortie du composant `cq/replication/components/agent`, ce qui entraîne une vulnérabilité de type Cross-site scripting (XSS) stockée. NPR-29452 : correctif pour CQ-4266263

### Formulaires {#forms-3}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-3}

* Aucun nouveau correctif pour le package de modules complémentaires AEM Forms.

### Programme d’installation de Forms JEE {#forms-jee-installer-2}

* Aucun nouveau correctif pour le programme d’installation d’AEM Forms JEE.

### Lots OSGI et packages de contenu dans 6.3.3.5 {#osgi-bundles-and-content-packages-included-in}

Liste des lots OSGi inclus dans AEM 6.3.3.5

[Obtenir le fichier](assets/do-not-localize/6_5-bundle-list.txt)

Liste des packages de contenu inclus dans AEM 6.3.3.5

[Obtenir le fichier](assets/do-not-localize/content_packages6335.txt)

### Pack de correctifs cumulés 6.3.3.4 {#cumulative-fix-pack-4}

Le pack de correctifs cumulatif 6.3.3.4 pour AEM apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du pack de services 3 (6.3.3.0) pour AEM 6.3 de septembre 2018.

Le pack de correctifs cumulatif 6.3.3.4 pour AEM nécessite la présence du pack de services 3 pour AEM 6.3. Vous devez donc installer le pack de correctifs cumulatif 6.3.3.x pour AEM après avoir installé le pack de services 3 pour AEM 6.3. Pour obtenir des instructions sur l’installation, reportez-vous aux notes de mise à jour du [pack de services 3 pour AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.16.
* Ajout du délai d’expiration du socket et de la connexion dans les agents de réplication Brand Portal.

### Ressources {#assets-4}

* Si vous chargez à nouveau une archive qui porte le même nom, les rendus ne sont pas générés pour les nouvelles ressources traitées. NPR-28643 : correctif pour CQ-4262286
* Le workflow CommandLineProcess échoue lorsque le nom de fichier comprend un guillemet simple. NPR-28805 : correctif pour CQ-4262287
* Les valeurs sont différentes entre la page de collection et la page de collection lors de l’utilisation d’un filtre. NPR-28642 : correctif pour CQ-4261405
* CommitFailedException se déclenche lors du chargement de ressources d’archives ZIP volumineuses. NPR-28528 : correctif pour CQ-4260903
* L’enregistrement des métadonnées de dossier échoue lors de la modification d’un dossier contenant des caractères spéciaux. NPR-28211 : correctif pour CQ-4260401
* Impossible de supprimer les rendus d’image d’une ressource vidéo à partir de la page Détails de la ressource. NPR-29149 : correctif pour CQ-4266073
* La diffusion vidéo sur poste de travail DMS7 à l’aide de DMComponent utilise le téléchargement progressif pour lire la vidéo en mode de publication et ne procède pas à la diffusion. NPR-28754 : correctif pour CQ-4263732
* Impossible de créer/modifier des paramètres d’image prédéfinis, car la restriction de l’accès à /etc/dam/video/dynamicmedia désactive les fonctionnalités pour les gestionnaires d’images. NPR-28662 : correctif pour CQ-4263022
* Le partage de lien avec des fichiers vidéo codés DMS7 génère des dossiers vides. NPR-28851 : correctif pour CQ-4206743
* La réplication d’AEM vers Brand Portal se bloque pendant de longues périodes. NPR-28913 : correctif pour CQ-4254932

### Communities {#communities-3}

* Impossible d’ouvrir les messages dont les pièces jointes se trouve dans les dossiers Éléments envoyés et Boîte de réception d’Outlook. NPR-28559 : correctif pour CQ-4217072

### Sites {#sites-4}

* Cross-site scripting (XSS) dans SuggestionHandler pour AEM 6.3. NPR-28692 : correctif pour CQ-4253821
* Le déploiement en profondeur se termine sans contenir toutes les branches dans la Live Copy respective. NPR-29175 : correctif pour CQ-4239472
* (MSM) Mettez en œuvre LiveCopyIndex à l’aide de oak-index. NPR-29198 : correctif pour CQ-4222472
* Le fichier `coral.js` inclut une version vulnérable de la bibliothèque `handlebars.js`. NPR-26973 : correctif pour CQ-4255377
* L’utilisation d’un composant Target avec un conteneur de mise en page et un composant de texte imbriqués renvoie une erreur JavaScript « Impossible de lire la propriété currentPos de null » lors de la modification du texte ou d’un clic sur le conteneur. NPR-29077 : correctif pour CQ-4246594
* (Interface d’utilisation tactile) Impossible de mettre à jour en masse les balises sur les pages qui sont déjà balisées avec des balises différentes. NPR-28729 : correctif pour CQ-4262922
* L’ouverture de la variante dans la vue Carte provoque une erreur 500. NPR-28611 : correctif pour CQ-4263571
* Le déploiement d’une structure qui a été déplacée dans une racine principale entraîne un `cq:moveTarget` erroné. NPR-28968 : correctif pour CQ-4265280

### Intégration {#integration}

* (Configurations du service cloud) La case « hérité de » qui apparaît au niveau racine doit être supprimée. NPR-28771 : correctif pour CQ-4259676
* com.day.cq.personalization.impl.TeaserResourceEventHandler résulte en une boucle infinie et provoque des mises à jour des nœuds lors de la publication. NPR-28561 : correctif pour CQ-4263096
* L’utilisation des informations d’identification Bright edge échoue avec une erreur de connexion. NPR-29167 : correctif pour CQ-4265872
* Problème de compilation dans OfferproxyTandtProvider.java en raison d’une instruction d’importation manquante pour la classe « Ressource » : instruction d’importation manquante : importer org.apache.sling.api.resource.Resource. NPR-28772

### Commerce {#commerce}

* L’option Trier ne fonctionne pas pour les ressources de la collection Commerce. NPR-28755 : correctif pour CQ-4213622

### Jetty {#jetty}

* Exceptions Jetty dans error.log pour chaque redirection 302 après l’installation de CFP2 sur AEM 6.3.3. NPR-28606 : rétroportage pour CQ-4262844

### IU - Fondation {#ui-foundation}

* Le fait de cliquer sur une balise supprime l’événement MouseUp global et la boîte de dialogue est figée en mode glissable. NPR-28641 : correctif pour CUI-7294

### WCM - MSM {#wcm-msm}

* Le déploiement de PushOnModify pour PageManager déplace les validations à plusieurs reprises depuis deux sessions, provoquant une condition de concurrence. NPR-28880 : correctif pour CQ-4266191

### Vulnérabilité {#vulnerability}

* Le cadre de protection CSRF ne fonctionne pas avec les formulaires AEM Foundation. NPR-28612 : correctif pour GRANITE-22231

### Formulaires {#forms-4}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

Les principaux aspects pour AEM Forms sont les suivants :

* Activation de l’option pour sélectionner plusieurs éléments par page sur la page d’affichage du jeu de politiques.
* Ajout de la fonctionnalité de file d’attente partagée pour tous les navigateurs.

### Package de modules complémentaires Forms {#forms-add-on-package-4}

#### Forms - Workflow {#forms-workflow}

* Une tâche de réponse de file d’attente partagée ouvre un élément Flash dans l’espace de travail HTML5. NPR-29161 : correctif pour CQ-4266498
* Impossible d’envoyer à partir de l’espace de travail si le bouton contient un caractère comportant un umlaut. NPR-29014 : correctif pour CQ-4263172

#### Forms - Document Security {#forms-document-security}

* Activation de l’option pour sélectionner plusieurs éléments par page sur la page d’affichage du jeu de politiques. NPR-29243 : correctif pour CQ-4268567 et CQ-4265132

#### Forms - Services Acrobat {#forms-document-services-1}

* OSGi Forms Assembler ne fonctionne pas avec les fichiers Acrobat. NPR-29049 : correctif pour CQ-4254426

#### Formulaires HTML5 {#html-forms-2}

* Un comportement différent est observé lors de la prévisualisation d’un XDP en tant que PDF par rapport au même XDP en tant que HTML dans Designer. NPR-28602 : correctif pour CQ-4260239

### Programme d’installation de Forms JEE {#forms-jee-installer-3}

* Aucun nouveau correctif pour le programme d’installation d’AEM Forms JEE.

### Lots OSGI et packages de contenu dans 6.3.3.4 {#osgi-bundles-and-content-packages-included-in-1}

Liste des lots OSGi inclus dans AEM 6.3.3.4

[Obtenir le fichier](assets/do-not-localize/list_of_osgi_bundlesincludedinaem633.4)

Liste des packages de contenu inclus dans AEM 6.3.3.4

[Obtenir le fichier](assets/do-not-localize/list_of_content_packagesincludedinaem633.4)

### Pack de correctifs cumulés 6.3.3.3 {#cumulative-fix-pack-5}

Le pack de correctifs cumulés 6.3.3.3 pour AEM apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du pack de services 3 (6.3.3.0) pour AEM 6.3 de septembre 2018.

Le pack de correctifs cumulatif 6.3.2.2 pour AEM nécessite la présence du pack de services 3 d’AEM 6.3. Vous devez donc installer le pack de correctifs cumulatif 6.3.3.x pour AEM après avoir installé le pack de services 3 pour AEM 6.3. Pour obtenir des instructions sur l’installation, reportez-vous aux notes de mise à jour du [pack de services 3 pour AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.16.
* Modifications de la pagination de la liste des jeux de politiques pour limiter 50 enregistrements par page.
* Rep ajouté : mise en cache dans les nœuds ignorables de l’écouteur de synchronisation des utilisateurs et utilisatrices d’AEM Communities sur les instances de publication.
* Ajout d’un attribut aria-label pour le bouton « Liste et vue Carte ».
* Un caractère d’échappement était inclus pour la virgule lors d’une recherche.
* Activation de la prise en charge des ressources synthétiques pour la politique de contenu.

#### Ressources {#assets-5}

* Impossible de télécharger plusieurs fichiers de type `.jp2`, `.max`, `.oft` et `.msg`. NPR-28002 : correctif pour CQ-4210856
* Les paramètres de publication d’ImageServer ne se répliquent pas vers une diffusion hybride. NPR-28329 : correctif pour CQ-4253030

#### Communities {#communities-4}

* Activation de la navigation au clavier pour les composants d’activation AEM Communities sur l’instance de publication. NPR-27739 : correctif pour CQ-4253856
* Activation de la navigation au clavier pour déclencher la lecture du contenu. NPR-27738 : correctif pour CQ-4254026
* Ajout d’un attribut aria-label pour le bouton « Liste et vue Carte ». NPR-27736 : correctif pour CQ-4254027
* (Rétroportage) Rep ajouté : mettre en cache dans les nœuds ignorables du module d’écoute de synchronisation des utilisateurs d’AEM Communities sur les instances de publication. NPR-27841 : correctif pour CQ-4247234
* Les caractères spéciaux sont précédés d’un caractère d’échappement (\) dans la zone de recherche. NPR-27839 : correctif pour CQ-4259757
* Erreur lors de la recherche de caractères tels que `(`, `+` et `?` dans la recherche rapide. NPR-28212 : correctif pour CQ-4260969
* Impossible de supprimer les commentaires dans le contenu généré par l’utilisateur ou l’utilisatrice à l’aide de l’API. NPR-28075 : correctif pour CQ-4260534
* Les commentaires publiés sur la page suivante sont surlignés en jaune lorsqu’un nouveau commentaire est publié. NPR-28148 : correctif pour CQ-4259681
* Impossible d’ouvrir les messages dont les pièces jointes se trouve dans les dossiers Envoyé et Boîte de réception de Outlook. NPR-28559 : correctif pour CQ-4217072

#### Sites {#sites-5}

* L’exécution de la purge de version dans AEM 6.3 provoque la répétition constante d’un avertissement dans les journaux. NPR-27750 : correctif pour CQ-4206870
* Le plug-in de style n’est pas pris en charge dans le mode plein écran de l’éditeur de texte enrichi. NPR-27622 : correctif pour CQ-4258674
* La liste `loaderPromises` n’est pas effacée une fois le cadre de contenu chargé dans editor.js. NPR-27768 : correctif pour CQ-4205337
* Impossible de définir une politique de modèle pour un parsys imbriqué sans la définir dans le composant parent. NPR-27987 : correctif pour CQ-4246095
* L’explorateur de composants ne nettoie pas les données entrées par l’utilisateur ou l’utilisatrice et peut donc générer des erreurs JavaScript. NPR-27986 : correctif pour CQ-4247590
* La page apparaît vide lorsque l’utilisateur ou l’utilisatrice tente de modifier le fragment de contenu. NPR-27669
* La mise en surbrillance de l’annotation disparaît quand l’utilisateur ou l’utilisatrice clique sur l’annotation. BPR-27196 : correctif pour CQ-4254423

#### Intégration {#integration-1}

* ResourceResolver ne résout pas des domaines multiples pour le composant Target. NPR-28265 : correctif pour CQ-107847
* L’annulation de l’héritage de la Live Copy fonctionne désormais correctement sur les conteneurs ciblés, car les actions sont affichées. NPR-28129 : correctif pour CQ-4259813

#### Réplication {#replication-1}

* DispatcherFlushRules provoquait un dysfonctionnement de la réplication dans AEM 6.3.3.1. NPR-28150 : correctif pour CQ-4261401

#### Campaign - Ciblage {#campaign-targeting-1}

* Exception NullPointerException dans TargetedContentManager. Correctif pour CQ-4263485

#### Social - SCORM {#social-scorm}

* Supprimez la référence au cloud SCORM (Shareable Content Object Reference Model) dans le lecteur. Correctif pour CQ-4260779

#### DAM - Général {#dam-general}

* Le téléchargement via l’e-mail de partage de lien renvoie un fichier ZIP vide ou corrompu. Correctif pour CQ-4259686

#### `MAC` - Intégration de Test&amp;Target {#mac-test-target-integration}

* L’option de configuration du composant Target n’est pas disponible pour les audiences autres que l’audience par défaut. Correctif pour CQ-4261370

#### Traduction {#translation-1}

* Activez la prise en charge du service MS® Translator dans AEM 6.3 après la mise à niveau de MS® Translator vers l’API v3.0. NPR-28365 : correctif pour CQ-4259096

### Formulaires {#forms-5}

### Package de modules complémentaires Forms {#forms-add-on-package-5}

#### Forms - Workflow {#forms-workflow-1}

* Impossible d’effectuer le rendu des formulaires PDF sur l’espace de travail HTML5. NPR-28059 : correctif pour CQ-4260373

#### Forms - Services Acrobat {#forms-document-services-2}

* Impossible d’afficher les jeux de politiques au-delà des 1 000 premiers répertoriés dans la vue Jeux de politiques de l’Admin Console. NPR-28060, NPR-26047 : correctif pour CQ-4249865
* Une exception est générée avec le nom `java.lang.IllegalArgumentException message:No enum constant com.adobe.internal.pdfm.docbuilder.signature.PathValidationFailureReason.SIGNED_IN_FUTURE`, empêchant l’exécution du processus de courte durée. NPR-28652

#### Forms - Formulaires adaptatifs {#forms-adaptive-forms}

* Les éléments ajoutés ou supprimés dans la liste déroulante ne sont pas mis à jour lorsque l’on coche les éléments de cases à cocher. NPR-28224 : correctif pour CQ-4252834

### Forms - Programme d’installation JEE {#forms-jee-installer-4}

* Aucun nouveau correctif pour le programme d’installation d’AEM Forms JEE.

### Lots OSGI et packages de contenu dans 6.3.3.3 {#osgi-bundles-and-content-packages-included-in-2}

Liste des lots OSGi inclus dans AEM 6.3.3.3

[Obtenir le fichier](assets/do-not-localize/6333_bundle_list.txt)

Liste des packages de contenu inclus dans AEM 6.3.3.3

[Obtenir le fichier](assets/do-not-localize/content_package_list_6333.txt)

### Pack de correctifs cumulés 6.3.3.2 {#cumulative-fix-pack-6}

Le pack de correctifs cumulés 6.3.3.2 pour AEM apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du pack de services 3 (6.3.3.0) pour AEM 6.3 de septembre 2018.

Le pack de correctifs cumulatif 6.3.3.2 pour AEM nécessite la présence du pack de services 3 d’AEM 6.3. Vous devez donc installer le pack de correctifs cumulatif 6.3.3.x pour AEM après avoir installé le pack de services 3 pour AEM 6.3. Pour obtenir des instructions d’installation, voir les notes de mise à jour du pack de services 3 d’AEM 6.3.

Les principaux aspects du pack de correctifs cumulatif AEM sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.15.
* Ajout de la prise en charge de l’onglet Règles et application de celui-ci sur le dossier de ressources dans le schéma de métadonnées de dossier.
* Prise en charge de la pagination activée pour la page de liste des groupes sur l’instance de publication.
* Activation de la configuration de la notification unreadCount avec n’importe quel nombre. Par défaut, cette valeur est définie sur 20.
* Correctifs dans le vérificateur de lien externe.

#### Ressources {#assets-6}

* La liste déroulante en cascade n’est pas prise en charge dans les listes déroulantes dynamiques. NPR-27044 : correctif pour CQ-4252564
* Amélioration de la requête afin d’utiliser la fonction ExpiryNotification. NPR-26999 : correctif pour CQ-4251188
* Migration des règles du schéma de métadonnées vers le schéma de métadonnées de dossier. NPR-27771 : rétroportage pour CQ-4257737, CQ-4257735, CQ-4259822
* L’ajustement des références de ressources ne parvient pas à mettre à jour les références des ressources qui font partie de ResourceCollections Sling. NPR-26759 : correctif pour CQ-4252605
* Le téléchargement via l’e-mail de partage de lien renvoie un fichier ZIP vide ou corrompu. NPR-27997 : correctif pour CQ-4259686
* Le codage vidéo hybride ne se termine pas et aucune miniature n’est créée. NPR-27122 : correctif pour CQ-4255080

#### Sites {#sites-6}

* La suspension de la page parente supprime le type de mixin cq:LiveRelationship de la page manquante. NPR-26996 : correctif pour CQ-4254113
* (Vérificateur de lien externe) Les liens internes apparaissent rompus sur les différentes pages, mais cela ne fonctionne pas pour les liens externes. NPR-27481 : correctif pour CQ-4257780
* L’héritage de la configuration de Cloud Service est interrompu lors de la modification d’autres propriétés de page. NPR-27311 : correctif pour CQ-4256785
* Exception de pointeur nul lors de l’utilisation d’un formulaire de composants principaux avec un formulaire de composants de base. NPR-27333 : correctif pour CQ-4249176
* L’éditeur de texte enrichi supprime la balise de remplacement vide. NPR-26938 : correctif pour CQ-4253267
* (IU classique) Problèmes de performances avec la sélection. Le listener a été modifié dans le cas de plusieurs listes déroulantes. NPR-27115 : correctif pour CQ-4237215
* Lorsque l’éditeur de texte enrichi est associé à plusieurs champs, l’erreur Uncaught TypeError: fieldAPI.getName n’est pas une fonction à foundation.js se produit. NPR-27146 : correctif pour CQ-4253155, CQ-4259967
* Le focus/curseur reste dans l’éditeur de texte enrichi même lorsque vous cliquez sur un bouton radio dans le navigateur Safari. NPR-27144 : correctif pour CQ-4249635
* La page apparaît vide lorsque l’utilisateur ou l’utilisatrice tente de modifier le fragment de contenu. NPR-27669
* Impossible de créer une version pour les fragments d’expérience. NPR-27689 : correctif pour CQ-4259009

#### Intégration {#integration-2}

* com.day.cq.personalization.impl.BrandsRetriever parcourt l’arbre entier pour recueillir les marques disponibles. NPR-27060 : correctif pour CQ-4255790
* Les `cq:actions` ne sont pas prises en compte pour un composant ciblé. NPR-27616 : correctif pour CQ-4257497

#### Sling {#sling}

* Lorsque data-sly-use est utilisé avec des classes portant un nom identique, le code non conforme est généré. NPR-27282 : correctif pour Sling-7581

#### Commerce {#commerce-1}

* Mise à jour vers Apache Felix Http Jetty 4.0.6. NPR-26472 : correctif pour Granite-22916

#### DAM - Client DM {#dam-dm-client}

* Une image ne s’affiche pas après avoir spécifié des points d’arrêt dans un composant Dynamic Media. Correctif pour CQ-4256168

#### DAM - DMServices {#dam-dmservices}

* MixedMediaSet avec la vidéo associée ne se synchronise pas correctement. Correctif pour CQ-4251650
* La vidéo ne se lit pas dans l’éditeur de paramètres prédéfinis de la visionneuse pour la visionneuse de supports variés. Correctif pour CQ-4251442

#### DAM - Général {#dam-general-1}

* Le lien vers le modèle de fragment de contenu est manquant après l’application du correctif SP3. Correctif pour CQ-4259029

#### DAM - IU {#dam-ui}

* L’interface d’utilisation du schéma de métadonnées des dossiers ne fonctionne plus correctement après l’installation du SP3. Correctif pour CQ-4257737

#### Communities {#communities-5}

* Ajoutez la prise en charge de la pagination pour la liste de groupes lors de la publication. NPR-26953 : correctif pour CQ-4246525
* La notification du nombre d’éléments non lus ne peut pas être définie au-delà de 21. NPR-27496 : correctif pour CQ-4252829
* Le nombre d’abonnements d’utilisateurs et d’utilisatrices est limité à 1 000. NPR-27615 : correctif pour CQ-4254689
* Erreur observée lors du chargement d’une pièce jointe autre qu’une image (par exemple .pdf) dans le forum. NPR-27375 : correctif pour CQ-4257753
* Le lien pour les réponses ne fonctionne pas lors d’un clic sur une ligne. NPR-24556 : correctif pour CQ-4256138
* Les relations avec le contenu créé par l’utilisateur ou l’utilisatrice ne sont pas supprimées lors de la suppression du contenu créé par l’utilisateur ou l’utilisatrice. NPR-27631 : correctif pour CQ-4258706
* Impossible de rechercher par valeur d’adresse dans la recherche par mot-clé si la communauté est définie avec le fournisseur de ressources de stockage de base de données (DSRP). NPR-27652 : correctif pour CQ-4253261
* Cliquer sur l’icône de corbeille de l’image après la confirmation de suppression supprime définitivement la pièce jointe. NPR-27340 : correctif pour CQ-4255150
* Les publications et réponses du forum sont ajoutées en haut de la deuxième page. Lorsqu’elles sont actualisées, la publication se déplace à l’emplacement approprié en haut de la première page. NPR-27341 : correctif pour CQ-4247338
* Le libellé du statut d’achèvement de la ressource d’activation Scorm apparaît vide dans l’interface d’utilisation. NPR-27152 : correctif pour CQ-4249994
* Si l’option **Autoriser les personnes disposant de privilèges** est activée, les personnes membres disposant de privilèges ne doivent pouvoir créer des éléments que pour les utilisateurs et les utilisatrices qui sont membres de la communauté. NPR-27901 : correctif pour CQ-4251235

#### Soutenance {#sustenance}

* Les journaux d’activité du gestionnaire de modules doivent être extraits dans un fichier journal distinct. NPR-27323 : correctif pour Granite-14866

#### Traduction {#translation-2}

* La prévisualisation de la traduction ne fonctionne pas avec l’exemple de contenu we.retail. NPR-27170 : correctif pour CQ-4241179

* Correctifs proactifs de connexion à la plateforme. NPR-26961
* Les opérations Enregistrer et fermer sur les propriétés de page ne renvoient pas vers la page appropriée dans AEM WAR avec Tomcat. NPR-27567 : correctif pour Granite-23671

* Une fois enregistré, le texte saisi est perdu via la fonction sourceEdit. Correctif pour CQ-4259273

### Formulaires {#forms-6}

### Package de modules complémentaires Forms {#forms-add-on-package-6}

#### Forms - Document Security {#forms-document-security-1}

* Problème de simultanéité avec le SDK client JEE. NPR-27572 : correctif pour CQ-4247156

#### Forms - Services Acrobat {#forms-document-services-3}

* La création d’un modèle de données de formulaire basé sur SOAP échoue dans WebSphere®. NPR-27692 : correctif pour CQ-4253702

#### Forms - Formulaires adaptatifs {#forms-adaptive-forms-1}

* Vulnérabilité aux injections XML avec les formulaires AEM. NPR-27863 : correctif pour CQ-4257315
* Le composant Conteneur AEM Forms devient invisible lorsque le mauvais formulaire est configuré dans la page AEM Sites et que la case « Les formulaires couvrent toute la largeur de la page » est cochée. NPR-25972 : correctif pour CQ-4239287, CQ-4249133

### Programme d’installation de Forms JEE {#forms-jee-installer-5}

#### Foundation JEE {#foundation-jee-1}

* La création d’un modèle de données de formulaire basé sur SOAP échoue dans WebSphere®. NPR-27692 : correctif pour CQ-4253702

#### Lots OSGI et packages de contenu inclus {#osgi-bundles-and-content-packages-included}

Liste des lots OSGi inclus dans AEM 6.3.3.2

[Obtenir le fichier](assets/do-not-localize/63332bundle_list.txt)

Liste des packages de contenu inclus dans AEM 6.3.3.2

[Obtenir le fichier](assets/do-not-localize/6332content_package.txt)

### Pack de correctifs cumulés 6.3.3.1 {#cumulative-fix-pack-7}

Le pack de correctifs cumulés 6.3.3.1 pour AEM apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du pack de services 3 (6.3.3.0) pour AEM 6.3 de septembre 2018.

Le pack de correctifs cumulatif 6.3.3.1 pour AEM nécessite la présence du pack de services 3 d’AEM 6.3. Vous devez donc installer le pack de correctifs cumulatif 6.3.3.x pour AEM après avoir installé le pack de services 3 pour AEM 6.3. Pour obtenir des instructions d’installation, reportez-vous aux notes de mise à jour du [Pack de services 3 d’AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.14.
* Amélioration des performances du prédicat et de la recherche.
* Correction d’un problème lié à la gestion de FormData pour la valeur par défaut.
* Mise à niveau de FormBuilder vers la dernière version de Handlebars.
* Ajout du servlet de configuration pour la configuration de modification de l’éditeur de texte enrichi en mode boîte de dialogue.
* Ajout de la prise en charge des champs composites.
* Activation/désactivation des éléments de barre d’outils de l’éditeur de texte enrichi avec une politique de contenu pour la boîte de dialogue de modification.

#### Ressources {#assets-7}

* Si le découplage IDS est activé, le workflow de mise à jour DAM ne lie plus les références. NPR-26135 : correctif pour CQ-4250933
* La décompression d’une archive créée par l’étape de décompression avec un dossier dont le nom contient un % ne s’ouvre pas. NPR-26275 : correctif pour CQ-4251482
* Le caractère guillemet simple empêche la mise à jour des métadonnées. NPR-26808 : correctif pour CQ-4254305
* (Omnisearch) Problème de performances lors de la recherche au sein d’une collection. NPR-26714 : correctif pour CQ-4253408
* L’utilisation de GQLConverter avec une recherche de texte intégral contenant les lettres « OR » dans le texte est traitée de manière incorrecte. NPR-26564 : correctif pour CQ-4247362
* Le partage d’un lien de ressource à partir de plusieurs clients ajoute un identifiant client formant une URL non valide. NPR-26482 : correctif pour CQ-4253540
* Désactivation de « Chemin d’accès au dossier racine de l’entreprise » dans l’interface utilisateur de configuration du cloud Dynamic Media. NPR-26361 : correctif pour CQ-4249505
* L’importation des fichiers RAW .mos dure trop longtemps. NPR-26296 : correctif pour CQ-4250661
* Le partage de liens de ressources ne permet pas d’ajouter plusieurs utilisateurs et utilisatrices internes avec un identifiant numérique d’utilisateur ou d’utilisatrice. NPR-26206 : correctif pour CQ-4251466
* Corruption des fichiers zip compressés avec l’algorithme deflate64. NPR-26793 : correctif pour CQ-4253995
* Le processus de génération de miniatures ne fonctionne pas correctement pour les fichiers PDF complexes, ce qui entraîne la création de miniatures dont une partie de l’image est manquante. NPR-26057 : correctif pour CQ-4250944
* Problème d’utilisation de la mémoire de tas avec la génération de miniatures. NPR-25545 : correctif pour CQ-4246960
* La création de nombreuses relations sur une ressource entraîne une erreur. NPR-26309 : correctif pour CQ-4250708
* L’option **Supprimer le rendu** ne fonctionne pas et renvoie une erreur « rien à supprimer ». NPR-26007 : correctif pour CQ-4213414
* Impossible de supprimer les valeurs par défaut des champs à plusieurs valeurs. NPR-25116 : correctif pour CQ-4247856
* (DM Hybrid) La réplication de catalogue échoue dans AEM 6.3.2 avec Dynamic Media. NPR-26406 : correctif pour CQ-4251306

#### Sites {#sites-7}

* Rétroportage proactif des correctifs de Sites. NPR-26963
* Les balises sont créées deux fois lorsqu’il existe une différence dans le type de casse de Titre et Nom. NPR-26877 : correctif pour CQ-4254134
* Les politiques ne contrôlent pas les fonctionnalités de l’éditeur de texte enrichi dans la boîte de dialogue de modification. NPR-27059, NPR-26750 : correctif pour CQ-4241130
* Questions de caching ou de non caching de segment.js dans le contexte du client. NPR-26622 : correctif pour CQ-4253486
* Les activations de règle de segmentation (/etc/segmentation) pour les règles enfants en mode classique provoquent la suppression de la publication. NPR-26601 : correctif pour CQ-4253588
* L’ajout d’un « caractère spécial » fait défiler la boîte de dialogue de l’éditeur de texte enrichi vers le haut. NPR-26435 : correctif pour CQ-4249869
* (IU tactile) La barre d’outils devient inutilisable avec plusieurs éditeurs de texte enrichi lorsqu’on passe du mode plein écran à une boîte de dialogue flottante. NPR-25652 : correctif pour CQ-4206008
* La promotion d’un lancement de plusieurs pages crée plusieurs versions pour chaque page. NPR-26810 : correctif pour CQ-4254663
* Les champs de balises d’un modèle de fragment de contenu structuré ne reflètent pas les opérations de déplacement des balises. NPR-26801 : correctif pour CQ-4251805
* (IU tactile) La dépublication de la page enfant depuis l’éditeur de page ne fonctionne pas après un changement du nom de la page dans le plan directeur. NPR-26774 : correctif pour CQ-4254175
* La page dépubliée ne fonctionne pas avec les références. NPR-26749 : correctif pour CQ-4254372
* Lors de la création d’une variante en tant que Live Copy, il est nécessaire que l’utilisateur ou l’utilisatrice actualise la page afin d’en refléter les données. NPR-26663 : correctif pour CQ-4254328
* (Interface d’utilisation classique) En revenant aux propriétés de la page, l’image de la miniature n’utilise plus l’héritage, disparaît de site admin et de sidekick, et apparaît vide. NPR-26562 : correctif pour CQ-4252346
* Lorsqu’une version d’une page est créée et qu’une comparaison est déclenchée, les nœuds de /content/versionshistory sont répertoriés dans la liste des Live Copies pour le plan directeur. NPR-26506 : correctif pour CQ-4243957
* Les URL de l’éditeur d’administration de fragments d’expérience ne permettent pas les superpositions. NPR-26318 : correctif pour CQ-4252156

#### Plateforme {#platform}

* Fuite de session dans ReplicationEventListener avec des événements de test. NPR-25937 : correctif pour CQ-4251090
* La réplication utilise le jeton expiré pour OAuth, ce qui entraîne plusieurs erreurs. NPR-25894 : correctif pour GRANITE-22388

#### Intégration {#integration-3}

* Le SDK incorporé avec AEM est interrompu avec une mise à niveau vers Handlebars 4 en raison de l’utilisation de modèles incompatibles. NPR-26699 : correctif pour CQ-4248974
* La publication d’une page avec une nouvelle ressource désactive la page enfant de l’instance de publication sans notification. NPR-24869 : correctif pour CQ-4247832
* La réplication utilise un jeton ayant expiré pour OAuth. NPR-25984 : correctif pour Granite-22388

#### Réplication {#replication-2}

* Le transport HTTP peut provoquer une fuite des sessions ouvertes. Correctif pour Granite-17434
* L’accès simultané par plusieurs agents de réplication entraîne des exceptions dans les journaux lors de l’accès au nœud du jeton d’accès. NPR-26964 : correctif pour Granite-23276, Granite-23155

#### ContextHub {#contexthub}

* Le fichier `coral.js` inclut une version vulnérable de la bibliothèque `handlebars.js`. Correctif pour CQ-4255377

#### DAM - Client DM {#dam-dm-client-1}

* La suppression d’une copie d’une ressource d’image rend la ressource d’image d’origine inutilisable. Correctif pour CQ-4251648
* Téléchargement redondant de contenu d’image supplémentaire à partir des serveurs S7. Correctif pour CQ-4248770

#### Granite {#granite}

* Le fournisseur OAuth d’AEM n’effectue pas de recherche non sensible à la casse. NPR-26133 : correctif pour GRANITE-22650
* Le programme de validation de package ne valide pas les packages inclus dans CFP/SP. NPR-26775 : correctif pour Granite-22825

#### Communities {#communities-6}

* Problème de délimiteur avec les résultats de la recherche. NPR-27051 : correctif pour CQ-4248939
* Remplace la valeur de la liste déroulante de Dallas à Virginia dans Adobe Storage Resource Provider. NPR-26936 : correctif pour CQ-4254434
* Activation de la prise en charge de la recherche de titre localisée dans SocialTagManager. NPR-26932 : correctif pour CQ-4250276
* Les images en pièces jointes n’affichent pas de miniatures lors de la création d’une publication de forum. NPR-26380 : correctif pour CQ-4253105
* Le plug-in Coller à partir de Word ne parvient pas à charger plus d’une image. NPR-26728 : correctif pour CQ-4253638
* Impossible de filtrer le contenu dans la page de modération. NPR-26697 : correctif pour CQ-4213766
* (Vulnérabilité de sécurité) Prise de contrôle du compte en raison d’une mauvaise configuration de JWT. NPR-26440 : correctif pour CQ-4253314
* La récupération des données à partir du fournisseur de ressources de stockage Adobe est lente. NPR-26237 : correctif pour NPR-24152
* La page de composition des messages privés est instable et lente. NPR-26120 : correctif pour CQ-4250923
* La notification « Tout marquer comme lu » rend uniquement les 10 premiers messages comme non lus sans actualisation de la page. NPR-27036 : correctif pour CQ-4254058
* Clic de pagination des sections de commentaires Communities et de comportement de chargement de page. NPR-27030 : correctif pour CQ-4251228
* (Recherche dans le forum) Le bouton Précédent saute la page et revient à forum.html. NPR-26949 : correctif pour CQ-4254804
* La notification non lue n’augmente pas au-dessus de 21. NPR-26947 : correctif pour CQ-4251251
* (Tâche SearchScheduledPosts) Ajout du commutateur activer/désactiver dans ConfigMgr. NPR-26924 : correctif pour CQ-4250463
* Le chemin d’accès de Tomcat Context(/aempublish) disparaît lors du défilement de la page Affectations. NPR-26919 : correctif pour CQ-4254345
* NullPointerException lors de la création d’un groupe et d’un ou d’une membre. NPR-26778 : correctif pour CQ-4248095
* Le contenu que le modérateur ou la modératrice a désépinglé et a décidé de ne pas mettre en vedette ne fonctionne pas avec le principe de responsabilité unique (SRP) de MySQL. NPR-26767 : correctif pour CQ-4251520
* Problèmes de fonctionnalité de recherche avec certains caractères. NPR-26726 : correctif pour CQ-4247744
* Activez les liens profonds pour l’interface utilisateur de modération et les ressources d’activation. NPR-26705 : correctif pour CQ-4251381
* Problème lorsqu’une recherche est effectuée dans le composant Forum. NPR-26577 : correctif pour CQ-4251303
* La recherche utilisant conjointement le prénom et le nom dans les messages de communauté ne renvoie pas les résultats attendus. NPR-26377 : correctif pour CQ-4253150
* La pagination ne se met pas à jour lors de la suppression des réponses. NPR-26327
* La suppression d’une publication fonctionne, mais provoque une erreur dans la console et la publication reste visible dans l’interface d’utilisation. NPR-26292 : correctif pour CQ-4252803
* La pagination ne se met pas à jour de manière dynamique et la liste des réponses continue de s’allonger. NPR-26145 : correctif pour CQ-4251586
* Les paramètres du groupe ne se chargent pas dans un groupe qui contient plusieurs milliers de personnes. NPR-25642 : correctif pour CQ-4238426
* Échec du lecteur de ressources du catalogue pour les chemins d’accès au contexte. NPR-25640 : correctif pour CQ-4238426
* (Recherche dans le forum) - Les liens paginés vers des fils qui contiennent beaucoup de publications ne fonctionnent pas dans les notifications. Correctif pour CQ-4254202
* La console de modération affiche uniquement cinq entrées avec Firefox. Correctif pour CQ-4254128
* Les groupes ne sont pas visibles lors de la création d’un site. NPR-27148 : correctif pour CQ-4251788
* Exception NullPointer lors de l’ajout d’un groupe et de personnes membres aux paramètres de rôles et de l’autorisation d’une personne membre disposant de privilèges dans la fonction blog. NPR-21732, NPR-27176 : correctif pour CQ-4255909
* La modification du site et l’ajout de personnes membres aux paramètres de rôles renvoie une exception NullPointer. NPR-27132 : correctif pour CQ-4255909

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
* Mettez à jour les bibliothèques clientes granite coralui2 et coralui3 pour supprimer Handlebars de la version. NPR-25606 : correctif pour Granite-22116

### Formulaires {#forms-7}

### Package de modules complémentaires Forms {#forms-add-on-package-7}

#### Forms - Document Security {#forms-document-security-2}

* Exceptions de survol de clé principale dans les journaux du serveur pour les clés inactives. NPR-26748 : correctif pour CQ-4253705
* Impossible de créer ou de modifier les paramètres de filigrane de Document Security. NPR-26267, NPR-26129 : correctif pour CQ-4250234

#### Forms - Services Acrobat {#forms-document-services-4}

* La validation PDF/A ne s’affiche pas valide avec « validate PDF/A ». NPR-25934 : correctif pour CQ-4248558

#### Forms - Communication interactive {#forms-interactive-communication}

* Si vous modifiez et enregistrez un module modifiable, puis ouvrez ou fermez l’aperçu du PDF, l’aperçu du PDF et de l’HTML de la lettre reste visible. Les deux aperçus restent fonctionnels dans la même fenêtre. NPR-26770 : correctif pour CQ-4253217

#### Forms - Workflow {#forms-workflow-2}

* L’espace de travail se bloque par intermittence et affiche les points de départ à plusieurs reprises. NPR-26461 : correctif pour CQ-4253439
* Une exception ESAPI est générée dans les logs lorsque des accolades sont utilisées dans le nom de la tâche. Correctif pour CQ-4256627
* Une exception de pointeur nulle est rapportée lorsque le point de départ associé au formulaire/jeu de formulaires adaptatif non prérempli est ouvert. Correctif pour CQ-4256124
* Impossible d’envoyer l’email à l’aide du paramètre global. NPR-26163 : correctif pour CQ-111110
* Impossible d’ouvrir l’espace de travail après l’application du fichier axis.jar. NPR-26131 : correctif pour CQ-4251126
* Le bouton Actualiser ne parvient pas à synchroniser les dernières données du serveur vers les formulaires adaptatifs. Correctif pour CQ-4255670
* Une exception est générée lors de la définition d’un modèle de recherche à partir de l’interface utilisateur d’administration et de son utilisation pour effectuer une recherche dans l’espace de travail AEM Forms. Correctif pour CQ-4255649
* Les détails du suivi des workflows sous les applications dont le nom contient des parenthèses ne s’affichent pas dans l’espace de travail HTML. Correctif pour CQ-4242101
* L’enregistrement des modifications sur l’écran des préférences de l’espace de travail HTML renvoie une exception. Correctif pour CQ-4241485
* L’approbation en bloc est défaillante après installation de la dernière version de JEE. Correctif pour CQ-4241486
* Le brouillon de tâche/point de départ échoue sur la dernière version du serveur JEE 6.4. Correctif pour CQ-4241484
* Utilisation du paramètre Date().getTime().toString pour initialiser la session au lieu de Date.toString(). Correctif pour CQ-4241483
* Lors de l’ouverture de /lc/ws, une exception de type caractère vulnérable est observée dans le paramètre HTML. Correctif pour CQ-4241481

#### Vulnérabilité {#vulnerability-1}

* Vulnérabilité au cross-site scripting (XSS) par stockage dans l’onglet Remarques du gestionnaire de formulaires. NPR-27157 : correctif pour CQ-4255556

### Programme d’installation de Forms JEE {#forms-jee-installer-6}

#### Foundation JEE {#foundation-jee-2}

* Examen du code pour l’API Enterprise Security. Correctif pour CQ-4255638
* Échec du chargement d’esapi.properties en tant que ressource de chargeur de classe dans WAS9. Correctif pour CQ-4255631
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
* Correction des problèmes signalés dans le rapport de l’analyse du code statique du PDFG. NPR-23251 : correctif pour CQ-4213930

#### Lots OSGI et packages de contenu dans 6.3.3.1 {#osgi-bundles-and-content-packages-included-in-3}

Liste des lots OSGi inclus dans AEM 6.3.3.1

[Obtenir le fichier](assets/do-not-localize/63sp3cfp1bundlelist.txt)

Liste des packages de contenu inclus dans AEM 6.3.3.1

### Pack de correctifs cumulés 6.3.2.2 {#cumulative-fix-pack-8}

Le pack de correctifs cumulés 6.3.2.2 pour AEM apporte une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale du pack de services 2 (6.3.2.0) pour AEM 6.3 d’avril 2018.

Le pack de correctifs cumulatif 6.3.2.2 pour AEM nécessite la présence du pack de services 2 d’AEM 6.3. Vous devez donc installer le pack de correctifs cumulatifs AEM 6.3.2.x après avoir installé le Pack de services 2 AEM 6.3. Pour obtenir des instructions d’installation, reportez-vous aux notes de mise à jour du [pack de services 2 d’AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions).

Les principaux aspects du **pack de correctifs cumulés AEM** sont les suivants :

* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.11.
* Activation des sous-ressources et de la visionneuse de ressources multipages dans Brand Portal.
* Modification de la longueur du type de champ à 255 afin de prendre en charge tous les types MIME possibles pour les différents types de pièces jointes.
* Configuration d’un message d’erreur du serveur lorsqu’une image enfreint les critères de chargement.
* Ajout de la prise en charge de STARTTLS dans Day CQ Mail Service.
* Mettez à jour vers les dernières versions de cq-wcm-content et com.adobe.cq.launches.it.serverside.
* Mettez à jour com.adobe.granite.ui.coralui3-rte vers la dernière version publiée.
* S’assure que la condition de rendu renvoie un résultat sain si expressionResolver est nul.
* Coral.ColumnView : ajout de la prise en charge de Maj+clic.

### Ressources {#assets-8}

* Le champ Groupe d’utilisateurs fermé (CUG) du dossier de ressources ne rappelle pas le groupe « tout le monde ». NPR-23163 : correctif pour CQ-4239377
* La recherche de collecte dynamique enregistrée ne renvoie pas tous les résultats. NPR-23243 : correctif pour CQ-4240355
* (ExpiryNotificationJobImpl) Optimisation de la requête existante. NPR-23330 : correctif pour CQ-4205249
* (Profil des métadonnées) Les valeurs de balise standard définies au moment de la création ne sont pas disponibles après l’enregistrement. NPR-23370 : correctif pour CQ-4235458
* (IU tactile) Impossible de déplacer plusieurs ressources en raison d’une erreur JS. NPR-23395 : correctif pour CQ-4241279
* Discordance de la taille du téléchargement par rapport aux informations affichées. NPR-23418 : correctif pour CQ-4242774
* Le type MIME extrait pour l’extension de fichier LSR et SKETCH est incorrect et entraîne un téléchargement de fichier non valide. NPR-23644 : correctif pour CQ-4243260
* (Firefox/Chrome) Impossible de télécharger les ressources dans la page Partage de ressources. NPR-23963 : correctif pour CQ-4244391
* Les facettes de recherche de l’administrateur des ressources disparaissent dans les panneaux de recherche après prévisualisation. NPR-23964 : correctif pour CQ-4244410
* La dépublication du formulaire de recherche supprime complètement le formulaire de recherche par défaut. NPR-23291 : correctif pour CQ-4241382
* (Brand Portal) La recherche dans le prédicat du répertoire devrait être filtrée lors de la réplication. NPR-23292 : correctif pour CQ-4241385
* L’action Publier dans l’interface utilisateur du Brand Portal n’est pas disponible. NPR-23293 : correctif pour CQ-4241161
* Le bouton Publier/Dépublier sur Brand Portal ne devrait pas être disponible pour les fragments de contenu. NPR-23318 : correctif pour CQ-4245086
* (Brand Portal) Activer la création de sous-ressources lors de la publication d’une ressource. NPR-23331 : correctif pour CQ-4242018
* Les requêtes Dynamic Media n’utilisent pas le client commun proxy/HTTP. NPR-10727 : correctif pour CQ-45695, CQ-88800
* Impossible d’annoter une ressource vidéo MP4 de rendu unique dans Dynamic Media S7 (DMS7). NPR-22046 : correctif pour CQ-4215912
* Les données EmbedXMP sont toujours définies comme « actives » pour le processus de génération Pyramid Tiff. NPR-22903 : correctif pour CQ-4234498
* Problèmes d’affichage/de sélection du rendu dynamique avec un grand nombre de préréglages d’image. NPR-23151 : correctif pour CQ-4217511
* Problème avec la vidéo de codage Dynamic Media - Modification/Nouveau chargement du lanceur. NPR-23237 : correctif pour CQ-4240260
* Correctif de gestion des proxys pour le transfert HTTP dans Dynamic Media S7. NPR-24001 : correctif pour CQ-244140

### Sites {#sites-8}

* Des disparités dans le créateur de requêtes provoquent une traduction xPath différente entre les versions 6.2 et 6.3. NPR-23245 : correctif pour CQ-4240396
* L’onglet Miniature de la propriété de page ne provoque pas l’agrandissement de la boîte de dialogue. NPR-22844 : correctif pour CQ-4241474
* Les parsys provoquent une défaillance qui affecte la largeur d’image de l’appareil de l’émulateur et coupe (place hors-cadre) tout composant qui y est ajouté. NPR-22926 : correctif pour CQ-4238224
* Lors de l’exécution de plusieurs lancements, le lancement est promu dans l’instance de création, mais les modifications ne sont pas répliquées sur le serveur de publication en raison de l’absence d’autorisations de réplication. NPR-22934 : correctif pour CQ-4234746
* Un autre utilisateur ou une autre utilisatrice dans une autre session peut modifier une page verrouillée par un utilisateur ou une utilisatrice au cours de la première session. NPR-23057 ; correctif pour CQ-4199017
* Correction de l’option de réorganisation dans la vue Liste. NPR-23065 : correctif pour CQ-4239321
* (Éditeur de page) L’image d’un composant image disparaît lors de la réouverture de la boîte de dialogue. NPR-23156 : correctif pour CQ-4239978
* L’éditeur de modèles affiche uniquement 20 modèles ou dossiers et ne charge pas les autres lorsque l’on fait défiler la page vers le bas. NPR-23185 : correctif pour CQ-4238483
* (IU classique) Une erreur est générée lors du déplacement ou du changement de nom des pages. NPR-23213 : correctif pour CQ-4240971
* Impossible de modifier ou de créer des segments ContextHub. NPR-23218 : correctif pour CQ-4226948
* (Éditeur de texte enrichi) - L’opération Remplacer modifie le format d’un mot. NPR-23271 : correctif pour CQ-4239677
* Le bouton Déploiement est manquant dans l’onglet Plan directeur pour les variantes XF. NPR-23320 : correctif pour CQ-4240404
* L’UI classique ne permet pas de modifier le CUG pour des raisons d’obsolescence. NPR-24122 : correctif pour 4241823
* Correctif proactif pour se protéger contre les promotions de contenu indésirables. NPR-24387 : correctif pour 4244993
* Après l’ajout d’environ 80 fragments dans un dossier dans Assets, le déclenchement du workflow à partir de la console de chronologie provoque des erreurs. NPR-23393 : correctif pour CQ-4211216
* Impossible de glisser-déposer des images dans la boîte de dialogue de l’éditeur de texte enrichi à partir de l’outil de recherche de contenu. NPR-23403 : correctif pour CQ-4242094
* Erreur « Valeur du sélecteur de récursivité non valide » lors de la migration d’un composant d’AEM 6.0 vers AEM 6.2. NPR-23532 : correctif pour CQ-4241258
* (Éditeur de texte enrichi) Les info-bulles affichent le nom de variable du plug-in au lieu du nom lisible du plug-in. NPR-23550 : correctif pour CQ-4243269
* Impossible d’enregistrer la boîte de dialogue avec la liste déroulante de sélection requise dans la version mobile/tablette. NPR-23904 : correctif pour CQ-4243096
* Les options du système de style apparaissent sur toutes les pages après l’installation de la version 6.3.2.1. NPR-23972 : correctif pour CQ-4244394
* L’UI classique ne permet pas de modifier le CUG pour des raisons d’obsolescence. NPR-24122 : correctif pour 4241823
* Correctif proactif pour se protéger contre les promotions de contenu indésirables. NPR-24387 : correctif pour 4244993
* Les références aux ressources ne sont pas mises à jour lorsque les ressources sont déplacées. NPR-23208 : correctif pour CQ-4239879

### Plateforme {#platform-1}

* La collecte dynamique n’affiche pas les résultats après l’enregistrement si vous utilisez un prédicat de balises dans la facette de recherche. NPR-23401 : correctif pour Granite-21278
* Patch pour jQuery 1.12.4 de clientlib afin d’inclure un correctif de sécurité. NPR-24128 : correctif pour Granite-20058
* Les traductions d’internationalisation sont à présent mises à jour, sauf si le lot est redémarré. NPR-23193 : correctif pour Sling-7190
* Résolveur de ressources non fermé dans ReplicationEventListener. NPR-23240 : correctif pour CQ-4241350
* Prise en charge de STARTTLS dans « Day CQ Mail Service ». NPR-23941 : correctif pour CQ-4240397
* Le nom de la balise de réclamation JCR doit être automatiquement renseigné en fonction du titre de la balise. NPR-24173 : correctif pour CQ-4199411

### Intégration {#integration-4}

* (Target) Les campagnes ne sont pas activées lors de l’utilisation du type d’API au format XML. NPR-23199 : correctif pour CQ-4240936****
* La réplication de référence de configuration échoue avec la structure de dossiers intermédiaire. NPR-23485 : correctif pour CQ-4242751

### Vulnérabilité {#vulnerability-2}

* L’intégration de Salesforce est vulnérable aux attaques SSRF (Server Side Request Forgery). NPR-24289 : correctif pour CQ-424527
* Cross-site scripting (XSS) dans les liens des Projets de l’IU d’administration. NPR-23272 : correctif pour CQ-4241795

### WCM - Composants Foundation {#wcm-foundation-components}

* Le tableau de Foundation est vulnérable au cross-site scripting par stockage. NPR-23214 : correctif pour CQ-4240760

### Traduction {#translation-3}

* Les propriétés de la Live Copy ne sont pas supprimées lors de la création de copies de langue. NPR-23123 : correctif pour CQ-4230641

### Interface utilisateur {#user-interface-1}

* Le sélecteur de date ne prend pas en charge la définition manuelle d’un conseil de type externe par un champ masqué. La modification de l’indicateur de type génère une erreur de conversion. NPR-23371 : correctif pour Granite-21194
* Coral.ColumnView : ajout de la prise en charge de Maj.+clic. NPR-23404 : correctif pour Granite-13338
* Sélectionner RT ne valide pas lorsqu’un élément avec une valeur vide est sélectionné. NPR-23405 : correctif pour Granite-21283
* (OMEGA) Rapport « Fonctionnalité » en anglais seulement. NPR-23990 : correctif pour Granite-21231
* Correctifs de l’API Coral.Autocomplete. NPR-23516

### Granite {#granite-1}

* Les connexions de suivi client Apache HTTP et une utilisation élevée du tas entraînent le crash du serveur AEM. NPR-23906 : correctif pour Granite-21056

### Commerce {#commerce-2}

* La sortie Json de la campagne ne contient pas la racine du contexte du servlet. NPR-23733 : correctif pour CQ-4243827

### Communities {#communities-7}

* La recherche sur Communities échoue pour quelques mots. NPR-23256 : correctif pour CQ-4240717
* Impossible d’attribuer des groupes pour le rôle des gestionnaires de communautés. NPR-23317 : correctif pour CQ-4241233 : CQ-4221399
* Problèmes de création de ressource avec des noms de ressources similaires. NPR-23319 : correctif pour CQ-4240700
* (ContextPath) La ventilation de la fonctionnalité de messagerie échoue pour les configurations Jetty et rencontre une erreur lors de la recherche de membres du groupe dans la liste des membres du groupe de communautés. NPR-23336 : correctif pour CQ-4241519, CQ-4242080
* Le chargement d’une image vers un forum Communities n’apparaît pas dans Adobe Storage Resource Provider (ASRP). NPR-23397 : correctif pour CQ-4242497
* Les idées supprimées apparaissent comme des liens actifs dans les activités. NPR-23406
* imsmanifest.xml ne peut pas être chargé si AEM s’exécute avec la racine contextuelle. NPR-23483 : correctif pour CQ-4242193
* Vulnérabilités de sécurité dans une ancienne version de Handlebars. NPR-23518 : correctif pour CQ-4243055
* Le service Tunnel ne fonctionne pas. NPR-23543 : correctif pour CQ-4242217
* Problèmes avec les composants de Communities lorsqu’ils sont accessibles via le Dispatcher et que Sling Dynamic Include y est activé. NPR-23586 : correctif pour CQ-4242360, CQ-4241522
* Lors de la recherche d’un terme de recherche qui génère de nombreux résultats par le biais de la recherche, puis de la saisie d’un nouveau terme, la pagination n’est pas réinitialisée. NPR-23739 : correctif pour CQ-4222593
* Problèmes lors de la recherche sur le composant Forum. NPR-23838 : correctif pour CQ-4243770
* (Marquage de la modération dans Communities) L’autorisation en bloc des messages marqués ne fonctionne pas. NPR-23845 : correctif pour CQ-4243962
* Le texte du bouton Trier n’affiche pas la valeur sélectionnée par défaut malgré la sélection de l’ordre de tri par défaut. NPR-23881 : correctif pour CQ-4243375
* Les notifications par web et par email ne sont pas déclenchées en raison d’un échec d’envoi du message aux groupes. NPR-23934 : correctif pour CQ-4242880
* Aucun détail sur les raisons et les utilisateurs et utilisatrices des indicateurs n’est affiché à l’aide de la configuration DSRP. NPR-23973 : correctif pour CQ-4243205
* Les motifs de marquage des personnes non marquées restent visibles. NPR-23974 : correctif pour CQ-4243822
* Le fait de joindre deux fois deux fichiers portant le même nom à une publication de formulaire génère une erreur de serveur. NPR-24166 : correctif pour CQ-4244367
* Impossible de stocker les pièces jointes avec des types MIME comportant plus de 15 caractères à l’aide de Database Storage Resource Developer (DSRP). NPR-24174
* Lorsqu’une image qui enfreint les critères de chargement est glissée et déposée dans le texte de la publication, une erreur du serveur est générée et un message d’erreur générique s’affiche. NPR-24243
* Correctifs de plusieurs problèmes côté serveur d’AEM Communities. NPR-23971 : correctif pour CQ-4243144, CQ-4242145, CQ-4243365, CQ-4244098
* Correctifs de plusieurs problèmes d’Adobe Social. NPR-24242 : correctif pour CQ-4245054, CQ-4245120, CQ-4245296

### Campagne {#campaign}

* La sortie Json de la campagne ne contient pas la racine du contexte du servlet. NPR-23733 : correctif pour CQ-4243827

### MSM {#msm}

* Lors du déploiement de la page, la Live Copy n’affiche pas les propriétés temporelles d’activation/désactivation héritées du principal. NPR-23873 : correctif pour CQ-4243431
* L’opération Live Copy n’ignore pas les nœuds enfants des composants supprimés. NPR-23058 : correctif pour CQ-4211662

### Déchargement {#offloading}

* Demande de mécanisme de nettoyage des ressources des instances de traitement, après un traitement ou régulièrement. NPR-23638 : correctif pour Granite-21337

## Formulaires {#forms-8}

### Package de modules complémentaires Forms {#forms-add-on-package-8}

#### Formulaires adaptatifs {#adaptive-forms-1}

* Déplacement de `ReCaptchaConfigService` vers le package interne. Correctif pour CQ-4217459
* Un champ numérique ne respecte pas la valeur minimale. NPR-23967 : correctif pour CQ-4244830
* Prise en charge de la fonctionnalité de partage multiple dans l’intégration des formulaires adaptatifs avec Adobe Sign. NPR-23383

#### Intégration du serveur principal {#backend-integration}

* (FDM)(WebService) Prise en charge du concept d’extensions de WSDL dans l’analyseur WSDL. NPR-23640
* Pour inclure SDLInvokerParams dans le SDK client du module complémentaire Forms. NPR-23157

### Programme d’installation de Forms JEE {#forms-jee-installer-7}

#### Process Management {#process-management}

* Impossible d’ouvrir l’espace de travail après l’application du nouveau fichier axis.jar. NPR-23316
* LiveCycle vulnérable à XSS sur PMAdmin. NPR-23267
* Après la mise à niveau vers AEM Forms 6.1, l’espace HTML se bloque lors de l’accès à la liste des tâches pour des utilisateurs spécifiques. NPR-23943

#### Base {#core}

* Forms JEE prend en charge l’authentification mutuelle PKCS#11. NPR-21372

#### Service PDFG {#pdfg-service-2}

* Le service de capture de papier se bloque pendant le traitement simultané des fichiers TIFF (taille d’environ 50 Ko). NPR-23556

#### Concepteur Forms {#forms-designer}

* Output du serveur AEM Forms - Description alternative manquante pour les annotations. NPR-22207
* Ajout de la prise en charge de PDF/UA aux formulaires XML générés via Designer et le Service Output. NPR-23132

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
* Mise à jour des lots de modèles Sling pour inclure le correctif de jeu de caractères.
* Publication asynchrone sur Brand Portal pour tous les types de ressources.
* Mise à jour de coralui-component-richtexteditor.git de 0.1.15 à 0.1.16.
* Correctifs de la fonctionnalité d’affichage/masquage des composants déroulants.
* Activation de l’inversion des images pour le composant d’image principal.
* Mise à jour des bundles HTTP Felix pour activer les attributs de session.

* Suppression de cache=true sur les modèles Sling en raison de problèmes de consommation de mémoire.

### Ressources {#assets-9}

* Lors de la modification du titre ou de l’image miniature dans les paramètres du dossier de ressources, le groupe d’origine et les autorisations du dossier sont remplacés. NPR-22171 : correctif pour CQ-4216080
* L’interface d’utilisation renvoie la fausse erreur « Échec de la publication sur Brand Portal. », alors que la tâche est ajoutée à la file d’attente de réplication et que les ressources sont publiées sur le Brand Portal. NPR-22179 : correctif pour CQ-4205273
* (IU tactile) Emplacement de chargement par défaut des ressources en mode Colonnes. NPR-22465 : correctif pour CQ-4237057
* AEM renvoie une erreur StackOverflow lors de la tentative de copie d’un schéma de ressources de `/conf/global` vers `/conf/mytenant`. NPR-22489 : correctif pour CQ-4235875
* La décompression d’une archive ZIP échoue en raison de l’espace à la fin du nom du dossier. NPR-22522 : correctif pour CQ-4238036
* Le tri à l’aide de la colonne Titre de la ressource ne fonctionne pas pour les résultats de recherche. NPR-22908 : correctif pour CQ-4239076
* La vidéo YouTube est balisée avec le chemin d’accès complet au lieu du nom de balise lui-même. NPR-22976 : correctif pour CQ-4238669
* La réorganisation des dossiers situés sous un dossier réorganisable n’est pas conservée. NPR-23125 : correctif pour CQ-4231761
* HTTP 504 : erreur de délai d’expiration de la passerelle lors de la tentative de partage de collections à l’aide du lien de partage. NPR-21928 : correctif pour CQ-4234507
* Les métadonnées des mots-clés PDF ne sont pas correctement extraites et modifiées lorsqu’un fichier PDF comporte plusieurs mots-clés. Pour résoudre ce problème, la propriété des métadonnées du champ Objet a été supprimée pour les ressources PDF. Vous pouvez toutefois modifier le schéma de métadonnées pour ajouter un champ de texte à plusieurs valeurs pour le champ Objet. NPR-21972 : correctif pour 4215741****
* Les ressources incorrectes sont supprimées si le dossier sélectionné est modifié entre l’affichage des deux fenêtres contextuelles. NPR-21980 : correctif pour CQ-4233675
* (DAM) Plusieurs vulnérabilités cross-site scripting (XSS) lors d’un ajout à l’assistant de collection. NPR-22432 : correctif pour CQ-4327086
* Le téléchargement des ressources échoue lors de l’utilisation de la gestion des droits numériques dans Assets dans Safari. Les personnes ne peuvent pas télécharger de ressources comportant une clause de non-responsabilité et des noms de fichier longs. NPR-22747 : correctif pour CQ-4236460 et CQ-4235274
* Définissez le partage public comme option par défaut lors de la publication de ressources dans Brand Portal. NPR-21931 : correctif pour CQ-4218816

### Sites {#sites-9}

* Le nouvel élément de la boîte de réception Workflow affiche le chemin de page au lieu du titre de la page. NPR-21634 : correctif pour CQ-4230672
* Lorsqu’ils sont modifiés, les composants de structure modifiables perdent les noms de classe CSS nécessaires pour la grille réactive. NPR-21741 : correctif pour CQ-4232374
* (IU tactile) Plusieurs vulnérabilités aux attaques cross-site scripting (XSS) pour les composants HTL. NPR-21899 : correctif pour CQ-4232511
* Impossible de modifier le type de ressource d’image de supports variés du fragment de contenu. NPR-21907 : correctif pour CQ-4233401
* Le mode plein écran du RTE pour la boîte de dialogue de l’IU tactile masque les plug-ins RTE. NPR-22034 : correctif pour CQ-4235457
* (IU tactile) L’éditeur de texte enrichi supprime tous les attributs autres que id de la balise &lt;a>. NPR-22044 : correctif pour CQ-4234133
* Plusieurs parsys empilés en raison de requêtes longues (plus de 6) ralentissent AEM. NPR-22134 : correctif pour CQ-4233904
* Impossible de modifier les autorisations sur les nœuds dont le nom contient deux points. NPR-22136 : correctif pour CQ-4236221
* (IU classique) La sortie de l’éditeur de texte enrichi HTML ajoute « list-position-style: inside; » comme titre de style intégré à la balise &lt;ul>. NPR-22145 : correctif pour CRTE-114
* TreeNode utilise l’attribut name lorsque le texte est vide. NPR-22146 : Correctif pour CQ-4234724 / CQ-4236300
* Problèmes de flux RSS, port -1 à AEM 6.3. NPR-22176 : correctif pour CQ-4233339
* (IU classique) Le raccourci de collage de texte (Ctrl+V) ne fonctionne pas pour le composant Texte (texte enrichi) prêt à l’emploi. NPR-22224 : correctif pour CQ-4236224
* Le filtrage d’un champ de balise ne fonctionne pas comme prévu lors de la saisie de texte. NPR-22236 : correctif pour CQ-4236655
* (Éditeur de page) Lors du collage de données textuelles dans le composant Zone cliquable, le composant Texte est également collé. NPR-22264 : correctif pour CQ-4236230
* Le champ obligatoire FileUpload de la boîte de dialogue entraîne des problèmes lors de l’envoi de la boîte de dialogue. NPR-22464 : correctif pour CQ-4222192
* Le déplacement sans autorisations de réplication lance une requête de workflow d’activation si la page déplacée ou ses référents ne peuvent pas être activés. NPR-22467 : correctif pour CQ-4211765
* Problèmes de performances lors du chargement d’une page avec des audiences importantes (2000+). NPR-22478 : correctif pour CQ-4209567
* Problèmes de persistance lorsque les boutiques ContextHub remplacent le calque de persistance par défaut lors de l’initialisation. NPR-22479 : correctif pour CQ-4218399
* Un lancement avec plusieurs pages ne publie pas les sous-pages sur les serveurs de publication si l’option « Inclure les sous-pages » n’est pas activée dans la première racine du contenu. NPR-22482 : correctif pour CQ-4237818
* (IU tactile) La suppression des lancements via la console d’interface d’utilisation classique rend toutes les pages non modifiables. NPR-22491 : correctif pour CQ-4225074
* Problèmes liés au composant Image en présence d’un espace supplémentaire dans la boîte de dialogue. NPR-22528 : correctif pour CQ-4238183
* Lors de l’ouverture du composant à l’aide du mode intégré, les plug-ins chargés précédemment ne sont pas visibles une seconde fois. NPR-22591 : correctif pour CQ-4236850
* La suppression d’un lancement dans un lancement imbriqué entraîne l’abandon des sous-lancements. NPR-22621 : correctif pour CQ-4202639
* (Sidekick de l’IU classique) L’onglet Workflow est désactivé lorsque la page est en phase de verrouillage du processus. NPR-22722 : correctif pour CQ-4237557
* Après avoir retourné une image ajoutée au composant image d’une page, les modifications ne sont pas enregistrées et l’image d’origine est affichée sur la page. La prise en charge du rendu a été ajoutée au composant image de base via [https://github.com/adobe/aem-core-wcm-components/pull/141](https://github.com/adobe/aem-core-wcm-components/pull/141). NPR-22801 : correctif pour CQ-4221539
* Lorsque l’utilisateur ou l’utilisatrice tente de supprimer l’ancre existante à partir du menu d’ancrage, la fenêtre du composant Éditeur de texte enrichi se ferme et les modifications ne sont pas enregistrées. NPR-22802 : correctif pour CQ-4238167
* Le filtre OmniSearch n’affiche pas toutes les actions dans la console Sites. NPR-22804 : correctif pour CQ-4239007
* Problème avec l’opération Copier/Coller dans l’IU tactile avec le presse-papiers du système d’exploitation et le presse-papiers AEM interne. NPR-22807 : correctif pour CQ-4220383
* Incohérence dans la mise en surbrillance de l’extrait renvoyée par la recherche Lucene. NPR-22879 : correctif pour CQ-4238513
* L’activation d’une page avec les instances de publication désactivées fait passer le statut en vert au lieu du jaune. NPR-22927 : correctif pour CQ-4236310
* (StyleSystem) Un saut s’applique à la position de l’écran lors de la sélection du style dans la fenêtre pop-up. NPR-23183 : correctif pour CQ-4238867
* (Gérer la publication) Le passage au mois suivant du calendrier nécessite plusieurs clics. NPR-23508 : correctif pour CQ-4242732

### Plateforme {#platform-2}

* Le servlet d’export Sling n’exporte pas correctement les caractères japonais. NPR-22153 : correctif pour CQ-4228920
* Blocage du planificateur au démarrage. NPR-22440 : correctif pour Sling-7004
* Impossible de synchroniser des groupes entre deux instances de publication. NPR-21943 : correctif pour Granite-19564
* Problèmes de performances avec la session partagée ou le résolveur de ressources org.apache.sling.i18n. NPR-23390 : correctif pour Sling-7543

### Intégration {#integration-5}

* Résolveur de ressources non fermé dans com.day.cq.analytics.sitecatalyst. NPR-22323 : correctif pour CQ-4236515
* TargetContentImpl ralentit AEM pendant les requêtes longues. NPR-22361 : correctif pour CQ-4236907
* Le moteur Target (mbox.js, at.js) n’utilise pas d’URL réécrites. Il utilise des URL contenant des deux-points qui peuvent échouer avec certains déploiements. NPR-22366 : correctif pour CQ-4237854
* Lors de la fourniture d’un fichier personnalisé at.js ou mbox.js, le script inclus est écrit sur la page en tant que texte au lieu de balises HTML. NPR-22441 : correctif pour CQ-4203691
* En mode Ciblage, les créauteurs et créautrices peuvent modifier un composant hérité du plan directeur sans annuler l’héritage. NPR-22751 : correctif pour CQ-4237907
* PersonalizationDataSource renvoie une exception NullPointer en raison d’une absence du nœud `jcr:content`. NPR-22850 : correctif pour CQ-4222122
* Le ciblage AEM échoue lors de l’utilisation d’une langue autre que l’anglais. NPR-22917 : correctif pour CQ-4218213
* Il manque des ressources connexes pour publier une page avec du contenu ciblé. NPR-23064 : correctif pour CQ-4227119
* Les utilisateurs et les utilisatrices ne peuvent pas voir les valeurs de paramètres statiques de test dans l’appel mBox qui s’affiche lors d’un test avec AT.js comme bibliothèque cliente dans la configuration cloud. NPR-21930 : correctif pour CQ-4234520

### Composants WCM-Foundation {#wcm-foundation-components-1}

* iParsys crée un décalage de position après avoir décoché la case Annuler/Désactiver l’héritage. NPR-21905 : correctif pour CQ-4230951
* La fonctionnalité Afficher/Masquer du composant déroulant de formulaire ne fonctionne pas comme prévu. NPR-22327 : correctif pour CQ-4222853
* Le composant CAPTCHA est désormais obsolète pour une meilleure sécurité. Si vous utilisez le composant CAPTCHA, le message « Le composant Captcha est obsolète et ne doit pas être utilisé » s’affiche après l’installation de la version 6.3.2.1 ou ultérieure. Le composant AEM peut être personnalisé de manière à inclure reCAPTCHA pour une meilleure sécurité. NPR-22151 : correctif pour CQ-4220052

### WCM - Éditeur de page {#wcm-page-editor}

* Cross-site scripting (XSS) reflété lors de l’utilisation d’un sélecteur non valide. Correctif pour CQ-4270397

### Traduction {#translation-4}

* Étude des problèmes liés à la fonctionnalité Aperçu. NPR-22114 : correctif pour CQ-4223753

### Interface utilisateur {#user-interface-2}

* Problèmes avec le sélecteur de mois du calendrier Coral lorsque la période « min » et « max » est définie. NPR-22716 : correctif pour CUI-7187
* (Interface d’utilisation classique) Le composant affiche les valeurs par défaut même si le service de modèle de données de formulaire associé est défini sur un champ vide. NPR-22272 : correctif pour GRANITE-19744

### Granite {#granite-2}

* Problèmes de stabilité affectant l’instance de publication AEM de partage de ressources, provoqués par des fuites de mémoire. NPR-22205, NPR-23178 : correctif pour Sling-5668, Sling-7292 et Sling-7470
* L’ID de service instable pour les noms d’attributs de session ne doit pas être utilisé. NPR-22821 : correctif pour Granite-21059
* Lorsqu’une session gérée par le tableau blanc http est invalidée, la session du conteneur est également invalidée si celle-ci ne comporte aucun autre attribut de session. NPR-23059 : correctif pour FELIX-5819
* LogbackManager peut ne pas disposer de certaines configurations OSGi au moment du démarrage. NPR-23060 : correctif pour Granite-19791

### Commerce {#commerce-3}

* Activez la création de workflow dans le menu Fragments d’expérience. NPR-22347 : correctif pour CQ-4221661
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
* Activation de l’identifiant PDF/UA dans l’arborescence d’accessibilité de Forms Designer.
* Activation de l’authentification de certificat pour les utilisateurs de Workbench.
* Ajout de la prise en charge de la création de fichiers PDF conformes à la norme PDF/A-2a ou PDF/A-3a.

### Package de modules complémentaires Forms {#forms-add-on-package-9}

#### IU d’administration Forms {#forms-admin-ui}

* Le mot de passe est visible en texte brut lors de l’inspection du champ de mot de passe pour les pages de configuration des connecteurs ECM. NPR-22508 : correctif pour CQ-4236065

#### Service Forms {#forms-service}

* Lorsque SSL est activé, les événements Envoyer et Abandon ne fonctionnent pas avec les analyses de formulaire. NPR-22637 ; correctif pour CQ-4237973

#### Gestion des utilisateurs {#user-management}

* Impossible de synchroniser LDAP en raison d’une version cglib-nodep incorrecte. NPR-22493 : correctif pour CQ-4234099

#### Formulaires adaptatifs {#adaptive-forms-2}

* Les fonctions personnalisées de l’éditeur de règles ajoutent une valeur supplémentaire après l’appel de fonction. Par conséquent, la validation échoue même si la fonction personnalisée renvoie true. NPR-22481 : correctif pour CQ-4235499
* Quel que soit le modèle de date sélectionné, le composant sélecteur de date ne suit pas le modèle lors de l’affichage des messages de validation minimum et maximum. NPR-22444 : correctif pour CQ-4236269
* Le format de date envoyé dans la requête d’envoi doit correspondre au modèle fourni dans le composant de sélecteur de date. NPR-22384
* Le nombre maximal de caractères spécifié pour un champ de texte de formulaire adaptatif n’est pas honoré sur les appareils Samsung sous Android™ 6.0. NPR-22363, NPR-22364 : correctif pour CQ-4235205
* (Microsoft® Edge) (IE11) Le composant Champ de texte de formulaire adaptatif avec champ multiligne affiche la valeur par défaut `Null` au lieu d’être vide. NPR-22284 : correctif pour CQ-69107
* Le codage d’entrée SOAP UTF-8 dans les formulaires adaptatifs renvoie des erreurs avec une page déformée. NPR-20105 : correctif pour CQ-4222669
* Le composant Conteneur AEM Forms n’est pas disponible pour modification une fois qu’un formulaire incorrect est configuré dans la page AEM Sites. Correctif pour CQ-4237456
* Les tests de développement échouent lors de leur exécution sur les serveurs JEE. Correctif pour CQ-4222082
* Échec des tests AF sur les serveurs JEE en raison de problèmes de minification dans le framework Calvin. Correctif pour CQ-4217220

#### Forms Manager {#forms-manager}

* (Firefox) Impossible de mettre à jour les propriétés de schéma XML des formulaires adaptatifs, car les options du document d’enregistrement (DOR) ne sont pas présélectionnées dans la page des propriétés. NPR-22298 : correctif pour CQ-4237402
* Les formulaires qui sont modifiés après la publication de la page ne sont pas republiés. NPR-23013 : correctif pour CQ-4236566

#### Intégration du serveur principal {#backend-integration-1}

* L’authentification de base OOTB pour les services SOAP ne fonctionne pas pour l’authentification de base dans l’intégration FDM. NPR-23238 : correctif pour CQ-4241308

#### Correspondence Management {#correspondence-management}

* Les fichiers XDP prêts à l’emploi, lorsqu’ils sont utilisés dans la lettre et prévisualisés, affichent le contenu chevauché avec le pied de page. Correctif pour CQ-4212414

#### Incohérence affectant le service assembleur {#assembler-service}

* Incohérence entre les rapports Acrobat DC et AEM concernant l’erreur de vérification de la conformité PDF/A-1b. NPR-22051, NPR-22050 : correctif pour CQ-4226128, CQ-4227671

### Programme d’installation de Forms JEE {#forms-jee-installer-8}

#### Workbench {#workbench}

* Activation de l’authentification de certificat pour les utilisateurs de Workbench. NPR-20644 : correctif pour CQ-4214486
* Le téléchargement du journal du serveur à l’aide de Workbench fonctionne uniquement pour un serveur, tandis que pour l’autre serveur, il ne fonctionne pas. NPR-21079 : correctif pour CQ-4229842

#### Process Management {#process-management-1}

* (Espace de travail HTML) Problèmes de taille d’écran avec les barres de défilement. NPR-23288
* (Espace de travail HTML) Les points de départ du workflow ne sont pas triés dans un ordre alphanumérique. NPR-22841 : correctif pour CQ-4238944
* (Espace de travail HTML) Les données de préparation sont déclenchées à la fermeture du formulaire dans l’espace de travail. NPR-21127 : correctif pour CQ-4224574
* (Espace de travail HTML) Lors de l’appel d’un workflow qui nécessite des remarques avec des descriptions longues, le bouton de développement des remarques ne fonctionne pas. Correctif pour CQ-4241488

#### Base {#core-1}

* Erreur rencontrée au démarrage lors du démarrage du planificateur. NPR-22990
* Les navigateurs sont empêchés de stocker les informations d’identification saisies dans les formulaires HTML. NPR-21762 : correctif pour CQ-4206543
* Les problèmes signalés dans l’analyse de code statique de base doivent être résolus. Correctif pour CQ-104446

#### Service PDFG {#pdfg-service-3}

* PDF Generator ne parvient pas à produire des documents PDF avec les niveaux de signets spécifiés. NPR-22921, NPR-22285 : correctif pour CQ-4230562
* Ajout de la prise en charge de la création de fichiers PDF conformes à la norme PDF/A-2a ou PDF/A-3a. NPR-23021 : correctif pour CQ-4214172

#### Concepteur Forms {#forms-designer-1}

* L’identifiant PDF/UA est manquant lors de l’enregistrement au format PDF depuis le Concepteur. NPR-23137
* Objets de chemin, par exemple : les bordures, les soulignements et les hyperliens ne sont pas balisés lors de l’enregistrement en tant que PDF depuis Designer. NPR-23136
* L’objet Image ne comporte pas de cadre de sélection lorsqu’il est enregistré en tant que PDF depuis Designer. NPR-23134
* Les hyperliens intégrés définis dans Designer ne sont pas balisés et ne comportent pas de texte secondaire lorsqu’ils sont enregistrés en tant que PDF à partir de Designer. NPR-23133
* L’ouverture du package de données XML avec le Concepteur d’AEM Forms 6.3 supprime le formatage XHTML de la source XML. NPR-21178 : correctif pour LC-3917046

#### Installation de LCM {#install-lcm}

* Mise à jour de Jsafe Jars vers Cryptoj 6.1.3.1 dans le programme d’installation et LCM. NPR-21370

#### Service Signatures {#signatures-service}

* Exception rencontrée lors de la signature numérique d’un document PDF via HSM. NPR-21154 : correctif pour CQ-4226978

### Lots OSGI et packages de contenu dans 6.3.2.1 {#osgi-bundles-and-content-packages-included-in-5}

Liste des lots OSGi inclus dans AEM 6.3.2.1

[Obtenir le fichier](assets/do-not-localize/bundle-list_002_.txt)

Liste des packages de contenu inclus dans AEM 6.3.2.1

[Obtenir le fichier](assets/do-not-localize/content_package_comparison.txt)

Le pack de correctifs cumulés 6.3.1.2 consiste en une mise à jour importante comprenant plusieurs correctifs internes et clients apportés depuis la disponibilité générale du Service Pack 1 (6.3.1.0) AEM 6.3 d’octobre 2017.

Les principaux aspects du pack de correctifs cumulatif AEM sont les suivants :

* Modification de l’interface utilisateur pour prendre en charge la mise en œuvre de la fonctionnalité CUG dans l’AEM Assets.
* Correction de problèmes de l’interface utilisateur sur la page de vérification des licences pour une meilleure expérience.
* Activation de la prise en charge des tâches du workflow OSGi dans l’application AEM Forms.

### Ressources {#assets-10}

* Modification de l’interface utilisateur pour prendre en charge la mise en œuvre de la fonctionnalité CUG dans l’AEM Assets. NPR-19485
* Le chargement d’une ressource en tant que nœud enfant direct de soi-même à l’aide de l’IU tactile provoque un problème. La ressource est chargée en tant qu’enfant direct de la ressource précédemment sélectionnée. NPR-19736
* Le prédicat de plage de dates et le prédicat de plage ne fonctionnent pas lors du chargement d’une recherche/collecte dynamique enregistrée. NPR-19844 : correctif pour CQ-4220808
* L’instance d’AEM est ralentie lorsque plusieurs ressources (plus de 4) sont publiées sur Brand Portal. NPR-20009 : correctif pour CQ-4213426
* Impossible de télécharger des ressources avec des espaces à partir de la page de vérification de licence. NPR-20067 : correctif pour CQ-4216557
* Problèmes de traitement lors du chargement de fichiers PSB avec plusieurs calques alpha. NPR-20250 : correctif pour CQ-4220869
* Les utilisateurs et les utilisatrices ne peuvent pas télécharger des fichiers qui possèdent des noms de fichier longs et des clauses de non-responsabilité définies. NPR-20254
* ProductAssetsUploader laisse les fichiers temporaires du cache Java™ dans le dossier TEMP Java™. NPR-20256 : correctif pour CQ-4221801
* Remplacement du code de comparaison de version par du code propriétaire Adobe en raison de problèmes de licence. NPR-20272 : correctif pour CQ-4223758
* Les métadonnées d’une propriété de chaîne, documentNumber, s’affichent sous la forme d’une date, alors qu’il doit s’agir d’un nombre. NPR-20291 : correctif pour CQ-4223991
* L’extraction de texte est bloquée pour un fichier PDF corrompu. NPR-20416 : correctif pour CTG-4150375
* Les fichiers compressés contenant des ressources dont les noms sont incompatibles avec UTF-8 ne sont pas correctement téléchargés. NPR-20420 : correctif pour CQ-4219961
* Un nombre trop élevé de caractères dans Omnisearch peut provoquer le crash du serveur AEM. NPR-20434 : correctif pour CQ-4223602
* Le défaut de métadonnées de l’API de ressources DAM rompt les API xmp-write-back. NPR-20607 : correctif pour CQ-4220455
* Problèmes de performances lors de l’ajout d’utilisateurs et d’utilisatrices à des collections. NPR-20699 : correctif pour CQ-4225733
* La publication sur le Brand Portal à partir d’AEM ne devrait pas être autorisée pour les ensembles de médias dynamiques. NPR-20320 : correctif pour CQ-4221147
* Les vidéos contenant des espaces et accents ne produit aucune vidéo pour la page Rendus. NPR-19961 : correctif pour CQ-4221014
* Résolution de plusieurs problèmes de gestion des dossiers avec les API d’Assets. NPR-20569
* AEM Dynamic Media Classic (anciennement Scene7) ne parvient pas à synchroniser les ressources à partir du serveur AEM. Ce problème se produit lorsque le chemin d’accès de destination dans la configuration du Cloud Service pointe vers un sous-dossier de chemin d’accès racine. CQ-4228265
* Un groupe d’e-mails d’Apache Commons `{org.apache.commons/commons-email/1.5}` a été ajouté en remplacement de `{com.day.commons.osgi.wrapper/com.day.commons.osgi.wrapper.commons-email/1.2.0-0002}`.

### Sites {#sites-10}

* Problèmes d’autorisation d’administration : impossible de supprimer les membres du groupe d’utilisateurs fermé des propriétés de la page. NPR-20631
* Le nom du workflow saisi doit être disponible dans la zone Notification lors de la publication de la page via Gérer la publication. NPR-20046 : correctif pour CQ-4221586
* L’application de texte stylisé sur deux lignes dans l’éditeur de texte enrichi, puis leur fusion au sein d’un même paragraphe supprime les étendues auxquelles un style est appliqué. NPR-20110 : correctif pour CQ-4223051
* Les modifications apportées aux propriétés des champs dans plusieurs onglets de la boîte de dialogue de modification des propriétés ne sont parfois pas enregistrées. NPR-20286
* Balise inattendue à la fin du contenu collé dans le fragment de contenu. NPR-20413 : correctif pour CQ-4224014
* Mise en œuvre d’un mécanisme dans Adobe Campaign pour récupérer la politique d’une ressource de contenu à partir d’une ressource de ciblage externe. NPR-20667
* Le plug-in de texte enrichi ne fonctionne pas pour les barres intégrées et en plein écran dans l’IU tactile multichamp. NPR-20973

### Campagne {#campaign-1}

* Les espaces réservés ne sont pas visibles dans une page qui contient plusieurs composants Parsys. NPR-20436 : correctif pour CQ-4215000

### Commerce {#commerce-4}

* Les fragments d’expérience ne s’affichent pas correctement dans Internet Explorer 11. NPR-20161 : correctif pour CQ-4223319
* Dans les workflows de commerce, une image vierge est automatiquement insérée lors de la création d’une variante basée sur un produit principal avec plusieurs images. NPR-20068 : correctif pour CQ-4222048
* Le filtrage par balises sur les pages de collection dans la console de produits ne fonctionne pas. NPR-20292 : correctif pour CQ-4224023

### Communities {#communities-8}

* Résultats de recherche incohérents avec le composant Résultats de recherche. NPR-20070 : correctif pour CQ-4220913
* Les notifications par e-mail ne sont pas déclenchées pour les activités liées au modérateur sur les composants publiés. NPR-20122
* La pagination vierge sans résultat s’affiche pour les utilisateurs et utilisatrices anonymes de la communauté. NPR-20136 : correctif pour CQ-4220738
* Configurez le déclencheur d’alerte lorsqu’un contenu créé par l’utilisateur ou l’utilisatrice est détecté comme spam ou lorsqu’un utilisateur ou une utilisatrice publie sur un site prémodéré. NPR-20274 : correctif pour CQ-96850
* Correction de plusieurs problèmes dans les pages des sites AEM Communities, dont des redirections incorrectes et des problèmes d’actualisation des pages. NPR-20344
* CommunityUserOperationExtension s’exécute dans une exception de conversion de classe. NPR-20532 : correctif pour CQ-4224385
* Après la création d’un site Communities, les utilisateurs et les utilisatrices ne peuvent pas l’ouvrir à partir du plan du site, car le chemin d’accès de contexte n’est pas ajouté en préfixe à l’URL. NPR-20730

### Intégration {#integration-6}

* Migration des informations d’identification Analytics existantes vers l’authentification WSSE. NPR-19962 : correctif pour CQ-4218071
* La réactivation du segment après toute modification échoue et renvoie une erreur. NPR-20054 : correctif pour CQ-4218401
* La configuration du service cloud Search&amp;Promote ignore la méthode de récupération de formulaire, ce qui la rend inutilisable sur l’instance de création. NPR-20447 : correctif pour CQ-4206076
* Une définition de filtre ambiguë dans le package de contenu entraîne un remplacement des chemins d’accès lorsque la fonction Search&amp;Promote est installée. NPR-20808

### Mobile On-Demand {#mobile-on-demand}

* Les propriétés des métadonnées des ressources de type TXT s’affichent dans différents éditeurs de métadonnées chaque fois que leurs propriétés sont affichées. NPR-20239

### Plateforme {#platform-3}

* Résolution d’une exception de résolveur de ressources non fermé. NPR-19749 : correctif pour Granite - 19143
* Demande d’affichage des cartes personnalisées au côté des contrôles d’intégrité par défaut dans le tableau de bord des opérations. NPR-20145
* Le calque d’annotation de l’éditeur de page ne fonctionne pas correctement dans Internet Explorer 11. NPR-20222 : correctif pour CQ-4222818
* Fuite de session lors de la définition de l’agent utilisateur en tant qu’administrateur dans l’agent de réplication. NPR-20578
* RequestAttributes est désormais désactivé pour les autres instructions data-sly-resource. NPR-20639 : correctif pour 4226206
* Correction de problèmes liés aux requêtes Curl Head pour les ressources prêtes à l’emploi dans AEM. NPR-20781 : correctif pour CQ-4221520

### Projets {#projects-1}

* Le chargement de différents projets à partir de la console Projets prend plus de temps. NPR-20314
* L’installation d’AEM 6.3.0.1 supprime le KeyStore de l’utilisateur ou de l’utilisatrice `dam-update-service`. NPR-20018
* Dans certains déploiements personnalisés, les utilisateurs et les utilisatrices qui tentent de sélectionner une personne désignée dans le module addTask prennent plus de temps pour remplir la liste dans le sélecteur d’utilisateur ou d’utilisatrice. NPR-20283 : correctif pour CQ-4224193

### Interface utilisateur {#user-interface-3}

* Le champ Couleur est défini sur « Toujours requis » malgré les attributs de la boîte de dialogue. NPR-19702
* La barre de défilement ne s’affiche pas pour le composant à champs multiples en plein écran dans Internet Explorer 11. NPR-20261 : correctif pour CQ-4219782
* Les requêtes antérieures ne sont pas abandonnées si des requêtes consécutives sont déclenchées, ce qui entraîne des résultats incorrects. NPR-20398 : correctif pour GRANITE-19306

### Workflow {#workflow-1}

* Les utilisateurs et utilisatrices ne sont pas informés des tâches de workflow qu’ils reçoivent dans leur boîte de réception. NPR-20213 : correctif pour CQ-4221639
* Le sélecteur d’utilisateurs et d’utilisatrices de Granite prêt à l’emploi ne charge aucune personne lorsque l’on clique sur la liste déroulante de la boîte de dialogue à l’étape Participant ou participante du modèle de workflow. NPR-20236

## Formulaires {#forms-10}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms {#forms-add-on-package-10}

#### Formulaires adaptatifs {#adaptive-forms-3}

* La prise en charge de l’expression d’agrégation pour les panneaux répétés est absente. NPR-20861
* La liste déroulante affiche la dernière valeur stockée, même si le service de modèle de données de formulaire associé ne renvoie pas de valeur. NPR-20710
* Impossible de modifier les règles existantes avec des contraintes booléennes dans l’éditeur de règles. NPR-21128

#### Portail des formulaires {#form-portal}

* Le profil HTML s’affiche pour un formulaire adaptatif, même si son type de ressource n’est pas XDP. NPR-20079

#### Intégration du serveur principal {#backend-integration-2}

* Impossible de définir la valeur du composant de commutateur entre true/false. NPR-21111

#### Workflow OSGI {#osgi-workflow}

* La gestion des envois de workflow répertorie uniquement dix applications. CQ-4230193

#### Formulaires HTML5 {#html-forms-3}

* Le nom d’un objet de formulaire XDP, comme un sous-formulaire, s’affiche sous forme d’info-bulle lorsqu’il n’est pas défini dans les configurations d’accessibilité. NPR-20523

### Programme d’installation de Forms JEE {#forms-jee-installer-9}

#### Process Management {#process-management-2}

* Le point de départ FormSetPrefillApp ne préremplit pas les champs du jeu de formulaires dans l’application AEM Forms. NPR-20950

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

Les principaux aspects du pack de correctifs cumulatif AEM sont les suivants :

* Activation de l’action Publier sur le Brand Portal pour le formulaire de schéma de métadonnées par défaut.
* Changement du comportement lors de l’affichage des titres sur une carte d’image pour les images ayant une propriété dc:title définie sur `String [] (multifield)`.
* Remplacement du rendu côté serveur du temps avec le composant foundation-time.
* Activation de la publication de balises à partir d’AEM dans Brand Portal depuis la console tagadmin/balisage.
* L’API JSON publiée consomme des fragments de contenu.
* Le référentiel intégré (Apache Jackrabbit Oak) a été mis à niveau vers la version 1.6.5.

### Ressources {#assets-11}

* Le mappage de deux champs avec la même propriété et différents types de champs de propriété génère une erreur interne. NPR-19462 : correctif pour CQ-4216828
* dc: title et dc: description ne basculent pas vers une valeur multichamp dans CRXDE Lite. NPR-19570 : HF pour CQ-4209086
* La visionneuse dynamique charge un rendu vidéo de qualité inférieure pour tester l’expérience de lecture vidéo en mode création. NPR-19004
* Le rendu dynamique ne peut pas être téléchargé pour les ressources qui incluent des espaces dans leur nom. NPR-19433 : correctif pour CQ-4211738
* Impossible de charger la liste complète des pages/ressources en mode Colonnes avec Chrome. NPR-19566 : correctif pour CQ-4214248
* L’option Publier sur le Brand Portal n’est pas disponible lors de la sélection d’un schéma, d’une facette de recherche ou d’un paramètre prédéfini. NPR-19550
* Lors de la sélection d’une ressource dans la vue Colonnes et d’un clic sur Modifier, la page renvoie une erreur. NPR-20301 : correctif pour CQ-4224052
* L’affichage Expiration des ressources est désactivé en cas de chevauchement de fuseaux horaires positifs et négatifs. NPR-20329 : correctif pour CQ-4219333

### Campagne {#campaign-2}

* Les composants du curseur de campagne n’apparaissent pas lorsque l’expérience par défaut est sélectionnée pour une campagne. NPR-19213

### Intégration {#integration-7}

* Le fichier at.js personnalisé n’est pas publié lorsqu’il est utilisé avec l’utilisateur anonyme. NPR-19542 : correctif pour CQ-4219592
* Le champ Moteur de ciblage dans l’assistant de configuration est défini sur ContextHub (AEM) au lieu d’Adobe Target. NPR-19320 : correctif pour CQ-4218465
* La section Audience est corrompue lors de la création de l’expérience. NPR-19110
* La boîte de dialogue de ciblage ne s’affiche pas en mode ciblage lorsqu’un module cible est modifié et enregistré plusieurs fois. NPR-19144 : correctif pour CQ-4216708
* Les propriétés d’accès des articles sont mal configurées dans Adobe Digital Publishing Solution dans l’IU classique. NPR-19367
* Comportement incorrect du pliage automatique lors de la personnalisation des offres via Campaign si les utilisateurs ont accès à plusieurs zones. NPR-19290 : correctif pour CQ-4218029

### Sites {#sites-11}

* Les valeurs de liste déroulante de champs multicomposites ne sont pas à nouveau renseignées en raison de la modification du code dans Sidekick.js après la mise à niveau de l’instance vers AEM 6.1SP2-CFP3. NPR-19450 : correctif pour CQ-4194771
* WCMMode.EDIT ne fonctionne pas pour les composants ciblés en mode création. NPR-19387
* L’API JSON publiée consomme des fragments de contenu. NPR-19500
* Les fonctionnalités gras, italique et souligné ne fonctionnent pas pour les champs de l’éditeur de texte enrichi dans la boîte de dialogue de création. NPR-19670 : NPR-19718 : correctif pour CQ-4219088

### Mobile On-Demand {#mobile-on-demand-1}

* Problèmes de rendu avec la console d’article AEM qui provoquent des ralentissements en cas d’utilisation d’images en taille réelle. NPR-19088

### Traduction {#translation-5}

* Impossible de générer l’aperçu pour les projets de traduction. NPR-19289

### Sécurité {#security}

* Erreur de connexion SSL. Impossible d’établir une connexion sécurisée au serveur. NPR-19628

### Communities {#communities-9}

* L’e-mail est déclenché lors de la publication de contenu avec des sites prémodérés. NPR-20008
* Les notifications par e-mail ne fonctionnent pas pour les activités liées au modérateur sur les composants publiés. NPR-19767 : HF pour CQ-4218060

### Plateforme {#platform-4}

* Problèmes de stabilité liés au déploiement du serveur de production AEM. NPR-19707
* Les bibliothèques de balises personnalisées qui font référence aux balises implémentées en tant que script sont introuvables après la mise à niveau vers AEM 6.3. NPR-19087
* Correctifs de bugs HTL pour AEM 6.3.1. NPR-19161
* Le champ de texte enrichi n’est pas modifiable dans les composants multi-champs. NPR-19604 : correctif pour Granite-16755
* Le service Modèle d’email Adobe ajoute des balises aux modèles utilisateur personnalisés. NPR-19190
* Correctif pour Oak 1.6.5. NPR-19148

### Commerce {#commerce-5}

* Le bouton Démarrer le workflow, après avoir sélectionné l’éditeur d’une variante XF, n’a aucun effet. NPR-19642 : correctif pour CQ-4207796

### Projets {#projects-2}

* Les éditeurs et les éditrices de projet ne peuvent pas copier/coller de ressources dans le dossier de ressources du projet. NPR-19619 : correctif pour CQ-4215321

### Gestion de contenu web {#web-content-management}

* Sur l’écran Déploiement, les cases à cocher correspondant aux pages Live Copy ne peuvent pas être cochées ni décochées. NPR-19518
* La modification en bloc des propriétés de page n’est pas correctement utilisable, car tous les onglets et champs sont actuellement disponibles pour la modification en bloc. NPR-19451
* Les propriétés prêtes à l’emploi et les propriétés d’alignement des images n’apparaissent pas lors de la modification d’une image dans l’interface d’utilisation classique. NPR-19488 : HF pour CQ-4217914

### Interface utilisateur {#user-interface-4}

* Lors de l’utilisation du navigateur Google Chrome, les utilisateurs et les utilisatrices ne peuvent pas charger la liste complète des pages/ressources dans la vue Colonnes de l’interface d’utilisation tactile. NPR-19566 : correctif pour CQ-4214248

### Brand Portal {#brand-portal-1}

* Impossible de publier des ressources à partir d’AEM avec des commentaires et des annotations. NPR-19590 : correctif pour CQ-4218386
* Activation de la publication de balises à partir d’AEM dans Brand Portal depuis la console tagadmin/tagging. NPR-20271 : correctif pour CQ-4223948
* Correction du champ « activé » sur l’interface utilisateur de configuration du service cloud Brand Portal. Correctif pour CQ-4211101
* La réplication du formulaire de recherche échoue. Correctif pour CQ-4220080

## Formulaires {#forms-11}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms {#forms-add-on-package-11}

#### Formulaires adaptatifs {#adaptive-forms-4}

* Le workflow Envoyer vers JEE ne renvoie pas le paramètre de sortie du côté JEE vers AEM et renvoie l’erreur « Ignoré car la valeur n’est pas primitive ». NPR-20265
* Les formulaires adaptatifs n’autorisent pas les pièces jointes au format PDF dans Safari. NPR-19625
* RestoreGuideState remplace l’objet map customcontextproperty. CQ-4222877
* Lors de la configuration de Google `reCaptcha` à l’aide de Cloud Service, dans les environnements nécessitant la configuration d’org.apache.http.proxyconfigurator pour les connexions externes, les appels POST ne semblent pas passer par PROXY. NPR-20454
* Les formulaires adaptatifs basés sur des schémas XSD envoient des valeurs XML erronées pour les champs numériques des installations dont les paramètres régionaux comportent un séparateur décimal autre qu’un point (.), ce qui entraîne des erreurs. NPR-20444
* Les paramètres de proxy définis pour la « Configuration du proxy des composants HTTP Apache » ne sont pas respectés lors d’une requête HTTP vers un serveur tiers. Problèmes de délai d’expiration de connexion à l’aide des appels HTTP GET ou POST. NPR-20457, NPR-20456, NPR-20455, NPR-20451

#### Intégration de données Forms {#forms-data-integration}

* Les caractères UTF-8 en sortie du service SOAP ne sont pas correctement copiés dans les champs des formulaires adaptatifs pour les langues autres que l’anglais. NPR-20238 : NPR-20103

#### Correspondence Management {#correspondence-management-1}

* Le contenu copié et collé à partir du fichier Word perd sa couleur et sa police dans l’éditeur de texte. NPR-19521

#### Services d’assemblage {#assembler-services}

* Incohérence entre les résultats d’Acrobat et d’AEM lors de la vérification de la conformité d’un document au format PDFA-1b. NPR-19280

#### Workflow {#workflow-2}

* Étape de signature de workflow pour permettre aux appels HTTP de se connecter via le proxy. NPR-20529

#### Formulaires HTML5 {#html-forms-4}

* Ajout de la prise en charge de l’événement preSubmit. NPR-20604

### Programme d’installation de Forms JEE {#forms-jee-installer-10}

#### Process Management {#process-management-3}

* Les onglets Pièces jointes, Notes et Détails d’un workflow ne fonctionnent pas dans l’espace de travail lorsque le formulaire est agrandi/réduit et enregistré en tant que brouillon ou transféré. NPR-20243
* Le champ de texte multiligne (TextArea) ne conserve pas de nouveaux caractères de ligne ni de sauts de ligne après l’envoi de données dans l’espace de travail HTML. NPR-20085

#### Rapports de workflow {#process-reporting}

* La création de rapports sur les processus ne récupère pas correctement les données en raison d’une exception NullPointer. NPR-19759

>[!NOTE]
>
>Installation du package intégré LiveCycle répertorié dans l’article [Versions d’AEM Forms](aem-forms-releases.md) pour résoudre le problème.

#### Services standard {#standard-services}

* docConvertor ne prend pas en charge l’aplatissement des transparences dans les PDF et ne parvient pas à produire un fichier PDF/A. NPR-16228 : Correctif pour CQ-4214488

#### Base {#core-2}

* Lorsque l’on arrête le serveur AEM Forms exécuté en configuration de grappe sur l’application JBoss®, le serveur d’applications est déconnecté de la base de données. Cela peut entraîner des problèmes de corruption des données. NPR-19724

### Feature Packs inclus {#feature-packs-included-1}

* Le champ de schéma de métadonnées de liste déroulante ne peut pas être rendu obligatoire, car la validation obligatoire des champs est manquante pour les ressources. NPR-17882 : FP pour CQ-4208373

### Lots OSGI et packages de contenu dans 6.3.1.1 {#osgi-bundles-and-content-packages-included-in-7}

Liste des lots OSGi inclus dans AEM CFP 6.3.1.1

[Obtenir le fichier](assets/do-not-localize/bundle-list.txt)

Liste des packages de contenu inclus dans AEM CFP 6.3.1.1

[Obtenir le fichier](assets/do-not-localize/content-package-list.txt)

Le pack de correctifs cumulés 6.3.0.2 consiste en une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale d’AEM 6.3 en avril 2017.

Les principaux aspects du pack de correctifs cumulatif AEM sont les suivants :

* Vérifiabilité du contrôle d’accès des utilisateurs et utilisatrices
* Inclut la version 1.6.2 du référentiel intégré (Apache Jackrabbit Oak)
* Résolution des problèmes de résolveur de ressources non fermé
* Configuration simplifiée pour les services de contenu intelligent
* Résolution des problèmes de validation des fragments de contenu
* Modifiabilité améliorée des schémas de métadonnées sur les appareils hybrides
* Résolution des problèmes de synchronisation au niveau du composant dans les Live Copies
* Amélioration de l’utilisation des pages riches en contenu dans la vue Colonnes
* Amélioration de la conformité à la convention de nommage des pages pour les pages avec des titres longs
* Amélioration de l’expérience de personnalisation de campagne dans l’interface utilisateur tactile
* Correction de divers problèmes de superposition de projet

### Plateforme {#platform-5}

* Correctif pour Oak 1.6.2. NPR-16993
* Lors de l’ouverture de l’omni-recherche à l’aide d’un filtre, le chemin n’est plus défini. NPR-17398 : correctif pour CQ-4204870
* Exigence de vérifiabilité des modifications des autorisations des utilisateurs et utilisatrices dans AEM. NPR-17061
* Connexions persistantes aux services cloud DM provoquant des exceptions « Trop de fichiers ouverts ». CQ-4211407

### Ressources {#assets-12}

* Problèmes d’utilisation liés à la configuration des services de contenu intelligent à l’aide de différentes options. NPR-18200 : correctif pour CQ-4201557
* Fuite de ressources dans les flux binaires vers le magasin de données S3. NPR-18041 : correctif pour CQ-4209506
* Une erreur se produit lorsqu’un fichier texte codé en ASCII/UTF-8 est chargé vers AEM Assets et la création des miniatures échoue. NPR-18006 : CFP pour CQ-4209345
* Le schéma de métadonnées par défaut entraîne l’échec de la validation du fragment de contenu. NPR-17769 : correctif pour CQ-4211111
* Résolveur de ressources non fermé dans com.day.cq.dam.s7dam.common.analytics.impl.SiteCatalystReportRunner. NPR-17598 : CFP pour CQ-4209018
* Demande de création de plusieurs agents de réplication pour la publication de ressources dans Brand Portal. NPR-17189
* La tâche de révision des ressources sous le dossier de langue japonaise ne fonctionne pas. CQ-4204782
* Une exception de pointeur nul se produit lorsqu’une ressource est déplacée depuis sa page de propriétés. CQ-4204251
* AEM ne parvient pas à suivre les références ultérieures à une ressource dans la page de propriétés s’il est lié plusieurs fois à un document InDesign. CQ-4204186
* Problèmes liés à l’ajout de nouveaux onglets dans le formulaire de schéma de métadonnées lorsqu’il est modifié dans Chrome sur des appareils hybrides. CQ-4201810
* Lorsque des ressources en double sont chargées, l’option (supprimer/conserver) est appliquée à tous les fichiers, même s’ils ne sont pas sélectionnés dans la boîte de dialogue des doublons détectés. CQ-4201673
* Une exception NullPointerException se produit en cas de déplacement d’un dossier de ressources contenant plus de 150 références entrantes. CQ-4200981
* Dans le cas d’un dossier de ressources téléchargé, si un conflit survient lors de l’extraction du contenu du fichier ZIP, l’option par défaut s’affiche sous la forme Créer une version au lieu de Conserver les deux. CQ-97800
* Les utilisateurs et utilisatrices disposant d’autorisations en lecture seule sur l’application ne peuvent pas prévisualiser le contenu à partir de la gestion de contenu d’AEM Mobile. NPR-17486 : CFP pour CQ-4209690
* Le bouton Créer un catalogue ne fonctionne pas dans la vue Colonnes de la console Catalogue. CQ-4209952

### Sites {#sites-12}

* Problèmes liés à l’incorporation de composants image/vidéo via l’attribut data-sly-resource. NPR-18182 : CFP pour CQ-4212100
* Les composants localisés modifiés ne retrouvent pas leur forme d’origine lorsque l’héritage est réappliqué à une LiveCopy. NPR-18172 : correctif pour CQ-4211379
* Problèmes liés à la navigation dans une page riche en contenu dans la vue Colonnes de l’interface utilisateur tactile. NPR-17799 : correctif pour CQ-4199611
* Résolveur de ressources non fermé dans `com.day.cq.wcm.core.impl.VersionManagerImpl`. NPR-17789 : CFP pour CQ-4211152
* Le nom de page n’est pas généré selon la convention pour les titres de pages longs. NPR-17633 : correctif pour CQ-4209056
* Problèmes de création de page dans l’IU tactile d’AEM 6.3 déployée sur JBoss® EAP 6.4. NPR-17589 : correctif de CQ-4210137
* Le fournisseur de statut de workflow entraîne le verrouillage de l’instance en présence de groupes imbriqués. NPR-17556 : requête CFP pour CQ-4202056
* Résolveur de ressources non fermé dans les objets suivants :

   * `com.day.cq.wcm.undo.impl.BinaryValueManagerImpl` NPR-17497 : CFP pour CQ-4208673
   * `com.day.cq.commons.impl.ThumbnailProviderManagerImpl` NPR-17495 : CFP pour CQ-4208668
   * `com.day.cq.wcm.workflow.impl.WcmWorkflowServiceImpl` NPR-17494 : CFP pour CQ-4208669
   * `com.day.crx.delite.impl.AuthHttpContext` NPR-17493 : CFP pour GRANITE-17404

### Intégrations {#integrations-1}

* Résolution des erreurs du composant de recherche AEM qui peuvent se produire lorsque le client HTTP AEM Day 3.1 OSGI est configuré avec un proxy qui requiert une authentification Digest. NPR 18128 : correctif pour NPR-18029
* Problèmes de personnalisation des campagnes et des expériences associées via l’interface d’utilisation classique. NPR-18127 : correctif pour CQ-4211559
* Lors de la définition d’une marque/zone sur une page racine d’un site, l’héritage, une fois annulé, ne peut pas être restauré pour les zones des sous-pages. NPR-17753 : correctif pour CQ-4210139

### Workflow {#workflow-3}

* Dans un workflow non transitoire, les modifications apportées aux métadonnées et à l’historique du processus avant une étape de processus externe ne sont pas conservées. NPR-17848 : correctif pour GRANITE-17757
* Les valeurs des champs de la boîte de dialogue de workflow ne sont pas conservées dans le nœud de l’élément de travail. NPR-17734 : correctif pour CQ-4210369
* Une erreur de date non analysable se produit lors de la modification d’une tâche à partir de la boîte de réception. CQ-4208749

### Projets {#projects-3}

* Correction de divers problèmes de superposition de projet. NPR-17733
* La restructuration des capsules dans le module Projets le rend moins configurable. CQ-4209859
* Le chemin d’accès aux ressources change pour les sites localisés respectifs lorsque des pages sont ajoutées à la tâche de traduction. CQ-4206007

### Sécurité {#security-1}

* Problèmes de chargement d’images d’avatar pour les utilisateurs LDAP. NPR-16561
* Demande d’utilisation d’une version mise à niveau du servlet org.apache.sling.servlets.post (2.3.22) dans l’API Apache Sling pour prévenir une vulnérabilité XSS. NPR-18963

## Formulaires {#forms-12}

Les correctifs d’AEM Forms sont fournis par le biais du package complémentaire Forms et d’autres programmes d’installation de patchs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

Les principaux aspects pour AEM Forms sont les suivants :

* Correctifs dans les modules de texte de Correspondence Management, les aperçus de lettres et le lancement par programmation de la création de l’interface utilisateur de Correspondance Manager.
* Correctifs pour la validation PDF/A-1b, la conversion de fichiers d’image volumineux en PDF et de documents PDF en japonais dans PDF Generator.
* Correctifs d’utilisation pour Correspondence Management, Document Security et Forms Workflow.
* Ajout de la prise en charge de la capture des événements de contrôle pour le champ de signature tactile.

### Package de modules complémentaires Forms {#forms-add-on-package-12}

**Gestion des correspondances**

* Lors de la modification d’un fragment Correspondence Management, l’éditeur de texte affiche les conditions intégrées à côté du texte traité. CQ-4211930
* Lors de la création d’une lettre Correspondence Management, la description de la lettre n’est pas enregistrée. NPR-18089
* Une marge supplémentaire au-dessus et au-dessous d’une liste à puces est visible dans l’éditeur de texte, mais pas dans le rendu HTML ou PDF. NPR-18126
* Lorsque l’envoi par HTML a utilisé la méthode POST, le lancement de la création de l’UI Correspondence échoue. NPR-18202
* Lorsqu’un module de texte est enregistré et qu’une expression du module de texte ne contient aucune balise d’expression d’ouverture ou de fermeture, aucun message d’erreur ne s’affiche. Le module de texte affiche un message d’erreur et n’effectue pas le rendu dans la lettre. NPR-18535
* Lorsque vous ajoutez du nouveau contenu ou appuyez sur la touche `Enter`, une balise div est ajoutée au module de texte. NPR-18240

**Assembler**

* Lors de la validation d’un document PDF pour conformité à la norme PDF/A-1b, AEM Forms renvoie une erreur de validation : PDFA_CONTENT_003_DEVICE_DEPENDENT_COLOR_USED. Le document PDF ne renvoie pas l’erreur lorsqu’il est validé avec Adobe Preflight et des logiciels tiers. NPR-18011
* Lors de la validation de documents PDF pour la conformité à la norme PDF/A-1b, AEM Forms renvoie une erreur de validation : le champ de formulaire a plusieurs apparences. Les documents PDF sont conformes à la norme PDF/A-1b. NPR-18013

**Dossier de contrôle**

* Lors de la sélection pour traiter les fichiers à l’aide d’un workflow et de la création d’un dossier de contrôle, la liste déroulante de sélection de modèle de workflow apparaît tronquée. NPR-17566

**Formulaires HTML5**

* AEM Forms ne capture pas les événements de contrôle pour le champ de signature Griffonnage. NPR-15286

**Forms Manager**

* L’interface utilisateur AEM Forms répertorie toutes les ressources dans le premier ordre le plus ancien. Les utilisateurs ne sont pas en mesure de réorganiser les ressources dans le premier ordre le plus récent. NPR-18450

**Référence API Java™**

Ajout de JavaDocs pour la classe com.adobe.livecycle.content. NPR-18468

### Programme d’installation de Forms JEE {#forms-jee-installer-11}

**PDF Generator**

* Le service PDF Generator ne parvient pas à convertir des images de plus de 100 Mo en documents PDF. CQ-4208628
* Lorsque vous utilisez le service PDF Generator avec une reconnaissance optique des caractères en japonais, un PDF inversé est généré. NPR-17602

**Process Management**

* La variable TaskContext n’est pas renseignée pour les workflow AEM Forms. NPR-18199

**Document Security**

* Microsoft® Excel et Microsoft® PowerPoint prennent beaucoup plus de temps pour ouvrir les documents protégés par AEM Document Security Extension for Microsoft® Office. CQ-4212358
* Lorsqu’une nouvelle politique est créée et qu’une politique portant le même nom existe déjà, une erreur de serveur interne se produit. NPR-18247

## Feature Packs inclus {#feature-packs-included-2}

* Exigence de vérifiabilité des modifications des autorisations des utilisateurs et utilisatrices dans AEM. NPR-17061

Le pack de correctifs cumulatif 6.3.0.1 pour AEM consiste en une mise à jour importante comprenant plusieurs correctifs internes et clients rassemblés depuis la publication générale d’AEM 6.3 en avril 2017. Les principaux aspects du pack de correctifs cumulatif AEM sont les suivants :

* Améliorations dans les domaines suivants :

   * Composants Fragments de contenu, Sites, Éditeur de texte enrichi, Éditeur de règles et Éditeur de modèles
   * Révision sociale et connexion sociale à Facebook
   * Configuration et démarrage des tâches de traduction
   * Temps de réponse pour l’accès aux notifications dans les communautés de réseaux sociaux
   * Affichage des tâches de révision dans le référentiel DAM

* Fournit une option de validation dans le gestionnaire de packages pour la détection des conflits entre superposition et CFP

## Instructions de téléchargement du package CFP via la distribution logicielle {#download-instructions-for-cfp-via-package-share}

Vous pouvez télécharger le package CFP directement à partir de la [distribution de logiciels](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) ou effectuer les étapes suivantes :

1. Ouvrez la [Distribution de logiciels](https://experience.adobe.com/downloads). Vous avez besoin d’un Adobe ID pour vous connecter à la Distribution de logiciels.
1. Appuyez sur **[!UICONTROL Adobe Experience Manager]** disponible dans le menu d’en-tête.
1. Appuyez sur le nom du package, sélectionnez **[!UICONTROL Accepter les termes du contrat de licence utilisateur final]**, puis appuyez sur **[!UICONTROL Télécharger]**.

## Instructions d’installation {#installation-instructions}

Cette section décrit les exigences et les étapes à suivre pour installer le CFP.

### Avant l’installation {#before-you-install}

>[!NOTE]
>
>Les packs de fonctionnalités facultatifs fournis par Adobe dépendent de la version et du pack de correctifs cumulatif. Si vous avez installé un pack de fonctionnalités, contactez [l’équipe d’assistance clientèle d’AEM](https://experienceleague.adobe.com/fr?support-solution=General#support) pour valider sa compatibilité avec le pack de correctifs cumulatifs pour AEM 6.3.

>[!NOTE]
>
>Adobe recommande de valider chaque nouveau package d’installation avant d’essayer d’installer le package. La pré-validation analyse et signale les erreurs détectées avant l’installation et avertit les utilisateurs et utilisatrices de ces erreurs de manière proactive.
>
>Vous pouvez accéder à la documentation de l’option Valider à l’adresse [https://experienceleague.adobe.com/en/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions)

* AEM 6.3.3.0 est une condition préalable à l’installation du CFP. Consultez la [documentation de mise à niveau](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions) pour obtenir des instructions détaillées sur la mise à niveau d’une installation AEM vers AEM 6.3.
* Pour un déploiement en cluster utilisant RDBMK ou MongoDB, le package CFP peut être installé sur n’importe quelle instance de création qui utilise le gestionnaire de packages.
* Avant d’installer le pack de correctifs cumulatif, veillez à prendre un instantané ou à sauvegarder votre instance AEM.
* La désinstallation du CFP n’est pas prise en charge.

### Ajout de nouveaux enregistreurs {#adding-new-loggers}

Pour configurer la journalisation au niveau du débogage et récupérer un journal d’activités lors de l’installation de SP/CFP, procédez comme suit :

* Vous pouvez ajouter un nouvel enregistreur à l’emplacement par défaut [http://localhost:4502/system/console/slinglog](http://localhost:4502/system/console/slinglog) avec les propriétés suivantes :

   * Niveau de consignation : débogage
   * Additif : false
   * Fichier journal : logs/activity.log
   * Enregistreur : org.apache.jackrabbit.vault.packaging.impl.ActivityLog

Le fichier activity.log est créé dans le dossier crx -quickstart /logs.

### Installer le pack de correctifs cumulatifs par le biais de la distribution de logiciels {#install-the-cumulative-fix-pack-via-package-share}

1. Cliquez sur le lien [Distribution de logiciels](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/cumulativefixpack/aem-6.4.8-cfp-2.0.zip) pour télécharger le package.

1. Ouvrez [Package Manager](http://localhost:4502/crx/packmgr/index.jsp) et cliquez sur **[!UICONTROL Télécharger le package]** pour télécharger le package.

1. Sélectionnez le nom du package et cliquez sur **[!UICONTROL Installer]**.

### Installation automatique {#automatic-installation}

Le CFP peut être automatiquement installé dans une instance en cours d’exécution de la manière suivante :

* Placez le package dans `../crx-quickstart/install` pendant l’exécution du serveur. Le package est automatiquement installé.
* Utilisez l’[API HTTP du gestionnaire de modules](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions) (veillez à utiliser `cmd=install&recursive=true`) afin d’installer le package imbriqué.

### Validation de l’installation {#validate-installation}

1. La page Informations sur le produit (`/system/console/ productinfo`) doit maintenant afficher la chaîne de version mise à jour « Adobe Experience Manager, Version 6.3.3.8. » sous Produits installés.
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
1. Téléchargez le package complémentaire Forms correspondant répertorié dans les [versions d’AEM Forms](aem-forms-releases.md) pour votre système d’exploitation.
1. Installez le package complémentaire Forms comme décrit dans la section [Installation des packages complémentaires AEM Forms](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions).

#### Installation du package de lots AEM Forms JEE {#install-aem-forms-jee-bundles-package}

Les correctifs dans AEM Forms JEE sont fournis dans un programme d’installation distinct. Pour plus d’informations sur l’installation d’un CFP pour AEM Forms sur JEE, reportez-vous à [Installation d’un CFP pour AEM Forms JEE](install-cfp-aem-forms-jee.md).

#### Programme d’installation du Concepteur Forms {#designer-installer}

1. Pour installer la mise à jour, exécutez le fichier Designer 6.2.0_&lt;Langue>_Cumulative_QF.msp.
1. Sur l’écran de bienvenue, cliquez sur **Mettre à jour**. L’installation démarre.
1. Cliquez sur **Terminer** à la fin de l’installation.

## Paramètres de configuration pour AEM Forms JEE (JBoss® EAP) {#configuration-settings-for-aem-forms-jee-jboss-eap}

>[!NOTE]
>
>Si vous installez la version 6.3.3.0 ou une version ultérieure, procédez comme suit pour configurer les paramètres du serveur d’applications JBoss®. Si vous installez la version 6.3.3.0 sur un serveur AEM Forms qui s’exécute sur des serveurs d’applications Oracle WebLogic ou IBM® WebSphere, aucune configuration supplémentaire n’est nécessaire. Pour plus d’informations, reportez-vous aux [Notes de mise à jour d’AEM 6.3.3.0](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions).

## Mises à jour de configuration pour l’intégration de Search&amp;Promote {#configuration-updates-for-search-promote-integration}

Avec le pack de correctifs cumulés AEM 6.3.0.2 et les versions ultérieures, la configuration OSGi utilisée pour l’intégration de Search&amp;Promote est la **configuration du proxy des composants HTTP Apache**. La configuration du proxy du client HTTP 3.1 Day Commons n’est plus utilisée.

## Problèmes connus {#known-issues}

* Les erreurs et avertissements suivants peuvent survenir lors de l’installation du CFP d’AEM 6.3.3.x et peuvent être ignorés en toute sécurité :

   * &#42;WARN&#42; [OsgiInstallerImpl] org.apache.jackrabbit.vault.packaging.impl.InstallHookProcessorImpl Hook /META-INF/vault/hooks/cloudservices-wfchangeinstallhook-0.0.2-jar-with-dependencies.jar a généré une exception d’exécution.
   * &#42;ERROR&#42; [OsgiInstallerImpl] com.adobe.cq.social.cq-social-jcr-provider [com.adobe.cq.social.provider.jcr.impl.SpiSocialJcrResourceProviderImpl(2174)] Temporisation en attente de modification d’enregistrement pour terminer la désinscription. CQ-4209974.
   * Service org.apache.sling.engine.impl.SlingRequestProcessorImpl ServletResolver manquant, impossible de traiter les demandes, envoi de l’état 503
   * com.day.cq.wcm.mobile.core.MobileUtil isMobileResource : impossible de vérifier la ressource [/bin/receive], gestionnaire de pages indisponible
   * org.apache.sling.servlets.resolver.internal.SlingServletResolver : l’appel du gestionnaire d’erreurs entraînait une erreur.
   * org.apache.sling.servlets.resolver.internal.SlingServletResolver Erreur d’origine null
   * org.apache.sling.engine.impl.DefaultErrorHandler Échec du gestionnaire d’erreurs : java.io.IOException
   * &#42;ERROR&#42; [FelixDispatchQueue] com.day.cq.dam.cq-dam-core FrameworkEvent ERROR (org.osgi.framework.ServiceException : la fabrique de services a renvoyé une valeur « null ». (Composant : com.day.cq.dam.handler.standard.ps.PostScriptHandler))

**Brand Portal**

* À compter de la version 6.3.1.2, le bouton Publier sur Brand Portal pour les collections intelligentes est supprimé.

**Interface utilisateur**

>[!NOTE]
>
>Si l’un de ces deux problèmes vous concerne, contactez l’[Assistance clientèle AEM](https://experienceleague.adobe.com/fr?support-solution=General#support).

* Une utilisation intensive du processeur est observée en raison du nombre élevé de requêtes dans la fonctionnalité de recherche d’administration. NPR-24229
* PathField n’est pas sélectionné dans pathBrowser lors de la réouverture du composant. NPR-24177

## Paramètres de configuration requis pour NPR-27692 {#configuration-settings-required-for-npr}

>[!NOTE]
>
>Ce paramètre de configuration s’applique à CFP 6.3.3.2 et versions ultérieures. Il vous demande de mettre à jour les propriétés de délégation de démarrage dans le fichier de propriétés `sling`.

Pour mettre à jour manuellement les modifications apportées à adobe- LiveCycle® cq -author.ear/ cq .war, procédez comme suit :

* Arrêtez le serveur AEM.
* Accédez à adobe-livecycle-cq-author.ear/cq.war.
* Ouvrez adobe-livecycle-cq-author.ear/cq.war/WEB-INF/web.xml pour le modifier :

   * mettez à jour la valeur **sling.bootdelegation.ibm** param-name avec :

   * `com.ibm.xml.&#42;,com.ibm.crypto.pkcs11impl.provider,com.ibm.pkcs11,com.ibm.pkcs11.nat`

   * Après la modification ci-dessus, init-param doit se présenter comme suit :

     &lt;init-param>
&lt;param-name>sling.bootdelegation.ibm&lt;/param-name> &lt;param-value>com.ibm.xml.&#42;,com.ibm.crypto.pkcs11impl.provider,com.ibm.pkcs11,com.ibm.pkcs11.nat&lt;/param-value>
&lt;/init-param>

* Désinstallez le fichier EAR précédent du serveur d’applications WebSphere® et installez le fichier EAR mis à jour en suivant les étapes décrites à la section 10.2 du document [https://helpx.adobe.com/fr/pdf/aem-forms/6-3/install-single-server-websphere.pdf](https://helpx.adobe.com/fr/pdf/aem-forms/6-3/install-single-server-websphere.pdf).
* Enregistrez le fichier et redémarrez le serveur. [https://helpx.adobe.com/fr/pdf/aem-forms/6-3/install-single-server-websphere.pdf](https://helpx.adobe.com/fr/pdf/aem-forms/6-3/install-single-server-websphere.pdf)

## Paramètres de configuration requis pour NPR-23208 {#configuration-settings-required-for-npr-1}

>[!NOTE]
>
>Ce paramètre de configuration s’applique aux versions 6.3.2.2 et ultérieures. Il vous demande de mettre à jour manuellement les politiques de listes de contrôle d’accès (ACL) via CRX-DE, car les listes de contrôle d’accès ne sont pas mises à jour via l’installation du CFP en raison de l’élément « merge_preserve » acHandling.

**Documentation pour l’ajout manuel de politiques de liste de contrôle d’accès**

Pour mettre à jour les politiques de liste de contrôle d’accès, ajoutez les contrôles d’accès ci-dessous via CRX-DE :

`1)` À l’emplacement du chemin « /content »
`a)` Principal : reference-adjustment-service
Type : Allow
Privilèges : jcr:read, jcr:modifyProperties
Restrictions : rep:glob=&quot;/&#42;/jcr:content&quot;
`b)` Principal : reference-adjustment-service
Type : Allow
Privilèges : jcr:read, jcr:modifyProperties
Restrictions : rep:glob=&quot;/&#42;/jcr:content/&#42;&quot;

`2)` À l’emplacement du chemin « /content/usergenerated »
`a)` Principal : reference-adjustment-service
Type : Allow
Privilèges : `jcr:write`

`3)` À l’emplacement du chemin « /etc »
`a)` Principal : reference-adjustment-service
Type : Allow
Privilèges : jcr:read, jcr:modifyProperties
Restrictions : rep:glob=&quot;/&#42;/jcr:content&quot;
`b)` Principal : reference-adjustment-service
Type : Allow
Privilèges : jcr:read, jcr:modifyProperties
Restrictions : rep:glob=&quot;/&#42;/jcr:content/&#42;&quot;

## Paramètres de configuration requis pour NPR-19450 {#configuration-settings-required-for-npr-2}

>[!NOTE]
>
>Ce paramètre de configuration s’applique à CFP 6.3.1.1 et versions ultérieures.

**Configurez la propriété CQ.PAGE_PROPERTIES_MAX_RECURSION_LEVEL.**

La propriété contrôle la profondeur maximale de la sous-arborescence du nœud sous le nœud de page ` /jcr:content`, jusqu’à ce que les nœuds présents dans le référentiel soient utilisés pour obtenir les propriétés de la page. Les nœuds situés sous la profondeur spécifiée dans cette propriété sont ignorés.

La valeur par défaut est 1. Remplacez la valeur en recouvrant le fichier constants.js (`/libs/cq/ui/widgets/source/constants.js`), en retirant les balises de commentaire de la propriété `CQ.PAGE_PROPERTIES_MAX_RECURSION_LEVEL`. Ensuite, attribuez-lui la valeur requise (la profondeur maximale du `/jcr:content` de la page, où sont stockées les données des propriétés de la page).

**Si l’utilisateur ou l’utilisatrice doit créer plusieurs variantes de pages afin que le nombre de nœuds sous le nœud `/jcr:content` de la page soit supérieur à 1 000, procédez comme suit pour modifier la configuration :**

* Configurez la propriété JSON Résultats maximum d’Apache Sling.
* Obtenez le servlet à l’aide de `/system/console/ configMgr`.
* Définissez sa valeur sur un nombre supérieur à 1 000 (valeur par défaut actuelle) de sorte que ce nombre soit supérieur au nombre total de nœuds dans la sous-arborescence `/jcr:content` jusqu’à la profondeur configurée comme ci-dessus.

Cela permet au servlet Sling GET de renvoyer tous les nœuds requis.

## Uber Jar {#uber-jar}

Uber Jar pour la version 6.3.3.8 est disponible dans le Référentiel Adobe Maven public.

Pour utiliser Uber Jar dans un projet Maven, consultez l’article [Comment utiliser Uber Jar](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions) et incluez la dépendance suivante dans votre projet POM :

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

| Domaine | Fonctionnalité | Remplacement | Version |
|----|-----|-----|-----|
| Intégration d’Assets et d’Adobe Creative Cloud | [Le partage de dossiers AEM vers Creative Cloud](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions) a été introduit dans AEM 6.2 afin de permettre aux créatifs d’accéder aux ressources depuis AEM. Une nouvelle fonctionnalité publiée dans l’application Creative Cloud, Adobe Asset Link, offre une meilleure expérience d’utilisation. Elle permet également d’accéder plus facilement aux ressources d’AEM directement à partir de Photoshop, InDesign et Illustrator.</br></br> Adobe n’apporte pas d’autres améliorations à la fonctionnalité de partage de dossiers. Bien que cette fonctionnalité soit incluse dans AEM, nous recommandons à la clientèle d’utiliser le remplacement. | Adobe Asset Link ou application de bureau. Pour plus d’informations, consultez l’article [Intégration d’AEM Creative Cloud](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions). | AEM 6.3.3.x |

## Lots OSGi et packages de contenu inclus {#osgi-bundles-and-content-packages-included-1}

Les documents texte suivants répertorient les lots OSGi et les packages de contenu inclus dans le CFP :

* [Liste des lots OSGi inclus dans AEM 6.3.3.8](assets/do-not-localize/list_of_osgi_bundlesincludedin6338.txt)

* [Liste des packages de contenu inclus dans AEM 6.3.3.8](assets/do-not-localize/list_of_content_packageincludedin6338.txt)

>[!MORELIKETHIS]
>
>* [Versions et mises à jour d’AEM](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/aem-releases-updates)
>* [Page des correctifs AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/aem-releases-updates)
>* [Notes de mise à jour d’AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions)
>* [Page de produits AEM ](https://business.adobe.com/fr/products/experience-manager/adobe-experience-manager.html)
>* [Documentation d’AEM 6.3](https://experienceleague.adobe.com/fr/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions)
>* S’abonner aux [mises à jour de produits prioritaires d’Adobe](https://www.adobe.com/subscription/priority-product-update.html)
