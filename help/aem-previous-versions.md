---
title: Anciennes versions de AEM, CQ et CRX
description: Modules de documentation des versions antérieures d’Adobe Experience Manager, de CQ et de CRX.
translation-type: tm+mt
source-git-commit: 47b391ed659264b611f08d2fa9e45a923be5c445
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 27%

---


# Anciennes versions de [!DNL Adobe Experience Manager], CQ et CRX {#older-versions-aem-cq-crx}

## Anciennes versions de la documentation [!DNL Experience Manager] {#older-version-aem-documentation}

Les versions de [!DNL Experience Manager], CQ et CRX répertoriées sur cette page sont Fin de vie et ne sont plus officiellement vendues par Adobe. Les dernières versions de la documentation officielle relative à ces anciennes versions sont disponibles en libre-service. Nous vous recommandons d’effectuer la mise à niveau vers la dernière version (actuellement [[!DNL Experience Manager] 6.5](https://experienceleague.adobe.com/docs/experience-manager-65.html)).

>[!NOTE]
>
>Pour savoir quand une version [!DNL Experience Manager] arrivera à la fin de la prise en charge de base, voir [produits et périodes d&#39;assistance technique](https://helpx.adobe.com/fr/support/programs/eol-matrix.html) et rechercher `AEM`.

### Avant l’installation {#before-installation}

Avant de télécharger module, déterminez quelle audience va consulter le contenu. Cette décision détermine la façon dont il est déployé :

* Les développeurs peuvent procéder à une installation locale pour une consultation rapide.
* Si une consultation plus large de la documentation est nécessaire au sein d’une entreprise, il est recommandé de déployer le module sur une instance de création AEM accessible en interne, qui n’est pas en production.

>[!NOTE]
>
>Les utilisateurs doivent être connectés à l&#39;instance [!DNL Experience Manager] pour accéder à ce contenu sur [!DNL Experience Manager] Auteur. Ce contenu n’est pas accessible par défaut sur AEM Publish (car il est disponible sous /libs).

## Emplacement de distribution de logiciels {#software-distribution-locations}

Vous aurez besoin d&#39;une Adobe ID valide :

* Si vous n’avez pas d’Adobe ID, vous pouvez en créer un à l’adresse www.adobe.com.
Si vous avez besoin d&#39;aide pour créer ou gérer votre Adobe ID, [consultez ce guide](https://helpx.adobe.com/manage-account.html)

| [!DNL Experience Manager] Version | Lien du portail Distribution logicielle |
|:-----------:|:--------------------------------------------------:|
| [!DNL Experience Manager] 6.1 | [Télécharger AEM-DOCS-6.1 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem-docs/aem-docs-6-1.zip) |
| [!DNL Experience Manager] 6,0 | [Télécharger AEM-DOCS-6.0 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem-docs/aem-docs-6-0.zip) |
| [!DNL Experience Manager] 5.6.1 | [Télécharger AEM-DOCS-5.6.1 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem-docs/aem-docs-5-6-1.zip) |
| [!DNL Experience Manager] 5,6 | [Télécharger AEM-DOCS-5.6 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem-docs/aem-docs-5-6.zip) |
| CQ 5.5 | [Téléchargement de CQ-DOCS-5.5 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Faem-docs%2Faem-docs-5-5.zip) |
| CQ 5.4 | [Téléchargement de CQ-DOCS-5.4 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem-docs/aem-docs-5-4.zip) |
| CQ 5.3 | [Téléchargement de CQ-DOCS-5.3 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem-docs/aem-docs-5-3.zip) |
| CRX 2.3 | [Téléchargement de CRX-DOCS-2.3 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem-docs/crx-docs-2-3.zip) |
| CRX 2.2 | [Téléchargement de CRX-DOCS-2.2 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem-docs/crx-docs-2-2.zip) |
| CRX 2.1 | [Téléchargement de CRX-DOCS-2.1 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem-docs/crx-docs-2-1.zip) |
| CRX 2.0 | [Téléchargement de CRX-DOCS-2.0 à partir de Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem-docs/crx-docs-2-0.zip) |

## Installer un module de documentation {#how-to-install-documentation-package}

Pour installer un package de documentation hérité, [!DNL Experience Manager] doit être installé et en cours d&#39;exécution sur votre lecteur local ou réseau.

### Télécharger le package de documentation {#download-documentation-package}

1. Dans le tableau ci-dessus, sélectionnez le lien de la version de la documentation [!DNL Experience Manager] à télécharger. Par exemple, AEM 5.6.1.

1. Connectez-vous en utilisant votre Adobe ID. Si vous n’avez pas d’Adobe ID, il faut en créer un.

1. Sélectionnez le bouton **[!UICONTROL Télécharger]**.

1. Voici un exemple de ce qui s’affiche :

![Exemple de distribution de logiciels](assets/screen_shot_2020-07-10at161922.jpg)

### Installez le package sur votre instance locale {#install-package-local-instance}

1. Ouvrez l&#39;interface utilisateur [!DNL Experience Manager]. Dans un navigateur Web, saisissez : `http://localhost:4502/`. Connectez-vous en tant qu’administrateur.

1. Sélectionnez **[!UICONTROL Outils]** > **[!UICONTROL Déploiement]** > **[!UICONTROL Modules]**.

1. Dans l’interface utilisateur du gestionnaire de modules, sélectionnez **[!UICONTROL Télécharger le module]**.

1. Naviguez jusqu’à l’emplacement depuis lequel vous avez téléchargé le module AEM 5.6.1 (aem-docs-5-6-1.zip).

1. Sélectionnez le module et cliquez sur **[!UICONTROL OK]**.

1. Une fois le téléchargement du module terminé, il faut l’installer.

1. Dans l’interface utilisateur du gestionnaire de modules, repérez le module et sélectionnez **[!UICONTROL Installer]**.

1. Dans la boîte de dialogue de confirmation, sélectionnez à nouveau **[!UICONTROL Installer]**. Remarque : L’installation prend quelques minutes.

1. Dans un navigateur Web, lancez la page de documentation. A l’aide de l’exemple AEM 5.6.1, l’URL serait : http://localhost:4502/libs/aem-docs/content/en/cq/5-6-1.html.

## Obtenir de l&#39;aide de la communauté [!DNL Experience Manager] {#get-help-from-aem-community}

Si vous avez des questions sur l&#39;utilisation du Experience Manager, nous vous recommandons [de contacter nos experts de la communauté expérimentés dans les [!DNL Experience Manager] forums](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/ct-p/adobe-experience-manager-community).
