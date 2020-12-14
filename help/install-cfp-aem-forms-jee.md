---
title: Installation des correctifs cumulés sur AEM Forms JEE
description: Résumé des étapes d’installation et de configuration du Cumulative Fix Pack (CFP) sur AEM Forms JEE
contentOwner: AK
translation-type: tm+mt
source-git-commit: 050be3e2fc20242d222344bc9202752eda336b2e
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 23%

---


# Installation de packs de correctifs cumulés sur AEM[!DNL  Forms] JEE{#installing-cumulative-fix-packs-on-aem-forms-jee}

## Installer le CFP sur AEM 6.3 [!DNL Forms JEE] {#install-cfp-forms-6-3}

Effectuez les étapes suivantes, dans la séquence spécifiée, pour installer le pack de correctifs cumulatifs sur AEM 6.3 [!DNL Forms JEE].

1. Contactez le [support Adobe](https://www.adobe.com/fr/account/sign-in.supportportal.html) pour obtenir le programme d’installation AEM 6.3 [!DNL Forms JEE] pour le CFP.
1. Exécutez le programme d&#39;installation CFP et configurez AEM [!DNL Forms JEE] comme décrit dans [Installer et configurer AEM [!DNL Forms JEE]](#install-and-configure-aem-forms-jee).
1. Installez la dernière version du CFP AEM [6.3.3.x](release-notes-aem-6-3-cumulative-fix-pack.md)
1. Installez le [!DNL Forms] package Ajouté pour AEM CFP [6.3.3.x](aem-forms-releases.md).

### Installer AEM package de lots [!DNL Forms JEE] {#install-aem-forms-jee-bundles-package}

[[!DNL  Forms JEE] AEMpackage](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/cumulativefixpack/fd/AEM-FORMS-6.3-CFP1-JEE-PKG) (aemfd-jee-bundles-package-6.3CFP1; version 1.0.2) fournit à  [!DNL Forms] l’utilisateur les mêmes droits et fonctionnalités que sur l’AEM  [!DNL Forms JEE]   [!DNL Forms OSGi]. Vérifiez les packages installés dans Package Manager et installez-les s’ils ne sont pas déjà installés.

### Instructions supplémentaires pour CQ-4208044 {#additional-instructions-for-cq}

Si vous utilisez AEM serveur 6.3 [!DNL Forms JEE] avec la base de données Oracle, configurez les paramètres suivants après le déploiement de CFP1, c’est-à-dire après l’exécution de Configuration Manager. Ce paramètre est nécessaire pour synchroniser les utilisateurs, les groupes et les membres du groupe lors de l’exécution de la synchronisation de domaine d’entreprise. Voir la publication CQ-4208044 dans [Notes de mise à jour AEM 6.3](release-notes-aem-6-3-cumulative-fix-pack.md#main-pars-header-853219205).

1. Connectez-vous à l’interface utilisateur **Admin**.
1. Accédez à **[!UICONTROL Paramètres]** > **[!UICONTROL User Management]** > **[!UICONTROL Configuration]** > **[!UICONTROL Importer et exporter le fichier de configuration]**
1. Exportez le fichier config.xml.
1. Modifiez l’entrée &quot; `groupMemberDBQueryBatchSize`&quot; sous vos configurations de domaine dans *config.xml*. Exemple d&#39;entrée :

   &lt;entry key=&quot;groupMemberDBQueryBatchSize&quot; value=&quot;999&quot; />

1. Importez à nouveau le fichier modifié, puis relancez la synchronisation.

## Installer le CFP sur AEM 6.2 [!DNL  Forms JEE] {#install-cfp-on-aem-62-forms-jee}

Effectuez les étapes suivantes, dans la séquence spécifiée, pour installer le pack de correctifs cumulatifs sur AEM 6.2 [!DNL Forms JEE].

>[!NOTE]
>
>Si vous utilisez AEM 6.2 [!DNL Forms OSGi], suivez les instructions d&#39;installation indiquées dans les [Notes de mise à jour AEM 6.2 CFP.](release-notes-aem-6-2-cumulative-fix-pack.md)

1. Contactez le [support Adobe](https://www.adobe.com/account/sign-in.supportportal.html) pour obtenir le programme d&#39;installation AEM 6.2 [!DNL Forms JEE] pour le CFP.
1. Exécutez le programme d&#39;installation CFP et configurez AEM [!DNL Forms JEE] comme décrit dans [Installer et configurer AEM [!DNL Forms JEE]](install-cfp-aem-forms-jee.md#install-and-configure-aem-forms-jee).
1. Installez [AEM Hotfix 12785 version 7.0](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq620/hotfix/cq-6.2.0-hotfix-12785).
1. Installez [AEM 6.2 Service Pack 1](https://docs.adobe.com/docs/en/aem/6-2/release-notes/sp1.html).
1. Installez la dernière version [AEM Service Pack1 CFP](release-notes-aem-6-2-cumulative-fix-pack.md) 6.2 Service Pack1.
1. Installez le [!DNL Forms] package Ajouté pour [AEM 6.2 Service Pack 1 CFP](aem-forms-releases.md).

### Installer AEM package de lots [!DNL Forms JEE] {#install-aem-forms-jee-bundles-package-1}

[package](https://www.adobeaemcloud.com/content/packageshare/tools/login.html?resource=%2Fcontent%2Fmarketplace%2FmarketplaceProxy.html%3FpackagePath%3D%2Fcontent%2Fcompanies%2Fpublic%2Fadobe%2Fpackages%2Fcq620%2Fcumulativefixpack%2Ffd%2FAEM-FORMS-6.2-SP1-CFP5-JEE-PKG&amp;$$login$$=%24%24login%24%24)  AEM Forms JEE (aemfd-jee-bundles-package-6.2CFP5); version 1.0.2) fournit à  [!DNL Forms] l’utilisateur les mêmes droits et fonctionnalités que sur l’AEM  [!DNL Forms JEE]   [!DNL Forms OSGi]. Vérifiez les packages installés dans Package Manager et installez-les s’ils ne sont pas déjà installés.

### Configuration du délai d&#39;attente pour les opérations au niveau du composant (NPR-16774) {#configuring-timeout-for-operations-at-component-level-npr}

>[!NOTE]
>
>Après AEM 6.2 CFP4, vous pouvez utiliser les instructions suivantes pour configurer le délai d’attente des opérations DSC en cas de problème lié au délai d’attente pendant le processus de mise à niveau. (Voir NPR-16774 dans [Notes de mise à jour AEM 6.2 CFP4](release-notes-aem-6-2-cumulative-fix-pack.md)).

Le déploiement de DSC prend un temps variable en raison duquel il peut échouer. Pour modifier le délai d’expiration des opérations DSC telles que Install, Load, Début et Stop, vous devez définir `adobe.component.registry.timeout` à l’aide de l’argument JVM avec l’option -D.

Spécifiez la valeur de la clé en secondes. Par exemple : `-Dadobe.component.registry.timeout=300`

Vous pouvez également modifier les dépassements de délai au niveau du composant à l’aide des trois propriétés suivantes :

1. `adobe.all-component.timeout`: remplace les dépassements de délai de tous les Services du produit.
1. `adobe.<serviceName>.timeout`: remplace le délai d’expiration uniquement pour le service (&lt;servicename>) mentionné dans la clé. Si la valeur au niveau du service est définie, l’utilisation de cette commande remplace uniquement la valeur du délai d’expiration du service spécifié s’il est défini au niveau de l’application.
1. `adobe.<serviceName>.<operationName>.timeout`: Il remplace uniquement le délai d’expiration pour l’opération(&lt;servicename>) du service spécifique(s).&lt;operationname>) mentionné dans la clé. Si la valeur est définie au niveau de l’opération, l’utilisation de cette commande remplace uniquement la valeur du délai d’expiration du service spécifié s’il est défini au niveau de l’application ou du service.

**Exemples:**

Utilisez les commandes suivantes pour définir le délai d’expiration au niveau du composant :

1. Pour définir le délai d’expiration de toutes les opérations de service sur 600 s :

   set &quot; `JAVA_OPTS=%JAVA_OPTS% -Dadobe.all-component.timeout=600`&quot;

1. Pour définir le délai d&#39;expiration des valeurs d&#39;opération `DesigntimeService` sur 500 s, utilisez :

   set &quot; `JAVA_OPTS=%JAVA_OPTS% -Dadobe.DesigntimeService.timeout=500`&quot;

1. Pour définir le délai d&#39;expiration des valeurs d&#39;opération `DesigntimeService's previewLCA` sur 700 s, utilisez :

   set `"JAVA_OPTS=%JAVA_OPTS% -Dadobe.DesigntimeService.previewLCA.timeout=700`&quot;

1. Pour définir le `DSC operations` tel que load, install, etc. sur 600 s, utilisez :

   set &quot; `JAVA_OPTS=%JAVA_OPTS% -Dadobe.component.registry.timeout=600`&quot;

## Installer et configurer AEM [!DNL Forms JEE] {#install-and-configure-aem-forms-jee}

1. Effectuez une sauvegarde du dossier /deploy. Il est nécessaire si vous décidez de désinstaller le Quick Fix.
1. Arrêtez le serveur d’applications.
1. Extrayez le fichier d&#39;archive du programme d&#39;installation du correctif sur votre disque dur.
1. Dans le répertoire, dont le nom dépend du système d’exploitation que vous utilisez :

   **Windows**

   Accédez au répertoire approprié sur le support d’installation ou dans le dossier de votre disque dur dans lequel vous avez copié le programme d’installation :

   * (Windows 32 bits) : Disk1\InstData\Windows\VM
   * (Windows 64 bits) : Disk1\InstData\Windows_64bit\VM

   Cliquez ensuite en doublon sur le fichier nommé :

   * aemforms63_cfp_install.exe **(AEM [!DNL Forms] 6.3**)
   * aemforms62_cfp_install.exe **(AEM [!DNL Forms] 6.2**)
   * aemforms61_cfp_install.exe (**AEM [!DNL Forms] 6.1**)

   **Linux, Solaris, AIX**

   Accédez au répertoire approprié :

   * (Linux) : Disk1/InstData/Linux/ NoVM
   * (Solaris) : Disk1/InstData/Solaris/ NoVM
   * (AIX) : Disk1/InstData/AIX/VM

   Dans une invite de commande, tapez :

   * ./aemforms63_cfp_install.bin (**AEM [!DNL Forms] 6.3**)
   * ./aemforms62_cfp_install.bin (**AEM [!DNL Forms] 6.2**)
   * ./aemforms61_cfp_install.bin (**AEM [!DNL Forms] 6.1**)

   Un assistant s’ouvre alors et vous guide tout au long de l’installation.

1. Dans le panneau Introduction, cliquez sur **[!UICONTROL Suivant]**.
1. Dans l’écran Choisir le dossier d’installation, vérifiez que l’emplacement par défaut affiché est correct pour votre installation existante ou cliquez sur **[!UICONTROL Parcourir]** pour sélectionner le dossier de remplacement dans lequel AEM [!DNL Forms] est actuellement installé, puis cliquez sur **[!UICONTROL Suivant]**.
1. Lisez le résumé du correctif Quick Fix, puis cliquez sur **[!UICONTROL Suivant]**.
1. Lisez le résumé relatif à la pré-installation, puis cliquez sur **[!UICONTROL Installer]**. 
1. Lorsque l’installation est terminée, cliquez sur **[!UICONTROL Suivant]** pour appliquer les mises à jour du Quick Fix à vos fichiers installés.
1. La case à cocher Exécuter Configuration Manager est sélectionnée par défaut. Cliquez sur **[!UICONTROL Terminé]** pour exécuter Configuration Manager.

   pour exécuter Configuration Manager ultérieurement, désélectionnez l’option **[!UICONTROL Démarrer Configuration Manager]** avant de cliquer sur **[!UICONTROL Terminé]**. Vous pouvez début Configuration Manager ultérieurement à l’aide du script approprié dans le répertoire *`[AEM_forms_root]`/configurationManager/bin*.

1. En fonction de votre serveur d’applications, sélectionnez l’un des documents suivants et suivez les instructions de la section *Configuration et déploiement d’AEM [!DNL Forms]*.

   Pour AEM [!DNL Forms] 6.3, voir :

   * [ [!DNL Forms] Installation et déploiement d’AEM  pour JBoss](https://helpx.adobe.com/pdf/aem-forms/6-3/install-single-server-jboss.pdf)
   * [ [!DNL Forms] Installation et déploiement d’AEM  pour WebSphere](https://helpx.adobe.com/pdf/aem-forms/6-3/install-single-server-websphere.pdf)
   * [ [!DNL Forms] Installation et déploiement d’AEM  pour WebLogic](https://helpx.adobe.com/pdf/aem-forms/6-3/install-single-server-weblogic.pdf)

   Pour AEM [!DNL Forms] 6.2, voir :

   * [ [!DNL Forms] Installation et déploiement d’AEM  pour JBoss](http://www.adobe.com/go/learn_aemforms_installJBoss_62_fr)
   * [ [!DNL Forms] Installation et déploiement d’AEM  pour WebSphere](http://www.adobe.com/go/learn_aemforms_installWebSphere_62_fr)
   * [ [!DNL Forms] Installation et déploiement d’AEM  pour WebLogic](http://www.adobe.com/go/learn_aemforms_installWebLogic_62_fr)

   Pour AEM Forms 6.1, voir :

   * [ [!DNL Forms] Installation et déploiement d’AEM  pour JBoss](http://www.adobe.com/go/learn_aemforms_installJBoss_61)
   * [ [!DNL Forms] Installation et déploiement d’AEM  pour WebSphere](http://www.adobe.com/go/learn_aemforms_installWebSphere_61)
   * [ [!DNL Forms] Installation et déploiement d’AEM  pour WebLogic](http://www.adobe.com/go/learn_aemforms_installWebLogic_61)



1. Redémarrez AEM [!DNL Forms] serveur JEE.
