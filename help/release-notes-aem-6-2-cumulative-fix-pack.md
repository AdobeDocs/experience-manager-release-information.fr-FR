---
title: AEM 6.2 Cumulative Fix Pack
description: Notes de mise à jour cumulées du pack de correctifs Experience Manager 6.2 Analysez plus en détail les problèmes résolus dans divers packs de correctifs cumulatifs dans les composants Experience Manager.
translation-type: tm+mt
source-git-commit: 98d91e0367912d8962bb2f45ae972f50ccb71b5f
workflow-type: tm+mt
source-wordcount: '19975'
ht-degree: 21%

---


# aem 6.2 Notes de mise à jour cumulées du pack de correctifs{#release-notes-aem-cumulative-fix-pack}

<!-- TBD: Should we keep this article published after AEM 6.2 content is archived via UGP-1894. If an AEM version is EOL should we discard its details RNs but still retain its docs?
-->

## Informations sur la version {#release-information}

| **Produit** | Adobe Experience Manager  |
|---|---|
| **Version** | 6.2 |
| **Version ** | [Cumulative Fix Pack 6.2 SP1-CFP20](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq620/cumulativefixpack/AEM-6.2-SP1-CFP20) |
| **Condition requise** | [AEM 6.2 Service Pack 1](https://docs.adobe.com/docs/en/aem/6-2/release-notes/sp1.html) |
| **Disponibilité générale** | 6 juin 2019 |

### Pack de correctifs cumulés {#cumulative-fix-pack}

Adobe a introduit un modèle de diffusion unique pour la publication des correctifs. Au lieu de publier des correctifs pour des problèmes individuels, l’Adobe publie désormais un Cumulative Fix Pack (CFP) tous les mois (sous réserve de l’exécution de contrôles qualité). Un CFP est un module de contenus agrégés contenant plusieurs correctifs. Les CFP comprennent principalement des correctifs de bogues, mais peuvent également inclure des packs de fonctionnalités. Ils présentent les avantages suivants par rapport aux correctifs publiés individuellement :

* Cumulatifs par nature (par exemple, un CFP contient les correctifs apportés par le biais de CFP précédents)
* Meilleure assurance qualité
* Installation simplifiée (l’utilisateur installe un CFP en un seul module sans dépendances, hormis le dernier service pack)

Pour plus d’informations sur le CFP et sur d’autres types de versions, consultez le [Véhicule de version de maintenance](https://docs.adobe.com/content/docs/en/aem/6-2/deploy/maintenance-release-vehicle-definitions.html).

## À propos de cette version {#about-the-release}

aem Cumulative Fix Pack 6.2 SP1-CFP20 est le dernier Cumulative Fix Pack pour AEM 6.2. Il s&#39;agit d&#39;une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de [AEM 6.2 SP1](https://helpx.adobe.com/experience-manager/6-2/release-notes/sp1.html).

>[!CAUTION]
>
>Le fait d’installer le CFP sans avoir validé la compatibilité entre les  packs de fonctionnalités installés peut entraîner une défaillance du système ou la perte de configurations personnalisées, ce qui nécessiterait une restauration à partir de la sauvegarde pour résoudre le problème.

>[!NOTE]
>
>* Un nouveau lot Sling `discovery-  api` Johnzon 1.0.0 est inclus avec AEM Cumulative Fix Pack 6.2 SP1-CFP10. En outre, un utilisateur de service sling-discovery est ajouté avec les privilèges de lecture et d’écriture pour le noeud */var/discovery* dans le référentiel CRX.
   >
   >
* Le lot de courriels d&#39;apache commons **org.apache.commons/commons-email/1.5** a été ajouté en remplacement de **com.day.commons.osgi.wrapper/com.day.commons.osgi.wrapper.commons-email/1.2.0-0002**.
   >
   >
* Adobe recommande de déployer CFP via le dossier d’installation pour les clients disposant d’un grand nombre d’utilisateurs sur l’instance AEM.

>



## Problèmes inclus {#issues-included}

Cette section répertorie tous les problèmes et correctifs inclus dans le CFP actuel.

En outre, ce CFP comprend des correctifs fournis dans [les packs de correctifs cumulatifs précédents](#previous).

### Intégration {#integration}

* Amélioration de la personnalisation du ciblage Campaign à l’aide de la fonction de sauvegarde. NPR-29163 : correctif pour CQ-4264126
* com.day.cq.personalization.impl.TeaserResourceEventHandler résulte en une boucle infinie et provoque des mises à jour des nœuds lors de la publication. NPR-28561 : correctif pour CQ-4263096

### DAM - Général {#dam-general}

* Impossible d&#39;afficher/masquer le bouton de réplication pour les utilisateurs non-administrateurs dans des dossiers de stockage spécifiques. NPR-29026 : correctif pour CQ-4265361

### Vulnérabilité {#vulnerability}

* La structure de protection CSRF ne fonctionne pas avec les formulaires AEM Foundation. NPR-28612 : correctif pour GRANITE-22231

### Formulaires {#forms}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [AEM Forms Release](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package}

>[!NOTE]
>
>Pour les clients AEM Forms, il est impératif d’installer le module complémentaire AEM Forms après l’installation de tout pack de service, pack de correctif cumulatif ou pack de fonctionnalités d’AEM.

>[!NOTE]
>
>Les modules complémentaires AEM Forms permettent d’harmoniser les fonctionnalités des formulaires avec les service packs et les packs de correctifs cumulés AEM. Par conséquent, il est impératif d’installer AEM module complémentaire de formulaires après avoir installé AEM Service Pack, Cumulative Fix Pack ou Feature Pack.

#### Formulaires adaptatifs {#adaptive-forms}

* Problèmes de convivialité avec le composant de saisie tactile pour les périphériques iOS 12.1. NPR-29082 : correctif pour CQ-4261765

#### Forms - Document Security {#forms-document-security}

* La vérification de toutes les signatures d’un PDF à l’aide de PDF Advanced Electronic Signatures (PAdES) renvoie InvalidOperationException. NPR-27848 : correctif pour CQ-4244837

#### Forms - Correspondance {#forms-correspondence}

* Lors de la prévisualisation de la lettre au format PDF, le champ de texte placé sur le gabarit ne respecte pas la valeur saisie à partir de l’onglet de données ou selon la liaison de données spécifiée. NPR-29239 : correctif pour CQ-4266856.

#### Forms - Communication interactive {#forms-interactive-communication}

* Lorsqu’un caractère apostrophe est ajouté, les champs préremplis de la lettre s’affichent en caractères ASCII au lieu d’alphabets standard. NPR-28863 : correctif pour CQ-4262900

### Programme d’installation de Forms JEE {#forms-jee-installer}

* Aucun nouveau correctif AEM Forms dans le programme d’installation de Forms JEE.

## Correctifs et packs de fonctionnalités inclus dans les packs de correctifs cumulés précédents {#hotfixes-and-feature-packs-included-in-previous-cumulative-fix-packs}

### Pack de correctifs cumulés 19 {#cumulative-fix-pack-1}

aem Cumulative Fix Pack 6.2 SP1-CFP19 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de [AEM 6.2 SP1](https://helpx.adobe.com/experience-manager/6-2/release-notes/sp1.html).

Voici les points saillants de ce Cumulative Fix Pack :

* Prise en charge activée de la prise en charge de l’API v3.0 de MS Translator pour AEM 6.2
* Ajout d’un message journal après l’installation réussie du package pour tous les SP, CFP et HF.

### Ressources {#assets}

* Impossible de renommer le dossier DAM si l&#39;autorisation Modifier l&#39;ACL est manquante. NPR-27555 : correctif pour CQ-104652
* L’outil d’éditeur de paramètres d’image prédéfinis ne répond pas aux exigences de la version 6.2.1 CFP 17 et versions ultérieures. NPR-28147 : correctif pour CQ-4261041

### Sites {#sites}

* Le vérificateur de liens ne termine pas la tâche, est bloqué avec des liens qui ne répondent pas. NPR-27373 : correctif pour CQ-4256030
* Le fichier de segments ne se charge pas correctement en raison d’un chemin racine supplémentaire qui rompt le chemin du segment. NPR-28014 : correctif pour CQ-4260332

### Intégration {#integration-1}

* L’annulation de l’héritage de LiveCopy ne fonctionne pas correctement sur les conteneurs ciblés. NPR-28129 : correctif pour CQ-4259813
* Les actions cq:actions ne sont pas prises en compte pour un composant ciblé. NPR-27616 : correctif pour CQ-4257497

* L&#39;affichage d&#39;une icône pour rompre l&#39;héritage n&#39;est pas cohérent. NPR-27671 : correctif pour CQ-4257779

### Felix {#felix}

* Le détail du composant de console Web échoue avec 500 après l’installation de CFP 18 sur l’instance AEM 6.2 SP1. NPR-28350 : correctif pour CQ-4261095

### Traduction {#translation}

* Activez la prise en charge du service MS Translator dans AEM 6.3 après la mise à niveau de MS Translator vers l&#39;API v3.0. NPR-28123 : Correctif pour CQ-4259096

### IU - Fondation {#ui-foundation}

* Le calendrier des sites OOTB affiche des dates incorrectes. NPR-28392

### Granite {#granite}

* Le dictionnaire n’est pas invalidé pour les lots de ressources utilisant sling:basename . NPR-27624

### Soutenance {#sustenance}

* Les journaux d’activité du gestionnaire de packages doivent être extraits dans un fichier journal distinct. NPR-27323 : correctif pour Granite-14866
* Expression/formulation/ligne(s) normalisée(s) dans le fichier error.log à afficher une fois l’installation terminée. NPR-27835
* Le plug-in de package Granite sélectionne la dépendance d&#39;une version inférieure de org.apache.sling.i18n. Correctif pour CQ-4263245
* Le lot com.adobe.cq.com.adobe.cq.ui.commons est supprimé lors de l’installation du dernier CFP après la version 6.2SP1-CFP15. Correctif pour CQ-4258808

### Formulaires {#forms-1}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [AEM Forms Release](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-1}

#### Formulaires adaptatifs {#adaptive-forms-1}

* Vulnérabilité aux injections XML avec les formulaires AEM. NPR-27843 : correctif pour CQ-4257315

### Programme d’installation de Forms JEE {#forms-jee-installer-1}

* Aucun nouveau correctif AEM Forms dans le programme d’installation de Forms JEE.

### Les lots OSGI et les packages de contenu incluaient {#osgi-bundles-and-content-packages-included}

Le texte suivant documents la liste des lots OSGI et des packages de contenu inclus dans le CFP.

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP19

[Obtenir le fichier](assets/do-not-localize/cfp19_osgi_bundles.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP19

[Obtenir le fichier](assets/do-not-localize/cfp19_content_packages.txt)

### Pack de correctifs cumulés 18 {#cumulative-fix-pack-2}

aem Cumulative Fix Pack 6.2 SP1-CFP18 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de [AEM 6.2 SP1](https://helpx.adobe.com/experience-manager/6-2/release-notes/sp1.html).

Voici les points saillants de ce Cumulative Fix Pack :

* Prise en charge Ajoutée dans DAM CommandLineProcess pour tuer le processus à long terme.
* Correction d&#39;une fuite de session dans ReplicationEventListener.
* Prise en charge Ajoutée de la redirection vers le composant de page principal.

### Ressources {#assets-1}

* Les processus Camera Raw sont bloqués pendant les périodes d&#39;assimilation massive, ce qui finit par bloquer tout traitement du flux de travail. NPR-26990 : correctif pour NPR-23860
* La fonctionnalité de téléchargement exploite AEM Assets par le biais de la servlet de téléchargement de ressources, ce qui permet aux utilisateurs anonymes de télécharger tous les fichiers. NPR-27054, Correctif pour CQ-4254732
* Les caractères spéciaux apparaissent déchirés dans la ligne d’objet des modèles de courrier électronique dans AEM. NPR-26470 : correctif pour CQ-4252368

### Sites {#sites-1}

* En raison d&#39;un comportement incorrect de la classe ConfigPostProcessor, la suspension de l&#39;image parente supprime cq : Type de mixage LiveRelationship à partir de la page enfant. NPR-26745 : correctif pour CQ-4254163
* Ajoutez la prise en charge de la redirection au composant de page principal. NPR-26576 : correctif pour CQ-110529
* Migration du hub de contexte vers jquery 3. NPR-26956 : correctif pour CQ-4255472
* Les champs d’entrée d’ancrage apparaissent dans la section visible des navigateurs de la boîte de dialogue jusqu’à ce qu’ils soient maximisés. NPR-26852 : correctif pour CQ-4255019
* Copiez le collage du texte en insérant le &lt;br> indésirable dans le fragment Contenu. NPR-26660 : correctif pour CRTE-151
* L’administrateur de site classique ne génère pas la liste dans le volet de droite pour certaines pages. NPR-27247 : correctif pour CQ-4251621
* (IU classique) Les tentatives de déplacement/changement de nom des pages génèrent une erreur, &quot;Une erreur s’est produite lors du déplacement de la page&quot;. NPR-27179 : correctif pour CQ-4235907

### Intégration {#integration-2}

* com.day.cq.personalization.impl.BrandsRetriever parcourt l’arbre entier pour recueillir les marques disponibles. NPR-27060 : correctif pour CQ-4255790

### WCM - Composants Foundation {#wcm-foundation-components}

* Problème de fonctionnalité de recherche avec le composant liste Foundation. NPR-26817 : correctif pour CQ-4250324

### Plate-forme {#platform}

* En raison d’un tiret cadratin de caractère spécial, l’Editeur ne parvient pas à vider le cache. NPR-27199 : correctif pour CQ-4242790

### Granite {#granite-1}

* Le programme de validation de package ne valide pas les packages inclus dans CFP/SP. NPR-26775 : correctif pour Granite-22825

### Réplication {#replication}

* Fuite de session JCR dans ReplicationListener. NPR-27063 : correctif pour CQ-4232088

### Formulaires {#forms-2}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [AEM Forms Release](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-2}

* Aucun nouveau correctif AEM Forms dans le module complémentaire de Forms.

### Programme d’installation de Forms JEE {#forms-jee-installer-2}

* Aucun nouveau correctif AEM Forms dans le programme d’installation de Forms JEE.

#### Les lots OSGI et les packages de contenu incluaient {#osgi-bundles-and-content-packages-included-1}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP18

[Obtenir le fichier](assets/do-not-localize/62cfp18updated_bundles.txt)

Liste des packages de contenu inclus dans AEM 6.2 SP1-CFP18

[Obtenir le fichier](assets/do-not-localize/content_package_62sp1_cfp18.txt)

### Pack de correctifs cumulés 17 {#cumulative-fix-pack-3}

aem Cumulative Fix Pack 6.2 SP1-CFP17 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de [AEM 6.2 SP1](https://helpx.adobe.com/experience-manager/6-2/release-notes/sp1.html).

Voici les points saillants de ce Cumulative Fix Pack :

* Prise en charge Ajoutée des URL sans extension de site dans at-integration.js
* Suppression de l’importateur d’interrogation S7 de la configuration du service Cloud S7.
* Modifications apportées à la vue audiences afin de prendre en charge la structure de dossiers pour l’implémentation de plusieurs locataires.
* Mise à jour de jqueryui   clientlib v1.12.1.

### Ressources {#assets-2}

* Le démarrage de workflows à partir de l’interface utilisateur d’Asset nécessite que l’utilisateur dispose d’autorisations d’écriture/suppression/modification. NPR-25688 : correctif pour CQ-4250140
* Les boutons Publier et Annuler la publication restent visibles même pour les utilisateurs sans autorisation de &quot;réplication&quot;. NPR-25094
* (Workflow) Le flux de travaux des actifs de balises actives ne se traite pas via la configuration du proxy AEM. NPR-25915 : correctif pour CQ-4248202
* Supprimez l’importateur d’interrogation S7 de la configuration du service Cloud S7. NPR-25239 : correctif pour CQ-95236

### Sites {#sites-2}

* Les workflows démarrés à partir de l’Editeur -> Les informations de page contiennent le chemin de contexte dans la charge utile. NPR-26389 : correctif pour CQ-76804
* (Vérificateur de lien externe) Les liens https non valides sont affichés comme des liens valides. NPR-25541 : correctif pour CQ-4201333
* (IU classique) Lors de la création d’une page autonome sous une copie dynamique, la page est créée sous la forme d’une copie dynamique. NPR-25610 : correctif pour CQ-4249801
* Problèmes liés aux ressources de publication associées au composant Design Importer lorsqu’une page est activée. NPR-25638 : correctif pour CQ-102532
* La barre d’outils de texte enrichi RTE couvre la liste sélectionnée. NPR-25165 : correctif pour CQ-4248948
* Migrez contextub vers jquery 3. NPR-25059 : correctif pour Granite-19902
* Pour les composants d’analyse imbriqués, la première conception satisfaisante (avec le chemin le moins imbriqué) est toujours appliquée à partir de plusieurs composants disponibles. Pour plus d’informations, voir [Résolution du chemin de conception](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/page-templates-static.html). NPR-25250 : correctif pour CQ-4246276

### Intégration {#integration-3}

* A l’aide de l’intégration de la cible prête à l’emploi, le ciblage d’un composant effectue le rendu de la page entière au lieu d’un composant ciblé vide. NPR-25273 : correctif pour CQ-4248003
* La rupture de l’héritage en mode de ciblage montre toujours le composant comme ciblé avec l’héritage non rompu en mode d’édition. NPR-25324 : correctif pour CQ-4248162
* Lorsqu’une personnalisation est définie sur une page et qu’une audience est résolue, l’expérience correspondante s’affiche en mode d’édition. NPR-25731 : correctif pour CQ-4249465
* URL de bande-annonce erronée lors de l’utilisation d’AEM avec un chemin de contexte non défini par défaut. NPR-25971 : correctif pour CQ-4250953
* Rendu vide lors de l’utilisation de l’option d’exclusion. NPR-25295 : correctif pour CQ-4246792
* Les expériences supprimées de l’environnement d’auteur ne sont jamais supprimées du site de publication à l’activation de la page. NPR-24869 : correctif pour CQ-4247832

### DAM - Client DM {#dam-dm-client}

* (Chrome, Firefox) VideoPlayer ignore les clics de souris sur les périphériques tactiles. Correctif pour CQ-4247370

### Plate-forme {#platform-1}

* Permet de configurer le nombre maximal de Reprises lors de l’acquisition/de la publication d’un package. NPR-25328 : correctif pour Granite-22376
* Journalisation incorrecte en cas d&#39;erreurs de réplication. NPR-25308 : correctif pour CQ-4249402
* L’installation de Forms AEM 6.2 Forms CFP8 vers CFP14 entraîne l’échec de l’API Apache. NPR-25053 : correctif pour Granite-21771

### Granite {#granite-2}

* Le processus de synchronisation des utilisateurs échoue avec l&#39;exception OakConstraint0022. NPR-25729 : Correctif pour Oak-7428

### Communities {#communities}

* cq -social-as-provider bundle ne début pas avec les versions 3.x du pilote mongo. NPR-26271 : correctif pour CQ-4252710

### IU - Fondation {#ui-foundation-1}

* Mise à jour de jqueryui   clientlib v1.12.1. NPR-25090 : Correctif pour Granite-21981, CQ-4248897

* (Omnisearch) : La propriété &quot;Title&quot; est vulnérable aux scripts intersites (XSS) dans Sites. NPR-24994 : correctif pour Granite-19933

### Formulaires {#forms-3}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [AEM Forms Release](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-3}

#### Formulaires adaptatifs {#adaptive-forms-2}

* Codage incorrect lors de l&#39;envoi de données à partir du formulaire adaptatif. NPR-25539

#### Forms - Gestion {#forms-management}

* Les éléments de formulaire sans rapport signalés comme des références lors de la publication de la page. NPR-26167 : correctif pour CQ-4251004

### Forms - Programme d’installation JEE {#forms-jee-installer-3}

#### Document Security {#document-security}

* La variable est renseignée en tant que Liste de type de données, le sous-type est une chaîne, mais nous obtenons une erreur &quot;Impossible de contraindre l’objet&quot;. NPR-26194 : correctif pour CQ-4252287
* Impossible d&#39;accéder aux configurations de filigrane après l&#39;installation de 6.2-SP1-CFP15. NPR-26130 : correctif pour CQ-4250984

### Les lots OSGI et les packages de contenu incluaient {#osgi-bundles-and-content-packages-included-2}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP17

[Obtenir le fichier](assets/do-not-localize/62cfp17updated_bundles.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP17

[Obtenir le fichier](assets/do-not-localize/content_package_62sp1_cfp17_2.txt)

### Pack de correctifs cumulés 16 {#cumulative-fix-pack-4}

aem Cumulative Fix Pack 6.2 SP1-CFP16 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de [AEM 6.2 SP1](https://helpx.adobe.com/experience-manager/6-2/release-notes/sp1.html).

Voici les points saillants de ce Cumulative Fix Pack :

* Ajout de la prise en charge de STARTTLS dans Day CQ Mail Service.
* Correction de l’alignement des icônes ContextHub dans la fenêtre contextuelle de profil.
* Correctifs de la fonctionnalité d’affichage/masquage des composants déroulants.
* Mise à niveau vers la dernière version de Jackson 2.8.11

### Ressources {#assets-3}

* Impossible de lancer un processus à partir d&#39;une vue de liste. NPR-24393 : correctif pour CQ-4245788
* (Firefox/Chrome) Impossible de télécharger des ressources dans la page Partage de ressources. NPR-24523 : correctif pour CQ-4224408
* Amélioration de la qualité par défaut de la prévisualisation vidéo en AEM. NPR-24148 : correctif pour CQ-4244310

### Intégration {#integration-4}

* Lorsqu’un composant est ciblé sur une instance de publication, le scintillement s’affiche, affichant l’expérience par défaut avant l’expérience ciblée. NPR-23992 : correctif pour CQ-4242038
* Les expériences supprimées de l’environnement d’auteur ne sont jamais supprimées du site de publication à l’activation de la page. NPR-24869 : correctif pour CQ-4247832

### Plate-forme {#platform-2}

* Patch pour jQuery 1.12.4 de clientlib afin d’inclure un correctif de sécurité. NPR-24129 : correctif pour Granite-20058
* Ajout de la prise en charge de STARTTLS dans Day CQ Mail Service. NPR-23941 : correctif pour CQ-4240397
* Supprimez la commande aclHandling MERGE_PRESERVE par défaut. NPR-24593 : correctif pour Granite-21889
* LineChecker ne parvient pas à externaliser les liens lorsque la requête contient des paramètres de requête non valides. NPR-24127 : correctif pour CQ-4241893

### MSM {#msm}

* Correctifs proactifs pour les attaques de scripts intersites (XSS). NPR-21893 : correctif pour CQ-4223385
* MSM LiveRelationship : RolloutConfig effectif incorrect si BlueprintConfig est sur la racine. NPR-23999 : correctif pour CQ-4243000

### Sites {#sites-3}

* Pour créer une nouvelle expérience dans une zone de copie dynamique, l’héritage doit être rompu pour être configuré. NPR-24995, Correctif pour CQ-4248209
* (Interface utilisateur tactile) Plusieurs icônes de la barre d’outils supérieure disparaissent lors du verrouillage ou du déverrouillage d’une page. NPR-23954 : correctif pour CQ-4243345
* Les champs ne sont pas correctement alignés dans le contexte. NPR-23958
* Action de publication lors de la création de sauts de page verrouillés. NPR-23970 : correctif pour CQ-4243203
* Les rapports OOTB dans /etc/reports/ ne fonctionnent pas correctement et ne présentent aucun graphique de données historique. NPR-20035 : correctif pour CQ-4220180
* La création du lancement échoue lors de l&#39;initialisation du processus de lancement de la demande sur un projet. NPR-24255 : correctif pour CQ-4245030
* Les balises et les attributs HTML ignorés par les courriers électroniques après l’installation de CFP10. NPR-24287 : correctif pour CQ-4240028
* TagPicker : La suggestion de balise dans le champ de balise de métadonnées de schéma requête les noeuds pouvant être balisés, ce qui prend beaucoup de temps à charger. NPR-24347 : correctif pour CQ-4244291
* L&#39;intégration de Salesforce échoue avec les configurations de proxy. NPR-24418 : correctif pour CQ-4245300
* (WCM) PageManager laisse Page archivée sur Exception lors de la création de la révision. NPR-24565 : correctif pour CQ-4246203
* Le bouton Émulateur de périphérique disparaît du mode de modification et de prévisualisation après l’application de CFP14. NPR-24566 : correctif pour CQ-4247060
* (IU classique) Les balises entières s’affichent comme vides une fois créées dans la boîte de dialogue. NPR-24688, Correctif pour CQ-4246407
* Impossible de créer la version lors de la première tentative. NPR-24774 : correctif pour CQ-4232176
* Les rapports OOTB dans /etc/reports/ ne fonctionnent pas correctement et ne présentent aucun graphique de données historique. NPR-24138 : correctif pour CQ-4220180

### Vulnérabilité {#vulnerability-1}

* L’intégration de Salesforce est vulnérable aux attaques SSRF (Server Side Request Forgery). NPR-24289 : correctif pour CQ-4245277
* Vulnérabilité SSRF (Server Side Request Forgery) dans ReportingServicesProxyServlet. NPR-24657 : correctif pour CQ-4246880

### Granite {#granite-3}

* Les opérations de lecture des métadonnées ne sont pas terminées. NPR-24240 : correctif pour Granite-19866
* Mettez Jetty à jour vers la version 9.4.11.v20180605 pour corriger les vulnérabilités. NPR-25033 : correctif pour Granite-22120

### WCM - Composants Foundation {#wcm-foundation-components-1}

* PageComparator lançant ClassCastException lors du tri des pages. NPR-24123 : correctif pour CQ-4244048
* La fonctionnalité Afficher/Masquer du composant déroulant de formulaire ne fonctionne pas comme prévu. NPR-24562 : correctif pour CQ-4222853

### Interface utilisateur {#user-interface}

* Une utilisation intensive du processeur est observée en raison du nombre élevé de requêtes dans la fonctionnalité de recherche d’administrateurs. NPR-23588 : correctif pour Granite-21286
* (IU classique) Le composant affiche les valeurs par défaut même si le service de modèle de données de formulaire associé est défini sur un champ vide. NPR-21903 : correctif pour GRANITE-19744
* Lancement de NPE multichamp lorsque FormData n’est pas présent pour la demande. NPR-24513 : correctif pour Granite-21055

## Formulaires {#forms-4}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [AEM Forms Release](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-4}

#### Base {#core}

* (OSGI) AEM Forms OSGI affecté par l’alerte de sécurité de liaison de données Jackson. NPR-24274 : correctif pour CQ-4230245

#### Gestion des droits {#rights-management}

* Apache POI échoue après l&#39;installation AEM 6.2 SP1-CFP14. NPR-25054, NPR-25052 : correctif pour CQ-4245898, CQ-4244778

#### Formulaires HTML5 {#html-forms}

* Les données ne sont pas renseignées par préremplissage de champs multilignes dans la prévisualisation HTML. NPR-23357 : correctif pour CQ-4244212
* Lorsqu’une lettre est prévisualisée via la prévisualisation par défaut, le mappage des fragments de mise en page ne s’affiche pas alors que la même lettre s’affiche correctement lorsque vous cliquez sur le bouton prévisualisation. NPR-22993 : correctif pour CQ-4237745
* Problème de prévisualisation HTML d’un champ de texte lorsqu’un modèle de numéro de sécurité sociale est appliqué à un modèle. NPR-23205

#### Formulaires adaptatifs {#adaptive-forms-3}

* Erreur &quot;Guidelib is not defined&quot; lors de l’ajout d’un formulaire AEM au composant parsys. NPR-24269 : correctif pour CQ-4244546

### Programme d’installation de Forms JEE {#forms-jee-installer-4}

#### Forms-Install-LCM {#forms-install-lcm}

* Les fins de ligne de fenêtre dans les fichiers de script Shell empêchent LCM de s&#39;exécuter sous UNIX. NPR-22958

### Les lots OSGI et les packages de contenu incluaient {#osgi-bundles-and-content-packages-included-3}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP16

[Obtenir le fichier](assets/do-not-localize/6_2cfp16_bundlecomparison-list.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP16

[Obtenir le fichier](assets/do-not-localize/6_2cfp16_contentpackage-list.txt)

### Pack de correctifs cumulés 15 {#cumulative-fix-pack-5}

aem Cumulative Fix Pack 6.2 SP1-CFP15 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de [AEM 6.2 SP1](https://helpx.adobe.com/experience-manager/6-2/release-notes/sp1.html).

Voici les points saillants de ce Cumulative Fix Pack :

* Correctif de sécurité proactive dans la table Foundation pour préserver la cohérence de la conception.
* Prise en charge Ajoutée de typeHint pour enregistrer les valeurs sous forme de chaîne.
* Sécurité améliorée du service de préremplissage Forms
* Mettez à jour le fichier adobe-reader-extensions-dsc.jar pour obtenir des correctifs dans l’extension de Reader.
* Correction du hook de validation afin de tenir compte des éléments &quot;:non valides&quot; pour l’entrée du numéro de rappel.

### Ressources {#assets-4}

* Les données EmbedXMP sont toujours définies comme « actives » pour le workflow de génération Ptiff. NPR-22776 : correctif pour CQ-4234498
* Impossible de définir plusieurs valeurs par défaut dans les champs à plusieurs valeurs. NPR-22900 : correctif pour CQ-4239000
* (Dynamic Media) Lorsque vous cochez la case Rendus dynamiques, le fichier zip téléchargé génère l’image TIFF d’origine avec un fichier zéro octet. NPR-22410 : correctif pour CQ-4198471
* (IU tactile) Emplacement de téléchargement par défaut des ressources dans la vue de colonnes. NPR-23475 : correctif pour CQ-4237057

### Intégration {#integration-5}

* En mode Cible, les auteurs peuvent modifier un composant hérité du schéma sans annuler l&#39;héritage. NPR-22751 : correctif pour CQ-4237907
* La variable de chemin n&#39;est pas codée correctement, ce qui entraîne la création de scripts intersites non persistants (XSS). NPR-22851

### MSM {#msm-1}

* Lors du déploiement d’une LiveCopy avec plusieurs configurations de déploiement, si un ResourceNameConflict survient sous la racine, le flux de déploiement se termine sans inclure toutes les branches. NPR-22842 : correctif pour CQ-4236188

### Plate-forme {#platform-3}

* Implémentez une limite d’interrogation dans une demande de demande inversée. NPR-23351 : correctif pour Granite-21135****
* La modification du modèle de message n’est pas répercutée sur les journaux personnalisés. NPR-23486 : correctif pour CQ-4241974

### Sites {#sites-4}

* La création d’un lien dans un texte d’un éditeur de texte enrichi vers un document contenant des espaces ou d’autres caractères spéciaux ne fonctionne pas. NPR-22289 : correctif pour CQ-4224321
* L’enregistrement du segment avec une valeur énorme (10000000000) définit l’augmentation sur 0, générant un message d’erreur. NPR-22524 : correctif pour CQ-4237006
* Impossible de cliquer sur l&#39;élément Ajouté dans le composant Multifield. NPR-22552 : correctif pour CQ-4237404
* La barre de défilement horizontale n’est pas visible lorsque le titre du segment est long. NPR-22615 : correctif pour CQ-4237001
* Le chargement d’une audience vide génère un code JavaScript incorrect. NPR-22974 : correctif pour CQ-4238734
* Lors de la planification d’une activation ou de la désactivation, le titre du workflow est obligatoire. Par conséquent, le titre du workflow personnalisé n’est pas traduit dans la chronologie. NPR-23121 : correctif pour CQ-4237552
* Demande de correctifs pour les problèmes liés aux segments de Cible dans les sites. NPR-23128
* (Firefox) La case à cocher correspondant à la personne sélectionnée n’est pas correcte. NPR-23345
* Les étiquettes des différents modes s’affichent avec les icônes. NPR-23275
* Erreur de &quot;valeur de sélecteur de récursion non valide&quot; lors de la migration d&#39;un composant de AEM 6.0 à AEM 6.2. NPR-23503 : Correctif pour CQ-4241258

### Communautés {#communities-1}

* Les notifications par web et par e-mail ne sont pas déclenchées en raison d’un échec d’envoi du message aux groupes. NPR-23447 : correctif pour CQ-4242880

### Traduction {#translation-1}

* Les copies de langue des ressources sont créées lorsque la ressource &quot;Ne pas traduire&quot; est définie sur la configuration de traduction. NPR-22540 : correctif pour CQ-4237962

### Interface utilisateur {#user-interface-1}

* L&#39;utilisation d&#39;Omnisearch avec une requête de trait d&#39;union renvoie une erreur de serveur. NPR-22999 : correctif pour Granite-19674
* DatePicker ne prend pas en charge la définition manuelle d’un conseil de type externe par un champ masqué. La modification de l’indicateur de type génère une erreur de conversion. NPR-23333 : correctif pour Granite-21194

### WCM - Composants Foundation {#wcm-foundation-components-2}

* Le composant CAPTCHA a été abandonné pour une meilleure sécurité. Si vous utilisez le composant CAPTCHA, le message &quot;Le composant Captcha est obsolète et ne doit plus être utilisé.&quot; s’affiche après l’installation de la version 6.2 SP2-CFP15 ou ultérieure. aem composant peut être personnalisé pour inclure reCAPTCHA pour une meilleure sécurité NPR-22151 : Correctif pour CQ-4220052
* La table du composant WCM Foundation est vulnérable aux scripts intersites stockés. NPR-23206 : correctif pour CQ-4240760

### Vulnérabilité {#vulnerability-2}

* Cross-site scripting (XSS) dans les liens des Projets de l’IU d’administration. NPR-23272 : correctif pour CQ-4241795

## Formulaires {#forms-5}

### Package de modules complémentaires Forms {#forms-add-on-package-5}

#### Correspondence Management {#correspondence-management}

* Lorsqu’une lettre est prévisualisée via la prévisualisation par défaut, le mappage des fragments de mise en page ne s’affiche pas alors que la même lettre s’affiche correctement lorsque vous cliquez sur le bouton prévisualisation. NPR-23335 : correctif pour CQ-4237745
* Les données de la lettre correspondant aux liaisons définies dans XDP ne sont pas renseignées à l’aide de l’URL de lettre directe. NPR-24145 : correctif pour CQ-4244290

#### Mobile Forms {#mobile-forms}

* (Correspondence Management) Désalignement des données lors du chargement d’une lettre avec le code XML de la cible. NPR-22993 : correctif pour CQ-4237663

#### Service Reader Extensions {#reader-extensions-service}

* Impossible d&#39;appliquer l&#39;extension Reader à Adobe PDF. NPR-23067

#### Gestionnaire de formulaires {#forms-manager}

* Les Forms incorporées dans le site ne sont pas publiées lors de la republication de la page du site. NPR-23014 : correctif pour CQ-4236566

#### Vulnérabilité {#vulnerability-3}

* Correctifs proactifs pour les scripts intersites. NPR-20624 : correctif pour CQ-4206055
* Vulnérabilité au cross-site scripting (XSS) par stockage dans l’onglet Remarques du gestionnaire de formulaires. NPR-27157 : correctif pour CQ-4255556

#### Service Encryption {#encryption-service}

* (OSGI) [JEE] Etat de signature incorrect pour le PDF avec pièce jointe lors de la vérification à l’aide de &quot;Valider le processus PDF&quot;. NPR-23269, NPR-23737

### Programme d’installation de Forms JEE {#forms-jee-installer-5}

#### Base {#core-1}

* Les problèmes signalés dans l’analyse de code statique de Core-ext doivent être corrigés. NPR-13947

#### Service PDFG {#pdfg-service}

* Le convertisseur HTML vers PDF ne fonctionne pas. NPR-21545

### Les lots OSGI et les packages de contenu incluaient {#osgi-bundles-and-content-packages-included-4}

Le texte suivant documents la liste des lots OSGI et des packages de contenu inclus dans le CFP.

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP15

[Obtenir le fichier](assets/do-not-localize/6_2cfp15updated_bundles.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP15

[Obtenir le fichier](assets/do-not-localize/6_2_cfp15contentpackage-list.txt)

### Pack de correctifs cumulés 14 {#cumulative-fix-pack-6}

aem Cumulative Fix Pack 6.2 SP1-CFP14 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Modification des propriétés de métadonnées des fichiers améliorée.
* Reconfiguré le travail Notification d’expiration de mot de passe pour les actifs déjà en état d’expiration.
* Console d’interface utilisateur tactile personnalisée pour étendre d’autres paramètres régionaux.
* Mise à jour de cq-msm-core pour une synchronisation Livecopyindex efficace.
* Simplification de la fonctionnalité de réplication pour divers déploiements.

### Ressources {#assets-5}

* Les utilisateurs ne peuvent pas télécharger de ressources comportant une clause de non-responsabilité et de longs noms de fichier. NPR-22163 : correctif pour CQ-4235274
* Un guillemet simple empêche la mise à jour des métadonnées dans la vue à puces et l’interface utilisateur est complètement rompue lorsque vous ouvrez les propriétés d’un fichier à l’aide des actions rapides de la barre d’outils. NPR-22317, NPR-22353 : correctif pour CQ-4236990, CQ-4236469
* La tâche de notification d’expiration des ressources ne désactive pas les ressources expirées. NPR-22346 : correctif pour CQ-4237188
* Le téléchargement des ressources échoue lors de l’utilisation de la gestion des droits numériques dans Assets dans Safari. NPR-22378 : correctif pour CQ-4236460
* Le rendu Web pour une petite image présente une taille de pixel inexacte. NPR-22435 : correctif pour CQ-4236742

### Sites {#sites-5}

* (Interface utilisateur tactile) La balise déplacée s’affiche à l’ancien et au nouvel emplacement dans les propriétés de la page. NPR-21921, Correctif pour CQ-4238598
* (Interface utilisateur tactile) L’éditeur de texte enrichi supprime tous les attributs autres que id de la balise &lt;a>. NPR-22045 : correctif pour CQ-4234133
* Le fait de coller directement du contenu dans l’éditeur de texte enrichi à l’aide de Ctrl+V permet d’ignorer les sauts de ligne. NPR-22117 : correctif pour CUI-5881
* (Interface utilisateur tactile) Impossible d&#39;afficher plus de 40 balises sous espace de nommage. NPR-22290 : correctif pour CQ-99114
* Problèmes de flux RSS, port -1 à AEM 6.2 NPR-22158 : Correctif pour CQ-42333339
* (IE) Lors de la création d’un caractère dans un champ de texte enrichi pour la première fois, un espace de fin est ajouté au caractère. NPR-22443 : correctif pour CQ-4235343
* Lors d’une tentative de correspondance avec le nom du package, l’objet Java Use gèle SightlyJavaCompilerService en raison d’un espace de fin dans la déclaration du package. NPR-22557 : correctif pour Granite-20836
* La console d’interface utilisateur tactile ne sélectionne pas de nouvelles langues pour le balisage. NPR-22250 : correctif pour CQ-4239194

### Mobile On-Demand {#mobile-on-demand}

* (Digital Publishing Suite) Les champs Date de publication et Date de couverture devaient être définis pour les folios avant d’être téléchargés dans DPS. NPR-22484

### Commerce {#commerce}

* Plusieurs vulnérabilités de script intersite (XSS) dans l&#39;assistant de création de catalogue de commerce. NPR-22344 : correctif pour CQ-4237017

### MSM {#msm-2}

* La synchronisation de LiveCopyIndex entraîne une saturation des threads lors de longues mises à jour d’index. NPR-22214 : correctif pour CQ-90667
* la propriété cq:cugEnabled est désactivée lorsqu’un autre champ d’une livecopy est modifié, ce qui rend la page non protégée. NPR-22246 : correctif pour CQ-4236050
* L&#39;action Lancement de page ne parvient pas à mettre à jour les enfants lorsqu&#39;une page est suspendue. NPR-22483 : correctif pour CQ-4236956
* Le déploiement d’une structure qui a été déplacé dans un gabarit entraîne un cq:moveTarget erroné. NPR-22373 : correctif pour CQ-4232536

### Intégration {#integration-6}

* Tenter de trier les offres dans la bibliothèque du sélecteur d’offres entraîne un comportement erratique. NPR-22208 : correctif pour CQ-4235439
* TargetContentImpl ralentit AEM pendant les requêtes longues. NPR-22361 : correctif pour CQ-4236907
* Le moteur Target (mbox.js, at.js) n’utilise pas d’URL mal formées et utilise des URL contenant deux-points qui peuvent rencontrer des problèmes avec certains déploiements. NPR-22366 : correctif pour CQ-4237854
* La personnalisation de la page nécessite une publication directement sur le noeud de la marque. NPR-22370 : correctif pour CQ-4236895

### Foundation {#foundation}

* Les modèles Scripting Apache Sling utilisent le lot Provider **org.apache.sling.scripting.sitly.models.provider/1.0.18**. NPR-22614 : Correctif pour Sling-5944, Sling-6866

### Projets {#projects}

* Workflow Starter ne peut pas accepter la valeur TypeHint de String. NPR-22436 : correctif pour CQ-4237855

### Traduction {#translation-2}

* Étude des problèmes liés à la fonctionnalité Aperçu. NPR-22201 : correctif pour CQ-4223753

### Interface utilisateur {#user-interface-2}

* (IU classique) Le composant affiche les valeurs par défaut même si le service de modèle de données de formulaire associé est défini sur un champ vide. NPR-21903 : correctif pour GRANITE-19744

### WCM - Composants Foundation  {#wcm-foundation-components-3}

* Erreur lors de la publication d’une page Live Copy qui pointe vers une page d’importateur dans Adobe Campaigns. NPR-22470 : correctif pour CQ-4237164
* Erreurs JavaScript lors de l’ouverture de l’éditeur de fragments d’expérience. NPR-22598 : correctif pour CQ-4238415

### Workflow {#workflow}

* Le service de notification par courrier électronique de flux de travaux Day CQ déclenche un e-mail par noeud Mongo pour les notifications WorkflowCompleted et WorkflowAborted. NPR-22486 : correctif pour CQ-4238172

## Formulaires {#forms-6}

### Package de modules complémentaires Forms {#forms-add-on-package-6}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

#### Formulaires adaptatifs {#adaptive-forms-4}

* Incohérence dans la valeur d’espace réservé de liste déroulante dans le formulaire adaptatif dans IE11 et Chrome. NPR-22405 : correctif pour CQ-4227096

### Programme d’installation de Forms JEE {#forms-jee-installer-6}

#### Installation de LCM {#install-lcm}

* Mise à à jour de Jsafe Jars vers Cryptoj 6.1.3.1 dans le programme d’installation et LCM. NPR-22744

### Packs de fonctionnalités inclus {#feature-packs-included}

#### Process Management {#process-management}

* (Workspace HTML) Lorsqu’un utilisateur demande une tâche, le nombre de files d’attente est actualisé pour cet utilisateur particulier, mais pas pour les autres utilisateurs, sauf si la page est actualisée. NPR-19778 : correctif pour CQ-4233665

### bundles OSGI et packages de contenu inclus dans CFP14 {#osgi-bundles-and-content-packages-included-in-cfp}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP14

[Obtenir le fichier](assets/do-not-localize/6_2cfp14updated_bundles.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP14

[Get ](assets/do-not-localize/6_2_cfp14contentpackage-list.txt)
FileAEM Cumulative Fix Pack 6.2 SP1-CFP13 est une mise à jour importante qui inclut des correctifs client clés publiés depuis la disponibilité générale de AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Activation de la configuration de champ Paramètre statique dans les paramètres de composant de Cible lors de l’utilisation d’AT.js en tant que bibliothèque cliente.
* Correctifs de la fonctionnalité d’affichage/masquage des composants déroulants.
* Correctifs pour l’utilisation des audiences de synchronisation des cibles.
* Amélioration de la polyvalence de Correspondence Management pour qu’il puisse contenir des caractères spéciaux.

### Ressources {#assets-6}

* La purge de version ne parvient pas à supprimer les anciennes versions des ressources. NPR-21682 : correctif pour CQ-4212996
* La réorganisation des dossiers sous un dossier réordonnable n’est pas conservée. NPR-21964 : correctif pour CQ-4231761

### Sites {#sites-6}

* (TouchUI)(ClassicUI) Plusieurs vulnérabilités de script intersite (XSS) dans les composants HTML et principaux. NPR-21532 : correctif pour CQ-4232305 et CQ-4232511
* La création/mise en forme de contenu (par exemple, l’attribution/la suppression de nouveaux styles de liste) sur un texte sélectionné ne fonctionne pas correctement dans Internet Explorer 11. NPR-21533 : correctif pour CQ-4230689
* (Safari) Les utilisateurs ne peuvent pas vue tous les fichiers du panneau de recherche de ressources. NPR-21981 : correctif pour CQ-4213720
* Time Warp renvoie l’erreur &quot;RecursionTooDeepException&quot; avec une page altérée et aucune nouvelle version n’est créée, même si la date est modifiée. NPR-21707 : correctif pour CQ-4199536
* Lors du chargement d’une page dans l’éditeur, le fournisseur WorkflowStatusprovider (pageinfo.json) est chargé trois fois, ce qui entraîne un ralentissement de l’exécution de l’instance AEM. NPR-21778 : correctif pour CQ-59232

### Intégration {#integration-7}

* La création d’audiences de type et de navigateur mobiles en mode Cible de création ne fonctionne pas en AEM. NPR-21676, NPR-21681 : correctif pour CQ-4232100
* Avec une latence élevée lors de l’actualisation d’un composant ciblé, il est possible d’ajouter une autre offre avant que le composant ne soit complètement actualisé. NPR-21744 : Correctif pour CQ-4233158 / CQ-4234293
* Les utilisateurs ne peuvent pas voir les valeurs de paramètre statique de test dans l’appel de mbox qui s’affichent lors du test avec AT.js en tant que bibliothèque cliente dans la configuration cloud. NPR-21930 : correctif pour CQ-4234520

### Plate-forme {#platform-4}

* Problèmes de performances liés à la synchronisation des utilisateurs lorsque le nombre d’utilisateurs ou de groupes est important. NPR-20431 : correctif pour CQ-4223282
* Utilisateurs non synchronisés avec la synchronisation des utilisateurs à l’aide de la distribution Sling. NPR-21911 : correctif pour Granite-20404
* Eviter que les mots ne soient mis en surbrillance dans les extraits de recherche (sur une page de Geometrixx). NPR-21835 : correctif pour Granite-21067\
   Remarque : Ce correctif nécessite la norme Oak CFP 1.4.20 ou supérieure.

### Traduction {#translation-3}

* la propriété jcr est manquante pour l’ID utilisateur initiateur lors de la création du projet de traduction. NPR-21715 : correctif pour CQ-4230713

### WCM - Composants Foundation {#wcm-foundation-components-4}

* La fonctionnalité Afficher/Masquer du composant déroulant de formulaire ne fonctionne pas comme prévu. NPR-22164 : correctif pour CQ-4235288

## Formulaires {#forms-7}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms  {#forms-add-on-package-7}

#### Formulaires adaptatifs {#adaptive-forms-5}

* Injection d&#39;entité externe XML (XXE) dans Forms adaptatif. NPR-21982 : correctif pour CQ-109878
* (iOS11) Lorsque vous cliquez sur le composant de pièce jointe d’un fichier, la pièce jointe ouvre la caméra au lieu de l’explorateur de fichiers du périphérique. NPR-21926 : correctif pour CQ-4214348
* Le titre manquant dans l’interface utilisateur de création de thème provoque des exceptions et échoue le rendu de la boîte de dialogue. Correctif pour CQ-4236143

#### Correspondence Management {#correspondence-management-1}

* Problèmes de rendu avec les données xml contenant des caractères spéciaux. NPR-21712 : correctif pour CQ-4229137

### Programme d’installation de Forms JEE {#forms-jee-installer-7}

#### Incohérence affectant le service {#assembler-service}

* Le fichier PDF généré à l’aide de la version 6.2.0-ASM-1017-003 est endommagé. NPR-21427 : correctif pour CQ-4228046

#### Service PDFG {#pdfg-service-1}

* Echec de la reconnaissance optique des caractères en raison d’un format de page (PDF) inattendu provenant de fichiers PNG, JPEG et TIFF. NPR-19489 : correctif pour CQ-4209079

## bundles OSGI et packages de contenu inclus dans CFP13 {#osgi-bundles-and-content-packages-included-in-cfp-1}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP13

[Obtenir le fichier](assets/do-not-localize/cfp13_bundlecompare-list.txt)

Liste des packages de contenu inclus dans AEM 6.2SP1-CFP13

[Obtenir le fichier](assets/do-not-localize/cfp13_contentpackage-list.txt)

aem Cumulative Fix Pack 6.2 SP1-CFP12.1 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Amélioration de la gestion des métadonnées pour les champs à plusieurs valeurs.
* Prise en charge de codes de pays à plusieurs caractères (plus de deux) dans les workflows de traduction.
* Amélioration du rendu des pages comportant plusieurs composants imbriqués.
* Amélioration de la synchronisation des dates de publication des actifs entre AEM et Adobe Digital Publishing Suite.

### Ressources {#assets-7}

* Un nombre trop élevé de caractères dans l&#39;omni-recherche provoque le blocage du serveur AEM. NPR-21083 : correctif pour CQ-4223602
* Les valeurs spécifiées dans la deuxième option d’un champ à plusieurs valeurs dans le Schéma de métadonnées ne sont pas ajoutées aux valeurs précédemment spécifiées dans CRX-de. NPR-21220 : correctif pour CQ-4224526
* Le téléchargement des ressources échoue lors de l’utilisation de la gestion des droits numériques dans Assets dans Safari. NPR-21387 : correctif pour CQ-4230287

### Sites {#sites-7}

* (DAM) (ClassicUI) Plusieurs vulnérabilités de script intersite (XSS) dans certains fichiers SWF dans AEM démarrage rapide Auteur/Publier CQ. NPR-21073, NPR-21074 : Correctif pour NPR-20612
* Le sélecteur de balises ne traduit pas les balises disponibles dans plusieurs langues.NPR-21221 : Correctif pour CQ-78855
* Les problèmes de rendu avec AEM console d’article en tant qu’utilisation de plusieurs composants imbriqués la rendent lente. NPR-21271 : correctif pour CQ-4224158

### Intégration {#integration-8}

* Lors de l’ajout d’une structure de Cible, le mode de ciblage n’est pas disponible dans la liste du mode de sélection de l’éditeur. NPR-21047

### Mobile à la demande {#mobile-on-demand-1}

* (Digital Publishing Suite) Les dates de publication des folios dans AEM ne correspondent pas aux dates qui apparaissent dans Folio Producer. NPR-21145

### MSM {#msm-3}

* Le processus de réinitialisation de Live Copy s’arrête après la suppression de la première page locale dans la LC. NPR-21276 : correctif pour CQ-4229743

### Plate-forme {#platform-5}

* La bibliothèque de balises personnalisée qui référence les balises implémentées en tant que script est introuvable après la mise à niveau vers AEM 6.3. NPR-20149 : Correctif pour Granite-18433

### Traduction {#translation-4}

* Les workflows de traduction échouent avec des codes lang_country de plus de 2 caractères. NPR-21088 : correctif pour CQ-4197439
* La page des ressources ne doit pas être autorisée à être renvoyée à nouveau à un projet de traduction tant que le projet n’est pas terminé. NPR-21219 : correctif pour CQ-4209908

### Interface utilisateur {#user-interface-3}

* Le composant Select ne supprime pas la propriété cible lors de l’envoi du formulaire. NPR-21163 : correctif pour GRANITE-14125
* HTTP.encodePathOfURI développe le doublon pour coder le signe plus &quot;+&quot;. NPR-21417 : correctif pour GRANITE-16340

### Vulnérabilité {#vulnerability-4}

* Création de scripts intersites (XSS) dans l’éditeur de métadonnées DAM. NPR-21434 : correctif pour CQ-83472
* Plusieurs fichiers SWF vulnérables aux scripts intersites (XSS). NPR-20612 : correctif pour CQ-4213297

## Formulaires {#forms-8}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms  {#forms-add-on-package-8}

#### Correspondence Management {#correspondence-management-2}

* (IE11) Le rendu initial du contenu HTML se produit uniquement sur le côté gauche tandis que le côté droit se charge par intermittence après le chargement de l’interface utilisateur complète. NPR-21554
* Le bouton d’envoi prévisualisation de lettre est désactivé après l’installation AEM 6.2 SP1-CFP9. NPR-21547
* Lors de la sélection du type de liaison de ressources, la fenêtre Sélecteur de ressources ne s’ouvre pas dans l’assistant Modifier la liaison de données de lettre. NPR-21164 : correctif pour CQ-4194567
* Pour modifier un module de texte modifiable ou en ligne, appuyez sur l’icône Modifier appropriée ou cliquez avec le doublon sur le module de texte approprié dans la prévisualisation de lettre. NPR-21402

#### Formulaires adaptatifs {#adaptive-forms-6}

* Le composant de bouton d’envoi AEM Forms affiche type=&quot;button&quot; au lieu de type=&quot;submit&quot;. NPR-21007
* Les données persistent lors de l’ajout ou de la suppression de nouveaux panneaux pour les panneaux répétables. NPR-21408

### Programme d’installation de Forms JEE {#forms-jee-installer-8}

#### Base {#core-2}

* La mise à niveau vers la dernière mise à jour Java 8 Update 131 renvoie une exception : &quot;Le fournisseur JsafeJCE est désactivé, une vérification d’intégrité FIPS 140 requise a échoué&quot;. NPR-21355

   **Remarque :** Cette NPR nécessite des paramètres supplémentaires. Pour plus d&#39;informations, reportez-vous à la  [dernière mise à jour](release-notes-aem-6-2-cumulative-fix-pack.md#latest-java-update-throws-an-exception-npr) de Java 8.

* Mettez à jour les jsafe jars vers cryptoj 6.1.3.1 dans Core, Encryption, Signature &amp; Document Security. NPR-21360, NPR-21361, NPR-21356, NPR-21358

#### Installation de LCM {#install-lcm-1}

* Mettez à jour Jsafe Jars vers Cryptoj 6.1.3.1 dans installer &amp; LCM. NPR-21362

#### Service PDFG {#pdfg-service-2}

* Mettez à jour Jsafe Jars vers Cryptoj 6.1.3.1 dans PDFG. NPR-21359

#### Process Management {#process-management-1}

* (Workspace HTML) Activation du redimensionnement des colonnes afin que la catégorie de noms n’apparaisse pas tronquée. NPR-19770 : correctif pour CQ-4233668

#### Service Reader Extensions {#reader-extensions-service-1}

* Mettez à jour jsafe jars vers cryptoj 6.1.3.1 dans RE. NPR-21357

## bundles OSGI et packages de contenu inclus dans CFP12.1 {#osgi-bundles-and-content-packages-included-in-cfp-2}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP12.1

[Obtenir le fichier](assets/do-not-localize/cfp12_bundlecomparsion-list1.txt)

Liste des packages de contenu inclus dans AEM 6.2 SP1-CFP12.1

[Obtenir le fichier](assets/do-not-localize/cfp12_contentpackage-list.txt)

aem Cumulative Fix Pack 6.2 SP1-CFP11 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Mise à jour de cq-msm-core pour une synchronisation Livecopyindex efficace.
* Amélioration de l’efficacité de la modification des fragments de contenu.
* Fournit une option de validation dans le gestionnaire de packages pour détecter les autorisations d’ACL.
* Possibilité pour Campaign d’inclure un ID de courrier électronique pour la correspondance client.
* Amélioration des capacités de codage vidéo pour les fichiers Dynamic Media.
* Correctifs dans Sightly Component et LiveCopies.

### Ressources {#assets-8}

* Le codage vidéo Dynamic Media échoue pour les fichiers qui incluent des espaces dans leur nom. NPR-20818 : correctif pour CQ-102469
* Plusieurs vulnérabilités de script intersite (XSS) dans certains fichiers SWF dans AEM CQ Author/Publish quickstart. NPR-21071, NPR-21072
* Les utilisateurs ne peuvent pas télécharger de ressources comportant une clause de non-responsabilité et de longs noms de fichier. NPR-20255 : correctif pour CQ-4222139

### Sites {#sites-8}

* Intégration AEM et Campaign : Des liens spéciaux sont réécrits en Adobe Campaign pour empêcher les clients d&#39;envoyer des messages à : hyperliens dans leurs courriels. NPR-20787 : correctif pour CQ-4225760
* (Interface utilisateur tactile) AEM problèmes de convivialité et de performances lorsque la langue est définie sur le français. NPR-20854 : correctif pour CQ-4227628
* La liaison d’un fichier de ressources codé à l’aide du module externe de liens dans RTE renvoie un lien vide. NPR-20626, NPR-21059 : correctif pour CQ-4223011
* L’éditeur de métadonnées de fragments de contenu empêche les auteurs de contenu d’enregistrer les modifications dans les fragments de contenu. NPR-20641 : correctif pour CQ-4224755
* L’alias de propriété de page conduit à Demander la publication/Demander la déspublication. NPR-20731 : correctif pour CQ-4226227
* Problèmes de composant de texte avec le codage du lien dans l’élément RTE. NPR-20755 : correctif pour CQ-4224321

### Plate-forme {#platform-6}

* ResourceResolverImpl.map() n&#39;appelle pas ResourceDecorator. NPR-20788 : correctif pour GRANITE-19718
* org.apache.sling.i18n.DefaultLocaleResolver ne peut pas traiter les requêtes via org.apache.sling.engine.SlingRequestProcessor. NPR-20706 : correctif pour CQ-94880
* Demande d’ajout d’une option de validation dans Package Manager pour détecter si des autorisations/privilèges ACL sont modifiés sur un package particulier. Correctif pour CQ-4229196

### Intégration {#integration-9}

* (Search &amp; Promote) Une définition de filtre ambiguë pour le package de contenu conduit à des chemins remplacés lors de l’installation. NPR-20808 : correctif pour CQ-4227615

### Workflow {#workflow-1}

* Problèmes de stabilité liés au déploiement du serveur de production AEM. NPR-20979 : correctif pour Granite-19104

### Projets {#projects-1}

* (Interface utilisateur tactile) Impossible d&#39;ajouter des membres d&#39;équipe à un projet. NPR-20990 : correctif pour CQ-4205375

### Composants WCM-Foundation {#wcm-foundation-components-5}

* Le composant Sightly Image Component &#39;link to&#39; génère une erreur 403 en raison de l&#39;extension .html manquante. NPR-20823 : correctif pour CQ-4195909
* Sur un site de plan à l’aide de LiveCopy, la tentative de suppression d’un composant Form renvoie une exception NullPointerException et ajoute le composant Form au lieu de le supprimer. NPR-20855 : correctif pour CQ-4204628
* La synchronisation de LiveCopyIndex entraîne une saturation des threads lors de longues mises à jour d’index. NPR-20634 : correctif pour CQ-90667

### Sécurité {#security}

* Mise à jour proactive de la bibliothèque XSS. NPR-21174
* Mise à niveau vers Apache Commons Email 1.5 qui présente une API simplifiée pour envoyer des e-mails. NPR-20509 : correctif pour Granite-18240
* Correctif de sécurité appliqué à l&#39;API Apache Sling XSS Protection pour éliminer la possibilité de contournement de XSS. NPR-21290 : correctif pour GRANITE-19924
* Contournement XSS dans la fonction XSSAPI#getValidHref. NPR-21174 : correctif pour Granite-19924

### Applications mobiles {#mobile-apps}

* Correction de problèmes liés aux requêtes Curl Head pour les ressources prêtes à l’emploi dans AEM. NPR-20511 : correctif pour CQ-4221520 et CQ-103024

## Formulaires {#forms-9}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

Les principaux aspects pour AEM Forms sont les suivants :

* Activation de l’authentification de certificat pour les utilisateurs de Workbench.
* Correctifs d’utilisation pour Correspondence Management, les formulaires HTML5 et l’espace de travail AEM Forms.

### Package de modules complémentaires Forms {#forms-add-on-package-9}

#### Formulaires HTML5 {#html-forms-1}

* Problèmes de convivialité avec le composant de saisie tactile sur les périphériques iOS 10 et 11. NPR-21092

#### Correspondence Management {#correspondence-management-3}

* (Interface utilisateur de correspondance) Désactivez le bouton d’envoi après un clic. NPR-21078

### Programme d’installation de Forms JEE {#forms-jee-installer-9}

#### Incohérence affectant le service {#assembler-service-1}

* docConvertor ne parvient pas à produire PDF/A avec l’erreur &quot;Le préfixe &quot;stEvt&quot; pour l’élément &quot;stEvt:action&quot; n’est pas lié&quot;. NPR-21032 : correctif pour CQ-4222540
* Une exception est générée avec le nom java.lang.IllegalArgumentException message:No enum constant com.adobe.internal.pdfm.docbuilder.signature.PathValidationFailureReason.SIGNED_IN_FUTURE lors de l’appel du service OMPFSubmission/PDFA/PDFtoPDFA. Ceci empêche l’exécution du processus de vérification de signature de courte durée jusqu’au redémarrage du serveur. NPR-20792

#### Workbench {#workbench}

* Activez l’authentification de certificat pour les utilisateurs de Workbench. NPR-17548 : correctif pour CQ-4214486

#### Process Management {#process-management-2}

* Le processus de préparation des données invoque plusieurs fois lorsque le formulaire mobile est rendu avec les paramètres dataref. NPR-19801 : correctif pour CQ-4230427 : CQ-4230400

## bundles OSGI et packages de contenu inclus dans CFP11 {#osgi-bundles-and-content-packages-included-in-cfp-3}

Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP11

[Obtenir le fichier](assets/do-not-localize/cfp11_bundlecomparsion-list.txt)

Liste des packages de contenu inclus dans AEM 6.2 SP1-CFP11

[Obtenir le fichier](assets/do-not-localize/cfp11_contentpackage-list.txt)

aem Cumulative Fix Pack 6.2 SP1-CFP10 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Ajouté une nouvelle fonction d&#39;utilitaire onDialogLoaded pour les tests.
* Tests et configurations d&#39;unité frontale Ajoutés à ClientLibraryProxyServlet.
* Correctifs de performances dans le composant d’éditeur statique Images multiples.
* Mises à jour de la configuration dans le JCR ResourceBundleProvider JCR Apache Sling.

### Ressources {#assets-9}

* La prévisualisation des ressources ne fonctionne pas si les workflows de mise à jour des ressources sont désactivés. NPR-20543 : correctif pour CQ-4204986
* Problèmes de rendu avec la classe ajoutée dans le granit : propriété de classe (cq-damadmin-admin-assets-upload). NPR-20514 : correctif pour CQ-4219238
* Les ressources miniatures dont le titre comporte des caractères spéciaux affichent un objet java dans l’attribut alt de NPR-20347 : Correctif pour CQ-4223620
* Remplacement du code de comparaison de version par du code propriétaire Adobe en raison de problèmes de licence. NPR-20273 : correctif pour CQ-4223758
* Problèmes de traitement lors du téléchargement de fichiers PSB CMJN avec plusieurs calques alpha. NPR-20251 : correctif pour CQ-4220869
* Les dictionnaires d&#39;internationalisation ne fonctionnent pas si le serveur n&#39;est pas redémarré dans org.apache.sling.i18n 2.5.6. NPR-20525 : Correctif pour Granite - 19490
* Aucun vidage de thread n&#39;est généré en fonction de la période du Planificateur avec la configuration par défaut du collecteur de vidage de threads (début d&#39;AEM par défaut). NPR-20288 : Correctif pour GRANITE-19488 / GRANITE-12741 / CQ-90647.

### Sites {#sites-9}

* Si le filtre de date modifié est modifié après l&#39;ouverture de la recherche enregistrée, les résultats ne sont pas modifiés et les résultats affichés sont identiques à la valeur enregistrée précédente du filtre de date modifié. NPR-19739 : correctif pour CQ-4219425
* Le chargement des pages avec des composants imbriqués a échoué. NPR-20312
* Le processus de demande de suppression est déclenché lors de la suppression des packages de processus. NPR-20266 : correctif pour CQ-4221686
* (Interface utilisateur tactile) Problème de copie/collage avec le Presse-papiers du système d’exploitation et le Presse-papiers AEM interne. NPR-20228 : correctif pour CQ-4220383
* L’instance AEM devient lente avec la vue de liste lorsque plusieurs ressources (plus de 100) sont chargées. NPR-20034 : correctif pour CQ-4222695
* (IU tactile) La suppression des lancements via la console d’interface utilisateur classique rend toutes les pages non modifiables. NPR-20520 : correctif pour CQ-4225074
* La liste déroulante cible ne fonctionne pas avec plusieurs composants RTE dans une boîte de dialogue. NPR-20345 : correctif pour CQ-4220981

### Plate-forme {#platform-7}

* Lors d’un accès via une session anonyme, ClientLibraryProxyServlet ne transmet pas de requêtes proxy aux bibliothèques clientes sur l’instance de publication et renvoie une erreur HTTP 404 introuvable. NPR-20195 : correctif pour Granite-14409

### Intégration {#integration-10}

* La sélection du moteur de cible en tant que Adobe Target empêche le chargement du composant et génère une erreur dans le journal du serveur. NPR-20058 : correctif pour CQ-88071, CQ-109698, CQ-4201600

### Commerce {#commerce-1}

* Aucun message contextuel de confirmation ou de redirection n’apparaît lors de la création de produits de la même page. NPR-20257 : correctif pour CQ-4223414

### Interface utilisateur {#user-interface-4}

* Lorsque le sélecteur de date est un champ de plusieurs champs, les valeurs enregistrées dans les champs de date ne sont pas conservées lors de la modification du composant. NPR-20077 : correctif pour GRANITE-19147
* Les requêtes antérieures ne sont pas abandonnées si des requêtes consécutives sont déclenchées, ce qui entraîne des résultats incorrects. NPR-20397 : correctif pour GRANITE-19306

### WCM - Composants Foundation {#wcm-foundation-components-6}

* La propriété ImageMap existe toujours même après la suppression des images du composant d’éditeur statique Image multiple. NPR-20142 : correctif pour CQ-4222982

## Formulaires {#forms-10}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms  {#forms-add-on-package-10}

#### Formulaires adaptatifs {#adaptive-forms-7}

* Le script valueCommit est exécuté deux fois pour DropDownList lorsqu’il est modifié via l’interface utilisateur. NPR-19989 : correctif pour CQ-110212

### Programme d’installation de Forms JEE {#forms-jee-installer-10}

**Process Management**

* Le package CFP contient AEM Forms HTML Workspace version 2.2.26. NPR-20099
* Le formulaire prérempli ne fonctionne pas lorsque le formulaire pour périphériques mobiles est configuré pour la vue au format PDF. NPR-20566

**Gestion des droits**

* La boîte de dialogue de sélection des certificats d&#39;authentification mutuelle/CAC doit afficher les certificats avec une utilisation améliorée de la clé (EKU) comme authentification du client ou connexion à la carte à puce. NPR-20708
* Forms JEE prend en charge l’authentification mutuelle PKCS#11. NPR-15001

## bundles OSGI et packages de contenu inclus dans CFP10 {#osgi-bundles-and-content-packages-included-in-cfp-4}

Liste des lots OSGi inclus dans AEM CFP 6.2 SP1-CFP10

[Obtenir le fichier](assets/do-not-localize/bundle-list-cfp10.txt)

Liste des packages de contenu inclus dans AEM CFP 6.2 SP1-CFP10

[Obtenir le fichier](assets/do-not-localize/contentpackage-list-cfp10.txt)

aem Cumulative Fix Pack 6.2 SP1-CFP9 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale d&#39;AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Configuration de l’interface utilisateur d’Analytics Classic adaptée pour une entrée secrète.
* Correctifs du cache de persistance indépendant pour Contexthub.
* Calcul précis des dimensions d’actif.
* Optimisation des performances AEM lors de la publication de fichiers sur le portail de marques.
* Correctifs de la valeur Resourcetype dans le noeud de trame.
* Activation de la fonctionnalité de recherche de caractères spéciaux et sensibles à la casse pour le contenu des fragments de document.
* Amélioration de la Forms adaptative pour joindre un PDF en tant que pièces jointes dans Safari.\
   Fournit une nouvelle Dynamic Media qui se connecte à la nouvelle infrastructure de publication Dynamic Media pour une réplication plus rapide et plus évolutive.

### Ressources {#assets-10}

* AEM Assets ne parvient pas à extraire les références de sous-ressources pour les ressources d’InDesign ; les liens de duplicata vers la ressource sont inclus. NPR-19006 : correctif pour CQ-4204186
* L’option Trier ne fonctionne pas pour les ressources de la collection sous Commerce. NPR-19508 : correctif pour CQ-4213622
* Lorsqu’une ressource portant le même nom qu’une ressource existante est déplacée au même emplacement, la valeur de cq : lastReplicationAction pour les ressources est permuté entre elles, ce qui entraîne la création de métadonnées incorrectes. NPR-19531
* Un message d’erreur s’affiche lors de la publication d’un grand nombre de fichiers, même si tous les fichiers sont correctement publiés. NPR-19629 : correctif pour CQ-4219611
* Les rendus statiques sont répertoriés avec des dimensions fixes et ne reflètent pas la taille du rendu réel. NPR-20004
* L’instance d’AEM est ralentie lorsque plusieurs ressources (plus de 4) sont publiées sur Brand Portal. NPR-20009

### Sites {#sites-10}

* aem affiche un comportement inattendu lorsqu’un utilisateur tente de publier/annuler la publication/créer la version d’une page verrouillée par un autre utilisateur. NPR-19249; Correctif pour CQ-4215298 et CQ-4203856
* Lors de la promotion manuelle du lancement imbriqué, la page enfant est supprimée. NPR-19704
* Problèmes de persistance lorsque les boutiques ContextHub remplacent le calque de persistance par défaut lors de l’initialisation. NPR-19979 : correctif pour CQ-4218399
* Les fragments de contenu se chevauchent avec d’autres boutons. NPR-19980 : correctif pour CQ-4221519
* Page du site non affichée lors de l&#39;affichage à l&#39;aide d&#39;un alias dans SiteAdmin. NPR-20053 : correctif pour CQ-4221478
* Erreur lors de la publication d’une page Live Copy qui pointe vers une page d’importateur dans Adobe Campaigns. NPR-20066 : correctif pour CQ-4220846

### Plate-forme {#platform-8}

* Mise à niveau d’Apache POI vers la version 3.16 afin de prendre en charge l’inclusion d’une image d’arrière-plan des diapositives PPT dans les rendus. NPR-18286
* Problèmes de rendu avec Internet Browser 11 et Edge lors du téléchargement de plusieurs fichiers dans le même dossier. NPR-20062

### Intégration {#integration-11}

* Le fichier at.js personnalisé n’est pas publié lorsqu’il est utilisé avec l’utilisateur anonyme. NPR-19542 : correctif pour CQ-4219592
* Migration des informations d’identification Analytics existantes vers l’authentification WSSE. NPR-19962

### Brand Portal {#brand-portal}

* Activation de la publication de balises à partir d’AEM dans Brand Portal depuis la console tagadmin/tagging. NPR-20271

## Formulaires {#forms-11}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

### Package de modules complémentaires Forms  {#forms-add-on-package-11}

#### Correspondence Management {#correspondence-management-4}

* Activation de la fonctionnalité de recherche de texte réel dans les fragments de document lorsqu’une lettre est prévisualisée. NPR-19712

#### Formulaires adaptatifs {#adaptive-forms-8}

* Amélioration de la Forms adaptative pour joindre un PDF en tant que pièces jointes dans Safari. Pour prendre en charge la même fonctionnalité dans les formulaires existants, nous devons modifier la configuration dans le widget de pièce jointe et dans les &quot;types de fichier pris en charge&quot; mettre à jour la valeur application/pdf au lieu de .pdf. NPR-19623

#### Gestionnaire de formulaires {#forms-manager-1}

* Si validationState n’est pas défini sur un champ de formulaire adaptatif et que le événement elementFocusChanged se produit, un événement d’erreur (errorState) est renvoyé au serveur Adobe Analytics. NPR-19513

### Programme d’installation de Forms JEE {#forms-jee-installer-11}

#### Base {#core-3}

* Le gestionnaire de connexions n&#39;est pas disponible pendant l&#39;arrêt. Jboss supprime la dépendance JDBC avant que l’EAR de l’auteur ne soit dédéployé, ce qui entraîne des problèmes de corruption. NPR-19703

## Packs de fonctionnalités inclus {#feature-packs-included-1}

* Améliorations de la correction des miniatures et de la transparence à Dynamic Media. NPR-15207

## bundles OSGI et packages de contenu inclus dans CFP9 {#osgi-bundles-and-content-packages-included-in-cfp-5}

Liste des packages de contenu mis à jour dans AEM 6.2SP1-CFP9

[Obtenir le fichier](assets/do-not-localize/content_package-list62sp1-cfp9.txt)

Liste des lots OSGi mis à jour dans AEM 6.2SP1-CFP9

[Obtenir le fichier](assets/do-not-localize/content_package-list62sp1-cfp9-1.txt)

aem Cumulative Fix Pack 6.2 SP1-CFP8 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale d&#39;AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Présentation des balises aux modèles d’utilisateurs personnalisés sur le service de modèles de courrier électronique d’Adobe.
* Boutons TouchUI améliorés pour l&#39;application de bureau.
* Désactivation du bouton d’envoi en cliquant pour empêcher plusieurs envois de formulaire sur une page de traduction.
* Plusieurs composants RTE configurés dans une boîte de dialogue.
* Références renforcéesMises à jour en copie dynamique.
* Activation de la fonctionnalité de recherche sensible à la casse pour le contenu des fragments de document.
* Liste Ajoutée des bibliothèques Linux à la documentation d&#39;installation AEM Forms.

### Ressources {#assets-11}

* Problèmes liés à l’application du filtre Omnisearch sur les collections dynamiques dans le navigateur Safari. NPR-19511
* Les métadonnées des mots-clés PDF ne sont pas correctement extraites et modifiées lorsqu’un fichier PDF comporte plusieurs mots-clés. Pour résoudre ce problème, la propriété des métadonnées du champ Objet a été supprimée pour les ressources PDF. Vous pouvez toutefois modifier le schéma de métadonnées pour ajouter un champ de texte à plusieurs valeurs pour le champ Objet. NPR-19126
* Le service de notification de flux de travaux n’encode pas les liens dans le courrier électronique, ce qui les empêche de se charger une fois que les utilisateurs les ont cliqués. NPR-19490 : correctif pour CQ-4218055
* Impossible de charger la liste complète des pages/ressources en mode Colonnes avec Chrome. NPR-19458 : correctif pour CQ-4214248
* L&#39;icône Heure de désactivation incorrecte s&#39;affiche dans AEM boîte de réception lors de l&#39;activation du flux de travail &quot;Demande d&#39;Activation&quot;. NPR-19365 : CQ-4216174
* Problèmes de tri dans la vue de listes. NPR-19217 : CQ-95602
* Lors de la modification du titre ou de l’image miniature dans les paramètres du dossier de ressources, le groupe d’origine et les autorisations du dossier sont remplacés. NPR-19283 : correctif pour CQ-4216080
* Les stations de travail Windows 10 passent automatiquement en mode tactile pour désactiver certains boutons. NPR-19183

### Sites {#sites-11}

* Problèmes liés au fait que plusieurs composants RTE soient présents dans une boîte de dialogue. NPR-19311 : NPR-19587.
* La purge automatique de version dans vanilla AEM 6.2 ne fonctionne qu&#39;une seule fois après l&#39;initialisation de VersionManagerImpl. NPR-19315 : correctif pour CQ-4217175
* L’instance de flux de travail est bloquée sur l’étape de flux de travail &quot;Exportation Salesforce.com&quot;. NPR-19222 : correctif pour CQ-4212976
* Les pages de copies de langue créées à partir de copies dynamiques ne sont pas modifiables. NPR-18967
* ReferencesUpdateAction ne parvient pas à mettre à jour les liens dans une LiveCopy imbriquée avec changement de hiérarchie. NPR-18715 : correctif pour CQ-4214105

### Plate-forme {#platform-9}

* Le service Modèle de courrier électronique Adobe ajoute des balises aux modèles utilisateur personnalisés. NPR-19190 : correctif pour CQ-4217113

### Projets {#projects-2}

* Les éditeurs de projet ne peuvent pas copier/coller de ressources dans le dossier de ressources du projet. NPR-19619
* Impossible de générer la prévisualisation pour les projets de traduction après l&#39;installation de 6.2 SP1-CFP1. NPR-16481 : CQ-4204655

### Intégration {#integration-12}

* Les propriétés d’accès des articles sont mal configurées dans Adobe Digital Publishing Solution dans l’IU classique. NPR-19366
* Le rendu des vignettes en raison d’articles en taille réelle dans AEM console d’articles est optimisé. NPR-19086 : CQ-4217148
* Comportement incorrect du pliage automatique lors de la personnalisation des offres via Campaign si les utilisateurs ont accès à plusieurs zones. NPR-19290 : correctif pour CQ-4218029
* La boîte de dialogue de ciblage ne s’affiche pas en mode ciblage lorsqu’un module cible est modifié et enregistré plusieurs fois. NPR-19144 : correctif pour CQ-4216708

### Workflow {#workflow-2}

* Utilisateurs ne pouvant pas filtrer les notifications dans la boîte de réception par utilisateur/groupe dans l’interface utilisateur de la boîte de réception Classic. NPR-19122 : correctif pour CQ-4215374
* La zone cliquable ne conserve pas les coordonnées sélectionnées dans le composant d’image HTML. NPR-18911 : CQ-4211584

## Formulaires {#forms-12}

* Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [AEM Forms Release](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-12}

* Lorsque du contenu est copié à partir de Microsoft Word ou d’un navigateur Web vers l’éditeur de texte du gestionnaire de correspondance, le style est perdu. NPR-19530
* Le contenu sans saut de ligne dans l’éditeur de texte n’est pas encapsulé. NPR-19481
* Activation de la fonctionnalité de recherche de texte réel dans les fragments de document lorsqu’une lettre est prévisualisée. NPR-17792 : correctif pour CQ-4214501

#### Correspondence Management {#correspondence-management-5}

>[!NOTE]
>
>Cette fonctionnalité de recherche de fragments de texte présente certaines contraintes : -
>
>* Le contenu des fragments de document est sensible à la casse et les titres ne sont pas sensibles à la casse.
>* Les résultats de la recherche ne sont pas mis en évidence lorsqu&#39;une partie du mot recherché est dans un style différent ou contient un caractère spécial tel que &quot; ou &quot; ou \.
>* La recherche ne fonctionne pas pour le contenu dynamique (comme les valeurs d’élément du dictionnaire de données ou les valeurs de variable) dans le fragment de document.


#### Gestionnaire de formulaires {#forms-manager-2}

* Les propriétés de Schéma XML d’Adaptive Forms ne peuvent pas être modifiées après l’application de CFP6 à AEM 6.2. Correctif pour CQ-4219684
* Tous les services du lot principal AEM Forms Manager ne sont pas démarrés lors du redémarrage du serveur. Correctif pour CQ-4217014

### Programme d’installation de Forms JEE {#forms-jee-installer-12}

#### Installation de LCM {#install-lcm-2}

* L&#39;écran Administrateur sous Microsoft windows affiche la version 6.0 après l&#39;installation de CFP6. Correctif pour CQ-4217573

## Packs de fonctionnalités inclus {#feature-packs-included-2}

* Boutons TouchUI améliorés pour l&#39;application de bureau. NPR-18676

## bundles OSGi inclus dans CFP8 {#osgi-bundles-included-in-cfp}

Liste des lots OSGi mis à jour dans AEM 6.2SP1-CFP8

[Obtenir le fichier](assets/do-not-localize/updated-bundles-list-cfp8.txt)

Liste des packages de contenu mis à jour dans AEM 6.2SP1-CFP8

[Obtenir le fichier](assets/do-not-localize/6_2sp1-cfp8-contentpackagelist.txt)

aem Cumulative Fix Pack 6.2 SP1-CFP7 est une mise à jour importante qui inclut des correctifs client clés publiés depuis la disponibilité générale d&#39;AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Changement de comportement lors de l’affichage des titres sur la carte d’image pour l’image ayant une balise dc : propriété title définie sur String [] (multifield).
* Correctifs du problème de performances avec les Cloud Services Dynamic Media, l’interface utilisateur tactile et les interfaces de sécurité.
* Correctifs dans Apache Felix Http Bridge 3.0.8
* Résolution de la réplication binaire (BLR) entre l’environnement d’auteur et de publication.
* Prise en charge du fichier de bibliothèque de cibles, AT.JS, une bibliothèque d’implémentation pour l’intégration côté client avec Adobe Target conçue pour les implémentations Web classiques et les applications d’une seule page.
* Amélioration des performances AEM en introduisant un délai d’expiration de connexion configurable par l’utilisateur pour les solutions de Marketing Cloud (Analytics, DTM, Cible et S&amp;P).

### Ressources {#assets-12}

* Lors du test de l’assimilation de vidéos avec AEM 6.3 configuré avec les Cloud Services Dynamic Media, l’exception &quot;Trop de fichiers ouverts&quot; est générée. NPR-18734; Correctif pour CQ-4211407
* Le paramètre d’URL de vanité pour les ressources d’une page ne fonctionne pas après le redémarrage de l’instance AEM. NPR-18634; Correctif pour Granite-18085
* Dans TouchUI, le bouton Publier s’affiche pour les utilisateurs qui n’ont pas l’autorisation de publier des fichiers. NPR-18620; Correctif pour CQ-4214042
* L’option de rendu dynamique n’est pas présente dans la boîte de dialogue de téléchargement d’un fichier une fois le contrat de licence défini. NPR-18607; Correctif pour CQ-4212342
* Le rendu dynamique ne peut pas être téléchargé pour les ressources qui incluent des espaces dans leur nom. NPR-18571; Correctif pour CQ-4211738
* Impossible d’enregistrer plusieurs utilisateurs lors du partage du dossier de ressources avec Creative Cloud. NPR-18489; Correctif pour CQ-103297
* dc : title &amp; dc : description ne change pas en une valeur de plusieurs champs dans crx/de. NPR-18474; Correctif pour CQ-4209086
* L’opération de déplacement des ressources entraîne une dégradation des performances. NPR-18346
* Aucun élément n&#39;est affiché dans le journal lorsqu&#39;il est ouvert avec l&#39;option Afficher tout définie par défaut. NPR-18302; Correctif pour CQ-4211957
* Une erreur se produit lorsqu’un fichier texte codé en ASCII/UTF-8 est téléchargé vers AEM Assets et la création des miniatures échoue. NPR-18006 : CFP pour CQ-4209345
* Les boutons d’action de publication sont visibles même si l’utilisateur ne dispose pas de l’accès de réplication. NPR-17353; Correctif pour CQ-4209269
* Siteadmin et Miscadmin ne fonctionnent pas lorsque la minification est activée à l’aide de min:gcc;obfuscate=true. NPR-18593; Correctif pour CQ-4209220
* Les options de menu personnalisées n’apparaissent pas tant que l’écran n’est pas actualisé à chaque fois. NPR-18500; Correctif pour CQ-4213581
* Mettez à niveau le fichier moment.js vers la version 2.10.6. NPR-18596 ; Correctif pour Granite-11881
* L&#39;application d&#39;autorisations pour les macros DM rompt la vue pour l&#39;utilisateur administrateur. NPR-18544; Correctif pour CQ-4211729
* La fonction Publier ultérieurement pour les ressources génère une exception ArgumentException non autorisée. CQ-4214532

### Sites {#sites-12}

* Sur une grappe d’auteurs principale principale avec MongoDB, les deux auteurs tentent de déclencher la réplication pour le même contenu, lorsque le délai atteint On-time set for the content. NPR-18708; Correctif pour CQ-4210982
* NPE lors du déplacement d&#39;une ressource avec une référence sans jcr : noeud de contenu. NPR-18664
* Les espaces réservés ne sont pas visibles dans une page qui contient plusieurs composants parsys. NPR-18645; Correctif pour CQ-110253
* Problèmes de simultanéité dans AbstractCopyMoveCommand. NPR-18591
* Lors de la copie de texte vers un composant parsys à partir d&#39;une autre instance AEM, le paramètre est créé sans aucun paramètre resourceType défini. NPR-18511; Correctif pour CQ-4212306

### Plate-forme {#platform-10}

* Le programme d’installation de JCR ne met pas à jour la version du lot après l’installation du package. NPR-18728; Correctif pour NPR-15135
* La réplication binaire (BLR) échoue avec l&#39;environnement d&#39;auteur et de publication binaires b/w. NPR-18704
* Demande de résolution d&#39;Apache Felix Http Bridge dans AEM environnement. NPR-18297
* La réplication échoue lorsque plusieurs pages ayant une structure similaire sont répliquées simultanément avec la distribution de contenu Sling. NPR-18665; Correctif pour Granite-13712
* Des paquets de distribution Sling se construisant et non pas auto-nettoyés. NPR-18601; Correctif pour Granite-16183

### Intégration {#integration-13}

* L’affichage des offres publiées à partir des dossiers de bibliothèque génère un NPE. NPR-18732; Correctif pour CQ-4214593
* La date de début/fin d’une activité n’est pas mise à jour dans le JCR et la Cible lorsqu’elle passe d’une date spécifique à &quot;Lorsqu’elle est activée/désactivée&quot;. NPR-18612; Correctif pour CQ-104831
* L’intégration d’Analytics à l’AEM n’a pas de délai d’expiration de connexion ou de socket défini pour les connexions httpclient. NPR-18497
* L’intégration de la gestion dynamique des balises avec l’AEM n’a pas de délai d’expiration de connexion ou de socket défini pour les connexions httpclient. NPR-18495
* L&#39;intégration de la Cible avec l&#39;AEM n&#39;a pas de délai d&#39;expiration de connexion ou de socket défini pour les connexions httpclient. NPR-18494
* L’intégration de Search &amp; Promote à l’AEM n’a pas de délai d’expiration de connexion ou de socket défini pour les connexions httpclient. NPR-18493
* L’activité Target est désactivée après l’ajout d’une expérience supplémentaire. NPR-18227; Correctif pour CQ-4201895

### Composants WCM-Foundation {#wcm-foundation-components-7}

* Les zones cliquables ne conservent pas les coordonnées sélectionnées dans le composant d’image HTML. NPR-18530; Correctif pour CQ-4211584

### Traduction {#translation-5}

* Les résultats de recherche de traduction n’incluent pas les noms des projets de traduction. NPR-18224; Correctif pour CQ-4210658

### Portail de marque {#brand-portal-1}

* Activation de la publication de balises à partir d’AEM dans Brand Portal depuis la console tagadmin/tagging. CQ-4212165

## Formulaires {#forms-13}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [AEM Forms Release](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-13}

#### Correspondence Management {#correspondence-management-6}

* Les données correctes ne s’affichent pas dans le panneau de modification tant que le fragment n’est pas enregistré. NPR-19092
* Ajouter un fragment de document à une lettre prend beaucoup de temps. NPR-18958
* Si une déclaration XML existe dans un fichier xml de données et que le rendu de lettre est lancé via une requête POST, la lettre correspondante n’affiche pas les données. NPR-18870
* Aucun journal d’audit n’est généré pour les actions effectuées sur des ressources CM. NPR-16618

>[!NOTE]
>
>N’installez pas ce package d’Ajoute de CFP si vous êtes affecté par les deux problèmes suivants :
>
>* Copier Coller de Word / Web dans CM Text Editor affiche le contenu du saut de ligne. NPR-19530
>* Le contenu sans saut de ligne dans l&#39;éditeur de texte de CM n&#39;est pas renvoyé à la ligne. NPR-19449

>
>
Ces questions seront abordées dans la future PCP.

#### Formulaires adaptatifs {#adaptive-forms-9}

* Lors de l’ajout d’un nouveau panneau pour les panneaux répétables, la valeur du champ déroulant du panneau précédent est supprimée. NPR-18772
* Les champs de formulaire adaptatif marqués pour accepter uniquement des entiers acceptent également quelques caractères spéciaux du pavé numérique. NPR-18680
* Le script destiné à modifier le titre du bouton lors de l’initialisation du événement du panneau de commande ne fonctionne pas. NPR-18476
* La barre de défilement n’est pas visible dans le panneau de droite pour les règles créées dans l’éditeur de règles. NPR-18716

#### Application AEM Forms {#aem-forms-app}

* Forms ne s’affiche pas correctement dans l’application AEM Forms lorsqu’elle est en mode hors ligne ou n’est pas connectée au réseau. CQ-4218368

### Programme d’installation de Forms JEE  {#forms-jee-installer-13}

#### Service PDFG {#pdfg-service-3}

* PDF Generator ne parvient pas à produire des documents PDF avec les niveaux de signets spécifiés. Correctif pour CQ-4211102

## bundles OSGi inclus dans CFP7 {#osgi-bundles-included-in-cfp-1}

Liste des lots OSGi mis à jour dans AEM 6.2SP1-CFP7

[Obtenir le fichier](assets/do-not-localize/bundle-list-6_2sp1cfp7.txt)

Liste des packages de contenu mis à jour dans AEM 6.2SP1-CFP7

[Obtenir le fichier](assets/do-not-localize/cfp7_content_packages.txt)

aem Cumulative Fix Pack 6.2 SP1-CFP6 est une mise à jour importante qui inclut des correctifs client clés publiés depuis la disponibilité générale d&#39;AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Gestion efficace des composants masqués en mode de mise en page sur tablette.
* Présentation des actions rapides sur les périphériques hybrides.
* Résolution des problèmes de synchronisation au niveau des composants avec des copies en direct.

### Ressources {#assets-13}

* Le client est bloqué lorsque l’utilisateur qui n’a pas l’autorisation requise tente de déplacer l’opération sur un fichier. NPR-18330; Correctif pour CQ-4212560
* La fusion de plusieurs configurations de services de contenu dynamique entraîne des problèmes de convivialité. NPR-18273; Correctif pour CQ-4201557
* Les Workflows/actions de paiement ne sont pas disponibles à partir de la console Chronologie une fois approx. 80 fragments sont ajoutés dans le dossier Ressources. NPR-18257; Correctif pour CQ-4211214 et NPR-18251 ; Correctif pour CQ-4211216.
* Le système se bloque dans Mémoire insuffisante et manque de pagination pendant les rapports Ressources. NPR-17865; Correctif pour CQ-4209759
* La lecture de la vidéo publiée échoue sur le fichier vidéo codé. NPR-17849; Correctif pour CQ-4210739
* La miniature pour PDF n’est pas générée. NPR-17831, NPR-17750; Correctif pour CQ-4210547
* Les actifs expirés ne sont pas désactivés par la tâche de notification d’expiration DAM Adobe CQ. NPR-17666; Correctif pour CQ-107766
* Les activités d’expiration des ressources s’arrêtent si aucun propriétaire n’est affecté à une ressource. NPR-17665; Correctif pour CQ-4197946
* Une exception NullPointerException se produit en cas de déplacement d’un dossier de ressources contenant plus de 150 références entrantes. CQ-4200981

### Sites {#sites-13}

* La personnalisation ne fonctionne que pour la première adresse IP lorsque la règle de segmentation est définie pour une plage d’adresses IP. NPR-18121; Correctif pour CQ-83767
* Échec de la connexion en raison de NumberFormatException lorsque la propriété historyShow est activée. NPR-18073; Correctif pour CQ-101965
* Les pages supprimées marquées sont visibles dans l’interface utilisateur tactile. NPR-18025; Correctif pour CQ-86694
* Problèmes de performances lors du chargement d’une page avec des audiences importantes (2000+). NPR-17884; Correctif pour CQ-4209567
* Impossible de sélectionner une image après avoir supprimé une autre image de la page. NPR-17711; Correctif pour CQ-4201323

### Plate-forme {#platform-11}

* Les contrôles d’interface utilisateur tactile ne sont pas masqués pour les utilisateurs qui ne disposent pas des autorisations requises. NPR-17945; Correctif pour CQ-4211231
* Balises japonaises manquantes dans le champ du sélecteur de balises. NPR-17768; Correctif pour CQ-4210456
* La requête getsize() renvoie des résultats incorrects lorsque FastQuerySize est activé. NPR-18018
* La console Web de l&#39;instance Secondaire n&#39;est pas accessible. NPR-17861; Correctif pour Granite-14582

### Commerce {#commerce-2}

* La traversée de requête survient lorsque le modèle de catalogue n&#39;a aucune condition définie pour une section. NPR-18229; Correctif pour CQ-4211924

### Communautés {#communities-2}

* PollingImporterImpl. retarde AEM fermeture. NPR-18298; Correctif pour CQ-96133

### Intégrations {#integrations}

* Résolution des erreurs du composant de recherche AEM qui peuvent se produire lorsque le client HTTP AEM Day 3.1 OSGI est configuré avec un proxy qui requiert une authentification Digest. NPR 18128
* Case manquante pour rétablir l&#39;héritage. NPR-17753; Demande de correctif logiciel pour CQ-4210139
* Les utilisateurs ne peuvent pas définir la priorité lors du ciblage d’un composant avec plusieurs activités. NPR-18658; Correctif pour CQ-4210727
* Les utilisateurs ne peuvent pas parcourir le dossier /etc/segmentation pour sélectionner une audience créée sous le dossier /etc/segmentation/group1. NPR-18522

### Sécurité {#security-1}

* L&#39;Assistant Déplacer le fichier se bloque si l&#39;utilisateur ne dispose pas de l&#39;autorisation d&#39;écriture sur le dossier de cible. NPR-18300
* Demande d&#39;utilisation d&#39;une version mise à niveau de org.apache.sling.servlets.post servelet (2.3.22) dans l&#39;API Apache Sling pour préempter une vulnérabilité XSS. NPR-18963

### Traduction {#translation-6}

* La page des ressources ne doit pas être autorisée à être renvoyée à nouveau à un projet de traduction tant que le projet n’est pas terminé. NPR-18249; Correctif pour CQ-4209908

### Composants WCM-Foundation {#wcm-foundation-components-8}

* Impossible d’utiliser le composant iparsys de WCM Foundation dans les modèles modifiables. NPR-18223; Correctif pour CQ-4210384
* La zone cliquable ne conserve pas les coordonnées sélectionnées dans le composant d’image HTML. NPR-18032; Correctif pour CQ-4211584
* Lorsqu’un composant d’image HTML est généré, le nom de fichier dans l’URL est renommé, ce qui entraîne une URL endommagée. NPR-17908; Correctif pour CQ-4211587
* Impossible de quitter les propriétés de la page après avoir apporté des modifications. NPR-17832; Correctif pour CQ-96110

## Formulaires {#forms-14}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir [AEM Forms Release](aem-forms-releases.md).

### Package de modules complémentaires Forms {#forms-add-on-package-14}

**Correspondence Management**

* Le dictionnaire de données est lu à plusieurs reprises pendant le rendu de la lettre. NPR-18482, Correctif pour CQ-4210805
* Ajout de JavaDocs pour la classe com.adobe.livecycle.content. NPR-18467
* Lors de la création d’une lettre , la description de la lettre n’est pas enregistrée. NPR-18039
* Lorsqu’un module de texte est enregistré et qu’une expression du module de texte ne contient aucune balise d’expression d’ouverture ou de fermeture, aucun message d’erreur ne s’affiche. Le module de texte affiche un message d’erreur et n’effectue pas le rendu dans la lettre. NPR-17798
* Erreurs inattendues affichées dans les journaux lors de l’installation du module complémentaire. NPR-18295

**Gestionnaire de formulaires**

* L’interface utilisateur AEM Forms répertorie toutes les ressources dans le premier ordre le plus ancien. Les utilisateurs ne sont pas en mesure de réorganiser les ressources dans le premier ordre le plus récent. NPR-18451

### Programme d’installation de Forms JEE  {#forms-jee-installer-14}

**Service Output**

* Amélioration des performances du service Output pour AEM forms 6.2. NPR-18033

**Service Signatures**

* Impossible de signer un document PDF avec le module de sécurité matérielle distant. NPR-18017

## bundles OSGi inclus dans CFP6 {#osgi-bundles-included-in-cfp-2}

Liste des lots OSGi mis à jour dans AEM 6.2SP1-CFP6

[Obtenir le fichier](assets/do-not-localize/6.2sp1-cfp6-bundlelist.txt)

Liste des packages de contenu mis à jour dans AEM 6.2SP1-CFP6

[Obtenir le fichier](assets/do-not-localize/6_2sp1-cfp6-contentpackagelist.txt)

aem Cumulative Fix Pack 6.2 SP1-CFP5 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale de AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Correction de plusieurs problèmes d’interface utilisateur liés au partage, au déplacement, à la publication et au téléchargement de ressources.
* Augmentation de la capacité de la boîte de dialogue Déplacer à afficher les ressources référencées.
* Correction de plusieurs problèmes liés aux composants et workflows de gestion de contenu Web, tels que Annuler la publication et Purger les versions.
* Amélioration de la réactivité de la barre d&#39;actions en ce qui concerne l&#39;affichage des actions de barre d&#39;outils et des composants Coral.

### Ressources {#assets-14}

* Amélioration des performances de la fonctionnalité de publication sur le portail de marque. NPR-17189; Correctif pour CQ-4204150
* Le partage d’un fichier à l’aide de l’option Partager le lien ne crée pas de fichier zip avec une structure de dossiers aplatie à télécharger. NPR-17513; Correctif pour CQ-4209381
* La sélection d’un fichier dans la gestion des actifs numériques et le fait de cliquer sur Publier n’affichent pas l’option Publier sur le portail de la marque dans la page Détails du fichier. NPR-17351; Correctif pour CQ-94905
* Dans les étapes du processus de gestion des actifs numériques, les flux binaires acquis à partir de Session ou ResourceResolver doivent être fermés dans un bloc final afin de garantir que les fuites de ressources ne se produisent pas. NPR-17385; Correctif pour CQ-4209452
* Le téléchargement d’un document Word dans DAM entraîne une exception de pointeur nulle et l’instance de workflow reste bloquée à l’état En cours d’exécution. NPR-17160; Correctif pour CQ-4207358
* Les boutons Partager, Déplacer, Publier et Télécharger sont visibles pour les fichiers expirés sur la page Editeur de métadonnées pour les utilisateurs non-administrateurs. NPR-16903; Correctif pour CQ-101440/CQ-104535
* Les actions telles que Partager, Déplacer, Publier et Copier doivent être visibles pour les administrateurs dans la console Ressources. NPR-16902; Correctif pour CQ-4207111

### Sites {#sites-14}

* Lors du déplacement d’une page à l’aide de l’interface utilisateur classique et tactile, la boîte de dialogue Déplacer n’affiche pas les références au-delà de 150, ce qui empêche les utilisateurs de mettre à jour ces références et de republier la page. Ce problème a été résolu en introduisant une propriété pour l’interface utilisateur classique : &quot;maxRefNo&quot; qui peut être configuré sur le noeud siteadmin : &#39;/libs/wcm/core/content/siteadmin&#39;. Cette propriété spécifie le nombre maximum de références (valeur par défaut 150) qui s’affichent avant une opération de déplacement importante et si une page comporte plus de références, elles ne s’affichent pas dans la boîte de dialogue movePage. Cette configuration fonctionne également pour damadmin et miscadmin en appliquant la configuration aux noeuds : `'/libs/wcm/core/content/damadmin'` et `'/libs/wcm/core/content/miscadmin'` respectivement. NPR-17222; Correctif pour CQ-85878

* Lorsque vous travaillez avec des composants WCM, les hyperliens contenant des espaces sont supprimés dans l’éditeur de texte enrichi de l’interface utilisateur tactile. NPR-17698, NPR-17570; Correctif pour CQ-4206768
* Lors du déclenchement du flux de travail Request for Unpublication (Demande de déspublication) à partir des propriétés de la page, des erreurs JavaScript s’affichent pour les utilisateurs sans droits de réplication. NPR-17294; Correctif pour CQ-102064
* Le rendu ou l’exportation d’un composant d’image HTML modifie l’URL en numéro, renommant le nom de fichier, ce qui entraîne la rupture des liens. NPR-17245; Correctif pour CQ-59616
* La suppression d’un lancement dans un lancement imbriqué entraîne l’abandon des sous-lancements. NPR-17228; Correctif pour CQ-4202639
* L&#39;exécution de la version Purge dans AEM 6.2 avec l&#39;application d&#39;Oak 1.4.13 provoque un avertissement répété dans les journaux. NPR-17391; Correctif pour CQ-4206870
* Après l’installation d’un correctif ou d’une mise à niveau pour le composant ContextHub, le package de contenu remplace tous les segments dans /etc/segmentation/contexthub, ce qui entraîne la perte de tous les segments ContextHub personnalisés. NPR-17250; Correctif pour CQ-79958
* Lors de l’exécution d’un processus avec des groupes imbriqués en tant qu’utilisateurs de processus, le WorkflowStatusProvider (pageinfo.json) provoque le verrouillage de l’instance de processus. NPR-17555; Correctif pour CQ-4202056
* Lors de l’utilisation des composants de l’éditeur WCM-Page, il existe une énorme quantité d’espace vide à la fin de la page dans le mode de modification de l’interface utilisateur tactile de l’instance d’auteur. NPR-17510; Correctif pour CQ-4205441
* Le rendu ou l’exportation d’un composant d’image HTML modifie l’URL en un nombre, ce qui entraîne des liens rompus. NPR-17245; Correctif pour CQ-59616

### Interface utilisateur {#ui}

* La sélection d’un fichier et le fait de cliquer sur Outils de développement n’affichent pas toujours les actions de barre d’outils dans la barre d’actions en cas de connexion lente et la page doit être rechargée. NPR-17568; Correctif pour CQ-108365
* La barre d’actions doit être mise à jour pour utiliser deux conteneurs : coral-actionbar-Principal et coral-actionbar-secondaire, au lieu de coral-actionbar-conteneur. NPR-17591; Correctif pour GRANITE-15225

### Mobile à la demande {#mobile-on-demand-2}

* Les utilisateurs disposant d’autorisations de lecture seule sur l’application AEM Mobile ne peuvent pas prévisualisation le contenu de la page Gestion de contenu AEM Mobile. NPR-17390; Correctif pour CQ-4209690

### Sécurité {#security-2}

* Vulnérabilité XSS dans la sortie générée par HTMLRendererServlet. NPR-17136
* Demande visant à empêcher la divulgation des versions AEM dans la page AEM Flux de syndication Web. NPR-16219

### Formulaires {#forms-15}

#### Package de modules complémentaires Forms {#forms-add-on-package-15}

Les correctifs d’AEM Forms sont fournis par le biais de packages de modules complémentaires et d’autres programmes d’installation de correctifs fournis avec la version. Pour plus d’informations, voir Versions d’AEM Forms.

**Formulaires adaptatifs**

* Pour un formulaire adaptatif avec pièce jointe, les entrées de duplicata pour les balises afSubmissionInfo sont créées dans le code XML envoyé lorsque le formulaire est envoyé pour la deuxième fois. NPR-17364
* Lors de l’utilisation du navigateur Google Chrome, après la suppression d’une pièce jointe d’un formulaire, une nouvelle tentative de pièce jointe renvoie une erreur. NPR-17297
* S’il existe des panneaux chargés en différé imbriqués et répétables dans une Forms adaptative basée sur un modèle XSD ou sans formulaire, les valeurs renseignées dans le formulaire ne sont pas conservées dans le Document d’enregistrement (DOR). NPR-17176
* Les erreurs affichées dans le journal des erreurs de l&#39;éditeur de règles doivent être ajoutées dans le bloc catch d&#39;un code JavaScript de bloc try/catch. NPR-16757
* Le fait de cliquer sur un fichier joint dans un formulaire génère une erreur dans la console du navigateur et n’affiche pas la prévisualisation de pièces jointes. NPR-17174

**Correspondence Management**

* La fonctionnalité de l’interface utilisateur de création de correspondance se casse en cas d’ajout d’un texte inséré ou d’une ligne vierge dans l’interface utilisateur. NPR-17748
* Le navigateur clignote lorsqu’une lettre est ouverte pour modification. NPR-17576
* Lors de l’ajout de fonctions distantes dans des éléments de dictionnaire de données calculés, si le nombre de fonctions est supérieur à la longueur de l’onglet affichant les fonctions distantes, la barre de défilement n’apparaît pas dans l’onglet. NPR-17359
* La méthode d’API, import com.adobe.icc.services.api.LetterInstanceService ne fonctionne pas. NPR-17922, NPR-16008
* Une variable ajoutée dans un module de texte n’est pas visible dans le panneau Liaison de données lors de la modification d’une lettre. NPR-17940
* L’interface utilisateur de Correspondence Management ne se lance pas lorsque l’action d’envoi HTML utilise la méthode POST. NPR-17595

**Gestionnaire de formulaires**

* Avec un formulaire adaptatif configuré pour le test AB, cliquer sur Début AB Testing ne début pas le test et renvoie une erreur de console de navigateur. NPR-17838

**Service Forms**

* Les problèmes signalés dans l’analyse de code statique des formulaires OSGI doivent être corrigés. NPR-13951

#### Programme d’installation de Forms JEE {#forms-jee-installer-15}

**Service Output**

* L’utilisation d’AEM Forms 6.2 Output Service pour fusionner un formulaire spécifique avec un XML de données prend 20 fois plus de temps que le temps nécessaire au serveur LiveCycle ES4 SP1 pour la même opération. Il est corrigé sur les environnements Windows et Linux. NPR-17501

**Installation de LCM**

* Après avoir installé AEM Forms 6.2 GM et appliqué l’AEM 6.2 CFP, l’exécution de LiveCycle Configuration Manager affiche un point-virgule indésirable dans les informations de version et la date d’installation du correctif n’est pas mise à jour. NPR-14322

**Gestion des processus**

* La variable TaskContext n’est pas renseignée pour les workflow AEM Forms. CQ-4211857

#### Package de lots AEM Forms JEE {#aem-forms-jee-bundles-package}

* Les fonctionnalités des utilisateurs de formulaires, que ce soit à l’aide de la console d’interface utilisateur d’administration JEE ou de la console OSGi, doivent être les mêmes. NPR-17670

### Packs de fonctionnalités inclus dans CFP5 {#feature-packs-included-in-cfp}

**Package Forms JEE**

Process Management - Workspace HTML

* Lors de l&#39;attribution d&#39;une étape à l&#39;espace de travail, l&#39;onglet Pièces jointes de l&#39;espace de travail doit afficher un compteur pour les pièces jointes ou les notes au cas où il y aurait plusieurs pièces jointes ou notes. NPR-17771
* Demande de prise en charge d’Office 365 dans AEM JEE Forms pour les capacités de courrier électronique dans le processus des formulaires. NPR-13866

**Package d’Ajoute Forms**

Correspondence Management

* Lors de la modification de fragments dans l’éditeur de texte au cours d’une prévisualisation de lettre, le texte traité doit s’afficher pour modification au lieu des conditions insérées utilisées dans les fragments. NPR-15748, NPR-17504

### bundles OSGi inclus dans CFP5 {#osgi-bundles-included-in-cfp-3}

Liste des lots OSGi mis à jour entre AEM6.2 SP1-CFP5

[Obtenir le fichier](assets/do-not-localize/cfp5_osgi_bundles.txt)

Liste des packages de contenu mis à jour entre AEM6.2 SP1-CFP5

[Obtenir le fichier](assets/do-not-localize/content-package-cfp5.txt)

aem Cumulative Fix Pack 6.2 SP1-CFP4 est une mise à jour importante qui inclut les correctifs client clés publiés depuis la disponibilité générale d&#39;AEM 6.2 SP1.

Voici les points saillants de ce Cumulative Fix Pack :

* Correctifs dans les ressources pour le rendu de fichier Camera Raw, la vue de chronologie et l’orientation des images
* Amélioration des

   * Lancements WCM pour les sites
   * Processus des projets
   * Composants ContextHub

* Correctifs pour Campaign, Mobile à la demande et Traduction
* Améliorations de la convivialité de l’éditeur de règles de formulaires adaptatifs
* Éditeur de condition en ligne amélioré pour Correspondence Management dans les formulaires
* Correctifs pour la gestion des processus et le service de sortie pour AEM forms on JEE
* Correctif lié à Forms Designer pour l’éditeur de script

### Plate-forme {#platform-12}

* Le formulaire de recherche de Search &amp; Promote ignore le paramètre `environment` lorsque le service cloud est configuré, ce qui le rend inutilisable sur l’instance d’auteur. NPR-16594 : correctif pour CQ-4206076
* L&#39;Ajoute ou la personnalisation des colonnes dans les résultats **Assets OmniSearch** en les superposant dans /apps ne fonctionne pas. NPR-16737 : correctif pour CQ-4206785
* L&#39;outil **Diagnostic **page ne fonctionne pas après une mise à niveau statique de AEM 6.1 SP2 vers AEM 6.2 SP1. NPR-17121; Correctif pour CQ-4196786
* HTL : Lors de la sélection d’un forum, en créant une rubrique et une publication, la propriété `Sightly SightlyCompiledScript` ajoute une propriété `addSelectors` incorrecte à `RequestDispatcherOption`. NPR-17008 : correctif pour GRANITE-16384

* Prise en charge Ajoutée de `CRON expressions` dans `ManagedPollConfigs` utilisé par `ReportImporter`. NPR-16608 : demande de correctif pour CQ-4206066

* Le téléchargement d’une image d’avatar pour un utilisateur LDAP échoue. NPR-16561; Correctif pour Granite-17013
* Le nombre de résultats affichés sur l’écran Gestion des utilisateurs est différent dans Carte et vue de Liste. NPR-16241; Correctif pour GRANITE-16914
* Les notifications de flux de travail ne peuvent pas être chargées en différé lors de l’affichage dans le navigateur Google Chrome en mode plein écran. NPR-17013 : correctif pour CQ-4207567

### Ressources {#assets-15}

* L’orientation de l’image n’est pas correctement appliquée lors de l’importation d’une image avec une orientation définie. NPR-16750 : correctif pour CQ-4204356
* La vue de chronologie des ressources n’affiche aucun fichier même si l’option Afficher tout est définie par défaut. NPR-16957 : correctif pour CQ-98780
* Les fichiers bruts de l’appareil photo (y compris ARW, CR2, NEF, DNG et EPS) ajoutés en tant que rendu dans les ressources ne peuvent pas être sélectionnés ni supprimés. Ces fichiers sont automatiquement téléchargés lorsque l’utilisateur clique dessus. NPR-16949 : correctif pour CQ-4206846
* La création d’un fichier pdf dans un autre fichier pdf dans l’interface utilisateur Ressources n’affiche pas les fichiers pdf créés dans l’interface utilisateur DAM, bien qu’ils soient visibles dans le référentiel crx. NPR-16833 : correctif pour CQ-4206501
* Le téléchargement d’une ressource en tant que nœud enfant direct de soi-même à l’aide de l’IU tactile provoque un problème. La ressource est téléchargée en tant qu’enfant direct de la ressource précédemment sélectionnée. NPR-16534 : correctif pour CQ-4204287
* Dans l’interface utilisateur de gestion des actifs numériques, le fait de commenter une ressource et de marquer un utilisateur dans le commentaire ne génère pas de notification par courrier électronique. NPR-16589 : correctif pour CQ-102318

### Projets {#projects-3}

La console de processus Projets affiche une exception NullPointerException sur la page lorsque des workflows sont purgés. NPR-17017 : correctif pour CQ-4194269

### Sites {#sites-15}

* Les fichiers dans `ContextHub` ne sont pas minimisés sur l’instance d’auteur. NPR-17022 : correctif pour CQ-79456
* La promotion de lancement de WCM-Launches prend du temps pour promouvoir un lancement constitué d’une grande arborescence de page. NPR-16480 : correctif pour CQ-82731
* `ClientContext` Le rendu de condition de segment se bloque lorsqu’un segment (ou une audience) est créé avec une règle qui ne fonctionne pas ou qui n’est pas terminée. NPR-16759 : correctif pour CQ-4205104
* Dans les lancements WCM, les pages associées à un lancement ne sont pas annulées lorsque l’action est lancée à partir des propriétés de la page dans l’interface utilisateur tactile. NPR-16560 : correctif pour CQ-4204681
* Link Rewriter réécrit faussement des valeurs href contenant un deux-points en supposant que le deux-points &quot;:&quot; définit un espace de nommage JCR. NPR-16753 : correctif pour CQ-4203762
* Dans WCM-Design Importer, l’ouverture d’une page d’importation de test et la tentative de téléchargement d’un fichier zip entraîne des problèmes s’ils ont été téléchargés et supprimés précédemment. NPR-16486 : correctif pour CQ-90962
* La navigation vers le volet **[!UICONTROL Navigation globale]** à l’aide des navigateurs Firefox Safari et Google Chrome offre une expérience utilisateur différente. Le navigateur Firefox affiche le menu **[!UICONTROL Outils]** tandis que le navigateur Google Chrome affiche le menu **[!UICONTROL Navigation]**. NPR-16770; Correctif pour CQ-4200456

### Campagne {#campaign}

* Lors du test des modèles de campagne AEM et de la modification des adresses de contrôle pour inclure des &quot;données supplémentaires&quot;, la liste déroulante Adobe Campaign disparaît dans le Hub de contexte de l’interface utilisateur tactile. NPR-16771 : correctif pour CQ-105748

### Mobile à la demande {#mobile-on-demand-3}

* Lors du contrôle en amont d’une publication à partir de l’environnement d’auteur AEM, une action de contrôle en amont qui dure plus de 5 secondes provoque un pic inhabituel sur le tableau de bord d’intégration AEMM - AEM PECS avec un grand nombre de demandes d’état par seconde. NPR-16908 : correctif pour CQ-4207055
* La gestion de la configuration AEM Mobile échoue après l’installation de la mise à jour AEM-6.2-SP1-CFP1-1.0. NPR-16909 : correctif pour CQ-4204892

### Traduction {#translation-7}

* La prévisualisation des tâches de traduction ne fonctionne pas après l’installation de 6.2 SP1 - CFP1. NPR-16481; Correctif pour CQ-4204655
* La copie de langue créée à l’aide de la traduction pointe vers le Principal racine au lieu de la livecopy locale country. NPR-17257; Correctif pour CQ-4208287

### Sécurité {#security-3}

* Aucune validation de type MIME n’est effectuée lorsque des fichiers binaires sont téléchargés vers AEM. NPR-16617
* Problèmes de téléchargement d’images d’avatar pour les utilisateurs LDAP. NPR-16561

### Formulaires {#forms-16}

#### Package de modules complémentaires Forms {#forms-add-on-package-16}

**Formulaires adaptatifs**

* Dans Adaptive Forms Editor, le commentaire Paramètre de Cible dans head.jsp doit être remplacé par la nouvelle instruction Context Hub. NPR-17173
* Dans l’éditeur de règles Forms adaptatif, **[!UICONTROL Choisir un élément]** affiche le événement comme &quot;nul&quot;. NPR-17139
* Le formulaire envoyé est de nouveau envoyé lors de la navigation vers l’avant à l’aide de la flèche vers l’avant (>). NPR-17080
* Lors de l’envoi d’un formulaire adaptatif via AJAX, la fonction de rappel &quot;error&quot; n’est jamais appelée en cas d’erreur. NPR-17034
* Le fait de cliquer sur le bouton **[!UICONTROL Enregistrer le formulaire]** dans l’éditeur de règles au moment de l’exécution n’enregistre pas le formulaire. NPR-16905
* Le texte statique doit être exclu de l’ordre de tabulation dans le formulaire adaptatif. NPR-16749
* La valeur calculée d’un champ décimal s’affiche incorrectement. NPR-16596
* L’icône permettant d’afficher le contenu de l’aide doit être incluse dans l’ordre de tabulation des formulaires adaptatifs. NPR-16484
* Prise en charge de l’utilisation d’une expression régulière de type `dataRef=C:/Users/`dans la configuration du service de préremplissage par défaut **[!UICONTROL par défaut]** pour le préremplissage des données pour le Forms adaptatif. NPR-16425

* Les validations ne sont pas déclenchées correctement pour tous les panneaux en cas de scénario imbriqué chargé différé. NPR-15821

**Correspondence Management**

* Le rendu de lettre échoue si une lettre contient un module de texte vide (un module sans texte). NPR-17054
* Les sauts de ligne et les espaces de tabulation sont supprimés du contenu après avoir été collés dans l’éditeur de texte. NPR-17039
* L&#39;affichage des références d&#39;un module de texte prend beaucoup de temps si le module de texte est référencé dans de nombreuses lettres. NPR-17035
* La modification, l’enregistrement, la suppression et la définition de la référence pour les fragments de document prennent beaucoup de temps. NPR-17033
* Le texte justifié est rendu dans une autre police lors de l’aperçu de la lettre. NPR-16976
* La fonctionnalité de recherche ne fonctionne pas correctement si le texte recherché comporte plusieurs occurrences. NPR-16920
* La barre d’outils Editeur de texte s’affiche par intermittence dans le navigateur. NPR-16919
* Le concept **[!UICONTROL Enregistrer le formulaire]** de l&#39;éditeur de règles ne fonctionne pas. NPR-16905
* La liste déroulante Police ne renseigne pas la famille de polices lors de la création d’un module de texte basé sur le dictionnaire de données à l’aide d’Internet Explorer. NPR-16944
* Après avoir créé un fragment de texte, la police de la lettre change lors de l’aperçu de la lettre. NPR-16830
* Les lettres avec des espaces de tabulation au début ou entre les expressions du fragment de document ne peuvent pas être rendues ni prévisualisées. NPR-16769

**Mobile Forms**

* La prévisualisation de formulaires pour périphériques mobiles affiche le contenu superposé, bien que le formulaire s’affiche correctement pour le rendu au format PDF. NPR-17105

**Portail Formulaires**

* Cliquez sur le lien **[!UICONTROL Télécharger]** pour un formulaire envoyé pour ouvrir une page HTML au lieu d’un formulaire PDF. NPR-17082

* `Upload Comments` pour les pièces jointes ne s’affichent pas dans l’interface utilisateur pour les instances envoyées, bien qu’elles soient présentes dans le fichier XML stocké dans le référentiel crx. NPR-17075

**Service Reader Extensions**

* Un fichier spécifique n’est pas Reader étendu sur l’installation OSGI d’AEM forms. NPR-16625

#### Programme d’installation de Forms JEE  {#forms-jee-installer-16}

**Base**

* Lors du processus de mise à niveau, Configuration Manager échoue avec le délai d’expiration. NPR-16774 (voir [Configuration du délai d&#39;attente pour les opérations au niveau du composant](install-cfp-aem-forms-jee.md#configuring-timeout-for-operations-at-component-level-npr)).

**Gestion des processus - Workspace HTML**

* Le point de départ d’une Tâche de Début ne commence pas par les données soumises au moment de l’envoi du point de départ. NPR-16917
* Le fait de cliquer sur le bouton **[!UICONTROL Retour]** d’un formulaire dans Workspace HTML ne ferme pas le formulaire, mais le renvoie à sa file d’attente de groupe.\
   NPR-16352

**Gestion des processus**

* Permet aux utilisateurs de définir le nom d’affichage des tâches précédentes sur l’une des tâches suivantes d’une instance de processus. NPR-15382

**Service Output**

* Output Service ne parvient pas à traiter un fichier PDF qui est modifié pour inclure un champ &quot;millisecondes&quot; supplémentaire dans les métadonnées `date-time format`. NPR-16838

#### Concepteur Forms {#forms-designer}

* aem Designer Script Editor ne respecte pas les valeurs par défaut des propriétés de formulaire pour `Calculate Event`et `Validate Event`. NPR-15921

### Packages de fonctionnalités inclus dans CFP4 {#feature-packs-included-in-cfp-1}

**Package d’Ajoute Forms**

* Amélioration de l’éditeur de conditions en ligne pour Correspondence Management. NPR-10981

### bundles OSGi inclus dans CFP4 {#osgi-bundles-included-in-cfp-4}

Liste des lots OSGi mis à jour entre AEM 6.2 SP1 et CFP4

Les principaux points saillants du CFP3 sont les suivants :

* Fonctionnalités de recherche plus efficaces pour l’interface utilisateur classique et pour le composant de recherche AEM à l’aide du proxy avec l’authentification digest
* Correction de problèmes lors du téléchargement de fichiers et de l’affichage de métadonnées de fichiers
* Correction de problèmes lors de la création de dossiers et du déplacement de pages au cas où le titre comporte des caractères spéciaux.
* Correctifs pour l’utilisation du ciblage : synchronisation des audiences, publication des campagnes et sélection de la mesure Objectif dans l’interface utilisateur tactile
* résout les problèmes de synchronisation des tâches de traduction.
* Sécurité améliorée du service de préremplissage Forms
* Améliorations du composant brouillons et envois du portail de formulaires et du service Forms Barcoded
* Améliorations de la convivialité des formulaires adaptatifs contenant des widgets de pièce jointe ou des fragments chargés différés.
* Améliorations de la convivialité de Correspondence Management, notamment la fonctionnalité de recherche améliorée, la journalisation des ressources supprimées et l’importation de dictionnaires de données.

### Plate-forme {#platform-13}

* Une condition de course dans l&#39;**ModelAdapterFactory**, qui est possible lorsque deux threads essaient d&#39;injecter le même champ, entraîne l&#39;échec de construction du modèle. NPR-16443 : correctif pour SLING-6584
* Option de validation dans le gestionnaire de packages pour détecter tout conflit entre un fichier superposé (fichier JSP ou JavaScript) sous /apps et celui contenu dans un correctif sous /libs. L&#39;incrustation affectée peut alors être réévaluée afin d&#39;inclure les modifications du fichier sous /libs. NPR-16216 : correctif pour CQ-81729
* La connexion au fichier error.log s’arrête parfois quelques secondes après le démarrage de l’éditeur et doit être effacée pour s’exécuter à nouveau. Demande de mise à jour de la structure de journalisation et de fourniture de la journalisation Sling. NPR-15913 : correctif pour Granite-15452
* Demande de mise à jour de l’API JavaScript &quot; `use"` pour éviter toute erreur dans l’implémentation de l’API d’utilisation JavaScript HTML. NPR-16461 : correctif pour SLING-6780

### Sites {#sites-16}

* Après la mise à niveau de AEM 6.0 vers AEM 6.2, l’interface utilisateur classique affiche des performances lentes lors de la recherche de balises en raison de nombreuses requêtes. Pour résoudre ce problème, vous pouvez suivre les étapes mentionnées sous [Désactiver l’état de réplication dans la console de balisage (interface utilisateur classique)](release-notes-aem-6-2-cumulative-fix-pack.md#disable-replication-status-in-tagging-console-classic-ui-npr). NPR-15842 : correctif pour CQ-4201748.

* Lors de la création d’une page dans l’interface utilisateur tactile, la vérification d’entrée pour le champ &quot;nom&quot; ne vérifie pas le caractère spécial &quot;Apostrophe&quot; (identique à celui de l’interface utilisateur classique). Par conséquent, la page ne peut pas être déplacée. NPR-16404 : correctif pour CQ-4205321.
* L’application de styles différents sur deux lignes dans l’éditeur de texte enrichi, puis leur fusion, supprime le style appliqué sur la deuxième ligne. NPR-16389 : correctif pour CQ-4203835.
* Dans l’écran Sites utilisateur tactiles, la tentative de collage d’une page à l’intérieur d’une page sans sous-pages ne fonctionne pas car le bouton Coller n’apparaît pas. NPR-15894 : correctif pour CQ-4201696.
* Lors du défilement de l’onglet Pages dans le panneau Outil de recherche de contenu, quelques jeux de pages s’affichent indéfiniment dans l’interface utilisateur classique, tandis que l’interface utilisateur tactile affiche un ensemble limité de pages non répétées. NPR-16271 : correctif pour CQ-4202371
* L’ouverture des propriétés de page d’une LiveCopy dans l’interface utilisateur tactile et le fait de cliquer sur Enregistrer sans modification écrivent tout onglet LiveCopy et crée un noeud de configuration LiveSync. NPR-16327 : correctif pour CQ-108562
* La contrainte de formulaire ne peut pas lire la propriété `ConstraintMessage`. NPR-16388 : correctif pour CQ-101330
* Le composant `wcm/foundation/components/parsys` n&#39;affiche pas l&#39;espace réservé **[!UICONTROL &#39;Faire glisser les composants ici]**&#39;. NPR : 16748 : Correctif pour CQ-4205187

### Ressources {#assets-16}

* Le pixelliseur pdf cesse de fonctionner et provoque des problèmes de mémoire après avoir installé 6.2 SP1 ou Hotfix 12430. NPR-15991
* Les métadonnées d’une propriété de chaîne `documentNumber` s’affichent sous forme de date alors qu’elles doivent être un nombre. NPR-16134 : correctif pour GRANITE-16916
* Troncations de texte dans la bulle de événement de chronologie. NPR-16226 : correctif pour CQ-85226
* Lors de la création d’un dossier sous la hiérarchie de contenu avec un titre comportant des caractères spéciaux, la forme codée du caractère spécial s’affiche. NPR-15935 : correctif pour CQ-4202987
* L’utilisateur ne peut pas télécharger de fichiers ou créer de dossiers lors de la navigation dans les fichiers en raison d’un comportement incohérent lors de l’utilisation du bouton Créer. NPR-16410 : correctif pour CQ-4204793
* Des erreurs inattendues se produisent lors du téléchargement de ressources HTML partagées à partir de la vue d’articles dans AEM Création. NPR-16133 : Correctif pour AEMM-4155970

### Intégration {#integration-14}

* Lors de l’activation de l’authentification par proxy avec l’authentification Digest, le composant AEM Search renvoie une exception ConcurrentModificationException. NPR-15309 : correctif pour CQ-4199191
* Lors de la création d&#39;une Activité de test A/B de Cible en AEM, l&#39;audience ne se synchronise pas jusqu&#39;à la Cible et n&#39;affiche &quot;aucune audience&quot;. NPR-16229 : correctif pour CQ-4204210
* Après avoir installé SP1+NPR-11577 v1.2, lorsque vous sélectionnez &quot;Utiliser une mesure Analytics&quot; pour la mesure d’objectif lors du ciblage dans l’interface utilisateur tactile, la liste déroulante des mesures ne se charge jamais. NPR-16129 : correctif pour CQ-4204316
* Lors de l’utilisation du ciblage, la publication de la campagne ne publie pas automatiquement l’intégralité de l’arborescence, y compris la marque et le gabarit. NPR-15855 : correctif pour CQ-94630

### Traduction {#translation-8}

* La tâche de traduction de synchronisation n’est pas déclenchée automatiquement et AEM interrogation ne se produit pas sans interroger les projets de traduction. NPR-15163 : correctif pour CQ-90856

### Formulaires {#forms-17}

#### Package de modules complémentaires Forms {#forms-add-on-package-17}

**Formulaires adaptatifs**

* Lors de l’enregistrement d’un formulaire adaptatif avec une pièce jointe, le chemin d’accès complet de la pièce jointe est ajouté à la balise `fileAttachment` du XML généré, plutôt qu’au nom de la pièce jointe. NPR-16529
* Dans les formulaires adaptatifs basés sur XDP, le wrapper `afData/afBoundData` est présent dans le XML envoyé, même si le code XML prérempli ne contient pas de wrappers `afData/afBoundData`. NPR-16118

* Notation exponentielle dans le champ Nombre : Lors de l’utilisation de formulaires adaptatifs, si un nombre avec une fraction décimale supérieure à dix caractères au total est entré, le nombre se transforme en notation exponentielle dans le XML envoyé. NPR-16106
* Pour les formulaires qui contiennent à la fois un composant de pièce jointe et un fragment chargé différé, le fichier XML de données envoyé ne contient pas les informations relatives au composant de pièce jointe du fichier. NPR-16022
* Dans le cas d’un panneau répétable chargé en différé qui n’a pas d’ancêtre répétable, les enfants répétables d’une seconde instance du panneau ne se répètent pas. NPR-15944
* Lorsque vous essayez d’enregistrer un fragment à l’intérieur d’un fragment dans l’éditeur de formulaire, la racine du modèle de fragment ne renseigne pas la valeur du fragment enfant. NPR-15943
* Lors de la création d’une case à cocher avec un seul élément et de la tentative d’affichage du titre de la case à cocher en conservant le titre de l’élément masqué, l’action de création de dictionnaire renvoie `ArrayIndexOutOfBoundException` si le texte de l’élément est vide. Le dictionnaire n’est pas créé et aucune réponse d’erreur n’est générée à l’écran. NPR-15816
* Pour les formulaires adaptatifs avec des widgets de pièce jointe, certaines parties du formulaire sont désactivées une fois le fichier joint prévisualisé.\
   NPR : 16611

* Pour les widgets de pièce jointe où plusieurs pièces jointes sont autorisées, si une nouvelle instance de formulaire avec pièce jointe est envoyée sur un widget comportant une pièce jointe précédente, un code d’erreur s’affiche lors de l’ouverture de la pièce jointe ajoutée au lieu du contenu réel. NPR-16258
* Sécurisation du service de préremplissage de formulaires contre un accès non autorisé par le biais de protocoles tels que `file://`, `http://` et `ftp://`. Reportez-vous à &quot; [Configuration du service de préremplissage à l’aide de Configuration Manager](https://helpx.adobe.com/aem-forms/6-2/prepopulate-adaptive-form-fields.html#main-pars_header_944235754)&quot;. NPR-15414

* Demande de rendu du formulaire adaptatif au format PDF plutôt qu’au format HTML à l’étape de vérification et d’ajout de toutes les pièces jointes au PDF, de sorte que l’impression affiche le formulaire complet. NPR-9011

**Correspondence Management**

* Lorsque vous travaillez avec un fragment de texte dans une lettre en mode Prévisualisation/modification, si le texte est converti en liste, la fonctionnalité de lettre entière se rompt et une erreur JavaScript est générée. NPR-16460
* L’importation d’un fichier XSD pour créer un dictionnaire de données dans le noeud Correspondence Management échoue, car le navigateur ne répond plus chaque fois que le schéma XSD est téléchargé et que le noeud racine est sélectionné. Ce problème est indépendant du navigateur et n’apparaît pas dans les journaux du serveur. NPR-16452
* Lors de la prévisualisation d’une lettre à l’aide du navigateur Internet Explorer et de la tentative de modification de la taille de police du contenu, les valeurs de duplicata sont affichées de 8 à 72 dans la liste déroulante de la taille de police. NPR-16387
* Si un champ flottant s’affiche en tant que champ d’entrée à partir d’un fragment XDP, le champ ne s’étend pas dans la prévisualisation de lettres lors de l’utilisation du navigateur Internet Explorer. NPR-16367
* Lorsque vous tentez d’envoyer une lettre directement à partir de la prévisualisation, la fenêtre contextuelle du nom de la lettre ne s’affiche pas correctement en raison de son masquage. NPR-16353
* Les espaces de ligne ajoutés lors de la modification d’une lettre ne sont pas reflétés dans la fenêtre de Prévisualisation. Pour les listes de fragments de texte, l’espacement de la sortie PDF n’est pas correct. NPR-16267
* Lorsque vous travaillez sur un fragment de document de texte à l’aide du navigateur Internet Explorer, la tentative de mise en retrait du texte échoue car le curseur n’autorise pas la mise en retrait du texte. NPR-16128
* Ajouter ou modifier un dictionnaire de données en fragment de document de texte existant prend beaucoup de temps et l’utilisateur n’est pas toujours averti. NPR-16102
* Lors de la prévisualisation d’une lettre avec un contenu défilant à l’aide du navigateur Internet Explorer, la barre de défilement du navigateur chevauche la barre de défilement de la lettre et le contenu entier ne peut pas être affiché pour les fragments sur le côté droit. NPR-16068
* Lors de la création ou de la modification de fragments de document de texte à l’aide du navigateur Google Chrome, la liste déroulante de sélection de couleurs s’affiche automatiquement et ne peut pas être supprimée. L’utilisateur doit sélectionner la liste comme type de saisie de données pour pouvoir modifier le fragment. NPR-16067
* Lors de l’utilisation de l’API Letterinstance, la méthode `import com.adobe.icc.services.api.LetterInstanceService` ne fonctionne pas. NPR-16008
* La modification des formats d’affichage de date en `locale=en_US; dateFormat=MMM dd,yyyy;` dans la configuration d’Asset Composer ne fonctionne pas comme prévu et le format de date est affiché en tant que caractères indésirables. NPR-16007
* Le type de liaison de données dans les lettres lors de la recréation s’affiche sous la forme &quot;Utilisateur&quot;, même s’il est défini différemment plus tôt. NPR-16619

**Portail Formulaires**

* Les scénarios de mise à niveau des composants brouillons et envois ne fonctionnent pas avec l’exemple d’implémentation de base de données. NPR : 16752

**Service Forms Barcoded (BCF)**

* L’analyse de code statique du service Forms à code à barres (BCF) signale des problèmes. NPR-13855

#### Programme d’installation de Forms JEE  {#forms-jee-installer-17}

**Gestion des processus - Workspace HTML**

* Sécurisation du service de préremplissage de formulaires contre un accès non autorisé via des protocoles tels que &quot;file://&quot;, &quot;http://&quot; et &quot;ftp://&quot;. Pour plus d’informations, voir [Configuration du service de préremplissage à l’aide de Configuration Manager](https://helpx.adobe.com/aem-forms/6-2/prepopulate-adaptive-form-fields.html#main-pars_header_944235754). NPR-15434

**Gestion des utilisateurs **

* L’écran de connexion SAML affiche une version incorrecte (6.1.0) sur le serveur AEM 6.2. NPR-13825
* Avec AEM Forms configuré pour l’authentification par authentification unique (Kerberos), si l’authentification de l’utilisateur échoue lors de la tentative de connexion, un code d’erreur &quot;404&quot; est renvoyé. L’utilisateur est redirigé vers le site de connexion uniquement après avoir actualisé la page. NPR-15015

#### Concepteur Forms {#forms-designer-1}

* La modification de la langue du formulaire en français (Canada) dans la vérification orthographique du dictionnaire ne fonctionne pas dans AEM Forms Designer.\
   NPR-15896

### Packages de fonctionnalités inclus dans CFP3 {#feature-packs-included-in-cfp-2}

**Package d’Ajoute Forms**

* Lors de la suppression d’un fichier dans la gestion de la correspondance, un message d’avertissement doit être consigné dans le fichier error.log. NPR-13225
* Améliorez la fonctionnalité de recherche tout en prévisualisant une lettre dans la gestion de la correspondance afin d’activer la recherche de texte dans le contenu du fragment de texte, plutôt que de rechercher uniquement le titre ou l’étiquette de la lettre. NPR-16103

### bundles OSGi inclus dans CFP3 {#osgi-bundles-included-in-cfp-5}

Liste des lots OSGi mis à jour entre AEM 6.2 SP1 et CFP3

[Get ](assets/do-not-localize/osgi_bundle_list_for_aem-6.2sp1-cfp3.txt)
FileLes principaux points saillants du Cumulative Fix Pack 2 sont les suivants :

* Correctifs de stabilité et amélioration des performances de la plateforme AEM, y compris la structure et les opérations Sling
* Gestion des ressources améliorée avec plusieurs correctifs pour l’accès, le déplacement, la recherche, le téléchargement et la publication des ressources
* Amélioration de la création et de la gestion des sites avec des correctifs dans les composants Fragments de contenu, Plug-in Ancre, Diaporama et Context Hub
* Plusieurs correctifs dans l’interface utilisateur tactile, notamment l’éditeur de texte, Omnisearch et le processus de création de variantes
* Amélioration des workflows de traduction ; connecteur Microsoft amélioré pour l&#39;utilisation de nouvelles API de traduction pour le portail Azure
* Correctifs dans les projets et Campaign
* Amélioration de la création et de la gestion grâce à des correctifs dans les fonctionnalités des formulaires adaptatifs, de la gestion de la correspondance et du portail de formulaires
* Correctifs dans les composants de l’espace de travail Forms JEE de base, XTG et HTML

### Plate-forme {#platform-14}

* `SlingPostProcessor` est déclenché si la page référençant directement la structure Sling est modifiée. NPR-15754 : correctif pour CQ-104153

* La valeur des balises avec la propriété `tagBasePath` n’est pas récupérée dans la boîte de dialogue classique de l’interface utilisateur lors de l’accès à un composant de page. NPR-15543 : correctif pour CQ-4199950

* Lorsque vous effectuez des opérations Sling, lorsque vous avez un fragment nommé &quot;chunk_n_n-1&quot; `SlingFileUpload handler.getLastChunk` s&#39;exécute dans une boucle sans fin avec des blocs vides. NPR-15455 : correctif pour SLING-5701

* Lorsqu&#39;une interface étend une autre interface, les méthodes injectables de la super interface ne sont pas correctement injectées. NPR-15202 : correctif pour SLING-5710
* Une exception potentielle de pointeur nul n&#39;est pas empêchée lors de l&#39;utilisation de l&#39;appel de fonction `com.adobe.granite.infocollector.impl.FilesTraversal`. Correctif NPR-15169 pour CQ-4197640
* L’état du flux de travail est incohérent pour certains noeuds secondaires et une erreur s’affiche lors de la distribution de événements d’observation pour ce noeud. NPR-15701 : correctif pour GRANITE-13786
* Lorsque l’utilisateur sélectionne un noeud dans CRXDE (par exemple, /content/dam/), puis l’onglet &quot;Contrôle d&#39;accès&quot;, en s’assurant qu’une Liste de Contrôle d&#39;accès existe, faites glisser et déposez certains éléments pour déplacer les éléments autres que celui sélectionné. Correctif NPR-15696 pour GRANITE-16300
* La sélection d’un utilisateur dans la liste déroulante lors d’une tentative d’usurpation d’identité entraîne la disparition de l’ensemble de la fenêtre contextuelle de l’utilisateur. NPR-15774 : Correctif pour CQ-4201738/GRANITE-11895
* Dans Omnisearch, la recherche par balises avec des suggestions renseignées automatiquement ne fonctionne pas. NPR-15088 : correctif pour GRANITE-14426.\
   Remarque : Ce correctif nécessite la norme Oak CFP 1.4.11 ou supérieure.

### Auteur AEM Mobile {#mobile-aem-author}

* Lors de l’utilisation de packages AEM Mobile et ContentSync avec une application hybride, AEM répond à une demande de récupération (horodatages) effectuée par l’application avec le package le plus ancien, au lieu de celui demandé par l’application. NPR-15749 : correctif pour CQ-104153

### Sites {#sites-17}

* L’état de modification de la boîte de réception de flux de travail dans le noyau WCM ne change pas si l’utilisateur modifie une page après l’activation d’un flux de travail. NPR-15684 : Correctif pour CQ-4196974
* Le module externe Ancre de l’éditeur de texte enrichi pour l’interface utilisateur tactile génère du code HTML5 non conforme lorsque l’utilisateur clique sur l’icône d’ancrage et ajoute un nom. Il doit ajouter un attribut &#39;id&#39; au lieu de &#39;name&#39; dans la balise HTML5 pour l’élément d’ancrage. NPR-15650 : correctif pour CQ-89782
* Lorsqu’un schéma de métadonnées comportant de nombreux champs est créé et appliqué aux métadonnées du fragment de contenu, aucune barre de défilement n’est créée dans l’écran de métadonnées du fragment de contenu, rendant les champs non modifiables. NPR-15478 : correctif pour CQ-4202622
* La modification du composant de champ `TagInput` n’affiche pas les valeurs précédemment configurées par rapport aux champs de la boîte de dialogue. NPR-15464 : Correctif pour CQ-4200360

* Dans l’interface utilisateur de l’éditeur de fragments de contenu, au cas où de nombreuses variantes d’un fragment de contenu seraient créées, le panneau latéral n’affiche pas la barre de défilement pour parcourir toutes les variations. NPR-15445 : Correctif pour CQ-4199444
* Lorsque les utilisateurs sont supprimés des groupes directs, ils sont ajoutés aux groupes hérités. NPR-15400 : correctif pour CQ-98758
* Création WCM : L’auteur de l’interface utilisateur tactile n’autorise pas la modification de pages dont le nom contient des virgules. NPR-15396 : correctif pour CQ-4199723
* Lors de l’utilisation de l’interface utilisateur tactile pour la création, la fonction `Granite.author.editableHelper.doSelectParent` transmet les arguments dans le mauvais ordre, ce qui entraîne une erreur JavaScript. NPR-15349 : correctif pour CQ-4198594
* Le segment ContextHub affiche l’expérience même si le cookie d’exclusion est présent. NPR-15293 : correctif pour CQ-4198024
* Le composant Diaporama de l’interface utilisateur classique ne peut pas créer de diapositives ni faire glisser des images pour créer de nouvelles diapositives. NPR-15281 : correctif pour CQ-4194164
* Les utilisateurs, quelle que soit leur autorisation, se voient proposer les options &quot;Créer&quot; telles que Créer une page, Créer un site, Créer une copie dynamique, Créer un lancement et Créer un catalogue dans la console d&#39;administration du site. NPR-15278 : correctif pour CQ-94436
* Après avoir installé AEM 6.2 Service Pack 1, le curseur &quot;Inclure les sous-pages&quot; ne fonctionne plus pour les lancements de page. NPR-15230 : correctif pour CQ-4198449
* Demande d&#39;amélioration de la purge de version pour récupérer et traiter les versions en blocs et être également capable d&#39;utiliser un chemin spécifié dans une requête XPath. NPR-15186 : correctif pour CQ-109205
* Il manque le bouton Effacer dans l&#39;onglet Miniature Propriétés de la page du composant Sites. Correctif NPR-15143 pour CQ-4196997
* Pour un site qui utilise des Live Copies, la sélection de la case à cocher &quot;Live Copy&quot; dans le volet Colonnes de la console d’administration du site n’affiche pas correctement l’état de Live Copy et seule l’annotation HTML est affichée. NPR-15108 : correctif pour CQ-97086
* Lors de la modification de fragments de contenu, si l’utilisateur clique sur Terminé (’&quot;&quot;) pour le modifier avant d’obtenir la réponse de la publication, le contenu modifié n’est pas enregistré correctement. NPR-15014 : correctif pour CQ-4194095
* La fermeture de la page Modifier en mode Déformation temporelle et la tentative de réouverture de la page à partir de Siteadmin provoquent une erreur avec l’état &quot;500&quot; au lieu de rouvrir la page. NPR-14965 : correctif pour CQ-109647:
* Dans l’interface utilisateur de Digital Asset Manager (DAM), la recherche du sélecteur d’utilisateur Rechercher des autorisations entraîne une exception &quot;Mémoire insuffisante&quot;. NPR : 15307 : Correctif logiciel pour CQ-98542

### Ressources {#assets-17}

* Après avoir recherché un fichier dans Omnisearch, en sélectionnant un fichier et en tentant de modifier ses propriétés, en cliquant sur &quot;Propriétés de la Vue&quot;, puis en cliquant sur le bouton &quot;Enregistrer&quot;, les utilisateurs sont redirigés vers une page vierge. NPR-15900 : correctif pour CQ-4202372
* L’interface utilisateur Ressources ne répond pas aux événements. La sélection d’un fichier et le fait de cliquer sur &quot;Publier&quot; ou &quot;Rendus&quot; n’entraînent aucune activité. NPR-15828 : correctif pour CQ-4202247
* Lors de la publication d’un fichier à partir de la vue de cartes, la carte n’est pas mise à jour pour refléter l’état publié, sauf si la page est actualisée. NPR-15826 : Correctif pour CQ-102732
* Correctif cumulé contenant des correctifs d’actifs. NPR-15225
* Si le caractère esperluette (&#39;&amp;&#39;) est inclus dans le nom d’un dossier de ressources, le nom du dossier ne s’affiche pas correctement lors de la navigation vers le fichier. NPR-15775 : correctif pour CQ-4201735
* L’utilisation d’une esperluette (’&amp;’) dans le nom d’un fichier entraîne des problèmes lors de l’accès à ses propriétés. NPR-15770 : correctif pour CQ-4201737
* Lors de la navigation dans les ressources et de l’utilisation du mode d’affichage &quot;vue de colonnes&quot;, si l’utilisateur actualise la page après avoir sélectionné et cliqué sur un fichier, les détails du fichier s’affichent à la place du contenu actualisé. NPR-15768 : correctif pour CQ-4201727
* L’assimilation de PDS consomme 100 % de l’utilisation de l’UC avec un tas de bibliothèques pour les services pdf. NPR-15606 HotFix pour GRANITE-12929
* L’accès à l’interface utilisateur &quot;Mon lien partage&quot; à l’aide du navigateur Firefox n’affiche pas les éléments ou les utilisateurs partagés et l’écran est inutilisable. NPR-15539 : Correctif pour CQ-4200992
* Lors de l’utilisation de Digital Asset Manager, si une page est associée à un ensemble d’images, le déplacement des images vers un nouveau dossier rompt l’association des pages et la page associée manque certaines des images. NPR-15538 : correctif pour CQ-111479
* Dans le composant Dam Viewer, l’utilisation du mode d’exécution nosamplecontent entraîne des erreurs avec le média dynamique. NPR-15449 : correctif pour CQ-4195425
* Lors de la création de profils vidéo, si un paramètre prédéfini de codage vidéo de qualité élevée et de qualité moyenne est sélectionné, les modifications apportées ne sont pas enregistrées. NPR-15447 : correctif pour CQ-4195482
* Bien que le téléchargement d’une ressource sur le portail de marque échoue en raison d’une réponse d’erreur du serveur, l’état est mis à jour en &quot;Publié&quot; sur l’interface utilisateur du portail de marque, ce qui rend difficile le suivi du fichier manqué. NPR-15442 : correctif pour CQ-4197968
* Lors de la publication d’un dossier de ressources sur le portail de marque, où la publication dure plus d’une heure, certains fichiers ne peuvent pas être publiés. NPR-15441 : correctif pour CQ-4199493
* Lors de l’utilisation de la console Asset Finder dans la vue des colonnes, la tentative de création d’un dossier échoue une fois qu’elle réussit à réessayer. NPR-15370 : correctif pour CQ-4199448
* Si une ressource ou un dossier sélectionné dans l’interface utilisateur de gestion des actifs numériques comporte une virgule dans le nom, l’onglet Références n’est pas disponible et affiche le message &quot;La Liste des références n’est pas disponible pour plusieurs sélections&quot;. NPR-15362 : correctif pour CQ-4199721
* La publication d’un dossier sur le portail de marques ne modifie pas l’état de publication du dossier, même si les fichiers qu’il contient sont publiés avec succès. NPR-15292 : correctif pour CQ-4197667
* Lorsque vous accédez à la console Ressources dans l’interface utilisateur tactile, une exception s’affiche lors de l’activation de certains fichiers. NPR-15217 : Correctif pour CQ-108779
* Publication d’une vidéo sur YouTube lorsque la connexion est établie par le biais d’un serveur proxy. NPR-15109 : Correctif pour CQ-110332
* Utilisation d’un fichier dont le nom contient un point ou un point (.) dans data-sly-resource ne se résout pas à la même ressource et le chemin de sortie est terminé au point. NPR-15069 : correctif pour CQ-4195914
* Après la mise à niveau AEM 6.2 vers Service Pack1, la synchronisation des ressources dans Scene7 échoue. La propriété dam:Scene7FileStatus affiche l’état &quot; `UploadFailed`&quot; même pour les fichiers publiés. NPR-15269 : correctif pour CQ-4197708

### Interface utilisateur {#user-interface-5}

* Dans **[!UICONTROL Interface utilisateur tactile]**, la date enregistrée n&#39;est pas affichée pour les champs de date qui n&#39;ont pas de type=&#39;datetime&#39; lors de l&#39;utilisation du navigateur Internet Chrome version 56.0.2924.87. NPR-15383 : Correctif pour GRANITE-16481
* Dans **[!UICONTROL interface utilisateur tactile]**, l’éditeur de texte enrichi supprime le thread et les éléments de légende des tableaux HTML lors du rendu. NPR-15267 : correctif pour CRTE-41
* `FileUpload Validator` ne traite pas les cas où le démarrage automatique est true ou lorsque  `uploadFile()` est appelé manuellement et génère un rapport de validation non valide dans ces cas. NPR-15295 : correctif pour GRANITE-13499

* Omnisearch ne permet pas aux clients qui utilisent /apps d&#39;ajouter une source de données de colonne, car il suppose que la configuration de l&#39;emplacement est répertoriée sous */libs/granite/omnisearch/content/metadata/*. Correctif NPR-13188 pour GRANITE-16479
* Lors de l’utilisation de l’**[!UICONTROL interface utilisateur tactile]**, les variantes de produit ne sont pas créées au même niveau que le produit. L’utilisateur n’est pas informé de l’état du processus de création de la variante. NPR-15345 : Correctif pour CQ-4198948

**Scene7**

* L’exécution du processus Scene7 entraîne l’ouverture de fichiers qui ne se ferment pas. Demande d’amélioration du service AEM-S7 afin qu’il conserve et réutilise une seule instance HttpClient avec une configuration de pool partagée. NPR-15357 : Correctif pour CQ-109958

### Traduction {#translation-9}

* Lors de l’utilisation de projets de traduction, la mise à jour de copies de langue à partir du gabarit anglais produit 11 lancements distincts portant tous le même nom et la même racine source, mais avec des racines de lancement légèrement différentes, au cas où le nom de page suivrait un modèle défini. NPR-15605 : correctif pour CQ-4200699
* Les projets de traduction ne sont pas créés pour les pages lorsque les racines de langue comportent des tirets et des tirets dans leur nom. NPR-15171 : Correctif pour CQ-96286
* Demande de mise à jour du connecteur Microsoft pour pouvoir utiliser les API Microsoft Translator, que Microsoft rend disponibles dans le portail Azure. NPR-15320 : correctif pour CQ-101010

### Projets {#projects-4}

* Seuls 20 projets inactifs sont visibles dans l’écran Projets, bien qu’il existe plus de 20 projets inactifs dans le référentiel. NPR-15656 : correctif pour CQ-4200903

### Campagne {#campaign-1}

* Lors de l’utilisation des composants Campaign - Targeting et MAC - Test and Cible Integration, la dépublication des activités ne met pas à jour l’état de l’activité dans l’interface utilisateur du Principal. NPR-15401 : Correctif pour CQ-4199839
* Lors du déplacement d&#39;un produit dans AEM Commerce, l&#39;Assistant Déplacement de produit ignore les valeurs préremplies pour le nom du produit, le titre, les pages référencées, la création de l&#39;auteur et la date de création. NPR-15228 : correctif pour CQ-98617

### Sécurité {#security-4}

* Paramètre de jeton CSRF ajouté aux formulaires avec une méthode de GET. NPR-15229

### Formulaires {#forms-18}

#### Package de modules complémentaires Forms {#forms-add-on-package-18}

`**Adaptive Forms**`

* Les valeurs par défaut sont remplacées par des valeurs vides au format xml lors du préremplissage du formulaire adaptatif avec du code XML d’entrée. NPR-15721
* Le wrapper `afData/afBoundData` est présent dans le code XML envoyé, bien que même le code XML prérempli ne comporte pas de wrapper `afData/afBoundData` dans les formulaires adaptatifs basés sur un schéma XML. NPR-15541

* Les titres de la barre d’accordéon doivent être des en-têtes HTML &#39;h2&#39; modifiables au lieu de la balise &#39;a&#39;. NPR-15475
* La disposition en accordéon d’un panneau de formulaire n’est pas accessible aux utilisateurs de lecteurs d’écran. Les utilisateurs ne peuvent pas accéder à l’onglet en accordéon à l’aide du clavier uniquement à l’aide d’un lecteur d’écran tel que JAWS ou NVDA. NPR-15474

`**Correspondence Management**`

* L’enregistrement, la suppression et la définition de la référence pour un fragment de document prennent beaucoup de temps. NPR-15939
* Alignement des onglets défini dans Gérer les ressources sur le texte contenant plusieurs sauts d’en-tête dans l’interface utilisateur CCR. NPR-15818
* Les miniatures des modules de texte n’affichent pas le contenu aligné bien que le texte contienne du contenu aligné créé à l’aide d’onglets dans Google Chrome. NPR-15819

`**Forms Portal**`

* Le service de préremplissage ne fonctionne pas pour Forms XDP. NPR-15466
* Lors du stockage de brouillons et d’envois de formulaires adaptatifs dans la base de données, l’état du formulaire adaptatif est corrompu lorsque la connectivité de la base de données échoue pour une raison quelconque (par exemple, après une longue période d’inactivité). NPR-15297

#### Programme d’installation de Forms JEE  {#forms-jee-installer-18}

`**Core**`

* Après la mise à niveau vers la dernière version de Java 1.8.0_121-b13, l’interface utilisateur d’administration n’est pas accessible dans AEM Forms. NPR-15330

`**XTG**`

* Lors de l’utilisation du service Output pour fusionner un formulaire spécifique avec un XML de données, le temps de réponse est de 20 fois plus long que le temps pris par le serveur ES4 SP1 pour la même opération. NPR-15283

#### Application AEM Forms {#aem-forms-app-1}

* Lors de la récupération de tâches non enregistrées, le message affiché lors de la récupération de tâches non enregistrées doit être plus clair pour réduire les erreurs utilisateur. NPR-15377
* L’application AEM Forms ne rend pas les formulaires créés à partir de modèles personnalisés. NPR-15892
* Les utilisateurs ne peuvent pas se connecter à l’application AEM Forms. NPR-15891

Les principaux points saillants de AEM 6.2 SP2-CFP1 sont les suivants :

* Rationalise la fonctionnalité de réplication dans Sites :

   * Correctifs de divers problèmes de déploiement, de LiveCopy et d’écriture incorrecte

* Améliore la réactivité de l’interface utilisateur tactile pendant :

   * Recherches de ressources
   * tri basé sur la taille

* Amélioration de la gestion des balises dans les collections dynamiques
* Contrôles d&#39;accès plus serrés pendant les opérations CRUD sur les dossiers

### Plate-forme {#previous}

* Demande de suppression des appels d&#39;API `ReplicationQueue#forceRetry` au démarrage des agents de réplication, car ces appels ralentissent considérablement l&#39;instance, en particulier lorsqu&#39;elle dispose de nombreux agents de réplication. NPR-14032 : correctif pour GRANITE-13095
* Demande de configuration `DurboImportConfigurationProviderService` OSGi pour prendre en charge les champs qui peuvent stocker un tableau de valeurs. NPR-14570 : correctif pour CQ-108684
* L’utilisation du composant Sightly dans une page après la migration vers AEM 6.2 entraîne l’arrêt du fonctionnement de la boîte de dialogue Propriétés de la page. NPR-14328 : correctif pour CQ-108355
* La désactivation de la planification d’une tâche précédemment planifiée ne supprime pas le noeud correspondant sous */var/eventing/Schedu-jobs*. NPR-14253 : correctif pour SLING-5666
* Lorsqu’un administrateur tente de se faire passer pour un utilisateur supprimé, l’interface utilisateur ne s’actualise pas. NPR-14247 : correctif pour CQ-107446
* Vérification de la protection XSS provoquant un codage incorrect dans le composant Sightly. NPR-14004 : correctif pour CQ-93821
* Demande de mise à niveau de Jackrabbit Filevault vers la version 3.1.30 pour résoudre plusieurs problèmes. NPR-13454
* Une erreur de cache se produit lorsque la distribution Sling synchronise les packages de distribution de l’auteur à la publication. NPR-13034 : correctif pour GRANITE-13970

### Sites {#sites-18}

* Problèmes avec VersionManagerImpl lors de la purge de versions incorrectes de l’historique des versions. NPR-14372
* Le composant d’analyse WCM Sightly Foundation ignore les noms de balise de déclaration de composant, `cq:htmlTag / cq:tagName`. NPR-14225
* Lorsque Sightly Parsys est utilisé pour rendre les composants insérés via JavaScript dans l’interface utilisateur tactile, la décoration personnalisée est ignorée une fois la page actualisée. NPR-14122
* Les listes déroulantes de cible ne fonctionnent pas dans la boîte de dialogue IU tactile lorsque plusieurs champs Richtext, tels que les liens, sont créés. NPR-13911
* Lors de la modification d’un champ de texte avec plusieurs propriétés RTE (Rich Text Editor) dans une boîte de dialogue (interface utilisateur tactile), la cible d’action se déplace aléatoirement vers une propriété RTE spécifique. NPR-13703
* Le composant vidéo prêt à l’emploi par défaut n’affiche pas la miniature vidéo. NPR-14976
* Informations lentement chargées dans l’onglet Utilisations en direct de l’éditeur de modèles. NPR-14880 : correctif pour CQ-83417
* L’installation de Hotfix-10936 sur une instance AEM 6.2 désactive le composant iparsys. NPR-14330 : correctif pour CQ-106982
* Plusieurs problèmes de composant de déploiement et un problème de Live Copy après la migration vers AEM 6.1 SP1. NPR-15256
* L&#39;action Déploiement de page ne parvient pas à créer des enfants au-delà du premier niveau, même pour plusieurs configurations de Déploiement. NPR-15055
* Lors de l’envoi de la boîte de dialogue Propriétés de la page à partir de l’éditeur, les données inchangées dans les onglets LiveCopy sont réécrites. NPR-14693
* Lorsque la boîte de dialogue Propriétés de la page est envoyée par l&#39;éditeur, le processeur de post-traitement MSM écrit certains paramètres de la requête au lieu du paramètre `msm:writeLiveCopyConfig`. NPR-14434
* Plusieurs problèmes se rapportant au composant Déploiement, aux Live Copies et à d’autres aspects de la gestion multisite. NPR-12235

### Ressources {#assets-18}

* UnPack Workflow ne peut pas gérer les images contenant des caractères spéciaux dans le nom du fichier image. NPR-15227 : correctif pour CQ-103887
* Les ressources dont l’expression Répéter avec condition ne s’affichent pas correctement. Lorsque l’utilisateur prévisualisation le modèle de lettre `*CDN3835RLCEN*`, aucun fichier situé dans la zone cible de contenu ne s’affiche. Lorsque la ressource `*VIPReassement*`, qui est facultative et qui est présélectionnée, est désélectionnée, les autres ressources présélectionnées sont affichées dans la lettre. NPR-14844

* Lors de la création d’une collection dynamique, la balise de style n’est pas conservée lors de l’enregistrement de la collection dynamique. NPR-15081 : correctif pour CQ-4195494
* Requêtes de recherche de ressources s’exécutant lentement dans l’interface utilisateur tactile lors de recherches simultanées effectuées par plusieurs utilisateurs. NPR-15019 : Hotifx pour CQ-4195405
* Les métadonnées extraites pour une propriété de type `Long[]` sont converties en type `String[]` lorsque la ressource d’origine est rechargée à un autre emplacement. NPR-15016 : Correctif de CQ-4195005

* Utilisateurs ne pouvant pas supprimer une recherche enregistrée ou une collection dynamique. NPR-14924 : correctif pour CQ-108494
* La modification de métadonnées pour des ressources en bloc (mode d’ajout) lors de l’utilisation d’une valeur booléenne pour TypeHint dans un champ déroulant du schéma de métadonnées sous-jacent génère une erreur. NPR-14529 : correctif pour CQ-106876
* Les utilisateurs ne disposant pas de droits de réplication ne peuvent pas supprimer les dossiers Asset. NPR-14321 : correctif pour CQ-88271
* Lorsque vous tentez de modifier les profils vidéo d’une vidéo dans l’éditeur de Canal, la boîte de dialogue de conception ne s’ouvre pas et déclenche une exception de pointeur nul dans le journal des erreurs. NPR-14144 : correctif pour CQ-81101
* La propriété d’horodatage &quot;Créé&quot; générée par le système et affichée dans la page de propriétés d’un fichier est incorrecte. NPR-13992 : correctif pour CQ-95029
* Demande d’activation de la détection des ressources de duplicata pour les utilisateurs sans accès en lecture dans AEM Assets NPR-13851 : Correctif pour CQ-102281
* Les utilisateurs ne peuvent pas modifier les métadonnées des fichiers en bloc à partir de la page de propriétés. NPR-13721 : correctif pour CQ-100703
* Message d’erreur incorrect dans l’interface utilisateur classique lorsqu’un fichier duplicata est téléchargé. Le message d’erreur n’indique pas pourquoi le téléchargement a échoué. NPR-13691 : correctif pour CQ-99272
* AEM Assets ne peut pas trier plus de 50 fichiers par taille à la fois dans la vue de Liste lorsque le dossier contient de nombreux fichiers. CQ-100588
* La sélection de plusieurs actifs génère une erreur avec le code de réponse - 414 (Request-URI Too Long) si l’URI de fichier/dossier est trop long. NPR-13516 : correctif pour CQ-76076
* La page Rapport Ressources ne répond plus lorsque l’utilisateur sélectionne toutes les options dans la boîte de dialogue Configurer des colonnes. NPR-13187 : correctif pour CQ-95589
* Comportement inattendu du sélecteur de balises dans Safari et Internet Explorer. NPR-13134
* La modification de la recherche enregistrée à partir du rail de recherche d’administration des ressources permet de les enregistrer en tant que sélections dynamiques imbriquées, ce qui entraîne des problèmes de stabilité des environnements. NPR-13119 : correctif pour CQ-99460
* Après avoir déplacé un fichier (ou un dossier) puis l’avoir renommé, les métadonnées &quot;cq:name&quot; ne reflètent pas le nouveau nom de fichier (nom du dossier). NPR-13036 : correctif pour CQ-99141
* Les fichiers dont les noms contiennent des caractères spéciaux ne peuvent pas être téléchargés à partir du lien de téléchargement partagé par courrier électronique. NPR-12872 : correctif pour CQ-95795
* Les rapports d’actifs prêts à l’emploi générés en présence d’un nombre important de ressources provoquent de lourdes traversées lorsque la recherche n’atteint aucun pic d’index et d’utilisation du processeur. NPR-12811 : correctif pour CQ-84409
* Les utilisateurs de l’instance d’auteur AMS AEM Assets ont accès à des réseaux disparates, incapables de télécharger des fichiers à l’aide du transfert de blocs sans avoir à supprimer des privilèges sur les dossiers. NPR-12768 : correctif pour CQ-82715
* Dans les recherches basées sur des balises pour les ressources à l’aide du rail Recherche de ressources, la fonction Type avant ne se limite pas au chemin racine et affiche des balises de tous les espaces de nommage. NPR-12666
* Le composant StaticRenditions soulève une exception de pointeur nulle. NPR-12665
* Demande de désactivation de MissingMetadataNotificationJob, car l’interface utilisateur de notification de badge rompt la page avec une exception d’exécution &quot;Impossible d’analyser l’entrée&quot;. NPR-12500 : correctif pour CQ-93573
* L’option &quot;Désactiver la modification&quot; d’un champ de balise ne fonctionne pas dans les pages de propriétés des ressources sur TouchUI. NPR-12429 : correctif pour CQ-88835
* Correctifs d’API dans AEM Assets 6.2 pour l’implémentation SMB des applications complémentaires. NPR-11099
* Depuis la mise à jour de la requête Jquery, les utilisateurs ne peuvent pas sélectionner une collection de ressources et confirmer la sélection dans le panneau Associer le contenu d’un fragment de contenu. NPR-14847 : Backport pour CQ-4194209
* Bien que le tri soit infini côté client, seuls les articles/bannières/collections actuellement affichés dans l’interface utilisateur sont triés. NPR-14493 : correctif pour CQ-109926
* Demande de mise en oeuvre de la fonction omnisearch pour AEM service mobile à la demande. La recherche de mots-clés pour un article, une collection ou une bannière ne renvoie aucune correspondance. NPR-14093 : correctif pour CQ-101394
* Lors de l’utilisation du composant Coral-select (*granite/ui/components/coral/foundation/form/select*) dans une boîte de dialogue, l’initialisation de valeur ne fonctionne pas correctement dans Internet Explorer (navigateurs IE11 ou Edge) lorsque la valeur sélectionnée contient un seul élément. NPR-13395 : correctif pour CQ-101013

### Projets {#projects-5}

* Lors de l’exportation d’un projet de traduction créé avec la méthode de traduction comme &quot;humain&quot; et le fournisseur de traduction comme &quot;aucun&quot;, aucun fichier translation_export_summary.xml n’est généré car le fichier de mappage du GUID est manquant. NPR-13137 : correctif pour CQ-91976
* Dans les projets AEM, lors de la création d’un projet avec la propriété due date définie, la conversion de date définit incorrectement l’heure en raison de la différence de fuseau horaire entre le serveur et le client. NPR-13003 : correctif pour CQ-98288
* L&#39;option &quot;Révéler sur les sites&quot; est absente de la tâche de traduction lorsqu&#39;un projet de traduction est mis à jour. NPR-12966 : correctif pour CQ-93740
* Lorsqu’un projet de traduction est créé pour une page de site exportée, son rendu n’est pas correct dans la prévisualisation. NPR-12964 : correctif pour CQ-84627

### Workflow {#workflow-3}

* Le lien Charge dans l’onglet Archivage de la console de flux de travail renvoie une erreur avec le code de réponse &quot;404&quot; en cliquant dessus. NPR-14993 : correctif pour CQ-4194977
* Lors de l’utilisation AEM workflows par défaut, le publieur CQ ne parvient pas à envoyer une notification par courrier électronique au groupe qui ne dispose pas de l’adresse électronique d’un seul membre. NPR-14804 : demande de correctif pour CQ-91499
* Amélioration des performances de la boîte de réception et du badge de notification dans l’interface utilisateur tactile. NPR-14145 : correctif pour CQ-101125
* Les utilisateurs ne peuvent pas prévisualisation la charge à partir de la console de la boîte de réception du processus lors de l’initialisation de workflows. NPR-13226 : correctif pour CQ-100275
* Le cookie &quot;saml_request_path&quot; configuré à l&#39;aide du gestionnaire d&#39;authentification SAML affiche le cookie défini avec un &#39;?&#39; supplémentaire. character. En outre, lorsqu’une réponse SAML est renvoyée à AEM, le cookie AEM &quot;saml_request_path&quot; renvoie une valeur non valide en raison de caractères déjà codés. NPR-13517 : Correctif proactif pour GRANITE-11722 et GRANITE-14414

### Intégration de solution {#solution-integration}

* Après l’intégration de AEM 6.2 à Search &amp; Promote, si un utilisateur recherche un terme qui renvoie une bannière, la fonctionnalité de recherche ne répond plus. NPR-14549 : CFP pour CQ-109631

### Dynamic Media {#dynamic-media}

* De nombreuses tâches AEM-Scene7 sling qui ont été créées et annulées lors de l’activation AEM sont enregistrées en tant que tâches d’archivage pendant la réplication. NPR-12835 : correctif pour CQ-86115

### Sécurité {#security-5}

* Demande de résolution d&#39;un problème de validation d&#39;entrée dans le filtre WCMDebug. NPR-12444 : demande de correctif pour CQ-94890
* Demande proactive de correction du comportement XSS lors de l’utilisation de l’Assistant de création de lancements.\
   NPR-13062 : demande de correctif pour CQ-99577

#### Package de modules complémentaires Forms {#forms-add-on-package-19}

`Adaptive Forms`

* Lors de la création d’un panneau répétable à l’aide de formulaires adaptatifs, le titre du panneau ne peut pas être mis à jour au moment de l’exécution. NPR-15325
* Lorsque la valeur par défaut d’un bouton radio est définie et qu’une valeur autre que la valeur par défaut est sélectionnée lors de l’enregistrement ou de l’envoi, la valeur n’est pas affichée sur le préremplissage. NPR-15304
* Google Chrome affiche un comportement incorrect lors de l’utilisation du événement d’options pour remplir de manière dynamique la liste déroulante et envoyer la valeur de l’élément sélectionné. NPR-15198
* Lors de la création d’un panneau répétable à l’aide de formulaires adaptatifs, le titre du panneau ne peut pas être mis à jour au moment de l’exécution. NPR-15181
* Lors de l’utilisation du mode d’édition pour les formulaires adaptatifs, des erreurs JavaScript telles que - &quot;Le gestionnaire du composant n’est pas valide&quot; et &quot;guidelib is undefined&quot; sont survenues. NPR-15112
* Le chargement différé d’un fragment dans un panneau répétitif ne fonctionne pas comme prévu. NPR-13916, NPR-14785

`Correspondence Management`

* Les actifs de Correspondence Management avec `'Repeat with condition'`jeu d’expressions ne s’affichent pas correctement. NPR-14844
* Lors de la recherche d’une ressource Correspondence Management (telle qu’une lettre, un fragment de document ou tout autre type), l’icône File d’attente de téléchargement disparaît de la barre d’outils. NPR-14745
* Lors de la création d’un module de Liste, le basculement des propriétés spécifiques à la ressource (modifiable, obligatoire, par exemple) ne fonctionne pas. NPR-14689
* Le panneau Eléments de données de l’utilitaire Créateur d’Expressions continue à se charger au cas où un module de condition serait créé sans sélectionner de dictionnaire de données. NPR-14688
* Lors de la prévisualisation d’une lettre, les utilisateurs ne peuvent pas utiliser d’espaces de tabulation pour aligner le contenu au format tabulaire. NPR-14481
* Lors de l’exportation en bloc des actifs de Correspondence Management depuis l’interface utilisateur, AEM Forms Server génère des journaux inutiles. NPR-15226
* Lorsqu’une lettre est prévisualisée, le texte justifié s’affiche dans une autre police. NPR-15468

`**Forms Portal**`

* Les pièces jointes des formulaires envoyés sur le portail Forms ne sont pas visibles lorsqu’un nouveau brouillon de l’envoi du portail est envoyé. NPR-13515

`**Forms Manager**`

* Lors de la navigation dans le répertoire *FormandDocuments*, le bouton Coller ne s’affiche pas lorsque l’utilisateur copie un fichier, puis accède à un autre dossier. CQ-111327

#### Programme d’installation de Forms JEE {#forms-jee-installer-19}

`Rights Management`

* Le événement d&#39;audit associé à la connexion de l&#39;utilisateur est consigné avec une heure non valide. Le moment approprié pour le événement d&#39;audit n&#39;est pas traçable. NPR-13107
* Adobe Acrobat Reader et Microsoft Office n&#39;ont pas réussi à ouvrir les documents protégés par une authentification étendue. NPR-14482

`Process Management`

* Lorsqu&#39;une tâche de brouillon transférée dans l&#39;espace de travail HTML est renvoyée à l&#39;utilisateur initial, la tâche n&#39;apparaît pas dans la file d&#39;attente de l&#39;utilisateur initial. NPR-15178

`Assembler Service`

* AEM Forms ne parvient pas à valider un fichier PDF/A-2b contenant plus de deux signatures. NPR-14101

`XTG`

* Lors de l&#39;impression d&#39;un document à l&#39;aide d&#39;un bac d&#39;dérivation d&#39;imprimante, la fonction `GeneratePrintedOutput` n&#39;active pas la récupération de papier à partir du bac d&#39;dérivation de droite. NPR-14079

#### Concepteur Forms {#forms-designer-2}

* Forms Designer se bloque lorsque l’utilisateur exécute l’utilitaire de vérification orthographique avec la langue de formulaire sélectionnée en français (Canada). NPR-13740
* Forms Designer se bloque lorsque l’utilisateur sélectionne Calculer le événement ou valider le événement pour un champ de formulaire et modifie le langage en JavaScript, puis entre `this.` dans la fenêtre **[!UICONTROL Éditeur de script]**. NPR-12974

### Packages de fonctionnalités inclus dans CFP1 {#feature-packs-included-in-cfp-3}

`Mobile Forms` (Package d’Ajoute Forms) :

* Lorsqu’un formulaire adaptatif est créé à partir d’un fichier XDP, la tabulation pour l’accessibilité ne suit pas le modèle défini. NPR-12562

`Adaptive forms` (Package d’Ajoute Forms) :

* Le créateur de règles pour les formulaires adaptatifs ne fournit pas d’accès basé sur les rôles. Les modifications effectuées par un auteur ne peuvent pas faire l’objet d’un suivi. NPR-12840

`Core` (Programme d’installation de Forms JEE):

* La fonctionnalité CORS (CoreCross Origine Resource Sharing) en tant que filtre de servlet n’est pas activée pour Jboss+. NPR-13050

## Télécharger les instructions relatives aux CFP via la distribution de logiciels {#download-instructions-for-cfp-via-package-share}

>[!NOTE]
>
>Pour les clients AEM Forms, il est essentiel d’installer AEM module complémentaire de formulaires après avoir installé AEM Service Pack, Cumulative Service Pack ou Feature Pack.

Vous pouvez télécharger le package CFP directement à partir de Software Distribution ou effectuer les opérations suivantes :

1. Ouvrez [Distribution de logiciels](https://experience.adobe.com/fr/downloads). Vous avez besoin d’un Adobe ID pour vous connecter à la Distribution de logiciels.
1. Appuyez sur **[!UICONTROL Adobe Experience Manager]** dans le menu d’en-tête.
1. Appuyez sur le nom du package, sélectionnez **[!UICONTROL Accepter les termes du CLUF]**, puis appuyez sur **[!UICONTROL Télécharger]**.

## Instructions d&#39;installation pour CFP {#installation-instructions-for-cfp}

Cette section décrit les exigences et les étapes à suivre pour installer le CFP.

### Avant l’installation  {#before-you-install}

>[!NOTE]
>
>Les packs de fonctionnalités facultatifs fournis par Adobe dépendent de la version et du pack de correctifs cumulés. Si vous avez installé un pack de fonctionnalités, contactez [l’équipe d’assistance clientèle d’AEM](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html) pour valider sa compatibilité avec le pack de correctifs cumulés pour AEM 6.2.

>[!NOTE]
>
>Il est recommandé de valider  chaque nouveau package d’installation avant d’essayer d’installer le package. La pré-validation analyse et signale les erreurs détectées avant l’installation et avertit les utilisateurs de ces erreurs, recouvrements et autorisations de manière proactive.
>
>Vous pouvez accéder à la documentation de l’option Valider à l’adresse [https://docs.adobe.com/content/docs/en/aem/6-2/administer/content/package-manager.html#Package%20Validator](https://docs.adobe.com/content/docs/en/aem/6-2/administer/content/package-manager.html#Package%20Validator).

* aem 6.2 Service Pack 1 est une condition préalable pour la PCP. Pour obtenir des instructions sur l’installation, consultez les [Notes de mise à jour du service Pack 1 d’AEM 6.2](https://docs.adobe.com/docs/en/aem/6-2/release-notes/sp1.html).

* Le téléchargement Cumulative Fix Pack est disponible sur [Software Distribution](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq620/cumulativefixpack/AEM-6.2-SP1-CFP20), auquel vous pouvez accéder directement à partir de l&#39;instance AEM.
* Pour un déploiement en grappe utilisant ( RDBMK ou MongoDB), le package CFP peut être installé sur n’importe quelle instance d’auteur utilisant Package Manager.

* Avant d’installer le pack de correctifs cumulés, veillez à prendre un instantané ou à effectuer une sauvegarde de votre instance AEM.
* La désinstallation du CFP n’est pas prise en charge.

### Installer le CFP via la distribution de logiciels {#install-the-cfp-via-package-share}

Effectuez les étapes suivantes pour installer le Cumulative Fix Pack sur une instance AEM 6.2 SP1 existante :

1. Cliquez sur le lien [Distribution de logiciels](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/cumulativefixpack/aem-6.4.8-cfp-2.0.zip) pour télécharger le package.

1. Ouvrez [Package Manager](http://localhost:4502/crx/packmgr/index.jsp) et cliquez sur **[!UICONTROL Télécharger le package]** pour télécharger le package.

1. Sélectionnez le nom du package et cliquez sur **[!UICONTROL Installer]**.

### Installation automatique {#automatic-installation}

Le CFP peut être automatiquement installé dans une instance en cours d’exécution de la manière suivante :

* Placez le package dans ../crx-quickstart/install pendant l&#39;exécution du serveur. Le package est automatiquement installé.
* Utilisez l&#39;API [HTTP de Package Manager](https://helpx.adobe.com/fr/experience-manager/6-2/sites/administering/using/package-manager.html) - veillez à utiliser `cmd=install&recursive=true` pour installer le package imbriqué.

### Validation de l’installation {#validate-installation}

1. La page Informations sur le produit (/system/console/ productinfo ) doit maintenant afficher la chaîne de version mise à jour &quot;Adobe Experience Manager, Version 6.2.0.SP1-CFP20&quot; sous Produits installés.
1. Tous les lots OSGI sont ACTIFS ou FRAGMENT dans la console OSGI (utiliser la console web : /system/console/bundles).

>[!NOTE]
>
>Une fois l’installation du package terminée, un message d’information s’affiche indiquant que le package de contenu a été correctement installé, tel que &quot;Content Package AEM-6.2-Cumulative-Fix-Pack-SP1-CFP20 installé avec succès&quot;.

>[!NOTE]
>
>Depuis AEM 6.2 SP1-CFP1, le niveau de journal dans Jackrabbit FileVault est passé d&#39;INFO à DEBUG pour la plupart des messages. Pour obtenir les journaux d&#39;installation d&#39;un package de contenu installé sur AEM 6.2 SP1-CFP1 ou version ultérieure, activez le niveau de journal DEBUG pour `org.apache.jackrabbit.vault.packaging.impl`.

### Installation d’AEM Forms {#install-forms}

>[!NOTE]
>
>Ignorez cette section si vous n’utilisez pas AEM Forms.

#### Installation du module complémentaire AEM Forms  {#install-aem-forms-add-on}

>[!NOTE]
>
>(**AEM Forms on JEE only**) La procédure d’installation d’un CFP sur AEM Forms on JEE est décrite dans [Installation du CFP sur AEM Forms JEE](install-cfp-aem-forms-jee.md#install-cfp-on-aem-forms-jee).

1. Assurez-vous d’avoir installé le package CFP 6.2 SP1 AEM.
1. Téléchargez le module complémentaire Forms correspondant figurant dans les [versions AEM Forms](aem-forms-releases.md) de votre système d’exploitation.
1. Installez le module complémentaire Forms comme décrit dans la section [Installation des modules complémentaires de formulaires AEM](https://helpx.adobe.com/fr/experience-manager/6-2/forms/using/installing-configuring-aem-forms-osgi.html).

#### Installation du package de lots AEM Forms JEE {#install-aem-forms-jee-bundles-package}

Les correctifs dans AEM Forms JEE sont fournis dans un programme d’installation distinct. Pour plus d’informations sur l’installation d’un CFP pour AEM Forms sur JEE, reportez-vous à [Installation d’un CFP pour AEM Forms JEE](install-cfp-aem-forms-jee.md).

#### Programme d’installation du Concepteur Forms  {#designer-installer}

1. Pour installer la mise à jour, exécutez le fichier Designer6.2.0_&lt;Language>_Cumulative_QF.msp.
1. Sur l’écran de bienvenue, cliquez sur **Mettre à jour**. L’installation démarre.
1. Une fois l’installation terminée, cliquez sur **Terminer**.

## Paramètres de délai d’expiration configurables par l’utilisateur pour les connexions DTM, Analytics, Cible, Search &amp; Promote {#user-configurable-timeout-parameters-for-dtm-analytics-target-search-promote-connections}

Avec AEM Cumulative Fix Pack 6.2 SP1-CFP7 et versions ultérieures, les délais d&#39;expiration de la connexion ont été configurables sur toutes les connexions ci-dessus, selon les détails ci-dessous :

| **Connexions** | **Délai de connexion*** | **Délai d’expiration du socket**** |
|---|---|---|
| DTM | 30000ms | 3 000 ms |
| Analyses | 3 000 ms | 3 000 ms |
| Cible | 60000ms | 3 000 ms |
| Search&amp;Promote | 3 000 ms | 3 000 ms |

* **Délai d&#39;expiration de connexion*** - Délai d&#39;expiration en millisecondes jusqu&#39;à ce qu&#39;une connexion soit établie. Une valeur de délai d’expiration de zéro est interprétée comme un délai d’expiration infini.
* **Délai d’expiration du socket**** - Délai d’attente en millisecondes pour l’attente de données ou période d’inactivité maximale entre deux paquets de données consécutifs.

>[!NOTE]
>
>Avec AEM Cumulative Fix Pack 6.2 SP1-CFP6 et versions ultérieures, la configuration OSGi utilisée pour l&#39;intégration de Search &amp; Promote est Apache HTTP Components Proxy Configuration. La configuration du proxy du client HTTP 3.1 Day Commons n’est plus utilisée.

## Désactivation de l’état de réplication dans la console de balisage (interface utilisateur classique) (NPR-15842) {#disable-replication-status-in-tagging-console-classic-ui-npr}

Si vous utilisez CFP3 ou une version ultérieure, suivez ces instructions pour désactiver l’état de réplication dans la console Balisage de l’interface utilisateur classique :

* Incrustation *&quot;/libs/cq/tagging/widgets/source/widgets/admin/TagAdmin.js&quot;* dans */apps*

* Ajoute `replicationStateRequired` : &quot;false&quot; après la ligne 416.

   ```js
   415    baseParams: {
   416                    count: "false",
   417                    "replicationStateRequired": "false"
   418                },
   ```

## La dernière mise à jour Java 8 Update 131 renvoie une exception (NPR-21355) {#latest-java-update-throws-an-exception-npr}

>[!NOTE]
>
>Ces paramètres de configuration sont spécifiques aux clients AEM Forms qui utilisent Document Security.

La norme NPR-21355 est incluse dans CFP12.1. Si vous installez CFP12.1 ou une version ultérieure, effectuez la procédure ci-dessous pour configurer NPR-21355 sur le serveur d’applications JBoss. Si vous installez CFP12.1 sur un serveur AEM Forms s’exécutant sur des serveurs d’applications Oracle WebLogic ou IBM WebSpehere, aucune configuration supplémentaire n’est requise :

1. Sauvegardez, supprimez et créez un nouveau fichier module.xml. L’emplacement par défaut du fichier est [AEM_Forms_Installation_directory]/jboss/modules/system/couches/base/com/adobe/livecycle/main/

1. Ouvrez le fichier module.xml nouvellement créé pour le modifier. Ajoutez le code suivant au fichier 

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

1. Créez une sauvegarde des fichiers jsafeFIPS.jar, jsafeJCEFIPS.jar et certjFIPS.jar situés dans [AEM_Forms_Installation_directory]/jboss/modules/system/couches/base/com/adobe/livecycle/main/ et supprimez les fichiers du répertoire susmentionné.

   Contactez le [support Adobe](https://helpx.adobe.com/marketing-cloud/contact-support.html) pour obtenir de nouveaux fichiers JAR. Placez les fichiers JAR obtenus auprès de [l’assistance à l’Adobe](https://helpx.adobe.com/marketing-cloud/contact-support.html) à l’adresse [AEM_Forms_Installation_directory]/jboss/modules/system/couches/base/com/adobe/livecycle/main/

1. (Windows uniquement) Modifiez les fichiers de configuration `[AEM_Forms_Installation_directory]/jboss/standalone.conf.bat` ou `domain.conf.bat` :

   * Pour le serveur JBoss en configuration autonome, ouvrez le fichier standalone.conf.bat pour le modifier.
   * Pour JBoss Server dans la configuration de grappe, ouvrez le domaine.conf.bat pour le modifier.

   Ajoutez les lignes suivantes à la fin et enregistrez le fichier :

   set &quot;JAVA_OPTS=%JAVA_OPTS%-Djnlp.com.rsa.cryptoj.fips140loader=true&quot;

   set &quot;JAVA_OPTS=%JAVA_OPTS%-Dcom.rsa.cryptoj.fips140initialmode=NON_FIPS140_MODE&quot;

1. (Système d’exploitation Linux uniquement) Modifiez le répertoire [AEM_Forms_Installation_directory]/jboss/standalone.conf ou les fichiers de configuration domain.conf :

   * Pour le serveur JBoss en configuration autonome, ouvrez le fichier standalone.conf pour le modifier.
   * Pour JBoss Server dans la configuration de grappe, ouvrez domain.conf pour le modifier.

   Ajoutez les lignes suivantes à la fin et enregistrez le fichier :

   JAVA_OPTS=&quot;$JAVA_OPTS-Djnlp.com.rsa.cryptoj.fips140loader=true&quot;

   JAVA_OPTS=&quot;$JAVA_OPTS -Dcom.rsa.cryptoj.fips140initialmode=NON_FIPS140_MODE&quot;

## Paramètres de configuration requis pour NPR-19778 {#configuration-settings-required-for-npr}

>[!NOTE]
>
>Le RNP-1978 fait partie de la PCP14.

Par défaut, le nombre de files d’attente partagées n’est pas actualisé pour les autres utilisateurs lorsqu’un utilisateur demande une tâche. Pour cela, nous avons introduit une nouvelle propriété. Suivez les étapes ci-dessous pour configurer cette propriété sur votre instance AEM :

1. Accédez à Interface utilisateur d’administration -> Services -> Espace de travail -> Administration globale.
1. Exporter les paramètres globaux.
1. Dans le fichier XML téléchargé, ajoutez la balise `<client_tasksPollingInterval>10</client_tasksPollingInterval>` Ici, 10 est l’exemple de valeur en secondes. Vous pouvez le modifier en conséquence.
1. Enregistrez le fichier .
1. Revenez à l’interface utilisateur d’administration -> Services -> Espace de travail -> Administration globale.
1. Importez le fichier xml dans la section Importer les paramètres globaux.
1. Vous pouvez maintenant vous déconnecter du système et vous reconnecter.
1. Nombre de débuts de file d’attente partagés actualisés pour d’autres utilisateurs de l’espace de travail.
1. Pour désactiver l’interrogation, définissez la valeur sur 0 et importez à nouveau le fichier XML.

## Modifications de l&#39;interface utilisateur {#ui-changes}

* Changement de comportement lors de l’affichage des titres sur la carte d’image pour l’image ayant une balise dc : propriété title définie sur String [] ( multifield ) : seul le titre modifié le plus récent sera affiché sur la carte image dans l’interface utilisateur, bien que tous les titres seront enregistrés dans CRX. Correctif pour CQ-4217165

## Problèmes connus {#known-issues}

* La mise à jour AEM 6.2SP1-CFP19 et AEM 6.2SP1-CFP20 de CFP18 modifie la redirection racine vers la page d’accueil de l’interface utilisateur classique au lieu de /sites.html/content. Vous devrez peut-être corriger sling : Propriété de cible de /welcome.html à /index.html avec CRX Explorer. Ce problème n&#39;est pas observé lors de la mise à jour à partir de CFP17 ou d&#39;une version antérieure.

Les erreurs transitoires suivantes peuvent se produire lorsque vous installez AEM 6.2 SP1-CFPx. Cependant, aucune résolution n’est requise pour ces erreurs, car elles n’ont aucune incidence sur votre instance AEM et disparaissent après l’installation du CFP :

* Lors de la mise à niveau de l’instance AEM 6.2SP1-CFP20 vers AEM 6.5, certaines URL vanity peuvent ne pas fonctionner comme suit :

   * */projects.html*
   * */sites.html*

Toutefois, la solution consiste à redémarrer l’instance AEM après une mise à niveau.

* Une erreur interne au serveur HTTP 500 est reçue lorsque la page des détails du composant Webconsole est ouverte.
* Les erreurs de **création d’instance de composant** et **Service factory renvoyées null** se produisent en raison du redémarrage du référentiel :

   * com.day.cq.cq-personalization [com.day.cq.personalization.impl.DefaultProfileProvider(938)] Impossible de créer une instance de composant en raison d&#39;un échec de liaison de profileManager de référence
   * org.apache.sling.commons.Planificateur FrameworkEvent ERROR (org.osgi.framework.ServiceException : La fabrique de services a renvoyé la valeur null. (Composant : com.day.cq.tagging.impl.TagGarbageCollector (1687))

* Erreur observée lors de l&#39;installation du CFP dans Mongo et DB2 : **org.apache.sling.discovery.oak.TopologyWebConsolePlugin addDiscoveryLiteHistoryEntry : Exception : java.lang.NullPointerException**. Cette erreur ne se produira pas après l&#39;installation d&#39;un CFP sur CFP8.
* (Tâche de mise à jour du Planificateur de maintenance Granite Adobe) com.adobe.granite.maintenance.impl.TaskScheduler : Aucune tâche de maintenance trouvée avec le nom WorkflowPurgeTask pour le granit de fenêtre : hebdomadaire
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
* Lorsque vous installez CFPx sur AEM 6.2 SP1 qui inclut le pack de fonctionnalités Balises intelligentes, l’étape de flux de travaux précédemment ajoutée pour les ressources de balises actives est supprimée du flux de travaux de mise à jour des actifs de gestion des actifs numériques.

Voir la liste des [Problèmes connus dans AEM 6.2 SP1](https://docs.adobe.com/docs/en/aem/6-2/release-notes/sp1.html#Known).

## Uber Jar {#uber-jar}

Le Jar Uber pour la version 6.2 SP1-CFP20 est disponible dans le [référentiel Adobe Public Maven](https://repo.adobe.com/nexus/content/groups/public/com/adobe/aem/uber-jar/6.2.SP1-CFP19/).

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

## Les lots OSGI et les packages de contenu incluaient {#osgi-bundles-and-content-packages-included-5}

Le texte suivant documents la liste des lots OSGI et des packages de contenu inclus dans le CFP.

* [Liste des lots OSGi inclus dans AEM 6.2 SP1-CFP20](assets/do-not-localize/updated.txt)
* [Liste des packages de contenu inclus dans AEM 6.2SP1-CFP20](assets/do-not-localize/content_package_comparison_result.txt)

>[!MORELIKETHIS]
>
>* [Page des correctifs AEM 6.2](https://helpx.adobe.com/fr/experience-manager/kb/aem62-available-hotfixes.html)
>* [Notes de mise à jour AEM 6.2 SP1](https://docs.adobe.com/content/docs/en/aem/6-2/release-notes/sp1.html)
>* [Notes de mise à jour d’AEM 6.2](https://docs.adobe.com/docs/fr/aem/6-2/release-notes.html)
>* [Page de produits AEM ](http://www.adobe.com/fr/solutions/web-experience-management.html)
>* [Documentation d’AEM 6.2](https://docs.adobe.com/content/docs/fr/aem/6-2.html)
>* [Mises à jour des produits prioritaires de l&#39;](https://campaign.adobe.com/webApp/adbePriorityProductSubscribe) abonnement à l&#39; [Adobe](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)

