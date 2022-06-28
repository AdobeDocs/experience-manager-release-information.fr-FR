---
title: Pack de correctifs cumulés AEM 6.2
description: Notes de mise à jour du pack de correctifs cumulés AEM 6.2.
exl-id: f1c2d4ff-590b-46b5-b2b1-e2b5141f7cc0
source-git-commit: 44bb03aeb23c2c44fa037b020c3b9c8eadfa0fb7
workflow-type: ht
source-wordcount: '19928'
ht-degree: 100%

---

# Notes de mise à jour du pack de correctifs cumulés AEM 6.2{#release-notes-aem-cumulative-fix-pack}

<!-- TBD: Should we keep this article published after AEM 6.2 content is archived via UGP-1894. If an AEM version is EOL should we discard its details RNs but still retain its docs?
-->

## Informations sur la version {#release-information}

| **Produit** | Adobe Experience Manager |
|---|---|
| **Version** | 6.2 |
| **Mise à jour** | Pack de correctifs cumulés 6.2 SP1-CFP20 |
| **Prérequis** | [AEM 6.2 Service Pack 1](https://docs.adobe.com/docs/en/aem/6-2/release-notes/sp1.html) |
| **Disponibilité générale** | 6 juin 2019 |

### Pack de correctifs cumulés {#cumulative-fix-pack}

Adobe a introduit un modèle de diffusion unique pour la publication des correctifs. Au lieu de publier des correctifs ad hoc pour chaque problème, Adobe publie désormais un pack de correctifs cumulés (CFP) tous les mois (sous réserve de contrôles de qualité satisfaisants). Un CFP est un module de contenus agrégés contenant plusieurs correctifs. Les CFP comprennent principalement des correctifs de bugs, mais peuvent également inclure des Feature Packs. Ils présentent les avantages suivants par rapport aux correctifs publiés individuellement :

* Cumulatifs par nature (par exemple, un CFP contient les correctifs apportés par le biais de CFP précédents)
* Meilleure assurance qualité
* Installation simplifiée (l’utilisateur installe un CFP en un seul module sans dépendances, hormis le dernier Service Pack)

Pour plus d’informations sur le CFP et sur d’autres types de versions, consultez le [Véhicule de version de maintenance](https://docs.adobe.com/content/docs/en/aem/6-2/deploy/maintenance-release-vehicle-definitions.html).

## À propos de cette version {#about-the-release}

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP20, dernier pack de correctifs cumulés pour AEM 6.2, est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’[AEM 6.2 SP1](https://helpx.adobe.com/fr/experience-manager/6-2/release-notes/sp1.html).

>[!CAUTION]
>
>Le fait d’installer le CFP sans avoir validé la compatibilité entre les Feature Packs installés peut entraîner une défaillance du système ou la perte de configurations personnalisées, ce qui nécessiterait une restauration à partir de la sauvegarde pour résoudre le problème.

>[!NOTE]
>
>* Un nouveau bundle Sling `discovery-  api` Johnzon 1.0.0 est inclus avec le pack de correctifs cumulés d’AEM 6.2 SP1-CFP10. En outre, un sling-discovery d’utilisateur de service est ajouté avec les privilèges de lecture et d’écriture pour le nœud */var/discovery* dans le référentiel CRX.
>
>* Le groupe d’email d’apache commons **org.apache.commons/commons-email/1.5** a été ajouté en remplacement de **com.day.commons.osgi.wrapper/com.day.commons.osgi.wrapper.commons-email/1.2.0-0002**.
>
>* Adobe recommande de déployer CFP par le biais du dossier d’installation pour les clients qui comptent un grand nombre d’utilisateurs sur une instance AEM.
>


## Problèmes inclus {#issues-included}

Cette section répertorie tous les problèmes et correctifs inclus dans le CFP actuel.

En outre, ce CFP inclut des correctifs fournis dans les [packs de correctifs cumulés](#previous) précédents.

### Intégration {#integration}

* Rétroportage de plusieurs améliorations de la personnalisation du ciblage des campagnes. NPR-29163 : correctif pour CQ-4264126
* com.day.cq.personalization.impl.TeaserResourceEventHandler résulte en une boucle infinie et provoque des mises à jour des nœuds lors de la publication. NPR-28561 : correctif pour CQ-4263096

### DAM - Général {#dam-general}

* Impossible d’afficher/de masquer le bouton de réplication pour les utilisateurs non-administrateurs dans des dossiers DAM spécifiques. NPR-29026 : correctif pour CQ-4265361

### Vulnérabilité {#vulnerability}

* La structure de protection CSRF ne fonctionne pas avec les formulaires AEM Foundation. NPR-28612 : correctif pour GRANITE-22231

### Formulaires {#forms}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package}

>[!NOTE]
>
>Pour les clients AEM Forms, il est impératif d’installer le module complémentaire AEM Forms après l’installation de tout Service Pack, pack de correctifs cumulés ou Feature Pack d’AEM.

>[!NOTE]
>
>Les packages de modules complémentaires AEM Forms permettent d’harmoniser les fonctionnalités des formulaires avec les Service Packs et les packs de correctifs cumulés AEM. Il est donc impératif d’installer le package de module complémentaire AEM Forms après avoir installé un Service Pack, un pack de correctifs cumulés ou un Feature Pack AEM.

#### Formulaires adaptatifs {#adaptive-forms}

* Problèmes d’utilisation avec le composant de griffonnage pour les appareils iOS 12.1. NPR-29082 : correctif pour CQ-4261765

#### Forms - Document Security {#forms-document-security}

* La vérification de toutes les signatures dans un PDF à l’aide de PDF Advanced Electronic Signatures (PAdES) génère InvalidOperationException. NPR-27848 : correctif pour CQ-4244837

#### Forms – Correspondance {#forms-correspondence}

* Lors de la prévisualisation de la lettre au format PDF, le champ de texte placé sur le gabarit de page ne respecte pas la valeur saisie à partir de l’onglet de données ou selon la liaison de données spécifiée. NPR-29239 : correctif pour CQ-4266856.

#### Forms - Communication interactive {#forms-interactive-communication}

* Lorsqu’un caractère apostrophe est ajouté, les champs préremplis de la lettre apparaissent comme caractères ASCII au lieu de l’alphabet classique. NPR-28863 : correctif pour CQ-4262900

### Programme d’installation de Forms JEE {#forms-jee-installer}

* Aucun nouveau correctif AEM Forms dans le programme d’installation de Forms JEE.

## Correctifs et Feature Packs inclus dans les packs de correctifs cumulés précédents {#hotfixes-and-feature-packs-included-in-previous-cumulative-fix-packs}

### Pack de correctifs cumulés 19 {#cumulative-fix-pack-1}

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP19 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’[AEM 6.2 SP1](https://helpx.adobe.com/fr/experience-manager/6-2/release-notes/sp1.html).

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Prise en charge de l’API MS Translator v3.0 pour AEM 6.2
* Ajout d’un message dans le journal après l’installation réussie du package pour tous les SP, CFP et HF.

### Ressources {#assets}

* Impossible de renommer le dossier DAM en l’absence de l’autorisation de modification d’ACL. NPR-27555 : correctif pour CQ-104652
* L’outil d’édition des préréglages d’image ne répond pas dans 6.2.1 CFP 17 et versions ultérieures. NPR-28147 : correctif pour CQ-4261041

### Sites {#sites}

* Le vérificateur de liens ne termine pas la tâche. Il est bloqué avec des liens qui ne répondent pas. NPR-27373 : correctif pour CQ-4256030
* Le fichier de segments ne se charge pas correctement en raison d’un chemin racine supplémentaire qui rompt le chemin du segment. NPR-28014 : correctif pour CQ-4260332

### Intégration {#integration-1}

* L’annulation de l’héritage de LiveCopy ne fonctionne pas correctement sur les conteneurs ciblés. NPR-28129 : correctif pour CQ-4259813
* Les actions cq  :actions ne sont pas prises en compte pour un composant ciblé. NPR-27616 : correctif pour CQ-4257497

* L’affichage d’une icône pour rompre l’héritage n’est pas cohérent. NPR-27671 : correctif pour CQ-4257779

### Felix {#felix}

* Le détail du composant de console Web échoue avec 500 après l’installation du CFP 18 sur l’instance d’AEM 6.2 SP1. NPR-28350 : correctif pour CQ-4261095

### Traduction {#translation}

* Activez la prise en charge du service MS Translator dans AEM 6.3 après la mise à niveau de MS Translator vers l’API v3.0. NPR-28123 : correctif pour CQ-4259096

### IU - Fondation {#ui-foundation}

* Le calendrier des sites OOTB affiche des dates incorrectes. NPR-28392

### Granite {#granite}

* Le dictionnaire n’est pas invalidé pour les lots de ressources avec sling :basename. NPR-27624

### Soutenance {#sustenance}

* Les journaux d’activité du gestionnaire de packages doivent être extraits dans un fichier journal distinct. NPR-27323 : correctif pour Granite-14866
* Expression/formulation/ligne(s) de journal normalisée(s) dans le fichier error.log à afficher une fois l’installation terminée. NPR-27835
* Le plug-in du package Granite sélectionne la dépendance d’une version inférieure d’org.apache.sling.i18n. Correctif pour CQ-4263245
* Le lot com.adobe.cq.com.adobe.cq.ui.commons est supprimé lors de l’installation du dernier CFP après 6.2SP1-CFP15. Correctif pour CQ-4258808

### Formulaires {#forms-1}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-1}

#### Formulaires adaptatifs {#adaptive-forms-1}

* Vulnérabilité aux injections XML avec les formulaires AEM. NPR-27843 : correctif pour CQ-4257315

### Programme d’installation de Forms JEE {#forms-jee-installer-1}

* Aucun nouveau correctif AEM Forms dans le programme d’installation de Forms JEE.

### Lots OSGI et packages de contenu inclus {#osgi-bundles-and-content-packages-included}

Le texte suivant répertorie les lots OSGI et les packages de contenu inclus dans le CFP.

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP19

[Obtenir le fichier](assets/do-not-localize/cfp19_osgi_bundles.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP19

[Obtenir le fichier](assets/do-not-localize/cfp19_content_packages.txt)

### Pack de correctifs cumulés 18 {#cumulative-fix-pack-2}

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP18 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’[AEM 6.2 SP1](https://helpx.adobe.com/fr/experience-manager/6-2/release-notes/sp1.html).

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Prise en charge Ajoutée dans DAM CommandLineProcess pour tuer le processus à long terme.
* Correction d’une fuite de session dans ReplicationEventListener.
* Ajout de la prise en charge de la redirection vers le composant de page principal.

### Ressources {#assets-1}

* Les processus Camera RAW sont bloqués pendant les périodes d’assimilation massive, ce qui finit par bloquer tout traitement du flux de travail. NPR-26990 : correctif pour NPR-23860
* La fonctionnalité de téléchargement exploite AEM Assets par le biais du servlet de téléchargement de ressources, ce qui permet aux utilisateurs anonymes de télécharger toutes les ressources. NPR-27054, correctif pour CQ-4254732
* Les caractères spéciaux apparaissent cassés dans la ligne d’objet des modèles de courrier électronique dans AEM. NPR-26470 : correctif pour CQ-4252368

### Sites {#sites-1}

* En raison d’un comportement incorrect de la classe ConfigPostProcessor, la suspension de l’image parente supprime le type de mixage cq : LiveRelationship à partir de la page enfant. NPR-26745 : correctif pour CQ-4254163
* Ajoutez la prise en charge de la redirection au composant de page principal. NPR-26576 : correctif pour CQ-110529
* Migration du hub de contexte vers jquery 3. NPR-26956 : correctif pour CQ-4255472
* Les champs d’entrée d’ancrage apparaissent hors de la section visible des navigateurs dans la boîte de dialogue jusqu’à ce qu’ils soient agrandis. NPR-26852 : correctif pour CQ-4255019
* L’opération de copier-coller du texte insère le texte indésirable &lt;br> dans le fragment de contenu. NPR-26660 : correctif pour CRTE-151
* L’administrateur de site Classic ne génère pas la liste dans le volet de droite pour certaines pages. NPR-27247 : correctif pour CQ-4251621
* (IU classique) Les tentatives de déplacement/renommage des pages génèrent une erreur, « Une erreur s’est produite lors du déplacement de la page ». NPR-27179 : correctif pour CQ-4235907

### Intégration {#integration-2}

* com.day.cq.personalization.impl.BrandsRetriever parcourt l’arbre entier pour recueillir les marques disponibles. NPR-27060 : correctif pour CQ-4255790

### WCM - Composants Foundation {#wcm-foundation-components}

* Problème de fonctionnalité de recherche avec le composant de liste Foundation. NPR-26817 : correctif pour CQ-4250324

### Plateforme {#platform}

* En raison du caractère spécial de tiret cadratin, l’éditeur ne parvient pas à vider le cache. NPR-27199 : correctif pour CQ-4242790

### Granite {#granite-1}

* Le programme de validation de package ne valide pas les packages inclus dans CFP/SP. NPR-26775 : correctif pour Granite-22825

### Réplication {#replication}

* Fuite de session JCR dans ReplicationListener. NPR-27063 : correctif pour CQ-4232088

### Formulaires {#forms-2}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-2}

* Aucun nouveau correctif AEM Forms dans le module complémentaire de Forms.

### Programme d’installation de Forms JEE {#forms-jee-installer-2}

* Aucun nouveau correctif AEM Forms dans le programme d’installation de Forms JEE.

#### Lots OSGI et packages de contenu inclus {#osgi-bundles-and-content-packages-included-1}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP18

[Obtenir le fichier](assets/do-not-localize/62cfp18updated_bundles.txt)

Liste des packages de contenu inclus dans AEM 6.2 SP1-CFP18

[Obtenir le fichier](assets/do-not-localize/content_package_62sp1_cfp18.txt)

### Pack de correctifs cumulés 17 {#cumulative-fix-pack-3}

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP17 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’[AEM 6.2 SP1](https://helpx.adobe.com/fr/experience-manager/6-2/release-notes/sp1.html).

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Ajout de la prise en charge des URL sans extension dans at-integration.js
* Suppression de l’importateur d’interrogation S7 de la configuration du service cloud S7.
* Modifications apportées à la vue audiences afin de prendre en charge la structure de dossiers pour l’implémentation multiclients.
* Mise à jour de jqueryui clientlib v1.12.1.

### Ressources {#assets-2}

* Le lancement de workflows à partir de l’interface utilisateur Assets nécessite que l’utilisateur dispose d’autorisations d’écriture/suppression/modification. NPR-25688 : correctif pour CQ-4250140
* Les boutons Publier et Annuler la publication restent visibles même pour les utilisateurs sans autorisation de « réplication ». NPR-25094
* (Workflow) Le workflow de balisage intelligent des ressources n’est pas traité via la configuration du proxy AEM. NPR-25915 : correctif pour CQ-4248202
* Supprimez l’importateur d’interrogation S7 de la configuration du service cloud S7. NPR-25239 : correctif pour CQ-95236

### Sites {#sites-2}

* Les workflows démarrés à partir de l’Éditeur -> Informations sur la page contiennent le chemin d’accès au contexte dans la charge utile. NPR-26389 : correctif pour CQ-76804
* (Vérificateur de liens externes) Les liens https non valides sont affichés comme des liens valides. NPR-25541 : correctif pour CQ-4201333
* (IU classique) Lors de la création d’une page autonome sous une Live Copy, la page est créée en tant que Live Copy. NPR-25610 : correctif pour CQ-4249801
* Problèmes liés à la publication de ressources associée au composant Design Importer lorsqu’une page est activée. NPR-25638 : correctif pour CQ-102532
* La barre d’outils de texte enrichi RTE couvre la liste sélectionnée. NPR-25165 : correctif pour CQ-4248948
* Migrez contexthub vers jquery 3. NPR-25059 : correctif pour Granite-19902
* Pour les composants parsys imbriqués, la première conception satisfaisante (avec le chemin le moins imbriqué) est toujours appliquée à partir de plusieurs composants disponibles. Pour plus d’informations, voir [Résolution du chemin de conception](https://helpx.adobe.com/fr/experience-manager/6-3/sites/developing/using/page-templates-static.html). NPR-25250 : correctif pour CQ-4246276

### Intégration {#integration-3}

* Avec l’intégration de la cible prête à l’emploi, le ciblage d’un composant entraîne le rendu de la page entière au lieu d’un composant ciblé vide. NPR-25273 : correctif pour CQ-4248003
* La rupture de l’héritage en mode de ciblage présente encore le composant comme ciblé avec l’héritage non rompu en mode d’édition. NPR-25324 : correctif pour CQ-4248162
* Lorsqu’une personnalisation est définie sur une page et qu’une audience est résolue, l’expérience correspondante apparaît en mode d’édition. NPR-25731 : correctif pour CQ-4249465
* URL de teaser erronée lors de l’utilisation d’AEM avec un chemin de contexte non défini par défaut. NPR-25971 : correctif pour CQ-4250953
* Rendu vide lors de l’utilisation de l’option d’exclusion. NPR-25295 : correctif pour CQ-4246792
* Les expériences supprimées de l’environnement de création ne sont jamais supprimées du site de publication lors de l’activation de la page. NPR-24869 : correctif pour CQ-4247832

### DAM - Client DM {#dam-dm-client}

* (Chrome, Firefox) VideoPlayer ignore les clics de souris sur les périphériques tactiles. Correctif pour CQ-4247370

### Plateforme {#platform-1}

* Autoriser la configuration du nombre maximal de reprises lors de l’acquisition/de la publication d’un package. NPR-25328 : correctif pour Granite-22376
* Journalisation incorrecte en cas d’erreurs de réplication. NPR-25308 : correctif pour CQ-4249402
* L’installation de Forms AEM 6.2 Forms CFP8 à CFP14 entraîne l’échec d’Apache POI. NPR-25053 : correctif pour Granite-21771

### Granite {#granite-2}

* Échec du processus de synchronisation des utilisateurs avec l’exception OakConstraint0022. NPR-25729 : correctif pour Oak-7428

### Communities {#communities}

* Le lot cq -social-as-provider ne démarre pas avec les versions 3.x de mongo driver. NPR-26271 : correctif pour CQ-4252710

### IU - Fondation {#ui-foundation-1}

* Mise à jour vers jqueryui clientlib v1.12.1. NPR-25090 : correctif pour Granite-21981, CQ-4248897

* (Omni-recherche) : la propriété « Titre » est vulnérable au cross-site scripting (XSS) dans Sites. NPR-24994 : correctif pour Granite-19933

### Formulaires {#forms-3}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-3}

#### Formulaires adaptatifs {#adaptive-forms-2}

* Codage incorrect lors de l’envoi de données à partir du formulaire adaptatif. NPR-25539

#### Forms – Gestion {#forms-management}

* Ressources de formulaire sans rapport signalées comme références pendant la publication de la page. NPR-26167 : correctif pour CQ-4251004

### Forms - Programme d’installation JEE {#forms-jee-installer-3}

#### Document Security {#document-security}

* La variable est renseignée comme type de données Liste, le sous-type est chaîne, mais nous obtenons une erreur « Impossible de contraindre l’objet ». NPR-26194 : correctif pour CQ-4252287
* Impossible d’accéder aux configurations de filigrane après l’installation de 6.2-SP1-CFP15. NPR-26130 : correctif pour CQ-4250984

### Lots OSGI et packages de contenu inclus {#osgi-bundles-and-content-packages-included-2}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP17

[Obtenir le fichier](assets/do-not-localize/62cfp17updated_bundles.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP17

[Obtenir le fichier](assets/do-not-localize/content_package_62sp1_cfp17_2.txt)

### Pack de correctifs cumulés 16 {#cumulative-fix-pack-4}

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP16 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’[AEM 6.2 SP1](https://helpx.adobe.com/fr/experience-manager/6-2/release-notes/sp1.html).

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Ajout de la prise en charge de STARTTLS dans Day CQ Mail Service.
* Correction de l’alignement des icônes ContextHub dans l’infobulle de profil.
* Correctifs de la fonctionnalité d’affichage/masquage des composants déroulants.
* Mise à niveau vers la dernière version de Jackson 2.8.11

### Ressources {#assets-3}

* Impossible de lancer un workflow à partir d’un affichage par liste. NPR-24393 : correctif pour CQ-4245788
* (Firefox/Chrome) Impossible de télécharger les ressources dans la page Partage de ressources. NPR-24523 : correctif pour CQ-4224408
* Amélioration de la qualité par défaut de la prévisualisation vidéo dans AEM. NPR-24148 : correctif pour CQ-4244310

### Intégration {#integration-4}

* Lorsqu’un composant est ciblé sur une instance de publication, le scintillement apparaît pour illustrer l’expérience par défaut avant l’expérience ciblée. NPR-23992 : correctif pour CQ-4242038
* Les expériences supprimées de l’environnement de création ne sont jamais supprimées du site de publication lors de l’activation de la page. NPR-24869 : correctif pour CQ-4247832

### Plateforme {#platform-2}

* Patch pour jQuery 1.12.4 de clientlib afin d’inclure un correctif de sécurité. NPR-24129 : correctif pour Granite-20058
* Ajout de la prise en charge de STARTTLS dans Day CQ Mail Service. NPR-23941 : correctif pour CQ-4240397
* Supprimez la valeur par défaut MERGE_PRESERVE aclHandling. NPR-24593 : correctif pour Granite-21889
* LineChecker ne parvient pas à externaliser les liens lorsque la requête contient des paramètres de requête non valides. NPR-24127 : correctif pour CQ-4241893

### MSM {#msm}

* Correctifs proactifs pour les attaques de cross-site scripting (XSS). NPR-21893 : correctif pour CQ-4223385
* MSM LiveRelationship : RolloutConfig effective incorrecte si BlueprintConfig est sur la racine. NPR-23999 : correctif pour CQ-4243000

### Sites {#sites-3}

* Pour créer une expérience dans une zone Live Copy, l’héritage à rompre doit être configuré. NPR-24995, correctif pour CQ-4248209
* (Interface utilisateur tactile) Plusieurs icônes de la barre d’outils supérieure disparaissent lors du verrouillage ou du déverrouillage d’une page. NPR-23954 : correctif pour CQ-4243345
* Les champs ne sont pas alignés correctement dans ContextHub. NPR-23958
* Une action de publication sur la page verrouillée rompt la création. NPR-23970 : correctif pour CQ-4243203
* Les rapports prêts à l’emploi dans /etc/reports/ ne fonctionnent pas correctement et ne présentent aucun graphique de données historiques. NPR-20035 : correctif pour CQ-4220180
* La création du lancement échoue lors de l’initialisation du workflow « Lancement de requête » sur un projet. NPR-24255 : correctif pour CQ-4245030
* Les balises et attributs HTML sont ignorés par les emails après l’installation de CFP10. NPR-24287 : correctif pour CQ-4240028
* TagPicker : la suggestion de balise dans le champ de balise de schéma de métadonnées interroge des nœuds pouvant être balisés, ce qui entraîne un temps de chargement important. NPR-24347 : correctif pour CQ-4244291
* L’intégration de Salesforce échoue avec les configurations de proxy. NPR-24418 : correctif pour CQ-4245300
* (WCM) PageManager laisse Page archivé sur Exception lors de la création de la révision. NPR-24565 : correctif pour CQ-4246203
* Le bouton Émulateur de périphérique disparaît du mode de modification et de prévisualisation après l’application de CFP14. NPR-24566 : correctif pour CQ-4247060
* (IU classique) Les balises entières apparaissent comme vides une fois créées dans la boîte de dialogue. NPR-24688, correctif pour CQ-4246407
* Impossible de créer la version lors de la première tentative. NPR-24774 : correctif pour CQ-4232176
* Les rapports prêts à l’emploi dans /etc/reports/ ne fonctionnent pas correctement et ne présentent aucun graphique de données historiques. NPR-24138 : correctif pour CQ-4220180

### Vulnérabilité {#vulnerability-1}

* L’intégration de Salesforce est vulnérable aux attaques SSRF (Server Side Request Forgery). NPR-24289 : correctif pour CQ-4245277
* Vulnérabilité SSRF (Server Side Request Forgery) dans ReportingServicesProxyServlet. NPR-24657 : correctif pour CQ-4246880

### Granite {#granite-3}

* Les opérations de lecture des métadonnées ne sont pas terminées. NPR-24240 : correctif pour Granite-19866
* Mettez à jour Jetty vers la version 9.4.11.v20180605 pour corriger les vulnérabilités. NPR-25033 : correctif pour Granite-22120

### WCM - Composants Foundation {#wcm-foundation-components-1}

* PageComparator émet ClassCastException lors du tri des pages. NPR-24123 : correctif pour CQ-4244048
* La fonctionnalité Afficher/Masquer du composant déroulant de formulaire ne fonctionne pas comme prévu. NPR-24562 : correctif pour CQ-4222853

### Interface utilisateur {#user-interface}

* Une utilisation intensive du processeur est observée en raison du nombre élevé de requêtes dans la fonctionnalité de recherche d’administrateurs. NPR-23588 : correctif pour Granite-21286
* (IU classique) Le composant affiche les valeurs par défaut même si le service de modèle de données de formulaire associé est défini sur un champ vide. NPR-21903 : correctif pour GRANITE-19744
* Lancement de NPE multichamp lorsque FormData n’est pas présent pour la requête. NPR-24513 : correctif pour Granite-21055

## Formulaires {#forms-4}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-4}

#### Base {#core}

* (OSGI) AEM Forms OSGI affecté par l’alerte de sécurité de liaison de données Jackson. NPR-24274 : correctif pour CQ-4230245

#### Gestion des droits {#rights-management}

* Apache POI échoue après l’installation d’AEM 6.2 SP1-CFP14. NPR-25054, NPR-25052 : correctif pour CQ-4245898, CQ-4244778

#### Formulaires HTML5 {#html-forms}

* Les données ne sont pas renseignées par préremplissage de champs multilignes dans la prévisualisation HTML. NPR-23357 : correctif pour CQ-4244212
* Lorsqu’une lettre est prévisualisée via la prévisualisation par défaut, le mappage des fragments de mise en page ne s’affiche pas alors que la même lettre apparaît correctement lorsque vous cliquez sur le bouton de prévisualisation. NPR-22993 : correctif pour CQ-4237745
* Problème de prévisualisation HTML d’un champ de texte lorsqu’un modèle de numéro de sécurité sociale est appliqué à un modèle. NPR-23205

#### Formulaires adaptatifs {#adaptive-forms-3}

* Erreur « Guidelib n’est pas défini » lors de l’ajout d’un formulaire AEM au composant parsys. NPR-24269 : correctif pour CQ-4244546

### Programme d’installation de Forms JEE {#forms-jee-installer-4}

#### Forms-Install-LCM {#forms-install-lcm}

* Les fins de lignes de fenêtres dans les fichiers de script Shell empêchent l’exécution de LCM sous UNIX. NPR-22958

### Lots OSGI et packages de contenu inclus {#osgi-bundles-and-content-packages-included-3}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP16

[Obtenir le fichier](assets/do-not-localize/6_2cfp16_bundlecomparison-list.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP16

[Obtenir le fichier](assets/do-not-localize/6_2cfp16_contentpackage-list.txt)

### Pack de correctifs cumulés 15 {#cumulative-fix-pack-5}

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP15 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’[AEM 6.2 SP1](https://helpx.adobe.com/fr/experience-manager/6-2/release-notes/sp1.html).

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Correctif de sécurité proactive dans le tableau Foundation pour préserver la cohérence de la conception.
* Ajout de la prise en charge de typeHint pour enregistrer des valeurs sous forme de chaîne.
* Renforce la sécurité du service de préremplissage Forms
* Mettez à jour le fichier adobe-reader-extensions-dsc.jar pour obtenir des correctifs dans Reader Extension.
* Correction du hook de validation afin de tenir compte des éléments « :invalid » pour l’entrée de numéro de rappel.

### Ressources {#assets-4}

* Les données EmbedXMP sont toujours définies comme « actives » pour le workflow de génération Ptiff. NPR-22776 : correctif pour CQ-4234498
* Impossible de définir plusieurs valeurs par défaut dans les champs à plusieurs valeurs. NPR-22900 : correctif pour CQ-4239000
* (Dynamic Media) Lorsque vous cochez la case Rendus dynamiques, le fichier zip téléchargé génère l’image TIFF d’origine avec un fichier à zéro octet. NPR-22410 : correctif pour CQ-4198471
* (IU tactile) Emplacement de téléchargement par défaut des ressources en mode Colonnes. NPR-23475 : correctif pour CQ-4237057

### Intégration {#integration-5}

* En mode Target, les auteurs peuvent modifier un composant hérité du plan directeur sans annuler l’héritage. NPR-22751 : correctif pour CQ-4237907
* La variable de chemin n’est pas codée correctement, ce qui entraîne un cross-site scripting (XSS) non persistant. NPR-22851

### MSM {#msm-1}

* Pendant le déploiement d’une LiveCopy avec plusieurs configurations de déploiement, si un ResourceNameConflict survient sous la racine, le flux de déploiement se termine sans inclure toutes les branches. NPR-22842 : correctif pour CQ-4236188

### Plateforme {#platform-3}

* Implémentez une limite d’interrogation dans une requête d’application inversée. NPR-23351 : correctif pour Granite-21135****
* La modification du modèle de message n’est pas répercutée sur les journaux personnalisés. NPR-23486 : correctif pour CQ-4241974

### Sites {#sites-4}

* La création d’un lien dans un texte d’un éditeur de texte enrichi vers un document contenant des espaces ou d’autres caractères spéciaux ne fonctionne pas. NPR-22289 : correctif pour CQ-4224321
* L’enregistrement du segment avec une valeur énorme (10000000000) définit l’amplification sur 0, générant un message d’erreur. NPR-22524 : correctif pour CQ-4237006
* Impossible de cliquer sur Ajouter un élément dans le composant Multifield. NPR-22552 : correctif pour CQ-4237404
* La barre de défilement horizontale n’est pas visible lorsque le titre du segment est long. NPR-22615 : correctif pour CQ-4237001
* Le chargement d’une audience vide génère un code JavaScript incorrect. NPR-22974 : correctif pour CQ-4238734
* Lors de la planification d’une activation ou de la désactivation, le titre du workflow est obligatoire. Le titre du workflow personnalisé n’est donc pas traduit dans le journal. NPR-23121 : correctif pour CQ-4237552
* Requête de correctifs pour les problèmes liés aux segments cibles dans Sites. NPR-23128
* (Firefox) La case à cocher pour la personne sélectionnée n’est pas la bonne. NPR-23345
* Les étiquettes des différents modes apparaissent avec les icônes. NPR-23275
* Erreur « Valeur du sélecteur de récursivité non valide » lors de la migration d’un composant d’AEM 6.0 vers AEM 6.2. NPR-23503 : correctif pour CQ-4241258

### Communities {#communities-1}

* Les notifications par web et par email ne sont pas déclenchées en raison d’un échec d’envoi du message aux groupes. NPR-23447 : correctif pour CQ-4242880

### Traduction {#translation-1}

* Les copies de langue des ressources sont créées lorsque la ressource « Ne pas traduire » est définie sur la configuration de traduction. NPR-22540 : correctif pour CQ-4237962

### Interface utilisateur {#user-interface-1}

* L’utilisation d’Omni-recherche avec une requête de trait d’union renvoie une erreur de serveur. NPR-22999 : correctif pour Granite-19674
* DatePicker ne prend pas en charge la définition manuelle d’un conseil de type externe par un champ masqué. La modification de l’indicateur de type génère une erreur de conversion. NPR-23333 : correctif pour Granite-21194

### WCM - Composants Foundation {#wcm-foundation-components-2}

* Le composant CAPTCHA a été abandonné pour une meilleure sécurité. Si vous utilisez le composant CAPTCHA, le message « Le composant Captcha est obsolète et ne doit plus être utilisé. » s’affiche après l’installation de la version 6.2 SP2-CFP15 ou ultérieure. Le composant AEM peut être personnalisé de manière inclure reCAPTCHA pour une meilleure sécurité. NPR-22151 : correctif pour CQ-4220052
* Le composant « Tableau » de WCM Foundation est vulnérable au cross-site scripting par stockage. NPR-23206 : correctif pour CQ-4240760

### Vulnérabilité {#vulnerability-2}

* Cross-site scripting (XSS) dans les liens des Projets de l’IU d’administration. NPR-23272 : correctif pour CQ-4241795

## Formulaires {#forms-5}

### Package de modules complémentaires Forms {#forms-add-on-package-5}

#### Correspondence Management {#correspondence-management}

* Lorsqu’une lettre est prévisualisée via la prévisualisation par défaut, le mappage des fragments de mise en page ne s’affiche pas alors que la même lettre apparaît correctement lorsque vous cliquez sur le bouton de prévisualisation. NPR-23335 : correctif pour CQ-4237745
* Les données de la lettre correspondant aux liaisons définies dans XDP ne sont pas renseignées avec l’URL de lettre directe. NPR-24145 : correctif pour CQ-4244290

#### Mobile Forms {#mobile-forms}

* (Correspondence Management) Désalignement des données lors du chargement d’une lettre avec le code XML de la cible. NPR-22993 : correctif pour CQ-4237663

#### Service Reader Extensions {#reader-extensions-service}

* Impossible d’appliquer l’extension Reader à Adobe PDF. NPR-23067

#### Forms Manager {#forms-manager}

* Les formulaires incorporés dans Site ne sont pas publiées lors de la republication de la page de Site. NPR-23014 : correctif pour CQ-4236566

#### Vulnérabilité {#vulnerability-3}

* Correctifs proactifs pour le cross-site scripting. NPR-20624 : correctif pour CQ-4206055
* Vulnérabilité au cross-site scripting (XSS) par stockage dans l’onglet Remarques du gestionnaire de formulaires. NPR-27157 : correctif pour CQ-4255556

#### Service Encryption {#encryption-service}

* (OSGI) [JEE] État de signature incorrect pour le PDF avec pièce jointe lors de la vérification avec « Valider le processus PDF ». NPR-23269, NPR-23737

### Programme d’installation de Forms JEE {#forms-jee-installer-5}

#### Base {#core-1}

* Les problèmes signalés dans l’analyse de code statique de l’extension Core doivent être résolus. NPR-13947

#### Service PDFG {#pdfg-service}

* Le convertisseur HTML vers PDF ne fonctionne pas. NPR-21545

### Lots OSGI et packages de contenu inclus {#osgi-bundles-and-content-packages-included-4}

Le texte suivant répertorie les lots OSGI et les packages de contenu inclus dans le CFP.

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP15

[Obtenir le fichier](assets/do-not-localize/6_2cfp15updated_bundles.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP15

[Obtenir le fichier](assets/do-not-localize/6_2_cfp15contentpackage-list.txt)

### Pack de correctifs cumulés 14 {#cumulative-fix-pack-6}

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP14 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Amélioration de la capacité de modification des propriétés de métadonnées.
* Reconfiguration de la tâche de notification de l’expiration de mots de passe pour les ressources déjà expirées.
* Console de l’interface utilisateur tactile personnalisée pour étendre d’autres paramètres régionaux.
* Mise à jour de cq-msm-core pour une synchronisation Livecopyindex efficace.
* Simplification de la fonctionnalité de réplication pour divers déploiements.

### Ressources {#assets-5}

* Les utilisateurs ne peuvent pas télécharger de ressources comportant une clause de non-responsabilité et de longs noms de fichier. NPR-22163 : correctif pour CQ-4235274
* Un guillemet simple empêche la mise à jour des métadonnées dans l’affichage par lots et l’interface utilisateur est complètement rompue lorsque vous ouvrez les propriétés d’une ressource à l’aide des actions rapides de la barre d’outils. NPR-22317, NPR-22353 : correctif pour CQ-4236990, CQ-4236469
* La tâche de notification d’expiration des ressources ne désactive pas les ressources expirées. NPR-22346 : correctif pour CQ-4237188
* Le téléchargement des ressources échoue lors de l’utilisation de la gestion des droits numériques dans Assets dans Safari. NPR-22378 : correctif pour CQ-4236460
* Le rendu Web pour une petite image présente une taille de pixel inexacte. NPR-22435 : correctif pour CQ-4236742

### Sites {#sites-5}

* (IU tactile) La balise déplacée apparaît à l’ancien et au nouvel emplacement dans les propriétés de la page. NPR-21921, correctif pour CQ-4238598
* (IU tactile) L’éditeur de texte enrichi supprime tous les attributs autres que id de la balise &lt;a>. NPR-22045 : correctif pour CQ-4234133
* Le fait de coller directement du contenu dans l’éditeur de texte enrichi à l’aide de Ctrl+V fait perdre les sauts de ligne. NPR-22117 : correctif pour CUI-5881
* (IU tactile) Impossible d’afficher plus de 40 balises sous l’espace de noms. NPR-22290 : correctif pour CQ-99114
* Problèmes de flux RSS, port -1 à AEM 6.2 NPR-22158 : correctif pour CQ-4233339
* (IE) Lors de la création d’un caractère dans un champ de texte enrichi pour la première fois, un espace de fin est ajouté au caractère. NPR-22443 : correctif pour CQ-4235343
* Lors d’une tentative de mise en correspondance du nom du package, l’objet Java Use gèle SightlyJavaCompilerService en raison d’un espace de fin dans la déclaration du package. NPR-22557 : correctif pour Granite-20836
* La console de l’interface utilisateur tactile ne sélectionne pas de nouvelles langues pour le balisage. NPR-22250 : correctif pour CQ-4239194

### Mobile On-Demand {#mobile-on-demand}

* (Digital Publishing Suite) Les champs Date de publication et Date de couverture devaient être définis pour les folios avant leur chargement dans DPS. NPR-22484

### Commerce {#commerce}

* Plusieurs vulnérabilités de cross-site scripting (XSS) dans l’assistant de création de catalogue de commerce. NPR-22344 : correctif pour CQ-4237017

### MSM {#msm-2}

* La synchronisation de LiveCopyIndex entraîne une saturation des threads lors de longues mises à jour d’index. NPR-22214 : correctif pour CQ-90667
* La propriété cq:cugEnabled est désactivée lorsqu’un autre champ d’une LiveCopy est modifié, ce qui rend la page non protégée. NPR-22246 : correctif pour CQ-4236050
* L’action de déploiement de page ne permet pas de mettre à jour les enfants lorsqu’une page est suspendue. NPR-22483 : correctif pour CQ-4236956
* Le déploiement d’une structure qui a été déplacé dans un gabarit entraîne un cq:moveTarget erroné. NPR-22373 : correctif pour CQ-4232536

### Intégration {#integration-6}

* Une tentative de tri des offres dans la bibliothèque de sélection des offres entraîne un comportement erratique. NPR-22208 : correctif pour CQ-4235439
* TargetContentImpl ralentit AEM pendant les requêtes longues. NPR-22361 : correctif pour CQ-4236907
* Le moteur Target (mbox.js, at.js) n’utilise pas d’URL mal formées et utilise des URL contenant deux-points qui peuvent rencontrer des problèmes avec certains déploiements. NPR-22366 : correctif pour CQ-4237854
* La personnalisation de la page nécessite un droit de publication sur le nœud de la marque. NPR-22370 : correctif pour CQ-4236895

### Foundation {#foundation}

* Les modèles Apache Sling Scripting Sightly Models utilisent le lot Provider **org.apache.sling.scripting.sightly.models.provider/1.0.18**. NPR-22614 : correctif pour Sling-5944, Sling-6866

### Projets {#projects}

* Le lanceur de workflow ne peut pas accepter la valeur TypeHint de la chaîne. NPR-22436 : correctif pour CQ-4237855

### Traduction {#translation-2}

* Étude des problèmes liés à la fonctionnalité Aperçu. NPR-22201 : correctif pour CQ-4223753

### Interface utilisateur {#user-interface-2}

* (IU classique) Le composant affiche les valeurs par défaut même si le service de modèle de données de formulaire associé est défini sur un champ vide. NPR-21903 : correctif pour GRANITE-19744

### WCM - Composants Foundation  {#wcm-foundation-components-3}

* Erreur lors de la publication d’une page Live Copy qui pointe vers une page d’importateur dans Adobe Campaigns. NPR-22470 : correctif pour CQ-4237164
* Erreurs JavaScript lors de l’ouverture de l’éditeur Fragments d’expérience. NPR-22598 : correctif pour CQ-4238415

### Workflow {#workflow}

* Le service de notification par courrier électronique de workflow Day CQ déclenche un courrier électronique par nœud Mongo pour les notifications WorkflowCompleted et WorkflowAborted. NPR-22486 : correctif pour CQ-4238172

## Formulaires {#forms-6}

### Package de modules complémentaires Forms {#forms-add-on-package-6}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

#### Formulaires adaptatifs {#adaptive-forms-4}

* Incohérence dans la valeur d’espace réservé de liste déroulante dans les Formulaires adaptatifs dans IE11 et Chrome. NPR-22405 : correctif pour CQ-4227096

### Programme d’installation de Forms JEE {#forms-jee-installer-6}

#### Installation de LCM {#install-lcm}

* Mise à jour de Jsafe Jars vers Cryptoj 6.1.3.1 dans le programme d’installation et LCM. NPR-22744

### Feature Packs inclus {#feature-packs-included}

#### Process Management {#process-management}

* (Workspace HTML) Lorsqu’un utilisateur demande une tâche, le numéro dans la file d’attente est actualisé pour cet utilisateur, mais pas pour les autres utilisateurs, sauf si la page est actualisée. NPR-19778 : correctif pour CQ-4233665

### Lots OSGI et packages de contenu dans CFP14 {#osgi-bundles-and-content-packages-included-in-cfp}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP14

[Obtenir le fichier](assets/do-not-localize/6_2cfp14updated_bundles.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP14

[Obtenir le fichier](assets/do-not-localize/6_2_cfp14contentpackage-list.txt)
Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP13 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Activation de la configuration de champ Paramètre statique dans les paramètres de composant cible pendant l’utilisation d’AT.js comme bibliothèque cliente.
* Correctifs de la fonctionnalité d’affichage/masquage des composants déroulants.
* Correctifs pour l’utilisation des audiences de synchronisation des cibles.
* Renforcement de la polyvalence de Correspondence Management pour prendre en charge les caractères spéciaux.

### Ressources {#assets-6}

* La purge de version ne parvient pas à supprimer les anciennes versions des ressources. NPR-21682 : correctif pour CQ-4212996
* La réorganisation des dossiers situés sous un dossier réorganisable n’est pas conservée. NPR-21964 : correctif pour CQ-4231761

### Sites {#sites-6}

* (IU tactile)(IU classique) Plusieurs vulnérabilités de cross-site scripting (XSS) dans les composants HTL et principaux. NPR-21532 : correctif pour CQ-4232305 et CQ-4232511
* La création/mise en forme de contenu (par exemple, l’attribution/la suppression de nouveaux styles de liste) sur un texte sélectionné ne fonctionne pas correctement dans Internet Explorer 11. NPR-21533 : correctif pour CQ-4230689
* (Safari) Les utilisateurs ne peuvent pas afficher toutes les ressources dans le volet de recherche de ressources. NPR-21981 : correctif pour CQ-4213720
* Time Warp renvoie l’erreur « RecursionTooDeepException » avec une page altérée et aucune nouvelle version n’est créée, même si la date est modifiée. NPR-21707 : correctif pour CQ-4199536
* Lors du chargement d’une page dans l’éditeur, le fournisseur WorkflowStatusprovider (pageinfo.json) est chargé trois fois, ce qui entraîne un ralentissement des performances de l’instance AEM. NPR-21778 : correctif pour CQ-59232

### Intégration {#integration-7}

* La création d’audiences de type Mobile et Navigateur en mode Cible de création ne fonctionne pas dans AEM. NPR-21676, NPR-21681 : correctif pour CQ-4232100
* Avec une latence élevée pendant l’actualisation d’un composant ciblé, il est possible d’ajouter une autre offre avant l’actualisation complète du composant. NPR-21744 : Correctif pour CQ-4233158 / CQ-4234293
* Les utilisateurs ne peuvent pas voir les valeurs de paramètre statique de test dans l’appel mbox qui s’affiche lors du test avec AT.js comme bibliothèque cliente dans la configuration cloud. NPR-21930 : correctif pour CQ-4234520

### Plateforme {#platform-4}

* Problèmes de performances liés à la synchronisation des utilisateurs lorsque le nombre d’utilisateurs ou de groupes est important. NPR-20431 : correctif pour CQ-4223282
* Utilisateurs non synchronisés avec la synchronisation des utilisateurs à l’aide de la distribution Sling. NPR-21911 : correctif pour Granite-20404
* Prévention de la mise en surbrillance de mots vides dans les extraits de recherche (sur une page de Geometrixx). NPR-21835 : correctif pour Granite-21067\
   Remarque : Ce correctif nécessite Oak CFP 1.4.20 ou version supérieure.

### Traduction {#translation-3}

* la propriété jcr est manquante pour l’ID utilisateur initiateur lors de la création du projet de traduction. NPR-21715 : correctif pour CQ-4230713

### WCM - Composants Foundation {#wcm-foundation-components-4}

* La fonctionnalité Afficher/Masquer du composant déroulant de formulaire ne fonctionne pas comme prévu. NPR-22164 : correctif pour CQ-4235288

## Formulaires {#forms-7}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms {#forms-add-on-package-7}

#### Formulaires adaptatifs {#adaptive-forms-5}

* Injection d’entité externe XML (XXE) dans Formulaires adaptatifs. NPR-21982 : correctif pour CQ-109878
* (iOS11) Lorsque vous cliquez sur une pièce jointe, le fichier correspondant ouvre la caméra au lieu de l’explorateur de fichiers du périphérique. NPR-21926 : correctif pour CQ-4214348
* Le titre manquant dans l’interface utilisateur de création de thème provoque une exception et un échec du rendu de la boîte de dialogue. Correctif pour CQ-4236143

#### Correspondence Management {#correspondence-management-1}

* Problèmes de rendu avec les données xml contenant des caractères spéciaux. NPR-21712 : correctif pour CQ-4229137

### Programme d’installation de Forms JEE {#forms-jee-installer-7}

#### Incohérence affectant le service assembleur {#assembler-service}

* Le fichier PDF généré à l’aide de la version 6.2.0-ASM-1017-003 est endommagé. NPR-21427 : correctif pour CQ-4228046

#### Service PDFG {#pdfg-service-1}

* Échec de la reconnaissance optique des caractères en raison d’un format de page (PDF) inattendu provenant de fichiers PNG, JPEG et TIFF. NPR-19489 : correctif pour CQ-4209079

## Lots OSGI et packages de contenu dans CFP13 {#osgi-bundles-and-content-packages-included-in-cfp-1}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP13

[Obtenir le fichier](assets/do-not-localize/cfp13_bundlecompare-list.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP13

[Obtenir le fichier](assets/do-not-localize/cfp13_contentpackage-list.txt)

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP12.1 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Amélioration de la gestion des métadonnées pour les champs à plusieurs valeurs.
* Prise en charge des codes de pays à plusieurs caractères (plus de deux) dans les workflows de traduction.
* Amélioration du rendu des pages comportant plusieurs composants imbriqués.
* Amélioration de la synchronisation des dates de publication des actifs entre AEM et Adobe Digital Publishing Suite.

### Ressources {#assets-7}

* Un nombre trop élevé de caractères dans l’omni-recherche provoque le blocage du serveur AEM. NPR-21083 : correctif pour CQ-4223602
* Les valeurs spécifiées dans la deuxième option d’un champ à plusieurs valeurs dans le schéma de métadonnées ne sont pas ajoutées aux valeurs spécifiées précédemment dans CRX-de. NPR-21220 : correctif pour CQ-4224526
* Le téléchargement des ressources échoue lors de l’utilisation de la gestion des droits numériques dans Assets dans Safari. NPR-21387 : correctif pour CQ-4230287

### Sites {#sites-7}

* (DAM) (IU classique) Plusieurs vulnérabilités de cross-site scripting (XSS) dans certains fichiers SWF dans le démarrage rapide d’AEM CQ Author/Publish. NPR-21073, NPR-21074 : correctif pour NPR-20612
* Le sélecteur de balises ne traduit pas les balises disponibles dans plusieurs langues. NPR-21221 : correctif pour CQ-78855
* Problèmes de rendu avec la console d’article AEM car l’utilisation de plusieurs composants imbriqués la rendent lente. NPR-21271 : correctif pour CQ-4224158

### Intégration {#integration-8}

* Lors de l’ajout d’une structure Cible, le mode de ciblage n’est pas disponible dans la liste du mode de sélection de l’éditeur. NPR-21047

### Mobile à la demande {#mobile-on-demand-1}

* (Digital Publishing Suite) Les dates de publication des folios dans AEM ne correspondent pas aux dates qui apparaissent dans Folio Producer. NPR-21145

### MSM {#msm-3}

* Le processus de réinitialisation de Live Copy s’est arrêté après la suppression de la première page locale dans la LC. NPR-21276 : correctif pour CQ-4229743

### Plateforme {#platform-5}

* Les taglibs personnalisées qui font référence aux balises implémentées en tant que script sont introuvables après la mise à niveau vers AEM 6.3. NPR-20149 : correctif pour Granite-18433

### Traduction {#translation-4}

* Les workflows de traduction échouent avec des codes lang_country de plus de 2 caractères. NPR-21088 : correctif pour CQ-4197439
* La page des ressources ne devrait pas pouvoir être envoyée à nouveau à un projet de traduction tant que le projet n’est pas terminé. NPR-21219 : correctif pour CQ-4209908

### Interface utilisateur {#user-interface-3}

* Le composant de sélection ne supprime pas la propriété cible pendant l’envoi du formulaire. NPR-21163 : correctif pour GRANITE-14125
* HTTP.encodePathOfURI expand code doublement le signe plus « + ». NPR-21417 : correctif pour GRANITE-16340

### Vulnérabilité {#vulnerability-4}

* Cross-site scripting (XSS) dans l’éditeur de métadonnées DAM. NPR-21434 : correctif pour CQ-83472
* Plusieurs fichiers SWF vulnérables au cross-site scripting (XSS). NPR-20612 : correctif pour CQ-4213297

## Formulaires {#forms-8}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms {#forms-add-on-package-8}

#### Correspondence Management {#correspondence-management-2}

* (IE11) Le rendu initial du contenu HTML se produit uniquement sur le côté gauche tandis que le côté droit se charge par intermittence une fois l’interface utilisateur complètement chargée. NPR-21554
* Le bouton d’envoi de prévisualisation de lettre est désactivé après l’installation d’AEM 6.2 SP1-CFP9. NPR-21547
* Lors de la sélection du type de liaison de ressources, la fenêtre du Sélecteur de ressources ne s’ouvre pas dans l’assistant Modifier la liaison de données de lettre. NPR-21164 : correctif pour CQ-4194567
* Pour modifier un module de texte incorporé ou modifiable, appuyez sur l’icône Modifier ou double-cliquez sur le module de texte approprié dans l’aperçu de la lettre. NPR-21402

#### Formulaires adaptatifs {#adaptive-forms-6}

* Le composant de bouton d’envoi d’AEM Forms affiche type=&quot;button&quot; au lieu de type=&quot;submit&quot;. NPR-21007
* Les données persistent lors de l’ajout ou de la suppression de nouveaux panneaux pour les panneaux répétables. NPR-21408

### Programme d’installation de Forms JEE {#forms-jee-installer-8}

#### Base {#core-2}

* La mise à niveau vers la dernière mise à jour 131 de Java 8 produit une exception : « Le fournisseur JsafeJCE est désactivé, une vérification d’intégrité FIPS 140 requise a échoué ». NPR-21355

   **Remarque :** Cette NPR nécessite des paramètres supplémentaires. Pour plus d’informations, reportez-vous à la [dernière mise à jour de Java 8](#latest-java-update-throws-an-exception-npr).

* Mise à jour de Jsafe Jars vers Cryptoj 6.1.3.1 dans Core, Encryption, Signature &amp; Document Security. NPR-21360, NPR-21361, NPR-21356, NPR-21358

#### Installation de LCM {#install-lcm-1}

* Mise à jour de Jsafe Jars vers Cryptoj 6.1.3.1 dans le programme d’installation et LCM. NPR-21362

#### Service PDFG {#pdfg-service-2}

* Mise à jour de Jsafe Jars vers Cryptoj 6.1.3.1 dans PDFG. NPR-21359

#### Process Management {#process-management-1}

* (Workspace HTML) Activation du redimensionnement des colonnes afin que la catégorie de noms n’apparaisse pas tronquée. NPR-19770 : correctif pour CQ-4233668

#### Service Reader Extensions {#reader-extensions-service-1}

* Mise à jour de Jsafe Jars vers Cryptoj 6.1.3.1 dans RE. NPR-21357

## Lots OSGI et packages de contenu dans CFP12.1 {#osgi-bundles-and-content-packages-included-in-cfp-2}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP12.1

[Obtenir le fichier](assets/do-not-localize/cfp12_bundlecomparsion-list1.txt)

Liste des packages de contenu inclus dans AEM 6.2 SP1-CFP12.1

[Obtenir le fichier](assets/do-not-localize/cfp12_contentpackage-list.txt)

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP11 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Mise à jour de cq-msm-core pour une synchronisation Livecopyindex efficace.
* Amélioration de l’efficacité de la modification des fragments de contenu.
* Fournit une option de validation dans le gestionnaire de modules pour détecter les droits d’ACL.
* Possibilité pour Campaign d’inclure un ID de courrier électronique pour la correspondance client.
* Amélioration des capacités de codage vidéo pour les fichiers Dynamic Media.
* Correctifs dans Sightly Component et LiveCopies.

### Ressources {#assets-8}

* Le codage vidéo Dynamic Media échoue pour les fichiers dont le nom comporte des espaces. NPR-20818 : correctif pour CQ-102469
* Plusieurs vulnérabilités de cross-site scripting (XSS) dans certains fichiers SWF dans le démarrage rapide d’AEM CQ Author/Publish. NPR-21071, NPR-21072
* Les utilisateurs ne peuvent pas télécharger de ressources comportant une clause de non-responsabilité et de longs noms de fichier. NPR-20255 : correctif pour CQ-4222139

### Sites {#sites-8}

* Intégration d’AEM et Campaign : des liens spéciaux sont réécrits dans Adobe Campaign et empêchent les clients d’envoyer des liens hypertexte mailto: dans leurs courriers électroniques. NPR-20787 : correctif pour CQ-4225760
* (IU tactile) Problèmes d’utilisation d’AEM et problèmes de performances lorsque la langue est définie sur le français. NPR-20854 : correctif pour CQ-4227628
* La liaison d’un fichier de ressources codé à l’aide du plug-in de liaison dans RTE renvoie un lien vide. NPR-20626, NPR-21059 : correctif pour CQ-4223011
* L’éditeur de métadonnées de fragments de contenu empêche les auteurs de contenu d’enregistrer les modifications apportées aux fragments de contenu. NPR-20641 : correctif pour CQ-4224755
* L’alias de propriété de page conduit à Demander la publication/Demander l’annulation de la publication. NPR-20731 : correctif pour CQ-4226227
* Problèmes de composants de texte avec le codage du lien dans l’élément RTE. NPR-20755 : correctif pour CQ-4224321

### Plateforme {#platform-6}

* ResourceResolverImpl.map() n’appelle pas ResourceDecorator. NPR-20788 : correctif pour GRANITE-19718
* org.apache.sling.i18n.DefaultLocaleResolver ne peut pas traiter les requêtes via org.apache.sling.engine.SlingRequestProcessor. NPR-20706 : correctif pour CQ-94880
* Requête d’ajout d’une option de validation dans Package Manager pour détecter si des autorisations/privilèges ACL sont modifiés sur un package particulier. Correctif pour CQ-4229196

### Intégration {#integration-9}

* (Search&amp;Promote) Une définition de filtre ambiguë pour le package de contenu conduit à des chemins remplacés lors de l’installation. NPR-20808 : correctif pour CQ-4227615

### Workflow {#workflow-1}

* Problèmes de stabilité liés au déploiement du serveur de production AEM. NPR-20979 : correctif pour Granite-19104

### Projets {#projects-1}

* (IU tactile) Impossible d’ajouter des membres de l’équipe à un projet. NPR-20990 : correctif pour CQ-4205375

### Composants WCM-Foundation {#wcm-foundation-components-5}

* Le composant Sightly Image « link to » produit une erreur 403 en raison de l’absence d’extension .html. NPR-20823 : correctif pour CQ-4195909
* Sur un site de plans directeurs qui utilise LiveCopy, la tentative de suppression d’un composant Form renvoie une exception NullPointerException et rétablit le composant Form au lieu de le supprimer. NPR-20855 : correctif pour CQ-4204628
* La synchronisation de LiveCopyIndex entraîne une saturation des threads lors de longues mises à jour d’index. NPR-20634 : correctif pour CQ-90667

### Sécurité {#security}

* Mise à jour proactive de la bibliothèque XSS. NPR-21174
* Mise à niveau vers Apache Commons Email 1.5 qui présente une API simplifiée pour l’envoi d’e-mail. NPR-20509 : correctif pour Granite-18240
* Correctif de sécurité appliqué à l’API Apache Sling XSS Protection pour éliminer la possibilité de contournement de XSS. NPR-21290 : correctif pour GRANITE-19924
* Contournement de XSS dans la fonction XSSAPI#getValidHref. NPR-21174 : correctif pour Granite-19924

### Applications mobiles {#mobile-apps}

* Correction de problèmes liés aux requêtes Curl Head pour les ressources prêtes à l’emploi dans AEM. NPR-20511 : correctif pour CQ-4221520 et CQ-103024

## Formulaires {#forms-9}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

Les principaux aspects pour AEM Forms sont les suivants :

* Activation de l’authentification de certificat pour les utilisateurs de Workbench.
* Correctifs d’utilisation pour Correspondence Management, les formulaires HTML5 et l’espace de travail AEM Forms.

### Package de modules complémentaires Forms {#forms-add-on-package-9}

#### Formulaires HTML5 {#html-forms-1}

* Problèmes d’utilisation avec le composant de griffonnage sur les périphériques iOS 10 et 11. NPR-21092

#### Correspondence Management {#correspondence-management-3}

* (Interface utilisateur Correspondence) Désactivez le bouton d’envoi après un clic. NPR-21078

### Programme d’installation de Forms JEE {#forms-jee-installer-9}

#### Incohérence affectant le service assembleur {#assembler-service-1}

* docConvertor ne parvient pas à produire PDF/A avec l’erreur « (Le préfixe « stEvt » pour l’élément « stEvt:action » n’est pas lié » ). NPR-21032 : correctif pour CQ-4222540
* Une exception est générée avec le nom java.lang.IllegalArgumentException message:No enum constant com.adobe.internal.pdfm.docbuilder.signature.PathValidationFailureReason.SIGNED_IN_FUTURE lors de l’appel du service OMPFSubmission/PDFA/PDFtoPDFA. Ceci empêche de terminer le processus de vérification de signature de courte durée jusqu’au redémarrage du serveur. NPR-20792

#### Workbench {#workbench}

* Activez l’authentification de certificat pour les utilisateurs de Workbench. NPR-17548 : correctif pour CQ-4214486

#### Process Management {#process-management-2}

* Le processus de préparation des données est appelé plusieurs fois lorsque le formulaire mobile est rendu avec les paramètres dataref. NPR-19801 : correctif pour CQ-4230427 : CQ-4230400

## Lots OSGI et packages de contenu dans CFP11 {#osgi-bundles-and-content-packages-included-in-cfp-3}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP11

[Obtenir le fichier](assets/do-not-localize/cfp11_bundlecomparsion-list.txt)

Liste des packages de contenu inclus dans AEM 6.2 SP1-CFP11

[Obtenir le fichier](assets/do-not-localize/cfp11_contentpackage-list.txt)

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP10 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Ajout d’une nouvelle fonction d’utilitaire onDialogLoaded pour les tests.
* Ajout de tests et configurations de l’unité frontale à ClientLibraryProxyServlet.
* Correctifs de performances dans le composant d’éditeur statique d’images multiples.
* Mises à jour de la configuration dans le JCR Apache Sling ResourceBundleProvider.

### Ressources {#assets-9}

* La prévisualisation des ressources ne fonctionne pas si les workflows de mise à jour des ressources sont désactivés. NPR-20543 : correctif pour CQ-4204986
* Problèmes de rendu avec ajout de classe dans la propriété de classe granite: (cq-damadmin-admin-assets-upload). NPR-20514 : correctif pour CQ-4219238
* Les ressources miniatures dont le titre comporte des caractères spéciaux affichent un objet java dans l’attribut alt de NPR-20347 : correctif pour CQ-4223620
* Remplacement du code de comparaison de version par du code propriétaire Adobe en raison de problèmes de licence. NPR-20273 : correctif pour CQ-4223758
* Problèmes de traitement lors du téléchargement de fichiers PSB CMJN PSB avec plusieurs calques alpha. NPR-20251 : correctif pour CQ-4220869
* Les dictionnaires d’internationalisation ne fonctionnent pas si le serveur n’est pas redémarré dans org.apache.sling.i18n 2.5.6. NPR-20525 : correctif pour Granite – 19490
* Aucune image mémoire de thread n’est générée en fonction de la période du planificateur avec la configuration par défaut du collecteur d’images mémoire de threads (démarrage d’AEM par défaut). NPR-20288 : correctif pour GRANITE-19488 / GRANITE-12741 / CQ-90647.

### Sites {#sites-9}

* Si le filtre de date de modification est modifié après l’ouverture de la recherche enregistrée, les résultats ne sont pas modifiés et les résultats affichés sont identiques à la valeur enregistrée précédente du filtre de date de modification. NPR-19739 : correctif pour CQ-4219425
* Le chargement des pages avec des composants imbriqués a échoué. NPR-20312
* Le processus de requête de suppression est déclenché lors de la suppression des packages de workflow. NPR-20266 : correctif pour CQ-4221686
* (IU tactile) Problème de copier/coller avec le presse-papiers du système d’exploitation et le presse-papiers interne d’AEM. NPR-20228 : correctif pour CQ-4220383
* L’instance AEM devient lente avec l’affichage par liste lorsque plusieurs ressources (plus de 100) sont chargées. NPR-20034 : correctif pour CQ-4222695
* (IU tactile) La suppression des lancements via la console d’interface utilisateur classique rend toutes les pages non modifiables. NPR-20520 : correctif pour CQ-4225074
* La liste déroulante cible ne fonctionne pas avec plusieurs composants RTE dans une boîte de dialogue. NPR-20345 : correctif pour CQ-4220981

### Plateforme {#platform-7}

* Lors d’un accès via une session anonyme, ClientLibraryProxyServlet ne transmet pas de requêtes proxy aux bibliothèques clientes sur l’instance de publication et renvoie une erreur HTTP 404 introuvable. NPR-20195 : correctif pour Granite-14409

### Intégration {#integration-10}

* La sélection du moteur cible comme Adobe Target empêche le chargement du composant et génère une erreur dans le journal du serveur. NPR-20058 : correctif pour CQ-88071, CQ-109698, CQ-4201600

### Commerce {#commerce-1}

* Aucun message contextuel de confirmation ou de redirection n’apparaît lors de la création de produits de la même page. NPR-20257 : correctif pour CQ-4223414

### Interface utilisateur {#user-interface-4}

* Lorsque Datepicker est un champ dans un groupe de plusieurs champs, les valeurs enregistrées dans les champs de date ne sont pas conservées lors de la modification du composant. NPR-20077 : correctif pour GRANITE-19147
* Les requêtes antérieures ne sont pas abandonnées si des requêtes consécutives sont déclenchées, ce qui entraîne des résultats incorrects. NPR-20397 : correctif pour GRANITE-19306

### WCM - Composants Foundation {#wcm-foundation-components-6}

* La propriété ImageMap existe toujours même après la suppression des images du composant d’éditeur statique d’images multiples. NPR-20142 : correctif pour CQ-4222982

## Formulaires {#forms-10}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms {#forms-add-on-package-10}

#### Formulaires adaptatifs {#adaptive-forms-7}

* Le script valueCommit est exécuté deux fois pour DropDownList lorsqu’il est modifié via l’interface utilisateur. NPR-19989 : correctif pour CQ-110212

### Programme d’installation de Forms JEE {#forms-jee-installer-10}

**Process Management**

* Le package CFP contient AEM Forms HTML Workspace version 2.2.26. NPR-20099
* Le formulaire prérempli ne fonctionne pas lorsque le formulaire mobile est configuré pour la vue au format PDF. NPR-20566

**Gestion des droits**

* La boîte de dialogue de sélection des certificats d’authentification mutuelle/CAC devrait afficher les certificats avec une utilisation améliorée de la clé (EKU) comme authentification du client ou connexion à la carte intelligente. NPR-20708
* Forms JEE prend en charge l’authentification mutuelle PKCS#11. NPR-15001

## Lots OSGI et packages de contenu dans CFP10 {#osgi-bundles-and-content-packages-included-in-cfp-4}

Liste des lots OSGi inclus dans AEM CFP 6.2 SP1-CFP10

[Obtenir le fichier](assets/do-not-localize/bundle-list-cfp10.txt)

Liste des packages de contenu inclus dans AEM CFP 6.2 SP1-CFP10

[Obtenir le fichier](assets/do-not-localize/contentpackage-list-cfp10.txt)

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP9 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Adaptation de la configuration de l’interface utilisateur d’Analytics Classic pour une entrée secrète.
* Correctifs du cache de persistance indépendant pour Contexthub.
* Calcul précis des dimensions de ressources.
* Optimisation des performances d’AEM lors de la publication de ressources sur Brand Portal.
* Correctifs dans la valeur Resourcetype dans le nœud de canevas.
* Activation de la fonctionnalité de recherche de caractères spéciaux et sensible à la casse pour le contenu du fragment de document.
* Amélioration des Formulaires adaptatifs pour joindre un PDF comme pièce jointe dans Safari.\
   Fournit un nouveau Dynamic Media qui se connecte à la nouvelle infrastructure de publication Dynamic Media pour une réplication plus rapide et plus évolutive.

### Ressources {#assets-10}

* AEM Assets ne parvient pas à extraire les références de sous-ressources pour les ressources d’InDesign ; inclure des doublons de liens vers la ressource. NPR-19006 : correctif pour CQ-4204186
* L’option Trier ne fonctionne pas pour les ressources de la collection sous Commerce. NPR-19508 : correctif pour CQ-4213622
* Lorsqu’une ressource portant le même nom qu’une ressource existante est déplacée au même emplacement, la valeur de cq: lastReplicationAction pour les ressources est permutée entre elles, ce qui entraîne la création de métadonnées incorrectes. NPR-19531
* Un message d’erreur apparaît lors de la publication d’un grand nombre de ressources, même si toutes les ressources sont publiées correctement. NPR-19629 : correctif pour CQ-4219611
* Les rendus statiques sont répertoriés avec des dimensions fixes et ne reflètent pas la taille du rendu réel. NPR-20004
* L’instance d’AEM est ralentie lorsque plusieurs ressources (plus de 4) sont publiées sur Brand Portal. NPR-20009

### Sites {#sites-10}

* AEM présente un comportement inattendu lorsqu’un utilisateur tente de publier/annuler la publication/créer une version d’une page verrouillée par un autre utilisateur. NPR-19249 : correctif pour CQ-4215298 et CQ-4203856
* Lors de la promotion manuelle du lancement imbriqué, la page enfant est supprimée. NPR-19704
* Problèmes de persistance lorsque les boutiques ContextHub remplacent le calque de persistance par défaut lors de l’initialisation. NPR-19979 : correctif pour CQ-4218399
* Les fragments de contenu se chevauchent avec d’autres boutons. NPR-19980 : correctif pour CQ-4221519
* Page du site non affichée lors de l’affichage à l’aide d’un alias dans SiteAdmin. NPR-20053 : correctif pour CQ-4221478
* Erreur lors de la publication d’une page Live Copy qui pointe vers une page d’importateur dans Adobe Campaigns. NPR-20066 : correctif pour CQ-4220846

### Plateforme {#platform-8}

* Mise à niveau d’Apache POI vers la version 3.16 afin de prendre en charge l’inclusion d’une image d’arrière-plan des diapositives PPT dans les rendus. NPR-18286
* Problèmes de rendu avec Internet Explorer 11 et Edge lors du chargement de plusieurs ressources dans le même dossier. NPR-20062

### Intégration {#integration-11}

* Le fichier at.js personnalisé n’est pas publié lorsqu’il est utilisé avec l’utilisateur anonyme. NPR-19542 : correctif pour CQ-4219592
* Migration des informations d’identification Analytics existantes vers l’authentification WSSE. NPR-19962

### Brand Portal {#brand-portal}

* Activation de la publication de balises à partir d’AEM dans Brand Portal depuis la console tagadmin/tagging. NPR-20271

## Formulaires {#forms-11}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms {#forms-add-on-package-11}

#### Correspondence Management {#correspondence-management-4}

* Activation de la fonctionnalité de recherche de texte réel dans les fragments de document lors de la prévisualisation d’une lettre. NPR-19712

#### Formulaires adaptatifs {#adaptive-forms-8}

* Amélioration des Formulaires adaptatifs pour joindre un PDF comme pièce jointe dans Safari. Pour prendre en charge la même fonctionnalité dans des formulaires existants, nous devons modifier la configuration dans le widget de pièce jointe et mettre à jour la valeur application/pdf au lieu de .pdf dans « Types de fichiers pris en charge ». NPR-19623

#### Forms Manager {#forms-manager-1}

* Si validationState n’est pas défini sur un champ de formulaire adaptatif et que le événement elementFocusChanged se produit, un événement d’erreur (errorState) est renvoyé au serveur Adobe Analytics. NPR-19513

### Programme d’installation de Forms JEE {#forms-jee-installer-11}

#### Base {#core-3}

* Le gestionnaire de connexions n’est pas disponible pendant l’arrêt. Jboss supprime la dépendance JDBC avant l’annulation du déploiement de l’EAR de l’auteur, ce qui entraîne des problèmes de corruption. NPR-19703

## Feature Packs inclus {#feature-packs-included-1}

* Améliorations de la transparence et de la correction des vignettes dans Dynamic Media. NPR-15207

## Lots OSGI et packages de contenu dans CFP9 {#osgi-bundles-and-content-packages-included-in-cfp-5}

Liste des packages de contenu mis à jour dans AEM 6.2SP1-CFP9

[Obtenir le fichier](assets/do-not-localize/content_package-list62sp1-cfp9.txt)

Liste des lots OSGi mis à jour dans AEM 6.2SP1-CFP9

[Obtenir le fichier](assets/do-not-localize/content_package-list62sp1-cfp9-1.txt)

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP8 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Présentation des balises pour les modèles d’utilisateurs personnalisés sur le service de modèles de courrier électronique d’Adobe.
* Améliorations apportées aux boutons de l’IU tactile pour l’application de bureau.
* Désactivation du bouton d’envoi en cliquant pour empêcher plusieurs envois de formulaires sur une page de traduction.
* Configuration de plusieurs composants RTE dans une boîte de dialogue.
* Renforcement des mises à jour des références dans Live Copy.
* Activation de la fonctionnalité de recherche sensible à la casse pour le contenu du fragment de document.
* Ajout de la liste des bibliothèques Linux dans la documentation d’installation d’AEM Forms.

### Ressources {#assets-11}

* Problèmes liés à l’application du filtre Omni-recherche sur les collections dynamiques dans le navigateur Safari. NPR-19511
* Les métadonnées des mots-clés PDF ne sont pas correctement extraites et modifiées lorsqu’un fichier PDF comporte plusieurs mots-clés. Pour résoudre ce problème, la propriété des métadonnées du champ Objet a été supprimée pour les ressources PDF. Vous pouvez toutefois modifier le schéma de métadonnées pour ajouter un champ de texte à plusieurs valeurs pour le champ Objet. NPR-19126
* Le service de notification de workflow n’encode pas les liens dans le courrier électronique, ce qui empêche leur chargement une fois que les utilisateurs ont cliqué dessus. NPR-19490 : correctif pour CQ-4218055
* Impossible de charger la liste complète des pages/ressources en mode Colonnes avec Chrome. NPR-19458 : correctif pour CQ-4214248
* L’icône d’heure de désactivation incorrecte apparaît dans la boîte de réception AEM lors de l’activation du workflow « Requête d’activation ». NPR-19365 : CQ-4216174
* Problèmes de tri dans l’affichage par liste. NPR-19217 : CQ-95602
* Lors de la modification du titre ou de l’image miniature dans les paramètres du dossier de ressources, le groupe d’origine et les autorisations du dossier sont remplacés. NPR-19283 : correctif pour CQ-4216080
* Les stations de travail Windows 10 passent automatiquement en mode tactile, ce qui entraîne la désactivation de certains boutons. NPR-19183

### Sites {#sites-11}

* Problèmes liés à la présence de plusieurs composants RTE dans une boîte de dialogue. NPR-19311 : NPR-19587
* La purge de version automatique dans vanilla AEM 6.2 ne fonctionne qu’une seule fois après l’initialisation de VersionManagerImpl. NPR-19315 : correctif pour CQ-4217175
* L’instance de workflow est bloquée sur l’étape de workflow « Salesforce.com Export ». NPR-19222 : correctif pour CQ-4212976
* Les pages de copies de langue créées à partir Live Copies ne sont pas modifiables. NPR-18967
* ReferencesUpdateAction ne parvient pas à mettre à jour les liens dans une LiveCopy imbriquée avec changement de hiérarchie. NPR-18715 : correctif pour CQ-4214105

### Plateforme {#platform-9}

* Le service Modèle de courrier électronique Adobe ajoute des balises aux modèles utilisateur personnalisés. NPR-19190 : correctif pour CQ-4217113

### Projets {#projects-2}

* Les éditeurs de projet ne peuvent pas copier/coller de ressources dans le dossier de ressources du projet. NPR-19619
* Impossible de générer l’aperçu des projets de traduction après l’installation de 6.2 SP1-CFP1. NPR-16481 : CQ-4204655

### Intégration {#integration-12}

* Les propriétés d’accès des articles sont mal configurées dans Adobe Digital Publishing Solution dans l’IU classique. NPR-19366
* Le rendu des vignettes est lent en raison d’articles en taille réelle dans la console AEM Article. NPR-19086 : CQ-4217148
* Comportement incorrect du pliage automatique lors de la personnalisation des offres via Campaign si les utilisateurs ont accès à plusieurs zones. NPR-19290 : correctif pour CQ-4218029
* La boîte de dialogue de ciblage ne s’affiche pas en mode ciblage lorsqu’un module cible est modifié et enregistré plusieurs fois. NPR-19144 : correctif pour CQ-4216708

### Workflow {#workflow-2}

* Les utilisateurs ne peuvent pas filtrer les notifications dans la boîte de réception par utilisateur/groupe dans l’interface utilisateur Classic de la boîte de réception. NPR-19122 : correctif pour CQ-4215374
* La zone cliquable ne conserve pas les coordonnées sélectionnées dans le composant d’image HTL. NPR-18911 : CQ-4211584

## Formulaires {#forms-12}

* Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-12}

* Lorsque le contenu est copié de Microsoft Word ou d’un navigateur Web vers l’éditeur de texte Correspondance manager. NPR-19530
* Le contenu sans saut de ligne dans l’éditeur de texte n’est pas encapsulé. NPR-19481
* Activation de la fonctionnalité de recherche de texte réel dans les fragments de document lors de la prévisualisation d’une lettre. NPR-17792 : correctif pour CQ-4214501

#### Correspondence Management {#correspondence-management-5}

>[!NOTE]
>
>Cette fonctionnalité de recherche de fragments de texte présente certaines contraintes :
>
>* Le contenu du fragment de document est sensible à la casse et les titres ne le sont pas.
>* Les résultats de la recherche ne sont pas mis en évidence lorsqu’une partie du mot recherché est dans un style différent ou contient un caractère spécial tel que &quot; ou ‘ ou \.
>* La recherche ne fonctionne pas pour le contenu dynamique (comme les valeurs d’élément du dictionnaire de données ou les valeurs de variable) dans le fragment de document.


#### Forms Manager {#forms-manager-2}

* Les propriétés de Schéma XML d’Adaptive Forms ne peuvent pas être modifiées après l’application de CFP6 à AEM 6.2. Correctif pour CQ-4219684
* Tous les services du lot principal AEM Forms Manager ne sont pas démarrés lors du redémarrage du serveur. Correctif pour CQ-4217014

### Programme d’installation de Forms JEE {#forms-jee-installer-12}

#### Installation de LCM {#install-lcm-2}

* L’écran Administrateur sous Microsoft Windows affiche la version 6.0 après l’installation de CFP6. Correctif pour CQ-4217573

## Feature Packs inclus {#feature-packs-included-2}

* Améliorations apportées aux boutons de l’IU tactile pour l’application de bureau. NPR-18676

## Lots OSGi inclus dans CFP8 {#osgi-bundles-included-in-cfp}

Liste des lots OSGi mis à jour dans AEM 6.2SP1-CFP8

[Obtenir le fichier](assets/do-not-localize/updated-bundles-list-cfp8.txt)

Liste des packages de contenu mis à jour dans AEM 6.2SP1-CFP8

[Obtenir le fichier](assets/do-not-localize/6_2sp1-cfp8-contentpackagelist.txt)

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP7 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Changement de comportement lors de l’affichage des titres sur la carte d’image pour les images ayant une propriété dc: title définie sur String (multichamp) [].
* Correctifs du problème de performances avec les Cloud Services Dynamic Media, l’interface utilisateur tactile et les interfaces utilisateur Security.
* Correctifs dans Apache Felix Http Bridge 3.0.8
* Résolution de la réplication sans contenu binaire (BLR) entre l’environnement de création et de publication.
* Prise en charge du fichier de bibliothèque cible, AT.JS, une bibliothèque d’implémentation pour l’intégration côté client avec Adobe Target conçue pour les implémentations Web classiques et les applications sur une seule page.
* Amélioration des performances AEM en introduisant un délai d’expiration de connexion configurable par l’utilisateur pour les solutions Experience Cloud (Analytics, DTM, Cible et S&amp;P).

### Ressources {#assets-12}

* L’exception « Trop de fichiers ouverts » est générée lors du test de l’assimilation de vidéos avec AEM 6.3 configuré avec les Cloud Services Dynamic Media. NPR-18734 ; correctif pour CQ-4211407
* Le paramètre d’URL Vanity pour les ressources d’une page ne fonctionne pas après le redémarrage de l’instance AEM. NPR-18634 ; correctif pour Granite-18085
* Dans l’interface utilisateur tactile, le bouton Publier apparaît pour les utilisateurs qui n’ont pas l’autorisation de publier les actifs. NPR-18620 ; correctif pour CQ-4214042
* L’option de rendu dynamique n’est pas présente dans la boîte de dialogue de téléchargement d’une ressource une fois l’accord de licence correspondant défini. NPR-18607 ; correctif pour CQ-4212342
* Le rendu dynamique ne peut pas être téléchargé pour les ressources qui incluent des espaces dans leur nom. NPR-18571 ; correctif pour CQ-4211738
* Impossible d’enregistrer plusieurs utilisateurs lors du partage du dossier de ressources avec Creative Cloud. NPR-18489 ; correctif pour CQ-103297
* dc: title &amp; dc: description ne bascule pas vers une valeur multichamp dans crx/de. NPR-18474 ; correctif pour CQ-4209086
* L’opération de déplacement des ressources entraîne une dégradation des performances. NPR-18346
* Aucun élément n’est affiché dans le journal lorsqu’il est ouvert avec l’option par défaut Afficher tout définie. NPR-18302 ; correctif pour CQ-4211957
* Une erreur se produit lorsqu’un fichier texte codé en ASCII/UTF-8 est téléchargé vers AEM Assets et la création des miniatures échoue. NPR-18006 : CFP pour CQ-4209345
* Les boutons d’action de publication sont visibles même si l’utilisateur ne dispose pas de l’accès pour réplication. NPR-17353 ; correctif pour CQ-4209269
* Siteadmin et Miscadmin ne fonctionnent pas lorsque la réduction est activée à l’aide de min:gcc;obfuscate=true. NPR-18593 ; correctif pour CQ-4209220
* Les options de menu personnalisées n’apparaissent pas tant que l’écran n’est pas actualisé à chaque fois. NPR-18500 ; correctif pour CQ-4213581
* Mise à niveau de moment.js vers 2.10.6. NPR-18596 ; correctif pour Granite-11881
* L’application d’autorisations pour les macros DM rompt l’affichage pour l’utilisateur administrateur. NPR-18544 ; correctif pour CQ-4211729
* La fonction Publier ultérieurement pour les ressources génère une exception Illegal ArgumentException. CQ-4214532

### Sites {#sites-12}

* Sur une grappe d’auteur actif-actif avec MongoDB, les deux auteurs tentent de déclencher la réplication pour le même contenu, lorsque le délai d’activation pour le contenu est atteint. NPR-18708 ; correctif pour CQ-4210982
* NPE lors du déplacement d’une ressource avec une référence sans nœud de contenu jcr:. NPR-18664
* Les espaces réservés ne sont pas visibles dans une page qui contient plusieurs composants parsys. NPR-18645 ; correctif pour CQ-110253
* Problèmes de simultanéité dans AbstractCopyMoveCommand. NPR-18591
* Lors de la copie de texte vers un composant parsys à partir d’une autre instance AEM, le parsys est créé sans type de ressource défini. NPR-18511 ; correctif pour CQ-4212306

### Plateforme {#platform-10}

* Le programme d’installation de JCR ne met pas à jour la version du lot après l’installation du package. NPR-18728 ; correctif pour NPR-15135
* La réplication sans élément binaire (BLR) échoue avec les éléments binaires n/b de l’environnement de création et de publication. NPR-18704
* Requête de résolution d’Apache Felix Http Bridge dans l’environnement AEM. NPR-18297
* La réplication échoue lorsque plusieurs pages ayant une structure similaire sont répliquées simultanément avec la distribution de contenu Sling. NPR-18665 ; correctif pour Granite-13712
* Des paquets de distribution Sling s’accumulent sans nettoyage automatique. NPR-18601 ; correctif pour Granite-16183

### Intégration {#integration-13}

* La visualisation des offres publiées à partir des dossiers de la bibliothèque produit une exception NPE. NPR-18732 ; correctif pour CQ-4214593
* La date de début/fin d’une activité n’est pas mise à jour dans le JCR et la Cible lorsqu’elle passe d’une date spécifique à « Lors de l’activation/désactivation ». NPR-18612 ; correctif pour CQ-104831
* L’intégration d’Analytics à AEM n’a pas de délai d’expiration de connexion ou de socket défini pour les connexions httpclient. NPR-18497
* L’intégration de DTM à AEM n’a pas de délai d’expiration de connexion ou de socket défini pour les connexions httpclient. NPR-18495
* L’intégration de Cible à AEM n’a pas de délai d’expiration de connexion ou de socket défini pour les connexions httpclient. NPR-18494
* L’intégration de Search &amp; Promote à AEM n’a pas de délai d’expiration de connexion ou de socket défini pour les connexions httpclient. NPR-18493
* L’activité Target est désactivée après l’ajout d’une expérience supplémentaire. NPR-18227 ; correctif pour CQ-4201895

### Composants WCM-Foundation {#wcm-foundation-components-7}

* Les zones cliquables ne conservent pas les coordonnées sélectionnées dans le composant d’image HTL. NPR-18530 ; correctif pour CQ-4211584

### Traduction {#translation-5}

* Les résultats de recherche de traduction n’incluent pas les noms des projets de traduction. NPR-18224 ; correctif pour CQ-4210658

### Brand Portal {#brand-portal-1}

* Activation de la publication de balises à partir d’AEM dans Brand Portal depuis la console tagadmin/tagging. CQ-4212165

## Formulaires {#forms-13}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-13}

#### Correspondence Management {#correspondence-management-6}

* Les données correctes ne sont pas affichées dans le panneau de modification tant que le fragment n’est pas enregistré. NPR-19092
* L’ajout d’un fragment de document à une lettre prend beaucoup de temps. NPR-18958
* Si une déclaration XML existe dans un fichier xml de données et que le rendu de lettre est lancé via une requête POST, la lettre correspondante n’affiche pas les données. NPR-18870
* Aucun journal d’audit n’est généré pour les actions effectuées sur des ressources CM. NPR-16618

>[!NOTE]
>
>N’installez pas ce module complémentaire CFP si vous êtes affecté par les deux problèmes suivants :
>
>* Un copier-coller de Word / Web vers l’éditeur de texte CM affiche un saut de ligne dans le contenu. NPR-19530
>* Le contenu sans saut de ligne dans l’éditeur de texte CM n’est pas encapsulé. NPR-19449
>
>Ces questions seront abordées dans un prochain CFP.

#### Formulaires adaptatifs {#adaptive-forms-9}

* Lors de l’ajout d’un nouveau panneau pour les panneaux répétables, la valeur du champ déroulant du panneau précédent est supprimée. NPR-18772
* Les champs de formulaires adaptatifs marqués pour accepter uniquement des entiers acceptent également quelques caractères spéciaux du pavé numérique. NPR-18680
* Le script destiné à modifier le titre du bouton lors de l’initialisation de l’événement du panneau guideroot ne fonctionne pas. NPR-18476
* La barre de défilement n’est pas visible dans le panneau de droite pour les règles créées dans l’éditeur de règles. NPR-18716

#### Application AEM Forms {#aem-forms-app}

* Les formulaires ne sont pas affichés correctement dans l’application AEM Forms en mode hors ligne ou lorsqu’elle n’est pas connectée au réseau. CQ-4218368

### Programme d’installation de Forms JEE  {#forms-jee-installer-13}

#### Service PDFG {#pdfg-service-3}

* PDF Generator ne parvient pas à produire des documents PDF avec les niveaux de signets spécifiés. Correctif pour CQ-4211102

## Lots OSGi inclus dans CFP7 {#osgi-bundles-included-in-cfp-1}

Liste des lots OSGi mis à jour dans AEM 6.2SP1-CFP7

[Obtenir le fichier](assets/do-not-localize/bundle-list-6_2sp1cfp7.txt)

Liste des packages de contenu mis à jour dans AEM 6.2SP1-CFP7

[Obtenir le fichier](assets/do-not-localize/cfp7_content_packages.txt)

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP6 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Gestion efficace des composants masqués en mode de mise en page sur tablette.
* Présentation des actions rapides sur les périphériques hybrides.
* Résolution des problèmes de synchronisation au niveau des composants avec Live Copies.

### Ressources {#assets-13}

* Le client est bloqué lorsque l’utilisateur qui ne dispose pas de l’autorisation requise tente de déplacer l’opération sur une ressource. NPR-18330 ; correctif pour CQ-4212560
* La fusion de plusieurs configurations de services de contenu dynamique entraîne des problèmes d’utilisation. NPR-18273 ; correctif pour CQ-4201557
* L’action/less workflows d’extraction ne sont pas disponibles à partir de la console Journal une fois qu’environ 80 fragments ont été ajoutés dans le dossier Ressources. NPR-18257 ; correctif pour CQ-4211214 et NPR-18251 ; correctif pour CQ-4211216.
* Le système se bloque en raison de la mémoire insuffisante et ne présente pas de pagination pendant les rapports de ressources. NPR-17865 ; correctif pour CQ-4209759
* La lecture de la vidéo publiée échoue sur la ressource vidéo codée. NPR-17849 ; correctif pour CQ-4210739
* La miniature pour le PDF n’est pas générée. NPR-17831, NPR-17750 ; correctif pour CQ-4210547
* Les ressources expirées ne sont pas désactivées par la tâche de notification d’expiration DAM Adobe CQ. NPR-17666 ; correctif pour CQ-107766
* Les activités d’expiration des ressources s’arrêtent si aucun propriétaire n’est affecté à une ressource. NPR-17665 ; correctif pour CQ-4197946
* Une exception NullPointerException se produit en cas de déplacement d’un dossier de ressources contenant plus de 150 références entrantes. CQ-4200981

### Sites {#sites-13}

* La personnalisation ne fonctionne que pour la première adresse IP lorsque la règle de segmentation est définie pour une plage d’adresses IP. NPR-18121 ; correctif pour CQ-83767
* Échec de la connexion en raison de l’exception NumberFormatException lorsque la propriété historyShow est activée. NPR-18073 ; correctif pour CQ-101965
* Les pages supprimées marquées sont visibles dans l’interface utilisateur tactile. NPR-18025 ; correctif pour CQ-86694
* Problèmes de performances lors du chargement d’une page avec des audiences importantes (2000+). NPR-17884 ; correctif pour CQ-4209567
* Impossible de sélectionner une image après avoir supprimé une autre image de la page. NPR-17711 ; correctif pour CQ-4201323

### Plateforme {#platform-11}

* Les commandes de l’interface utilisateur tactile ne sont pas masquées pour les utilisateurs qui ne disposent pas des autorisations requises. NPR-17945 ; correctif pour CQ-4211231
* Balises japonaises manquantes dans le champ tagpicker. NPR-17768 ; correctif pour CQ-4210456
* La requête getsize() renvoie des résultats incorrects lorsque FastQuerySize est activé. NPR-18018
* La console Web de l’instance secondaire n’est pas accessible. NPR-17861 ; correctif pour Granite-14582

### Commerce {#commerce-2}

* La traversée de requête survient lorsque le plan directeur de catalogue n’a aucune condition définie pour une section. NPR-18229 ; correctif pour CQ-4211924

### Communities {#communities-2}

* PollingImporterImpl. retarde la fermeture d’AEM. NPR-18298 ; correctif pour CQ-96133

### Intégrations {#integrations}

* Résolution des erreurs du composant de recherche AEM qui peuvent se produire lorsque le client HTTP AEM Day 3.1 OSGI est configuré avec un proxy qui requiert une authentification Digest. NPR 18128
* Case manquante pour rétablir l’héritage. NPR-17753 ; requête de correctif pour CQ-4210139
* Les utilisateurs ne peuvent pas définir la priorité lors du ciblage d’un composant avec plusieurs activités. NPR-18658 ; correctif pour CQ-4210727
* Les utilisateurs ne peuvent pas parcourir le dossier /etc/segmentation pour sélectionner une audience créée sous le dossier /etc/segmentation/group1. NPR-18522

### Sécurité {#security-1}

* L’assistant Déplacer une ressource se bloque si l’utilisateur ne dispose pas de l’autorisation d’écriture sur le dossier cible. NPR-18300
* Demande d’utilisation d’une version mise à niveau du servlet org.apache.sling.servlets.post (2.3.22) dans l’API Apache Sling pour prévenir une vulnérabilité XSS. NPR-18963

### Traduction {#translation-6}

* La page des ressources ne devrait pas pouvoir être envoyée à nouveau à un projet de traduction tant que le projet n’est pas terminé. NPR-18249 ; correctif pour CQ-4209908

### Composants WCM-Foundation {#wcm-foundation-components-8}

* Impossible d’utiliser le composant iparsys de WCM Foundation dans les modèles modifiables. NPR-18223 ; correctif pour CQ-4210384
* La zone cliquable ne conserve pas les coordonnées sélectionnées dans le composant d’image HTL. NPR-18032 ; correctif pour CQ-4211584
* Lors du rendu d’un composant de l’image HTL, le nom de fichier dans l’URL est renommé, ce qui produit une URL endommagée. NPR-17908 ; correctif pour CQ-4211587
* Impossible de quitter les propriétés de la page après avoir apporté des modifications. NPR-17832 ; correctif pour CQ-96110

## Formulaires {#forms-14}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [Versions d’AEM Forms](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-14}

**Correspondence Management**

* Le dictionnaire de données est lu à plusieurs reprises pendant le rendu de la lettre. NPR-18482, correctif pour CQ-4210805
* Ajout de JavaDocs pour la classe com.adobe.livecycle.content. NPR-18467
* Lors de la création d’une lettre, la description de la lettre n’est pas enregistrée. NPR-18039
* Lorsqu’un module de texte est enregistré et qu’une expression du module de texte ne contient aucune balise d’expression d’ouverture ou de fermeture, aucun message d’erreur ne s’affiche. Le module de texte affiche un message d’erreur et n’effectue pas le rendu dans la lettre. NPR-17798
* Erreurs inattendues affichées dans les journaux lors de l’installation d’un module complémentaire. NPR-18295

**Gestionnaire de formulaires**

* L’interface utilisateur AEM Forms répertorie toutes les ressources dans le premier ordre le plus ancien. Les utilisateurs ne sont pas en mesure de réorganiser les ressources dans le premier ordre le plus récent. NPR-18451

### Programme d’installation de Forms JEE  {#forms-jee-installer-14}

**Service Output**

* Amélioration des performances du service Output pour AEM Forms 6.2. NPR-18033

**Service Signatures**

* Impossible de signer un document PDF avec le module de sécurité matérielle distant. NPR-18017

## Lots OSGi inclus dans CFP6 {#osgi-bundles-included-in-cfp-2}

Liste des lots OSGi mis à jour dans AEM 6.2SP1-CFP6

[Obtenir le fichier](assets/do-not-localize/6.2sp1-cfp6-bundlelist.txt)

Liste des packages de contenu mis à jour dans AEM 6.2SP1-CFP6

[Obtenir le fichier](assets/do-not-localize/6_2sp1-cfp6-contentpackagelist.txt)

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP5 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Correction de plusieurs problèmes d’interface utilisateur liés au partage, au déplacement, à la publication et au téléchargement de ressources.
* Augmentation de la capacité de la boîte de dialogue Déplacer pour afficher les ressources référencées.
* Correction de plusieurs problèmes liés aux composants et workflows de gestion de contenu Web, tels que Annuler la publication et Purger les versions.
* Amélioration de la réactivité de la barre d’actions concernant l’affichage des actions de barre d’outils et des composants Coral.

### Ressources {#assets-14}

* Amélioration des performances de la fonctionnalité de publication sur Brand Portal. NPR-17189 ; correctif pour CQ-4204150
* Le partage d’un fichier à l’aide de l’option Partager le lien ne crée pas de fichier zip avec une structure de dossiers plate à télécharger. NPR-17513 ; correctif pour CQ-4209381
* La sélection d’un fichier dans la gestion des ressources numériques (DAM) et le fait de cliquer sur Publier ne font pas apparaître l’option Publier sur Brand Portal sur la page Détails de la ressource. NPR-17351 ; correctif pour CQ-94905
* Dans les étapes du workflow de gestion des ressources numériques (DAM), les flux binaires acquis à partir de Session ou ResourceResolver doivent être fermés dans un bloc final afin d’empêcher toute fuite de ressource. NPR-17385 ; correctif pour CQ-4209452
* Le chargement d’un document Word dans la gestion des ressources numériques (DAM) produit une exception de pointeur nul et l’instance de workflow reste bloquée à l’état En cours. NPR-17160 ; correctif pour CQ-4207358
* Les boutons Partager, Déplacer, Publier et Télécharger sont visibles pour les ressources expirées sur la page Éditeur de métadonnées pour les utilisateurs non administrateurs. NPR-16903 ; correctif pour CQ-101440 / CQ-104535
* Les actions telles que Partager, Déplacer, Publier et Copier doivent être visibles pour les administrateurs dans la console Ressources. NPR-16902 ; correctif pour CQ-4207111

### Sites {#sites-14}

* Lors du déplacement d’une page à l’aide de l’interface utilisateur classique et tactile, la boîte de dialogue Déplacer n’affiche pas les références au-delà de 150, ce qui empêche les utilisateurs de mettre à jour ces références et de republier la page. Ce problème a été résolu en introduisant une propriété pour l’interface utilisateur Classic : &quot;maxRefNo&quot; qui peut être configuré sur le nœud siteadmin : « /libs/wcm/core/content/siteadmin ». Cette propriété spécifie le nombre maximum de références (valeur par défaut 150) qui s’affichent avant une opération de déplacement importante et si une page comporte plus de références, elles ne sont pas affichées dans la boîte de dialogue movePage. Cette configuration fonctionne également pour damadmin et miscadmin en appliquant la configuration aux nœuds : `'/libs/wcm/core/content/damadmin'` et `'/libs/wcm/core/content/miscadmin'` respectivement. NPR-17222 ; correctif pour CQ-85878

* Lorsque vous travaillez avec des composants WCM, les liens hypertexte contenant des espaces sont supprimés dans l’éditeur de texte enrichi de l’interface utilisateur tactile. NPR-17698, NPR-17570 ; correctif pour CQ-4206768
* Lors du déclenchement du flux de travail de requête d’annulation de la publication à partir des propriétés de la page, des erreurs JavaScript apparaissent pour les utilisateurs qui ne disposent pas d’autorisations de réplication. NPR-17294 ; correctif pour CQ-102064
* Le rendu ou l’exportation d’un composant d’image HTL remplace l’URL par un numéro, renommant ainsi le fichier, ce qui entraîne la rupture des liens. NPR-17245 ; correctif pour CQ-59616
* La suppression d’un lancement dans un lancement imbriqué entraîne l’abandon des sous-lancements. NPR-17228 ; correctif pour CQ-4202639
* L’exécution de la purge de version dans AEM 6.2 avec Oak 1.4.13 provoque la répétition constante d’un avertissement dans les journaux. NPR-17391 ; correctif pour CQ-4206870
* Après l’installation d’un correctif ou d’une mise à niveau pour le composant ContextHub, le package de contenu remplace tous les segments dans /etc/segmentation/contexthub, ce qui entraîne la perte de tous les segments ContextHub personnalisés. NPR-17250 ; correctif pour CQ-79958
* Pendant l’exécution d’un workflow avec des groupes imbriqués en tant qu’utilisateurs de workflow, le WorkflowStatusProvider (pageinfo.json) provoque le verrouillage de l’instance de workflow. NPR-17555 ; correctif pour CQ-4202056
* Lors de l’utilisation des composants de l’éditeur WCM-Page, un espace vide important est présent à la fin de la page dans le mode de modification de l’interface utilisateur tactile de l’instance de création. NPR-17510 ; correctif pour CQ-4205441
* Le rendu ou l’exportation d’un composant d’image HTL remplace l’URL par un numéro, ce qui entraîne la rupture des liens. NPR-17245 ; correctif pour CQ-59616

### Interface utilisateur {#ui}

* La sélection d’un fichier et le fait de cliquer sur Outils de développement ne fait pas toujours apparaître les actions de barre d’outils dans la barre d’actions en cas de connexion lente et la page doit à nouveau être chargée. NPR-17568 ; correctif pour CQ-108365
* La barre d’actions doit être mise à jour pour utiliser deux conteneurs : coral-actionbar-primary et coral-actionbar-secondary, au lieu de coral-actionbar-container. NPR-17591 ; correctif pour GRANITE-15225

### Mobile à la demande {#mobile-on-demand-2}

* Les utilisateurs disposant d’autorisations de lecture seule sur l’application AEM Mobile ne peuvent pas prévisualiser le contenu de la page de gestion de contenu d’AEM Mobile. NPR-17390 ; correctif pour CQ-4209690

### Sécurité {#security-2}

* Vulnérabilité XSS dans la sortie générée par HTMLRendererServlet. NPR-17136
* Requête visant à empêcher la divulgation des versions AEM dans la page de flux de syndication Web d’AEM. NPR-16219

### Formulaires {#forms-15}

#### Package de modules complémentaires Forms {#forms-add-on-package-15}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

**Formulaires adaptatifs**

* Pour un formulaire adaptatif avec pièce jointe, les doublons d’entrées pour les balises afSubmissionInfo sont créés dans le code XML envoyé lorsque le formulaire est envoyé pour la deuxième fois. NPR-17364
* Lors de l’utilisation du navigateur Google Chrome, après la suppression d’une pièce jointe d’un formulaire, une nouvelle tentative d’ajout de pièce jointe renvoie une erreur. NPR-17297
* En présence de panneaux chargés en différé imbriqués et répétables dans des formulaires adaptatifs basés sur un modèle XSD ou sans formulaire, les valeurs renseignées dans le formulaire ne sont pas conservées dans le Document d’enregistrement (DE). NPR-17176
* Les erreurs affichées dans le journal des erreurs de l’éditeur de règles doivent être ajoutées dans le bloc de capture d’un code JavaScript de bloc try/catch. NPR-16757
* Un clic sur un fichier joint dans un formulaire génère une erreur dans la console du navigateur et ne permet pas d’afficher l’aperçu de la pièce jointe. NPR-17174

**Correspondence Management**

* La fonctionnalité de l’interface utilisateur de création de correspondance est rompue en cas d’ajout d’un texte incorporé ou d’une ligne vierge dans l’interface utilisateur. NPR-17748
* Le navigateur clignote lorsqu’une lettre est ouverte pour modification. NPR-17576
* Lors de l’ajout de fonctions distantes dans des éléments du dictionnaire de données calculés, si le nombre de fonctions est supérieur à la longueur de l’onglet qui affiche les fonctions distantes, la barre de défilement n’apparaît pas dans l’onglet. NPR-17359
* La méthode d’API, import com.adobe.icc.services.api.LetterInstanceService ne fonctionne pas. NPR-17922, NPR-16008
* Une variable ajoutée dans un module de texte n’est pas visible dans le panneau Liaison de données lors de la modification d’une lettre. NPR-17940
* L’interface utilisateur de Correspondence Management ne se lance pas lorsque l’action d’envoi HTML utilise la méthode POST. NPR-17595

**Gestionnaire de formulaires**

* Avec un formulaire adaptatif configuré pour le test AB, un clic sur Lancer le test AB ne lance pas le test et renvoie une erreur de console de navigateur. NPR-17838

**Service Forms**

* Les problèmes signalés dans l’analyse de code statique des formulaires OSGI doivent être résolus. NPR-13951

#### Programme d’installation de Forms JEE {#forms-jee-installer-15}

**Service Output**

* L’utilisation d’AEM Forms 6.2 Output Service pour fusionner un formulaire spécifique avec un fichier XML de données prend 20 fois plus de temps que le temps nécessaire au serveur LiveCycle ES4 SP1 pour la même opération. Cela a été corrigé dans les environnements Windows et Linux. NPR-17501

**Installation de LCM**

* Après avoir installé AEM Forms 6.2 GM et appliqué le CFP AEM 6.2, l’exécution de LiveCycle Configuration Manager fait apparaître un point-virgule indésirable dans les informations de version et la date d’installation du correctif n’est pas mise à jour. NPR-14322

**Process Management**

* La variable TaskContext n’est pas renseignée pour les workflow AEM Forms. CQ-4211857

#### Package de lots AEM Forms JEE {#aem-forms-jee-bundles-package}

* Les fonctionnalités pour les utilisateurs de formulaires doivent être les mêmes avec la console d’interface utilisateur d’administration JEE ou la console OSGi. NPR-17670

### Feature Packs inclus dans CFP5 {#feature-packs-included-in-cfp}

**Package Forms JEE**

Process Management – Espace de travail HTML

* Lors de l’attribution d’une étape à l’espace de travail, l’onglet Pièces jointes de l’espace de travail doit afficher un compteur pour les pièces jointes ou les notes s’il y en a plusieurs. NPR-17771
* Demande de prise en charge d’Office 365 dans AEM JEE Forms pour les fonctionnalités de courrier électronique dans le workflow des formulaires. NPR-13866

**Package de modules complémentaires Forms**

Correspondence Management

* Lors de la modification de fragments d’un aperçu de lettre dans l’éditeur de texte, le texte traité doit apparaître pour modification au lieu des conditions insérées utilisées dans les fragments. NPR-15748, NPR-17504

### Lots OSGi inclus dans CFP5 {#osgi-bundles-included-in-cfp-3}

Liste des lots OSGi mis à jour entre AEM 6.2 SP1 et CFP5

[Obtenir le fichier](assets/do-not-localize/cfp5_osgi_bundles.txt)

Liste des packages de contenu mis à jour entre AEM 6.2 SP1 et CFP5

[Obtenir le fichier](assets/do-not-localize/content-package-cfp5.txt)

Le pack de correctifs cumulés d’AEM 6.2 SP1-CFP4 est une mise à jour importante comportant des correctifs client importants publiés depuis la disponibilité générale d’AEM 6.2 SP1.

Les principaux aspects de ce pack de correctifs cumulés sont les suivants :

* Correctifs dans les ressources pour le rendu de fichier Camera Raw, l’affichage du journal et l’orientation des images
* Amélioration des éléments suivants :

   * Lancements WCM pour les sites
   * Workflow des projets
   * Composants ContextHub

* Correctifs pour Campaign, Mobile on-demand et Translation
* Améliorations de l’utilisation dans l’éditeur de règles des formulaires adaptatifs
* Amélioration de l’éditeur de conditions insérées pour Correspondence Management dans les formulaires
* Correctifs de la gestion des processus et le service Output pour AEM Forms sur JEE
* Correctif lié au Concepteur Forms pour l’éditeur de script

### Plateforme {#platform-12}

* Le formulaire de recherche de Search&amp;Promote ignore le paramètre `environment` lorsque le service cloud est configuré, ce qui le rend inutilisable sur l’instance de création. NPR-16594 : correctif pour CQ-4206076
* L’ajout ou la personnalisation des colonnes dans les résultats de l’**Omni-recherche de ressources** par superposition dans /apps ne fonctionne pas. NPR-16737 : correctif pour CQ-4206785
* La page **Outil de diagnostic** ne fonctionne pas après une mise à niveau statique d’AEM 6.1 SP2 vers AEM 6.2 SP1. NPR-17121 ; correctif pour CQ-4196786
* HTL : lors de la sélection d’un forum et de la création d’une rubrique et d’une publication, `Sightly SightlyCompiledScript` ajoute une propriété `addSelectors` incorrecte à `RequestDispatcherOption`. NPR-17008 : correctif pour GRANITE-16384

* Ajout de la prise en charge de `CRON expressions` dans `ManagedPollConfigs` utilisé par `ReportImporter`. NPR-16608 : demande de correctif pour CQ-4206066

* Le chargement d’une image d’avatar pour un utilisateur LDAP échoue. NPR-16561 ; correctif pour Granite-17013
* Le nombre de résultats affichés sur l’écran User Management est différent dans Carte et dans l’Affichage par liste. NPR-16241 ; correctif pour GRANITE-16914
* Les notifications de workflow ne peuvent pas être chargées en différé pendant l’affichage dans le navigateur Google Chrome en mode Plein écran. NPR-17013 : correctif pour CQ-4207567

### Ressources {#assets-15}

* L’orientation de l’image n’est pas appliquée correctement lors de l’importation d’une image avec une orientation définie. NPR-16750 : correctif pour CQ-4204356
* L’affichage du journal de ressources ne présente aucune ressource même si l’option « Afficher tout » est définie par défaut. NPR-16957 : correctif pour CQ-98780
* Les fichiers Camera Raw (y compris ARW, CR2, NEF, DNG et EPS), lorsqu’ils sont ajoutés comme rendu dans les ressources, ne peuvent pas être sélectionnés ni supprimés. Ces fichiers sont téléchargés automatiquement lorsque l’utilisateur clique dessus. NPR-16949 : correctif pour CQ-4206846
* La création d’un pdf dans un autre pdf dans l’interface utilisateur Assets n’affiche pas les pdf créés dans l’interface utilisateur DAM, bien qu’ils soient visibles dans le référentiel crx. NPR-16833 : correctif pour CQ-4206501
* Le téléchargement d’une ressource en tant que nœud enfant direct de soi-même à l’aide de l’IU tactile provoque un problème. La ressource est téléchargée en tant qu’enfant direct de la ressource précédemment sélectionnée. NPR-16534 : correctif pour CQ-4204287
* Dans l’interface utilisateur DAM, le fait de commenter une ressource et de marquer un utilisateur dans le commentaire ne produit pas de notification par courrier électronique. NPR-16589 : correctif pour CQ-102318

### Projets {#projects-3}

La console de workflow des projets affiche une exception NullPointerException sur la page lorsque des workflows sont purgés. NPR-17017 : correctif pour CQ-4194269

### Sites {#sites-15}

* Les fichiers dans `ContextHub` ne sont pas réduits sur l’instance de création. NPR-17022 : correctif pour CQ-79456
* La conversion du lancement de WCM-Launches prend beaucoup de temps pour promouvoir un lancement constitué d’une grande arborescence de page. NPR-16480 : correctif pour CQ-82731
* Le rendu de condition de segment `ClientContext` se bloque lorsqu’un segment (ou une audience) est créé avec une règle qui ne fonctionne pas ou qui n’est pas terminée. NPR-16759 : correctif pour CQ-4205104
* Dans WCM Launches, la publication des pages associées à un lancement n’est pas annulée lorsque l’action est lancée à partir des propriétés de la page dans l’interface utilisateur tactile. NPR-16560 : correctif pour CQ-4204681
* L’outil de réécriture de liens réécrit par erreur des valeurs href contenant un signe « deux-points » (:) en supposant qu’il définit un espace de nommage JCR. NPR-16753 : correctif pour CQ-4203762
* Dans l’outil d’importation WCM-Design, l’ouverture d’une page d’importation de test et la tentative de chargement d’un fichier zip provoquent des problèmes s’il a été chargé et supprimé précédemment. NPR-16486 : correctif pour CQ-90962
* La navigation vers le volet **[!UICONTROL Navigation globale]** à l’aide des navigateurs Firefox, Safari et Google Chrome offre une expérience utilisateur différente. Le navigateur Firefox affiche le menu **[!UICONTROL Outils]** tandis que le navigateur Google Chrome affiche le menu **[!UICONTROL Navigation]**. NPR-16770 ; correctif pour CQ-4200456

### Campagne {#campaign}

* Lors du test des modèles de campagne AEM et de la modification des adresses de contrôle pour inclure des « données supplémentaires », la liste déroulante Adobe Campaign disparaît de l’interface utilisateur tactile de Context Hub. NPR-16771 : correctif pour CQ-105748

### Mobile on-demand {#mobile-on-demand-3}

* Lors du contrôle en amont d’une publication depuis l’environnement de création d’AEM, une action de contrôle en amont qui dure plus de 5 secondes provoque un pic inhabituel sur le tableau de bord d’intégration AEMM – AEM PECS avec un grand nombre de demandes d’état par seconde. NPR-16908 : correctif pour CQ-4207055
* La gestion de la configuration d’AEM Mobile échoue après l’installation de la mise à jour d’AEM-6.2-SP1-CFP1-1.0. NPR-16909 : correctif pour CQ-4204892

### Traduction {#translation-7}

* La prévisualisation des tâches de traduction ne fonctionne pas après l’installation de 6.2 SP1 – CFP1. NPR-16481 ; correctif pour CQ-4204655
* La copie de langue créée à l’aide de la traduction pointe vers la racine principale au lieu de la Live Copy locale du pays. NPR-17257 ; correctif pour CQ-4208287

### Sécurité {#security-3}

* Aucune validation de type MIME n’est réalisée lorsque les binaires des fichiers sont transférés vers AEM. NPR-16617
* Problèmes de téléchargement d’images d’avatar pour les utilisateurs LDAP. NPR-16561

### Formulaires {#forms-16}

#### Package de modules complémentaires Forms {#forms-add-on-package-16}

**Formulaires adaptatifs**

* Dans l’éditeur de formulaires adaptatifs, le commentaire de Paramètre cible dans head.jsp doit être remplacé par la nouvelle instruction Context Hub. NPR-17173
* Dans l’éditeur de règles de formulaires adaptatifs, **[!UICONTROL Choisir un élément]** affiche l’événement comme « nul ». NPR-17139
* Le formulaire envoyé est de nouveau envoyé lors de la navigation vers l’avant à l’aide de la flèche vers l’avant (>). NPR-17080
* Lors de l’envoi d’un formulaire adaptatif via AJAX, la fonction de rappel « error » n’est jamais appelée en cas d’erreur. NPR-17034
* Un clic sur le bouton **[!UICONTROL Enregistrer le formulaire]** dans l’éditeur de règles au moment de l’exécution ne permet pas d’enregistrer le formulaire. NPR-16905
* Le texte statique doit être exclu de l’ordre de tabulation dans le formulaire adaptatif. NPR-16749
* La valeur calculée d’un champ décimal n’apparaît pas correctement. NPR-16596
* L’icône permettant d’afficher le contenu de l’aide doit être incluse dans l’ordre de tabulation des formulaires adaptatifs. NPR-16484
* Prise en charge de l’utilisation d’une expression régulière de type `dataRef=C:/Users/` dans la **[!UICONTROL configuration du service de préremplissage par défaut]** pour le préremplissage des données pour les formulaires adaptatifs. NPR-16425

* Les validations ne sont pas déclenchées correctement pour tous les panneaux en cas de scénario chargé différé imbriqué. NPR-15821

**Correspondence Management**

* Le rendu de lettre échoue si une lettre contient un module de texte vide (un module sans texte). NPR-17054
* Les sauts de ligne et les espaces de tabulation sont supprimés du contenu après avoir été collés dans l’éditeur de texte. NPR-17039
* L’affichage des références d’un module de texte prend beaucoup de temps si le module de texte est référencé dans de nombreuses lettres. NPR-17035
* La modification, l’enregistrement, la suppression et la définition de la référence pour les fragments de document prennent beaucoup de temps. NPR-17033
* Le texte justifié est rendu dans une autre police lors de l’aperçu de la lettre. NPR-16976
* La fonctionnalité de recherche ne fonctionne pas correctement si le texte recherché comporte plusieurs occurrences. NPR-16920
* La barre d’outils de l’éditeur de texte apparaît par intermittence dans le navigateur. NPR-16919
* La commande **[!UICONTROL Enregistrer le formulaire]** de l’éditeur de règles ne fonctionne pas. NPR-16905
* La liste déroulante Police ne renseigne pas la famille de polices lors de la création d’un module de texte sur la base du dictionnaire de données à l’aide d’Internet Explorer. NPR-16944
* Après avoir créé un fragment de texte, la police de la lettre change lors de l’aperçu de la lettre. NPR-16830
* Les lettres avec des espaces de tabulation au début ou entre des expressions du fragment de document ne peuvent pas être rendues ni prévisualisées. NPR-16769

**Mobile Forms**

* L’aperçu Mobile Form affiche un contenu superposé, bien que le formulaire soit affiché correctement pour le rendu PDF. NPR-17105

**Portail Formulaires**

* Un clic sur le lien **[!UICONTROL Télécharger]** pour un formulaire envoyé fait apparaître une page HTML au lieu d’un formulaire PDF. NPR-17082

* Les `Upload Comments` pour les pièces jointes ne sont pas affichés dans l’interface utilisateur pour les instances envoyées, bien qu’ils soient présents dans le fichier XML stocké dans le référentiel crx. NPR-17075

**Service Reader Extensions**

* Un fichier spécifique n’est pas étendu à Reader sur l’installation OSGI d’AEM Forms. NPR-16625

#### Programme d’installation de Forms JEE  {#forms-jee-installer-16}

**Base**

* Lors du processus de mise à niveau, Configuration Manager échoue en raison du délai d’expiration. NPR-16774 (voir [Configuration du délai d’expiration pour les opérations au niveau du composant](install-cfp-aem-forms-jee.md#configuring-timeout-for-operations-at-component-level-npr)).

**Process Management – Espace de travail HTML**

* Le point de départ depuis Démarrer la tâche ne commence pas par les données soumises au moment de l’envoi du point de départ. NPR-16917
* Un clic sur le bouton **[!UICONTROL Retour]** pour un formulaire dans l’espace de travail HTML ne ferme pas le formulaire, mais le renvoie à sa file d’attente de groupe.\
   NPR-16352

**Process Management**

* Autoriser les utilisateurs de définir le nom d’affichage des tâches précédentes sur l’une des tâches suivantes d’une instance de processus. NPR-15382

**Service Output**

* Le service Output ne parvient pas à traiter un fichier PDF qui est modifié pour inclure un champ « milli-sec » supplémentaire dans les métadonnées `date-time format`. NPR-16838

#### Concepteur Forms {#forms-designer}

* L’éditeur de script AEM Designer ne respecte pas les valeurs par défaut des propriétés de formulaire pour `Calculate Event`et `Validate Event`. NPR-15921

### Feature Packs inclus dans CFP4 {#feature-packs-included-in-cfp-1}

**Package de modules complémentaires Forms**

* Amélioration de l’éditeur de conditions en ligne pour Correspondence Management. NPR-10981

### Lots OSGi inclus dans CFP4 {#osgi-bundles-included-in-cfp-4}

Liste des lots OSGi mis à jour entre AEM 6.2 SP1 et CFP4

Les principaux aspects du CFP3 sont les suivants :

* Fonctionnalité de recherche plus efficace pour l’interface utilisateur Classic et pour le composant de recherche AEM à l’aide du proxy avec authentification Digest
* Corrige les problèmes lors du chargement de ressources et de l’affichage de métadonnées de ressources
* Corrige les problèmes lors de la création de dossiers et du déplacement de pages au cas où le titre comporte des caractères spéciaux.
* Correctifs pour l’utilisation des audiences de ciblage-synchronisation, la publication de campagnes et la sélection de la mesure de l’objectif dans l’interface utilisateur tactile
* Résout des problèmes de synchronisation pour les tâches de traduction
* Renforce la sécurité du service de préremplissage Forms
* Améliorations du composant d’envois et de brouillons du portail de formulaires et du service Barcoded Forms
* Améliorations de l’utilisation des formulaires adaptatifs contenant des widgets de pièce jointe ou des fragments chargés différés.
* Améliorations de l’utilisation de Correspondence Management, notamment la fonctionnalité de recherche, la journalisation des ressources supprimées et l’importation de dictionnaires de données.

### Plateforme {#platform-13}

* Une condition de course dans **ModelAdapterFactory**, qui est possible lorsque deux threads essaient d’injecter le même champ, entraîne l’échec de le construction du modèle. NPR-16443 : correctif pour SLING-6584
* Option de validation dans le gestionnaire de modules pour détecter tout conflit entre un fichier recouvert (fichier JSP ou JavaScript) sous /apps et celui qui est contenu dans un correctif sous /libs. Le recouvrement affecté peut alors être réévalué afin d’inclure les modifications du fichier sous /libs. NPR-16216 : correctif pour CQ-81729
* La consignation dans le fichier error.log s’arrête parfois quelques secondes après le démarrage de l’éditeur et doit être effacée pour s’exécuter à nouveau. Demande de mise à jour du cadre de journalisation et de fourniture de la journalisation Sling. NPR-15913 : correctif pour Granite-15452
* Demande de mise à jour de l’API JavaScript `use"` pour éviter toute erreur dans l’implémentation de l’API d’utilisation de JavaScript HTL. NPR-16461 : correctif pour SLING-6780

### Sites {#sites-16}

* Après la mise à niveau d’AEM 6.0 vers AEM 6.2, l’interface utilisateur classique est lente lors de la recherche de balises en raison de nombreuses requêtes. Pour résoudre ce problème, vous pouvez suivre les étapes mentionnées sous [Désactivation de l’état de réplication dans la console de balisage (interface utilisateur Classic)](#disable-replication-status-in-tagging-console-classic-ui-npr). NPR-15842 : correctif pour CQ-4201748.

* Lors de la création d’une page dans l’interface utilisateur tactile, la vérification d’entrée pour le champ « nom » ne vérifie pas le caractère spécial « Apostrophe » (identique à celui de l’interface utilisateur classique). La page ne peut donc pas être déplacée. NPR-16404 : correctif pour CQ-4205321.
* L’application puis la fusion de styles différents sur deux lignes dans l’éditeur de texte enrichi supprime le style appliqué sur la deuxième ligne. NPR-16389 : correctif pour CQ-4203835.
* Sur l’écran Sites de l’interface utilisateur tactile, une tentative de collage d’une page à l’intérieur d’une page sans sous-page ne fonctionne pas car le bouton Coller n’apparaît pas. NPR-15894 : correctif pour CQ-4201696.
* Lors du défilement de l’onglet Pages de l’outil de recherche de contenu, quelques jeux de pages sont affichés indéfiniment dans l’interface utilisateur classique, tandis que l’interface utilisateur tactile présente un ensemble limité de pages non répétées. NPR-16271 : correctif pour CQ-4202371
* L’ouverture des propriétés de page d’une LiveCopy dans l’interface utilisateur tactile et le fait de cliquer sur Enregistrer sans modification entraîne l’écriture de tout onglet LiveCopy et la création d’un nœud de configuration LiveSync. NPR-16327 : correctif pour CQ-108562
* La contrainte de formulaire ne peut pas lire la propriété `ConstraintMessage`. NPR-16388 : correctif pour CQ-101330
* Le composant `wcm/foundation/components/parsys` n’affiche pas l’espace réservé **[!UICONTROL « Faire glisser les composants ici]** ». NPR : 16748 : correctif pour CQ-4205187

### Ressources {#assets-16}

* PDF Rasterizer cesse de fonctionner et provoque des problèmes d’épuisement de la mémoire après l’installation de la version 6.2 SP1 ou du correctif 12430. NPR-15991
* Les métadonnées d’une propriété de chaîne, `documentNumber`, apparaissent sous la forme d’une date alors qu’il devrait s’agir d’un nombre. NPR-16134 : correctif pour GRANITE-16916
* Troncatures de texte dans la bulle de événement du journal. NPR-16226 : correctif pour CQ-85226
* Lors de la création d’un dossier sous la hiérarchie de contenu avec un titre comportant des caractères spéciaux, la forme codée du caractère spécial est affichée. NPR-15935 : correctif pour CQ-4202987
* L’utilisateur ne peut pas télécharger de fichiers ni créer de dossiers lors de la navigation parmi les ressources en raison d’un comportement incohérent lors de l’utilisation du bouton « Créer ». NPR-16410 : correctif pour CQ-4204793
* Des erreurs inattendues se produisent lors du chargement de ressources HTML partagées à partir de la vue d’articles dans le composant AEM Authoring. NPR-16133 : correctif pour AEMM-4155970

### Intégration {#integration-14}

* Lors de l’activation de l’authentification par proxy avec l’authentification Digest, le composant AEM Search renvoie une exception ConcurrentModificationException. NPR-15309 : correctif pour CQ-4199191
* Lors de la création d’une activité de test A/B de cible dans AEM, l’audience ne se synchronise pas avec la Cible et affiche « aucune audience ». NPR-16229 : correctif pour CQ-4204210
* Après avoir installé SP1+NPR-11577 v1.2, lorsque vous sélectionnez « Utiliser une mesure d’analyse » pour la mesure de l’objectif lors du ciblage dans l’interface utilisateur tactile, la liste déroulante des mesures ne se charge jamais. NPR-16129 : correctif pour CQ-4204316
* Lors de l’utilisation du ciblage, la publication de la campagne ne publie pas automatiquement l’intégralité de l’arborescence, y compris la marque et le principal. NPR-15855 : correctif pour CQ-94630

### Traduction {#translation-8}

* La tâche de traduction de synchronisation n’est pas déclenchée automatiquement et l’interrogation d’AEM ne se produit pas sans interroger les projets de traduction. NPR-15163 : correctif pour CQ-90856

### Formulaires {#forms-17}

#### Package de modules complémentaires Forms {#forms-add-on-package-17}

**Formulaires adaptatifs**

* Lors de l’enregistrement d’un formulaire adaptatif avec une pièce jointe, le chemin d’accès complet de la pièce jointe est ajouté à la balise `fileAttachment` du code XML généré plutôt qu’au nom de la pièce jointe. NPR-16529
* Dans les formulaires adaptatifs basés sur XDP, le wrapper `afData/afBoundData` est présent dans le code XML envoyé même si le code XML prérempli ne contient pas de wrapper `afData/afBoundData`. NPR-16118

* Notation exponentielle dans le champ Nombre : lors de l’utilisation de formulaires adaptatifs, si un nombre avec une fraction décimale de plus de dix caractères au total est entré, le nombre se transforme en notation exponentielle dans le code XML envoyé. NPR-16106
* Pour les formulaires qui contiennent à la fois un composant de pièce jointe et un fragment chargé différé, le fichier XML de données envoyé ne contient pas les informations relatives au composant de pièce jointe. NPR-16022
* Pour un panneau répétable chargé en différé qui n’a pas d’ancêtre répétable, les enfants répétables dans une deuxième instance du panneau ne se répètent pas. NPR-15944
* Lorsque vous essayez d’enregistrer un fragment dans un fragment dans l’éditeur de formulaires, la racine du modèle de fragment ne renseigne pas la valeur du fragment enfant. NPR-15943
* Lors de la création d’une case à cocher avec un seul élément et d’une tentative d’affichage du titre de la case à cocher en conservant le titre de l’élément masqué, l’action de création de dictionnaire renvoie `ArrayIndexOutOfBoundException` si le texte de l’élément est vide. Le dictionnaire n’est pas créé et aucune réponse d’erreur n’est générée à l’écran. NPR-15816
* Pour les formulaires adaptatifs avec des widgets de pièce jointe, certaines parties du formulaire sont désactivées une fois le fichier joint prévisualisé.\
   NPR : 16611

* Pour les widgets de pièce jointe où plusieurs pièces jointes sont autorisées, si une nouvelle instance de formulaire avec pièce jointe est envoyée sur un widget comportant une pièce jointe précédente, un code d’erreur est affiché lors de l’ouverture de la pièce jointe ajoutée au lieu du contenu réel. NPR-16258
* Protection du service de préremplissage de formulaires contre un accès non autorisé par le biais de protocoles tels que `file://`, `http://` et `ftp://`. Voir « [Configuration du service de préremplissage à l’aide de Configuration Manager](https://helpx.adobe.com/aem-forms/6-2/prepopulate-adaptive-form-fields.html#main-pars_header_944235754). » NPR-15414

* Requête de rendu du formulaire adaptatif au format PDF plutôt que HTML à l’étape de vérification et ajout de toutes les pièces jointes au PDF, de sorte que l’impression présente le formulaire complet. NPR-9011

**Correspondence Management**

* Lorsque vous travaillez avec un fragment de texte dans une lettre en mode Aperçu/Modification, si le texte est converti en liste, la fonctionnalité de lettre entière est sans effet et une erreur JavaScript est générée. NPR-16460
* L’importation d’un fichier XSD pour créer un dictionnaire de données dans le nœud Correspondence Management échoue car le navigateur ne répond plus à chaque fois que le fichier XSD est chargé et que le nœud racine est sélectionné. Ce problème est indépendant du navigateur et n’apparaît pas dans les journaux du serveur. NPR-16452
* Lors de la prévisualisation d’une lettre à l’aide du navigateur Internet Explorer et d’une tentative de modification de la taille de police du contenu, les valeurs apparaissent en double de 8 à 72 dans la liste déroulante de taille de police. NPR-16387
* Si un champ flottant apparaît comme champ de saisie à partir d’un fragment XDP, le champ ne s’étend pas dans l’aperçu de lettre lors de l’utilisation du navigateur Internet Explorer. NPR-16367
* Lorsque vous tentez d’envoyer une lettre directement à partir de l’aperçu, la fenêtre contextuelle du nom de la lettre n’est pas affichée correctement car elle est masquée. NPR-16353
* Les espaces de ligne ajoutés lors de la modification d’une lettre ne sont pas reflétés dans la fenêtre d’aperçu. Pour les listes dans des fragments de texte, l’espacement de la sortie PDF n’est pas correct. NPR-16267
* Lorsque vous travaillez sur un fragment de document de texte à l’aide du navigateur Internet Explorer, la tentative de mise en retrait du texte échoue car le curseur n’autorise pas la mise en retrait du texte. NPR-16128
* L’ajout ou la modification d’un dictionnaire de données en fragment de document de texte existant prend beaucoup de temps et l’utilisateur n’est pas toujours informé. NPR-16102
* Lors de la prévisualisation d’une lettre avec un contenu défilant à l’aide du navigateur Internet Explorer, la barre de défilement du navigateur chevauche la barre de défilement de la lettre et le contenu entier ne peut pas être affiché pour les fragments sur le côté droit. NPR-16068
* Lors de la création ou de la modification de fragments de document de texte à l’aide du navigateur Google Chrome, la liste déroulante de sélection de couleurs apparaît automatiquement et ne peut pas être supprimée. L’utilisateur doit sélectionner la liste comme type de saisie de données pour pouvoir modifier le fragment. NPR-16067
* Lors de l’utilisation de l’API Letterinstance, la méthode `import com.adobe.icc.services.api.LetterInstanceService` ne fonctionne pas. NPR-16008
* Le passage des formats d’affichage de date sur `locale=en_US; dateFormat=MMM dd,yyyy;` dans la configuration d’Asset Composer ne fonctionne pas comme prévu et le format de date est affiché avec des caractères indésirables. NPR-16007
* Le type de liaison de données dans les lettres lors de la recréation est affiché comme « Utilisateur » même s’il avait été défini différemment auparavant. NPR-16619

**Portail Formulaires**

* Les scénarios de mise à niveau des composants brouillons et envois ne fonctionnent pas avec l’exemple d’implémentation de base de données. NPR : 16752

**Service Barcoded Forms (BCF)**

* L’analyse de code statique du service Barcoded Forms (BCF) signale des problèmes. NPR-13855

#### Programme d’installation de Forms JEE  {#forms-jee-installer-17}

**Process Management – Espace de travail HTML**

* Sécurisation du service de préremplissage de formulaires contre un accès non autorisé par le biais de protocoles tels que « file:// », « http:// » et « ftp:// ». Pour plus d’informations, voir [Configuration du service de préremplissage à l’aide de Configuration Manager](https://helpx.adobe.com/aem-forms/6-2/prepopulate-adaptive-form-fields.html#main-pars_header_944235754). NPR-15434

**Gestion des utilisateurs**

* L’écran de connexion SAML affiche une version incorrecte (6.1.0) sur le serveur AEM 6.2. NPR-13825
* Avec AEM Forms configuré pour l’authentification unique (Kerberos), si l’authentification de l’utilisateur échoue lors de la tentative de connexion, un code d’erreur « 404 » est renvoyé. L’utilisateur est redirigé vers le site de connexion uniquement après avoir actualisé la page. NPR-15015

#### Concepteur Forms {#forms-designer-1}

* Le passage de la langue du formulaire sur le français (Canada) dans la vérification orthographique du dictionnaire ne fonctionne pas dans AEM Forms Designer.\
   NPR-15896

### Feature Packs inclus dans CFP3 {#feature-packs-included-in-cfp-2}

**Package de modules complémentaires Forms**

* Lors de la suppression de toute ressource dans Correspondence Management, un message d’avertissement doit être consigné dans le fichier error.log. NPR-13225
* Améliorez la fonctionnalité de recherche tout en prévisualisant une lettre dans Correspondence Management afin d’activer la recherche de texte dans le contenu du fragment de texte plutôt que de rechercher uniquement l’étiquette ou le titre de la lettre. NPR-16103

### Lots OSGi inclus dans CFP3 {#osgi-bundles-included-in-cfp-5}

Liste des lots OSGi mis à jour entre AEM 6.2 SP1 et CFP3

[Obtenir le fichier](assets/do-not-localize/osgi_bundle_list_for_aem-6.2sp1-cfp3.txt)
Les principaux aspects du pack de correctifs cumulés 2 sont les suivants :

* Correctifs de stabilité et améliorations des performances de la plateforme AEM, y compris les opérations et le cadre Sling
* Amélioration de la gestion des ressources avec plusieurs correctifs pour l’accès, le déplacement, la recherche, le chargement et la publication des ressources
* Amélioration de la création et de la gestion des sites avec des correctifs dans les composants Context Hub, Fragments de contenu, Diaporama et module d’ancrage
* Plusieurs correctifs dans l’interface utilisateur tactile, notamment l’éditeur de texte, Omni-recherche et le processus de création de variantes
* Amélioration des workflows de traduction ; amélioration du connecteur Microsoft pour l’utilisation de nouvelles API de traduction pour le portail Azure
* Correctifs dans Projets et Campagne
* Amélioration de la création et de la gestion grâce à des correctifs dans les formulaires adaptatifs, la gestion de la correspondance et les fonctionnalités du portail de formulaires
* Correctifs dans les composants de l’espace de travail Forms JEE de base, XTG et HTML

### Plateforme {#platform-14}

* `SlingPostProcessor` est déclenché si la page qui référence directement le cadre Sling est modifiée. NPR-15754 : correctif pour CQ-104153

* La valeur pour les balises avec la propriété `tagBasePath` n’est pas récupérée dans la boîte de dialogue de l’interface utilisateur Classic lors de la navigation jusqu’à un composant de page. NPR-15543 : correctif pour CQ-4199950

* Lorsque vous effectuez des opérations Sling, lorsque vous avez un bloc nommé « chunk_n_n-1 », `SlingFileUpload handler.getLastChunk` forme une boucle sans fin avec des blocs vides. NPR-15455 : correctif pour SLING-5701

* Lorsqu’une interface étend une autre interface, les méthodes injectables sur la super interface ne sont pas injectées correctement. NPR-15202 : correctif pour SLING-5710
* Une exception potentielle de pointeur nul n’est pas empêchée lors de l’utilisation de l’appel de fonction `com.adobe.granite.infocollector.impl.FilesTraversal`. NPR-15169 correctif pour CQ-4197640
* L’état du workflow est incohérent pour certains nœuds secondaires et une erreur apparaît pendant la distribution d’événements d’observation pour ce nœud. NPR-15701 : correctif pour GRANITE-13786
* Lorsque l’utilisateur sélectionne un nœud dans CRXDE (par exemple /content/dam/) puis l’onglet « Contrôle d’accès » en s’assurant de l’existence d’une liste de contrôle d’accès, un glisser-déposer de certains éléments permet de déplacer les autres éléments que celui sélectionné. NPR-15696 correctif pour GRANITE-16300
* La sélection d’un utilisateur depuis la liste déroulante lors d’une tentative d’emprunt d’identité entraîne la disparition de l’ensemble de la fenêtre contextuelle de l’utilisateur. NPR-15774 : correctif pour CQ-4201738/GRANITE-11895
* Dans Omni-recherche, la recherche par balises avec des suggestions renseignées automatiquement ne fonctionne pas. NPR-15088 : correctif pour GRANITE-14426.\
   Remarque : Ce correctif nécessite Oak CFP 1.4.11 ou version supérieure.

### Auteur AEM Mobile {#mobile-aem-author}

* Lors de l’utilisation de packages AEM Mobile et ContentSync avec une application hybride, AEM répond à une demande de récupération (horodatages) effectuée par l’application avec le package le plus ancien, au lieu de celui qui est demandé par l’application. NPR-15749 : correctif pour CQ-104153

### Sites {#sites-17}

* L’état de modification de la boîte de réception Flux de travail dans le noyau de gestion de contenu web ne change pas si l’utilisateur modifie une page après l’activation d’un workflow. NPR-15684 : correctif pour CQ-4196974
* Le module d’ancrage dans l’éditeur de texte enrichi pour l’interface utilisateur tactile génère du code HTML5 non conforme lorsque l’utilisateur clique sur l’icône d’ancrage et ajoute un nom. Il doit ajouter un attribut « id » au lieu de « name » dans la balise HTML5 pour l’élément d’ancrage. NPR-15650 : correctif pour CQ-89782
* Lorsqu’un schéma de métadonnées comportant de nombreux champs est créé et appliqué aux métadonnées du fragment de contenu, aucune barre de défilement n’est créée sur l’écran de métadonnées du fragment de contenu, ce qui empêche toute modification des champs. NPR-15478 : correctif pour CQ-4202622
* La modification du composant de champ `TagInput` n’affiche pas les valeurs configurées précédemment par rapport aux champs de la boîte de dialogue. NPR-15464 : correctif pour CQ-4200360

* Dans l’interface utilisateur de l’éditeur de fragments de contenu, si de nombreuses variantes d’un fragment de contenu sont créées, le panneau latéral n’affiche pas la barre de défilement pour parcourir toutes les variations. NPR-15445 : correctif pour CQ-4199444
* Lors de la suppression d’utilisateurs de groupes directs, ils sont ajoutés aux groupes hérités. NPR-15400 : correctif pour CQ-98758
* Création WCM : l’auteur de l’interface utilisateur tactile ne permet pas la modification de pages dont le nom contient des virgules. NPR-15396 : correctif pour CQ-4199723
* Lors de l’utilisation de l’interface utilisateur tactile pour la création, la fonction `Granite.author.editableHelper.doSelectParent` transmet les arguments dans le mauvais ordre, ce qui entraîne une erreur JavaScript. NPR-15349 : correctif pour CQ-4198594
* Le segment ContextHub affiche l’expérience même si le cookie de droit d’opposition est présent. NPR-15293 : correctif pour CQ-4198024
* Le composant Diaporama de l’interface utilisateur Classic ne peut pas créer de diapositives ni faire glisser-déposer des images pour créer de nouvelles diapositives. NPR-15281 : correctif pour CQ-4194164
* Les utilisateurs, indépendamment de leur autorisation, peuvent voir les options « Créer » telles que Créer une page, Créer un site, Créer une Live Copy, Créer un lancement et Créer un catalogue dans la console d’administration de Site. NPR-15278 : correctif pour CQ-94436
* Après l’installation d’AEM 6.2 Service Pack 1, le curseur « Inclure les sous-pages » ne fonctionne plus pour les lancements de pages. NPR-15230 : correctif pour CQ-4198449
* Demande d’amélioration de la purge de version pour récupérer et traiter les versions en blocs et pouvoir utiliser un chemin spécifié dans une requête XPath. NPR-15186 : correctif pour CQ-109205
* Il manque le bouton Effacer dans l’onglet miniature Propriétés de la page du composant Sites. NPR-15143 correctif pour CQ-4196997
* Pour un site qui utilise des Live Copies, la sélection de la case à cocher « Live Copy » dans le volet Colonnes de la console d’administration du site ne permet pas d’afficher correctement l’état de Live Copy. Seule l’annotation HTML est affichée. NPR-15108 : correctif pour CQ-97086
* Lors de la modification de fragments de contenu, si l’utilisateur clique sur Terminé (« √ ») pour le modifier avant d’obtenir la réponse de la publication, le contenu modifié n’est pas enregistré correctement. NPR-15014 : correctif pour CQ-4194095
* La fermeture de la page Modifier en mode de distorsion du temps associée à une tentative de réouverture de la page à partir de Siteadmin provoque une erreur avec l’état « 500 » au lieu de rouvrir la page. NPR-14965 : correctif pour CQ-109647 :
* Dans l’interface utilisateur de gestion des ressources numériques (DAM), la recherche du sélecteur d’utilisateur Rechercher des autorisations produit une exception « Mémoire insuffisante ». NPR : 15307 : correctif pour CQ-98542

### Ressources {#assets-17}

* Après avoir recherché un fichier dans Omni-recherche, un utilisateur qui sélectionne une ressource et tente de modifier ses propriétés en cliquant sur « Afficher les propriétés » puis sur le bouton « Enregistrer » est redirigé vers une page vierge. NPR-15900 : correctif pour CQ-4202372
* L’interface utilisateur Assets ne répond pas aux événements. La sélection d’une ressource suivi d’un clic sur « Publier » ou « Rendus » n’entraîne aucune activité. NPR-15828 : correctif pour CQ-4202247
* Lors de la publication d’une ressource en mode Carte, la Carte n’est pas mise à jour pour refléter un état publié à moins que la page soit actualisée. NPR-15826 : correctif pour CQ-102732
* Correctif cumulé contenant des correctifs de ressources. NPR-15225
* Si le caractère esperluette (« &amp; ») est inclus dans le nom d’un dossier de ressource, le nom du dossier n’est pas affiché correctement lors de la navigation vers cette ressource. NPR-15775 : correctif pour CQ-4201735
* L’utilisation d’une esperluette (« &amp; ») dans le nom d’un fichier de ressource entraîne des problèmes lors de l’accès à ses propriétés. NPR-15770 : correctif pour CQ-4201737
* Lors de la navigation parmi les ressources et de l’utilisation du mode d’affichage Colonnes, si l’utilisateur actualise la page après avoir sélectionné et cliqué sur une ressource, les détails de cette ressource apparaissent à la place du contenu actualisé. NPR-15768 : correctif pour CQ-4201727
* L’ingestion PDS consomme 100 % d’UC avec un tas de bibliothèques pour les services pdf. NPR-15606 : correctif pour GRANITE-12929
* L’accès à l’interface utilisateur « My Link Shares » avec le navigateur Firefox ne permet pas d’afficher les éléments ou utilisateurs partagés et l’écran est inutilisable. NPR-15539 : correctif pour CQ-4200992
* Lors de l’utilisation de la gestion des ressources numériques, si une page est associée à un ensemble d’images, le déplacement des images vers un nouveau dossier rompt l’association des pages et certaines images manquent sur la page associée. NPR-15538 : correctif pour CQ-111479
* Dans le composant Dam Viewer, l’utilisation du mode d’exécution « nosamplecontent » entraîne des erreurs avec le média dynamique. NPR-15449 : correctif pour CQ-4195425
* Lors de la création de profils vidéo, si des paramètres prédéfinis de codage vidéo de qualité élevée et de qualité moyenne sont sélectionnés, les modifications apportées ne sont pas enregistrées. NPR-15447 : correctif pour CQ-4195482
* Malgré l’échec du chargement d’une ressource sur Brand Portal en raison d’une réponse d’erreur du serveur, l’état est mis à jour sur « Publié » sur l’interface utilisateur Brand Portal, ce qui rend difficile d’assurer le suivi du fichier manquant. NPR-15442 : correctif pour CQ-4197968
* Lors de la publication d’un dossier de ressources sur Brand Portal, si la publication dure plus d’une heure, certains fichiers ne sont pas publiés. NPR-15441 : correctif pour CQ-4199493
* Lors de l’utilisation de la console Asset Finder en mode Colonnes, une tentative de création de dossier échoue la première fois mais fonctionne lors de l’essai suivant. NPR-15370 : correctif pour CQ-4199448
* Si le nom d’une ressource ou d’un dossier sélectionné dans l’interface utilisateur DAM comporte une virgule, l’onglet Références n’est pas disponible et affiche le message « La Liste des références n’est pas disponible pour plusieurs sélections ». NPR-15362 : correctif pour CQ-4199721
* La publication d’un dossier sur Brand Portal ne modifie pas l’état de publication du dossier, même si les ressources du dossier sont publiées avec succès. NPR-15292 : correctif pour CQ-4197667
* Lorsque vous accédez à la console Assets dans l’interface utilisateur tactile, une exception apparaît lors de l’activation de certaines ressources. NPR-15217 : correctif pour CQ-108779
* Publication d’une vidéo sur YouTube lorsque la connexion est établie par le biais d’un serveur proxy. NPR-15109 : correctif pour CQ-110332
* L’utilisation d’un fichier dont le nom contient un point (.) dans data-sly-resource ne dirige pas vers la même ressource et le chemin de sortie se termine au niveau du point. NPR-15069 : correctif pour CQ-4195914
* Après la mise à niveau d’AEM 6.2 vers le Service Pack1, la synchronisation des ressources dans Scene7 échoue. La propriété dam:Scene7FileStatus affiche l’état « `UploadFailed` » même pour les ressources publiées. NPR-15269 : correctif pour CQ-4197708

### Interface utilisateur {#user-interface-5}

* Dans l’**[!UICONTROL interface utilisateur tactile]**, la date enregistrée n’est pas affichée pour les champs de date qui n’ont pas de type=&#39;datetime&#39; lors de l’utilisation du navigateur Internet Chrome version 56.0.2924.87. NPR-15383 : correctif pour GRANITE-16481
* Dans l’**[!UICONTROL interface utilisateur tactile]**, l’éditeur de texte enrichi supprime le thread et les éléments de légende des tables HTML lors du rendu. NPR-15267 : correctif pour CRTE-41
* `FileUpload Validator` ne traite pas les cas lorsque le démarrage automatique est défini sur true ou lorsque `uploadFile()` est appelé manuellement et génère un rapport de validation non valide dans ces cas. NPR-15295 : correctif pour GRANITE-13499

* Omni-recherche ne permet pas aux clients qui utilisent /apps d’ajouter une source de données de colonne, car la configuration de l’emplacement est supposée être répertoriée sous */libs/granite/omnisearch/content/metadata/*. NPR-13188 correctif pour GRANITE-16479
* Lors de l’utilisation de l’**[!UICONTROL interface utilisateur tactile]**, les variantes de produit ne sont pas créées au même niveau que le produit. L’utilisateur n’est pas informé de l’état du processus de création de variantes. NPR-15345 : correctif pour CQ-4198948

**Scene7**

* L’exécution du workflow Scene7 empêche la fermeture des fichiers ouverts. Demande d’amélioration du service AEM-S7 afin qu’il conserve et réutilise une seule instance HttpClient avec une configuration de mise en pool partagée. NPR-15357 : correctif pour CQ-109958

### Traduction {#translation-9}

* Lors de l’utilisation de projets de traduction, la mise à jour de copies de langue à partir du modèle anglais produit 11 lancements distincts qui ont tous le même nom et la même racine source, mais avec des racines de lancement légèrement différentes, au cas où le nom de page suivrait un modèle défini. NPR-15605 : correctif pour CQ-4200699
* Les projets de traduction ne sont pas créés pour les pages lorsque les noms de racines de langue comportent des tirets. NPR-15171 : correctif pour CQ-96286
* Demande de mise à jour du connecteur Microsoft pour pouvoir utiliser les API Microsoft Translator, que Microsoft met à disposition sur le portail Azure. NPR-15320 : correctif pour CQ-101010

### Projets {#projects-4}

* Seuls 20 projets inactifs sont visibles sur l’écran Projets, bien qu’il existe plus de 20 projets inactifs dans le référentiel. NPR-15656 : correctif pour CQ-4200903

### Campagne {#campaign-1}

* Lors de l’utilisation des composants Campaign – Targeting et MAC – Test et Target Integration, l’annulation de la publication des activités ne met pas à jour l’état de l’activité dans l’interface utilisateur Master. NPR-15401 : correctif pour CQ-4199839
* Lors du déplacement d’un produit dans AEM Commerce, l’assistant de déplacement de produit ignore les valeurs préremplies pour le nom du produit, le titre, les pages référencées, l’auteur et la date de création. NPR-15228 : correctif pour CQ-98617

### Sécurité {#security-4}

* Paramètre de jeton CSRF ajouté aux formulaires avec une méthode GET. NPR-15229

### Formulaires {#forms-18}

#### Package de modules complémentaires Forms {#forms-add-on-package-18}

`**Adaptive Forms**`

* Les valeurs par défaut sont remplacées par des valeurs vides dans le code xml lors du préremplissage du formulaire adaptatif avec du code XML d’entrée. NPR-15721
* Le wrapper `afData/afBoundData` est présent dans le code XML envoyé, bien que même le code XML prérempli ne comporte pas de wrapper `afData/afBoundData` dans les formulaires adaptatifs basés sur un schéma XML. NPR-15541

* Les titres de la barre en accordéon doivent être des en-têtes HTML « h2 » modifiables au lieu de la balise « a ». NPR-15475
* La disposition en accordéon d’un panneau de formulaire n’est pas accessible aux utilisateurs de lecteurs d’écrans. Les utilisateurs ne peuvent pas accéder à l’onglet en accordéon à l’aide du clavier uniquement lorsqu’ils utilisent un logiciel de lecteur d’écrans tel que JAWS ou NVDA. NPR-15474

`**Correspondence Management**`

* L’enregistrement, la suppression et la définition d’une référence pour un fragment de document prennent beaucoup de temps. NPR-15939
* L’alignement des tabulations défini dans Gérer les ressources sur du texte contenant plusieurs en-têtes est rompu dans l’interface utilisateur CCR. NPR-15818
* Les vignettes des modules de texte n’affichent pas le contenu aligné bien que le texte contienne du contenu aligné créé à l’aide de tabulations dans Google Chrome. NPR-15819

`**Forms Portal**`

* Le service de préremplissage ne fonctionne pas pour XDP Forms. NPR-15466
* Lors du stockage de brouillons et d’envois de formulaires adaptatifs dans la base de données, l’état du formulaire adaptatif est corrompu lors de la perte de connectivité à la base de données pour une quelque raison que ce soit (par exemple, après une longue période d’inactivité). NPR-15297

#### Programme d’installation de Forms JEE  {#forms-jee-installer-18}

`**Core**`

* Après la mise à niveau vers la dernière version de Java 1.8.0_121-b13, l’interface utilisateur Admin n’est pas accessible dans AEM Forms. NPR-15330

`**XTG**`

* Lors de l’utilisation du service Output pour fusionner un formulaire spécifique avec un contenu dataxml, le temps de réponse est 20 fois plus long que la même opération réalisée avec le serveur ES4 SP1. NPR-15283

#### Application AEM Forms {#aem-forms-app-1}

* Lors de la récupération de tâches non enregistrées, le message affiché lors de la récupération de tâches non enregistrées doit être plus clair afin de réduire les erreurs utilisateur. NPR-15377
* L’application AEM Forms ne rend pas les formulaires créés à partir de modèles personnalisés. NPR-15892
* Les utilisateurs ne peuvent pas se connecter à l’application AEM Forms. NPR-15891

Les principaux aspects d’AEM 6.2 SP2-CFP1 sont les suivants :

* Simplifie la fonctionnalité de réplication dans Sites :

   * Correctifs de divers problèmes de déploiement, de LiveCopy et d’écriture incorrecte

* Améliore la réactivité de l’interface utilisateur tactile pendant :

   * Recherches de ressources
   * Tri basé sur la taille

* Améliore la gestion des balises dans les collectes dynamiques
* Contrôles d’accès plus serrés pendant les opérations CRUD sur les dossiers

### Plateforme {#previous}

* Demande de suppression des appels d’API `ReplicationQueue#forceRetry` au démarrage des agents de réplication car ces appels ralentissent considérablement l’instance, en particulier lorsqu’elle dispose de nombreux agents de réplication. NPR-14032 : correctif pour GRANITE-13095
* Demande de configuration `DurboImportConfigurationProviderService` OSGi pour prendre en charge les champs qui peuvent stocker un ensemble de valeurs. NPR-14570 : correctif pour CQ-108684
* L’utilisation du composant Sightly dans une page après la migration vers AEM 6.2 entraîne l’arrêt du fonctionnement de la boîte de dialogue Propriétés de la page. NPR-14328 : correctif pour CQ-108355
* L’annulation de la planification d’une tâche précédemment planifiée ne supprime pas le nœud correspondant sous */var/eventing/scheduled-jobs*. NPR-14253 : correctif pour SLING-5666
* Lorsqu’un administrateur d’emprunter l’identité d’un utilisateur supprimé, l’interface utilisateur n’est pas actualisée. NPR-14247 : correctif pour CQ-107446
* Vérification de la protection XSS provoquant un codage incorrect dans le composant Sightly. NPR-14004 : correctif pour CQ-93821
* Demande de mise à niveau de Jackrabbit Filevault vers la version 3.1.30 afin de résoudre plusieurs problèmes. NPR-13454
* Une erreur de cache se produit lorsque la distribution Sling synchronise les packages de distribution de la création vers la publication. NPR-13034 : correctif pour GRANITE-13970

### Sites {#sites-18}

* Problèmes avec VersionManagerImpl lors de la purge de versions incorrectes de l’historique des versions. NPR-14372
* Le composant parsys WCM Sightly Foundation ignore les noms de balises de déclaration de composant, `cq:htmlTag / cq:tagName`. NPR-14225
* Lorsque Sightly Parsys est utilisé pour le rendu des composants insérés via JavaScript dans l’interface utilisateur tactile, la décoration personnalisée est ignorée une fois la page actualisée. NPR-14122
* Les listes déroulantes de cibles ne fonctionnent pas dans la boîte de dialogue de l’interface utilisateur tactile lorsque plusieurs champs Richtext, tels que des liens, sont créés. NPR-13911
* Lors de la modification d’un champ de texte avec plusieurs propriétés RTE (Rich Text Editor) dans une boîte de dialogue (IU tactile), la cible d’action passe aléatoirement sur une propriété RTE spécifique. NPR-13703
* Le composant vidéo prêt à l’emploi par défaut n’affiche pas la vignette de la vidéo. NPR-14976
* Informations chargées lentement dans l’onglet Utilisations en direct de l’éditeur de modèles. NPR-14880 : correctif pour CQ-83417
* L’installation du correctif 10936 sur une instance AEM 6.2 désactive le composant iparsys. NPR-14330 : correctif pour CQ-106982
* Plusieurs problèmes de composants de déploiement et un problème de Live Copy après la migration vers AEM 6.1 SP1. NPR-15256
* L’action de déploiement de page ne permet pas de créer des enfants au-delà du premier niveau, même pour configurations à plusieurs déploiements. NPR-15055
* Lors de l’envoi de la boîte de dialogue Propriétés de la page à partir de l’éditeur, les données inchangées dans les onglets LiveCopy sont réécrites. NPR-14693
* Lors de l’envoi de la boîte de dialogue Propriétés de la page depuis l’éditeur, le processeur de post-traitement MSM écrit certains paramètres de la requête au lieu du paramètre `msm:writeLiveCopyConfig`. NPR-14434
* Plusieurs problèmes associés au composant Déploiement, aux Live Copies et à d’autres aspects de MSM. NPR-12235

### Ressources {#assets-18}

* Le workflow de décompression ne peut pas gérer les images dont le nom de fichier contient des caractères spéciaux. NPR-15227 : correctif pour CQ-103887
* Les ressources dont l’expression de condition s’accompagne de Répéter ne sont pas affichées correctement. Lorsque l’utilisateur affiche l’aperçu du modèle de lettre `*CDN3835RLCEN*`, aucune ressource située dans la zone cible du corps n’est affichée. Lorsque la ressource facultative `*VIPReassement*` présélectionnée est désélectionnée, les autres ressources présélectionnées sont affichées dans la lettre. NPR-14844

* Lors de la création d’une collecte dynamique, la balise de style n’est pas conservée lors de l’enregistrement de la collecte dynamique. NPR-15081 : correctif pour CQ-4195494
* Requêtes de recherche de ressources exécutées lentement dans l’interface utilisateur tactile pendant des recherches simultanées effectuées par plusieurs utilisateurs. NPR-15019 : correctif pour CQ-4195405
* Les métadonnées extraites pour une propriété de type `Long[]` sont converties vers le type `String[]` lors d’un nouveau chargement de la ressource d’origine à un autre emplacement. NPR-15016 : correctif de CQ-4195005

* Utilisateurs ne peuvent pas supprimer une recherche enregistrée ou une collecte dynamique. NPR-14924 : correctif pour CQ-108494
* La modification de métadonnées pour des ressources en bloc (mode d’ajout) lors de l’utilisation d’une valeur booléenne pour TypeHint dans une liste déroulante du schéma de métadonnées sous-jacent génère une erreur. NPR-14529 : correctif pour CQ-106876
* Les utilisateurs ne disposant pas de droits de réplication ne peuvent pas supprimer les dossiers Asset. NPR-14321 : correctif pour CQ-88271
* Lorsque vous tentez de modifier les profils vidéo d’une vidéo dans l’éditeur de canal, la boîte de dialogue de conception ne s’ouvre pas et déclenche une exception de pointeur nul dans le journal d’erreur. NPR-14144 : correctif pour CQ-81101
* La propriété d’horodatage « Créé » générée par le système et affichée sur la page de propriétés d’une ressource est incorrecte. NPR-13992 : correctif pour CQ-95029
* Demande d’activation de la détection des doublons de ressources pour les utilisateurs sans accès en lecture dans AEM Assets NPR-13851 : correctif pour CQ-102281
* Les utilisateurs ne peuvent pas modifier les métadonnées des ressources en bloc à partir de la page de propriétés. NPR-13721 : correctif pour CQ-100703
* Message d’erreur incorrect dans l’interface utilisateur Classic lors du chargement d’un doublon de ressource. Le message d’erreur n’indique pas pourquoi le chargement a échoué. NPR-13691 : correctif pour CQ-99272
* AEM Assets ne peut pas trier plus de 50 ressources par taille à la fois en mode Liste lorsque le dossier contient de nombreuses ressources. CQ-100588
* La sélection de plusieurs actifs génère une erreur avec le code de réponse – 414 (Request-URI Too Long) si l’URI de ressource/dossier est trop long. NPR-13516 : correctif pour CQ-76076
* La page Rapport de ressources ne répond plus lorsque l’utilisateur sélectionne toutes les options dans la boîte de dialogue Configurer les colonnes. NPR-13187 : correctif pour CQ-95589
* Comportement inattendu du sélecteur de balises dans Safari et Internet Explorer. NPR-13134
* La modification de la recherche enregistrée à partir du rail de recherche d’administration des ressources permet de les enregistrer comme sélections dynamiques imbriquées, ce qui entraîne des problèmes de stabilité de l’environnement. NPR-13119 : correctif pour CQ-99460
* Après avoir déplacé un fichier (ou un dossier) puis l’avoir renommé, les métadonnées « cq:name » ne reflètent pas le nouveau nom de fichier (nom du dossier). NPR-13036 : correctif pour CQ-99141
* Les ressources dont les noms comportent des caractères spéciaux ne peuvent pas être téléchargées à partir du lien de téléchargement partagé par courrier électronique. NPR-12872 : correctif pour CQ-95795
* Les rapports de ressources prêts à l’emploi générés en présence d’un nombre important de ressources provoquent des traversées lourdes lorsque la recherche n’atteint aucun pic d’index et d’utilisation de l’UC. NPR-12811 : correctif pour CQ-84409
* Les utilisateurs de l’instance de création AMS AEM Assets y accèdent depuis différents réseaux qui ne permettent pas de charger des ressources en bloc sans disposer de droits de suppression sur les dossiers. NPR-12768 : correctif pour CQ-82715
* Dans les recherches basées sur des balises pour les ressources à l’aide du rail de recherche de ressources, la fonction Type Ahead ne se limite pas au chemin racine et affiche des balises issues de tous les espaces de nommage. NPR-12666
* Le composant StaticRenditions soulève une exception de pointeur nul. NPR-12665
* Demande de désactivation de la tâche MissingMetadataNotificationJob, car l’interface utilisateur Badge Notification rompt la page avec une exception d’exécution « Impossible d’analyser l’entrée ». NPR-12500 : correctif pour CQ-93573
* L’option « Désactiver la modification » d’un champ de balise ne fonctionne pas dans les pages de propriétés des ressources dans l’interface utilisateur tactile. NPR-12429 : correctif pour CQ-88835
* Correctifs d’API dans AEM Assets 6.2 pour l’implémentation SMB des applications complémentaires. NPR-11099
* Depuis la mise à jour de la requête Jquery, les utilisateurs ne peuvent pas sélectionner une collection de ressources et confirmer la sélection dans le panneau Associer le contenu d’un fragment de contenu. NPR-14847 : rétroportage pour CQ-4194209
* Malgré l’appel du tri infini côté client, seuls les articles/bannières/collections actuellement affichés dans l’interface utilisateur sont triés. NPR-14493 : correctif pour CQ-109926
* Demande de mise en œuvre de la fonction d’omni-recherche pour le service AEM mobile-on-demand. La recherche de mots-clés pour un article, une collection ou une bannière ne renvoie aucun résultat. NPR-14093 : correctif pour CQ-101394
* Lors de l’utilisation du composant Coral-select (*granite/ui/components/coral/foundation/form/select*) dans une boîte de dialogue, l’initialisation de valeur ne fonctionne pas correctement dans Internet Explorer (navigateurs IE11 ou Edge) lorsque la valeur sélectionnée contient un seul élément. NPR-13395 : correctif pour CQ-101013

### Projets {#projects-5}

* Lors de l’exportation d’un projet de traduction créé avec la méthode de traduction comme « humain » et le fournisseur de traduction comme « aucun », aucun fichier translation_export_summary.xml n’est généré en raison de l’absence de fichier de mappage du GUID. NPR-13137 : correctif pour CQ-91976
* Dans les projets AEM, lors de la création d’un projet avec la propriété de date d’échéance définie, la conversion de date définit l’heure incorrectement en raison de la différence de fuseau horaire entre le serveur et le client. NPR-13003 : correctif pour CQ-98288
* L’option « Révéler dans Sites » est absente de la tâche de traduction lors de la mise à jour d’un projet de traduction. NPR-12966 : correctif pour CQ-93740
* Lors de la création d’un projet de traduction pour une page de site exportée, son rendu dans l’aperçu n’est pas correct. NPR-12964 : correctif pour CQ-84627

### Workflow {#workflow-3}

* Le lien Charge utile dans l’onglet Archivage de la console Workflow renvoie une erreur avec le code de réponse « 404 » lorsque l’on clique dessus. NPR-14993 : correctif pour CQ-4194977
* Lors de l’utilisation des workflows AEM par défaut, le publieur CQ ne peut pas à envoyer une notification par courrier électronique à un groupe s’il manque l’adresse électronique d’un seul membre. NPR-14804 : demande de correctif pour CQ-91499
* Amélioration des performances de la boîte de réception et du badge de notification dans l’interface utilisateur tactile. NPR-14145 : correctif pour CQ-101125
* Les utilisateurs ne peuvent pas prévisualiser la charge utile à partir de la console de la boîte de réception de workflow lors de l’initialisation de workflows. NPR-13226 : correctif pour CQ-100275
* Le cookie « saml_request_path » configuré à l’aide du gestionnaire d’authentification SAML affiche le cookie défini avec un caractère « ? » supplémentaire. En outre, lorsqu’une réponse SAML est renvoyée à AEM, le cookie AEM « saml_request_path » renvoie une valeur non valide en raison de caractères déjà codés. NPR-13517 : correctif proactif pour GRANITE-11722 et GRANITE-14414

### Intégration de solution {#solution-integration}

* Après l’intégration d’AEM 6.2 avec Search&amp;Promote, si un utilisateur recherche un terme qui renvoie une bannière, la fonctionnalité de recherche ne répond plus. NPR-14549 : CFP pour CQ-109631

### Dynamic Media {#dynamic-media}

* De nombreuses tâches sling AEM-Scene7 qui ont été créées et annulées lors de l’activation d’AEM sont consignées comme tâches d’archivage pendant la réplication. NPR-12835 : correctif pour CQ-86115

### Sécurité {#security-5}

* Demande de résolution d’un problème de validation d’entrée dans le filtre WCMDebug. NPR-12444 : demande de correctif pour CQ-94890
* Demande proactive de correction du comportement XSS lors de l’utilisation de l’assistant de création de lancements.\
   NPR-13062 : demande de correctif pour CQ-99577

#### Package de modules complémentaires Forms {#forms-add-on-package-19}

`Adaptive Forms`

* Lors de la création d’un panneau répétable à l’aide de formulaires adaptatifs, le titre du panneau ne peut pas être mis à jour au moment de l’exécution. NPR-15325
* Lorsque la valeur par défaut d’un bouton radio est définie sur une valeur que la valeur par défaut lors de l’enregistrement ou de l’envoi, la valeur n’est pas affichée lors du préremplissage. NPR-15304
* Google Chrome présente un comportement incorrect lors de l’utilisation d’options pour renseigner de manière dynamique la liste déroulante et envoyer la valeur de l’élément sélectionné. NPR-15198
* Lors de la création d’un panneau répétable à l’aide de formulaires adaptatifs, le titre du panneau ne peut pas être mis à jour au moment de l’exécution. NPR-15181
* Lors de l’utilisation du mode d’édition pour les formulaires adaptatifs, des erreurs JavaScript telles que « Le gestionnaire du composant n’est pas valide » et « guidelib n’est pas défini » surviennent. NPR-15112
* Le chargement différé d’un fragment dans un panneau répétitif ne fonctionne pas comme prévu. NPR-13916, NPR-14785

`Correspondence Management`

* Les ressources de Correspondence Management avec l’expression `'Repeat with condition'` définie ne sont pas affichées correctement. NPR-14844
* Lors de la recherche d’une ressource Correspondence Management (telle qu’une lettre, un fragment de document ou tout autre type), l’icône File d’attente de téléchargement est absente de la barre d’outils. NPR-14745
* Lors de la création d’un module Liste, la désactivation des propriétés spécifiques à la ressource (telles que modifiable ou obligatoire) ne fonctionne pas. NPR-14689
* Le panneau Éléments de données de l’utilitaire Générateur d’expression continue à se charger en cas de création d’un module de condition sans sélectionner de dictionnaire de données. NPR-14688
* Lors de la prévisualisation d’une lettre, les utilisateurs ne peuvent pas utiliser d’espaces de tabulation pour aligner le contenu au format tabulaire. NPR-14481
* Lors de l’exportation en bloc des ressources de Correspondence Management depuis l’interface utilisateur, AEM Forms Server génère des journaux inutiles. NPR-15226
* Lorsqu’une lettre est prévisualisée, le texte justifié s’affiche dans une police différente. NPR-15468

`**Forms Portal**`

* Les pièces jointes aux formulaires envoyés sur le portail Forms ne sont pas visibles lorsqu’un nouveau brouillon est envoyé à partir de l’envoi depuis le portail. NPR-13515

`**Forms Manager**`

* Lors de la navigation dans le répertoire *FormsandDocuments*, le bouton Coller n’apparaît pas lorsque l’utilisateur copie une ressource puis accède à un autre dossier. CQ-111327

#### Programme d’installation de Forms JEE {#forms-jee-installer-19}

`Rights Management`

* L’événement d’audit associé à la connexion de l’utilisateur est consigné avec une heure non valide. Le moment approprié pour l’événement d’audit n’est pas traçable. NPR-13107
* Adobe Acrobat Reader et Microsoft Office ne peuvent pas ouvrir les documents protégés par une authentification étendue. NPR-14482

`Process Management`

* Lorsqu’une tâche de brouillon transférée dans l’espace de travail HTML est renvoyée à l’utilisateur initial, cette tâche n’apparaît pas dans la file d’attente de l’utilisateur initial. NPR-15178

`Assembler Service`

* AEM Forms ne peut pas valider un fichier PDF/A-2b contenant plus de deux signatures. NPR-14101

`XTG`

* Lors de l’impression d’un document à l’aide d’un bac de dérivation d’une imprimante, la fonction `GeneratePrintedOutput` ne permet pas l’utilisation de papier à partir du bac de dérivation de droite. NPR-14079

#### Concepteur Forms {#forms-designer-2}

* Forms Designer se bloque lorsque l’utilisateur exécute l’utilitaire de vérification orthographique avec le français (Canada) sélectionné comme langue de formulaire. NPR-13740
* Forms Designer se bloque lorsque l’utilisateur sélectionne Calculer l’événement ou Valider l’événement pour un champ de formulaire et définit le langage sur JavaScript, puis entre `this.` dans la fenêtre **[!UICONTROL Éditeur de script]**. NPR-12974

### Feature Packs inclus dans CFP1 {#feature-packs-included-in-cfp-3}

`Mobile Forms` (Package de modules complémentaires Forms) :

* Lors de la création d’un formulaire adaptatif à partir d’un fichier XDP, la tabulation pour l’accessibilité ne suit pas le modèle défini. NPR-12562

`Adaptive forms` (Package de modules complémentaires Forms) :

* Le créateur de règles pour les formulaires adaptatifs ne fournit pas d’accès basé sur les rôles. Les modifications apportées par un auteur ne peuvent pas faire l’objet d’un suivi. NPR-12840

`Core` (Programme d’installation de Forms JEE) :

* La fonctionnalité CORS (CoreCross Origine Resource Sharing) en tant que filtre de servlet n’est pas activée pour Jboss+. NPR-13050

## Instructions de téléchargement relatives aux CFP via la Distribution de logiciels {#download-instructions-for-cfp-via-package-share}

>[!NOTE]
>
>Pour les clients AEM Forms, il est impératif d’installer le module complémentaire AEM Forms après l’installation de tout Service Pack, pack de correctifs cumulés ou Feature Pack d’AEM.

Vous pouvez télécharger le module CFP directement à partir de distribution de logiciels ou suivre les étapes suivantes :

1. Ouvrez [Distribution de logiciels](https://experience.adobe.com/downloads). Vous avez besoin d’un Adobe ID pour vous connecter à la Distribution de logiciels.
1. Appuyez sur **[!UICONTROL Adobe Experience Manager]** disponible dans le menu d’en-tête.
1. Appuyez sur le nom du package, sélectionnez **[!UICONTROL Accepter les termes du contrat de licence utilisateur final]**, puis appuyez sur **[!UICONTROL Télécharger]**.

## Instructions d’installation pour CFP {#installation-instructions-for-cfp}

Cette section décrit les exigences et les étapes à suivre pour installer le CFP.

### Avant l’installation {#before-you-install}

>[!NOTE]
>
>Les Feature Packs facultatifs fournis par Adobe dépendent de la version et du pack de correctifs cumulés. Si vous avez installé un Feature Pack, contactez [l’équipe d’assistance clientèle d’AEM](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html) pour valider sa compatibilité avec le pack de correctifs cumulés pour AEM 6.2.

>[!NOTE]
>
>Il est recommandé de valider chaque nouveau package d’installation avant d’essayer d’installer le package. La pré-validation analyse et signale les erreurs détectées avant l’installation et avertit les utilisateurs de ces erreurs, chevauchements et droits de manière proactive.
>
>Vous pouvez accéder à la documentation de l’option Valider à l’adresse [https://docs.adobe.com/content/docs/en/aem/6-2/administer/content/package-manager.html#Package%20Validator](https://docs.adobe.com/content/docs/en/aem/6-2/administer/content/package-manager.html#Package%20Validator)

* AEM 6.2 Service Pack 1 est une condition préalable à l’installation du CFP. Pour obtenir des instructions sur l’installation, consultez les [Notes de mise à jour du service Pack 1 d’AEM 6.2](https://docs.adobe.com/docs/en/aem/6-2/release-notes/sp1.html).

* Le pack de correctifs cumulés peut être téléchargé sur [Distribution de logiciels](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html), accessible directement depuis l’instance AEM.
* Pour un déploiement en grappe utilisant (RDBMK ou MongoDB), le package CFP peut être installé sur n’importe quelle instance de création qui utilise le gestionnaire de modules.

* Avant d’installer le pack de correctifs cumulés, veillez à prendre un instantané ou à effectuer une sauvegarde de votre instance AEM.
* La désinstallation du CFP n’est pas prise en charge.

### Installer le CFP via distribution de logiciels {#install-the-cfp-via-package-share}

Suivez les étapes suivantes pour installer le pack de correctifs cumulés sur une instance existante d’AEM 6.2 SP1 :

1. Cliquez sur le lien [Distribution de logiciels](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/cumulativefixpack/aem-6.4.8-cfp-2.0.zip) pour télécharger le package.

1. Ouvrez [Package Manager](http://localhost:4502/crx/packmgr/index.jsp) et cliquez sur **[!UICONTROL Télécharger le package]** pour télécharger le package.

1. Sélectionnez le nom du package et cliquez sur **[!UICONTROL Installer]**.

### Installation automatique {#automatic-installation}

Le CFP peut être automatiquement installé dans une instance en cours d’exécution de la manière suivante :

* Placez le package dans ../crx-quickstart/install pendant l’exécution du serveur. Le package est automatiquement installé.
* Utilisez l’[API HTTP du gestionnaire de modules](https://helpx.adobe.com/fr/experience-manager/6-2/sites/administering/using/package-manager.html) (veillez à utiliser `cmd=install&recursive=true`) afin d’installer le package imbriqué.

### Validation de l’installation {#validate-installation}

1. La page Informations sur le produit (/system/console/productinfo) doit maintenant afficher la chaîne de version mise à jour « Adobe Experience Manager, Version 6.2.0.SP1-CFP20 » sous Produits installés.
1. Tous les lots OSGI sont ACTIFS ou FRAGMENT dans la console OSGI (utiliser la console web : /system/console/bundles).

>[!NOTE]
>
>Une fois l’installation du package réussie, un message d’information apparaît pour indiquer que le package de contenu a bien été installé, par exemple « AEM 6.2-Cumulative-Fix-Pack-SP1-CFP20 installé avec succès ».

>[!NOTE]
>
>Depuis AEM 6.2 SP1-CFP1, le niveau de journal dans Jackrabbit FileVault est passé d’INFO à DEBUG pour la plupart des messages. Pour obtenir les journaux d’installation d’un package de contenu installé sur AEM 6.2 SP1-CFP1 ou une version ultérieure, activez le niveau de journal DEBUG pour `org.apache.jackrabbit.vault.packaging.impl`.

### Installation d’AEM Forms {#install-forms}

>[!NOTE]
>
>Ignorez cette section si vous n’utilisez pas AEM Forms.

#### Installation du module complémentaire AEM Forms {#install-aem-forms-add-on}

>[!NOTE]
>
>(**AEM Forms sur JEE uniquement**) La procédure d’installation d’un CFP sur AEM Forms sur JEE est décrite dans [Installation du CFP sur AEM Forms JEE](install-cfp-aem-forms-jee.md#install-cfp-on-aem-forms-jee).

1. Vérifiez que vous avez installé le package AEM 6.2 SP1 CFP.
1. Téléchargez le module complémentaire Forms correspondant répertorié dans les [versions AEM Forms](aem-forms-releases.md) pour votre système d’exploitation.
1. Installez le module complémentaire Forms comme décrit dans la section [Installation des modules complémentaires AEM Forms](https://helpx.adobe.com/fr/experience-manager/6-2/forms/using/installing-configuring-aem-forms-osgi.html).

#### Installation du package de lots AEM Forms JEE {#install-aem-forms-jee-bundles-package}

Les correctifs dans AEM Forms JEE sont fournis dans un programme d’installation distinct. Pour plus d’informations sur l’installation d’un CFP pour AEM Forms sur JEE, reportez-vous à [Installation d’un CFP pour AEM Forms JEE](install-cfp-aem-forms-jee.md).

#### Programme d’installation du Concepteur Forms {#designer-installer}

1. Pour installer la mise à jour, exécutez le fichier Designer6.2.0_&lt;Langue>_Cumulative_QF.msp.
1. Sur l’écran de bienvenue, cliquez sur **Mettre à jour**. L’installation démarre.
1. Une fois l’installation terminée, cliquez sur **Terminer**.

## Paramètres de délai d’expiration configurables par l’utilisateur pour DTM, Analytics, Target, Search et Promote Connections {#user-configurable-timeout-parameters-for-dtm-analytics-target-search-promote-connections}

Avec le pack de correctifs cumulés AEM 6.2 SP1-CFP7 et versions ultérieures, les délais de connexion sont devenus configurables sur toutes les connexions ci-dessus, selon les détails ci-dessous :

| **Connexions** | **Délai de connexion&#42;** | **Délai d’expiration du socket&#42;&#42;** |
|---|---|---|
| DTM | 30 000 ms | 30 000 ms |
| Analyses | 30 000 ms | 30 000 ms |
| Cible | 60 000 ms | 30 000 ms |
| Search&amp;Promote | 30 000 ms | 30 000 ms |

* **Délai de connexion&#42;** : délai d’expiration en millisecondes jusqu’à ce qu’une connexion soit établie. Une valeur de délai nulle est interprétée comme un délai d’expiration infini.
* **Délai d’expiration du socket&#42;&#42;** : délai (en millisecondes) d’attente des données ou période d’inactivité maximale entre deux paquets de données consécutifs.

>[!NOTE]
>
>Avec le pack de correctifs cumulés AEM 6.2 SP1-CFP6 et les versions ultérieures, la configuration OSGi utilisée pour l’intégration de Search &amp; Promote est la configuration du proxy des composants HTTP Apache. La configuration du proxy du client HTTP 3.1 Day Commons n’est plus utilisée.

## Désactivation de l’état de réplication dans la console de balisage (interface utilisateur Classic) (NPR-15842) {#disable-replication-status-in-tagging-console-classic-ui-npr}

Si vous utilisez le CFP3 ou une version ultérieure, suivez ces instructions pour désactiver l’état de réplication dans la console de balisage de l’interface utilisateur Classic :

* Recouvrement *« /libs/cq/tagging/widgets/source/widgets/admin/TagAdmin.js »* dans */apps*

* Ajoutez `replicationStateRequired` : « false » après la ligne 416.

   ```js
   415    baseParams: {
   416                    count: "false",
   417                    "replicationStateRequired": "false"
   418                },
   ```

## La dernière mise à jour 131 de Java 8 renvoie une exception (NPR-21355) {#latest-java-update-throws-an-exception-npr}

>[!NOTE]
>
>Ces paramètres de configuration sont spécifiques aux clients AEM Forms qui utilisent Document Security.

La NPR-21355 est incluse dans le CFP12.1. Si vous installez le CFP12.1 ou une version ultérieure, effectuez la procédure ci-dessous pour configurer NPR-21355 sur le serveur d’applications JBoss. Si vous installez le CFP12.1 sur un serveur AEM Forms qui s’exécute sur des serveurs d’applications Oracle WebLogic ou IBM WebSpehere, aucune configuration supplémentaire n’est nécessaire :

1. Sauvegardez, supprimez et créez un nouveau fichier module.xml. L’emplacement par défaut du fichier est [Répertoire_d_installation_d_AEM_Forms]/jboss/modules/system/couches/base/com/adobe/livecycle/main/

1. Ouvrez le nouveau fichier module.xml créé pour le modifier. Ajoutez le code suivant au fichier :

   ```xml
   <module xmlns="urn:jboss:module:1.1"
   name="com.adobe.livecycle">
   <resources>
   <resource-root path="cryptojcommon.jar"/>
   <resource-root path="cryptojce.jar"/>
   <resource-root path="jcmFIPS.jar"/>
   <resource-root path="certj.jar"/>
   <resource-root path="cglib.jar"/>
   </resources>
   <dependencies>
   <module name="javax.api"/>
   <module name="asm.asm"/>
   </dependencies>
   </module>
   ```

1. Créez une sauvegarde des fichiers jsafeFIPS.jar, jsafeJCEFIPS.jar et certjFIPS.jar situés dans [Répertoire_d_installation_d_AEM_Forms]/jboss/modules/system/couches/base/com/adobe/livecycle/main/ et supprimez les fichiers du répertoire susmentionné.

   Contactez l’[assistance Adobe](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html) pour obtenir de nouveaux fichiers JAR. Placez les fichiers JAR obtenus auprès de l’[assistance à l’Adobe](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html) sous [Répertoire_d_installation_d_AEM_Forms]/jboss/modules/system/couches/base/com/adobe/livecycle/main/

1. (Windows uniquement) Modifiez les fichiers de configuration `[AEM_Forms_Installation_directory]/jboss/standalone.conf.bat` ou `domain.conf.bat` :

   * Pour la configuration autonome du serveur JBoss, ouvrez le fichier standalone.conf.bat pour le modifier.
   * Pour configuration grappe du serveur JBoss, ouvrez le fichier domaine.conf.bat pour le modifier.

   Ajoutez les lignes suivantes à la fin et enregistrez le fichier :

   set &quot;JAVA_OPTS=%JAVA_OPTS%-Djnlp.com.rsa.cryptoj.fips140loader=true&quot;

   set &quot;JAVA_OPTS=%JAVA_OPTS%-Dcom.rsa.cryptoj.fips140initialmode=NON_FIPS140_MODE&quot;

1. (Système d’exploitation basé sur Linux uniquement) Modifiez les fichiers de configuration [Répertoire_d_installation_d_AEM_Forms]/jboss/standalone.conf ou domain.conf :

   * Pour la configuration autonome du serveur JBoss, ouvrez le fichier standalone.conf pour le modifier.
   * Pour configuration grappe du serveur JBoss, ouvrez le fichier domaine.conf pour le modifier.

   Ajoutez les lignes suivantes à la fin et enregistrez le fichier :

   JAVA_OPTS=&quot;$JAVA_OPTS-Djnlp.com.rsa.cryptoj.fips140loader=true&quot;

   JAVA_OPTS=&quot;$JAVA_OPTS -Dcom.rsa.cryptoj.fips140initialmode=NON_FIPS140_MODE&quot;

## Paramètres de configuration requis pour NPR-19778 {#configuration-settings-required-for-npr}

>[!NOTE]
>
>La NPR-19778 fait partie du CFP14.

Par défaut, la valeur pour la file d’attente partagée n’est pas actualisée pour les autres utilisateurs lorsqu’un utilisateur demande une tâche. Nous avons créé une nouvelle propriété pour cela. Suivez les étapes ci-dessous pour configurer cette propriété sur votre instance AEM :

1. Accédez à Interface utilisateur d’administration -> Services -> Espace de travail -> Administration globale.
1. Exportez les paramètres globaux.
1. Dans le fichier XML téléchargé, ajoutez la balise `<client_tasksPollingInterval>10</client_tasksPollingInterval>`. Ici, 10 est l’exemple de valeur en secondes. Vous pouvez la modifier selon vos besoins.
1. Enregistrez le fichier.
1. Revenez à l’Interface utilisateur d’administration -> Services -> Espace de travail -> Administration globale.
1. Importez le fichier xml dans la section Importer les paramètres globaux.
1. Vous pouvez maintenant vous déconnecter du système et vous reconnecter.
1. La valeur pour la file d’attente partagée commence à être actualisée pour les autres utilisateurs de l’espace de travail.
1. Pour désactiver l’interrogation, définissez la valeur sur 0 et importez à nouveau le fichier XML.

## Modifications dans l’interface utilisateur {#ui-changes}

* Changement de comportement lors de l’affichage des titres sur la carte d’image pour les images ayant une propriété dc: title définie sur String (multichamp) [] : seul le dernier titre modifié sera affiché sur la carte Image dans l’interface utilisateur, bien que tous les titres soient enregistrés dans CRX. Correctif pour CQ-4217165

## Problèmes connus {#known-issues}

* La mise à jour vers AEM 6.2SP1-CFP19 et vers AEM 6.2SP1-CFP20 depuis le CFP18 définit la redirection racine sur la page d’accueil de l’interface utilisateur Classic au lieu de /sites.html/content. Vous devrez peut-être corriger la propriété de cible sling: de /welcome.html à /index.html avec CRX Explorer. Ce problème ne se produit pas lors de la mise à jour depuis le CFP17 ou une version antérieure.

Les erreurs transitoires suivantes peuvent se produire lorsque vous installez AEM 6.2 SP1-CFPx. Toutefois, aucune résolution n’est requise pour ces erreurs car elles n’ont aucun impact sur votre instance d’AEM et disparaissent après l’installation du CFP :

* Lors de la mise à niveau de l’instance AEM 6.2SP1-CFP20 vers AEM 6.5, certaines URL de vanité peuvent ne pas fonctionner, par exemple :

   * */projects.html*
   * */sites.html*

La solution consiste à redémarrer l’instance AEM après une mise à niveau.

* Une erreur interne de serveur HTTP 500 est reçue à l’ouverture de la page des détails du composant Webconsole.
* Des erreurs telles que **create component instance** et **Service factory returned null** se produisent en raison du redémarrage du référentiel :

   * com.day.cq.cq-personalization [com.day.cq.personalization.impl.DefaultProfileProvider(938)] Cannot create component instance due to failure to bind reference profileManager
   * org.apache.sling.commons.scheduler FrameworkEvent ERROR (org.osgi.framework.ServiceException: Service factory returned null. (Composant : com.day.cq.tagging.impl.TagGarbageCollector (1687))

* Erreur observée lors de l’installation du CFP dans Mongo et DB2 : **org.apache.sling.discovery.oak.TopologyWebConsolePlugin addDiscoveryLiteHistoryEntry : Exception : java.lang.NullPointerException**. Cette erreur ne se produira pas après l’installation d’un CFP au-delà du CFP8.
* (Adobe Granite Maintenance Scheduler Update Task) com.adobe.granite.maintenance.impl.TaskScheduler: No maintenance task found with name WorkflowPurgeTask for window granite:weekly
* `[sling-oak-observation-8]com.day.cq.dam.scene7.impl.Scene7DamChangeEventListener checking - isAsset`
* `[sling-oak-observation-8] com.day.cq.dam.scene7.impl.Scene7UploadServiceImpl synchronizeFolder failed for (null) failed`
* `[OsgiInstallerImpl] com.adobe.granite.offloading.impl.transporter.OffloadingAgentManager Cannot disable outbox replication agent.org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.adobe.cq.mobile.cq-mobile-core [com.adobe.cq.mobile.omnisearch.impl.MobileAppsOmniSearchHandler(3058)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.adobe.aemds.formsmanager.adobe-aemds-formsanddocuments-core [com.adobe.aem.formsndocuments.handlers.FormsAndDocumentOmniSearchHandler(2718)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored15.02.2017 08:28:06.511`
* `[OsgiInstallerImpl] com.adobe.aemds.formsmanager.adobe-aemds-formsanddocuments-core [com.adobe.aem.formsndocuments.handlers.ThemeOmniSearchHandler(2722)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.adobe.cq.screens.com.adobe.cq.screens.dcc [com.adobe.cq.screens.dcc.impl.ScreensOmniSearchHandler(332)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Cannot derive user name for bundle com.adobe.cq.screens.com.adobe.cq.screens.dcc [158] and sub service omnisearch-service)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.day.cq.cq-personalization [com.day.cq.personalization.impl.omnisearch.OfferOmniSearchHandler(947)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Cannot derive user name for bundle com.day.cq.cq-personalization [250] and sub service omnisearch-service)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.day.cq.cq-personalization [com.day.cq.personalization.impl.omnisearch.AudienceOmniSearchHandler(957)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Cannot derive user name for bundle com.day.cq.cq-personalization [250] and sub service omnisearch-service)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.day.cq.cq-personalization [com.day.cq.personalization.impl.omnisearch.ActivitiesOmnisearchHandler(958)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Cannot derive user name for bundle com.day.cq.cq-personalization [250] and sub service omnisearch-service)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.adobe.cq.commerce.cq-commerce-core [com.adobe.cq.commerce.impl.omnisearch.OrdersOmniSearchHandler(623)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Cannot derive user name for bundle com.adobe.cq.commerce.cq-commerce-core [225] and sub service omnisearch-service)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.adobe.cq.commerce.cq-commerce-core [com.adobe.cq.commerce.impl.omnisearch.ProductsOmniSearchHandler(625)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Cannot derive user name for bundle com.adobe.cq.commerce.cq-commerce-core [225] and sub service omnisearch-service)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.adobe.cq.commerce.cq-commerce-core [com.adobe.cq.commerce.impl.omnisearch.ProductCollectionsOmniSearchHandler(627)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Cannot derive user name for bundle com.adobe.cq.commerce.cq-commerce-core [225] and sub service omnisearch-service)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.adobe.cq.commerce.cq-commerce-core [com.adobe.cq.commerce.impl.omnisearch.CatalogsOmniSearchHandler(633)] The deactivate method has thrown an exception (org.apache.sling.api.resource.LoginException: Cannot derive user name for bundle com.adobe.cq.commerce.cq-commerce-core [225] and sub service omnisearch-service)org.apache.sling.api.resource.LoginException: Login Failure: all modules ignored`
* `[OsgiInstallerImpl] com.day.cq.dam.dam-webdav-support [com.adobe.cq.dam.webdav.impl.io.DamWebdavVersionLinkingJob(1697)] The deactivate method has thrown an exception (java.util.NoSuchElementException: No job found with name com.adobe.cq.dam.webdav.impl.io.DamWebdavVersionLinkingJob){code}`
* `[sling-default-5-discovery.connectors.common.runner.d6a26647-dd1c-4665-be2c-afdd19397e77096a1c19-18ce-4051-bbf1-166caed986f2] org.apache.sling.discovery.oak.pinger.OakViewChecker issueConnectorPings: connectorRegistry is null`
* `[sling-default-5-discovery.connectors.common.runner.d6a26647-dd1c-4665-be2c-afdd19397e77096a1c19-18ce-4051-bbf1-166caed986f2] org.apache.sling.discovery.oak.pinger.OakViewChecker announcementRegistry is null`
* Lorsque vous installez le CFPx sur AEM 6.2 SP1 avec le Feature Pack Balises intelligentes, l’étape de workflow ajoutée précédemment pour les ressources de balises intelligentes est supprimée du workflow de mise à jour des ressources DAM.

Voir la liste des [Problèmes connus dans AEM 6.2 SP1](https://docs.adobe.com/docs/en/aem/6-2/release-notes/sp1.html#Known).

## Uber Jar {#uber-jar}

Uber Jar pour 6.2 SP1-CFP20 est disponible dans le [Référentiel Maven public Adobe](https://repo.adobe.com/nexus/content/groups/public/com/adobe/aem/uber-jar/6.2.SP1-CFP19/).

Pour utiliser Uber Jar dans un projet Maven, incluez la dépendance suivante dans votre POM de projet :

```XML
<dependency>
    <groupId>com.adobe.aem</groupId>
    <artifactId>uber-jar</artifactId>
    <version>6.2.SP1-CFP20</version>
    <classifier>apis</classifier>
    <scope>provided</scope>
</dependency>
```

## Lots OSGI et packages de contenu inclus {#osgi-bundles-and-content-packages-included-5}

Le texte suivant répertorie les lots OSGI et les packages de contenu inclus dans le CFP.

* [Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP20](assets/do-not-localize/updated.txt)
* [Liste des packages de contenu inclus dans AEM 6.2SP1-CFP20](assets/do-not-localize/content_package_comparison_result.txt)

>[!MORELIKETHIS]
>
>* [Page des correctifs AEM 6.2](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/aem-releases-updates.html?lang=fr)
>* [Notes de mise à jour d’AEM 6.2 SP1](https://docs.adobe.com/content/docs/en/aem/6-2/release-notes/sp1.html)
>* [Notes de mise à jour d’AEM 6.2](https://docs.adobe.com/docs/en/aem/6-2/release-notes.html)
>* [Page de produits AEM ](http://www.adobe.com/fr/solutions/web-experience-management.html)
>* [Documentation d’AEM 6.2](https://docs.adobe.com/content/docs/en/aem/6-2.html)
>* [Mises à jour de produit prioritaires par Adobe](https://docs.adobe.com/content/help/fr/release-notes/experience-cloud/current.html)

