---
title: Installation des packs de correctifs cumulatifs sur AEM Forms JEE
description: Résumé des étapes d’installation et de configuration du pack de correctifs cumulatifs (CFP) sur AEM Forms JEE.
contentOwner: AK
exl-id: eed01a42-f4ab-4392-8b8e-eb5bbe2410a0
source-git-commit: 437dad5fffe71592b6f9f9b4099a253e3a55b0c8
workflow-type: ht
source-wordcount: '909'
ht-degree: 100%

---

# Installation de packs de correctifs cumulés sur AEM [!DNL  Forms] JEE {#installing-cumulative-fix-packs-on-aem-forms-jee}

## Installer le CFP sur AEM 6.3 [!DNL Forms JEE] {#install-cfp-forms-6-3}

Pour installer le pack de correctifs cumulatifs sur AEM 6.3 [!DNL Forms JEE], effectuez la séquence d’étapes suivante.

1. Pour obtenir le programme d’installation AEM 6.3 [!DNL Forms JEE] pour le CFP, contactez [l’assistance technique d’Adobe](https://experienceleague.adobe.com/?support-solution=General&amp;lang=fr&amp;support-tab=home#support).
1. Exécutez le programme d’installation du CFP et configurez AEM [!DNL Forms JEE] comme décrit dans [Installation et configuration d’AEM [!DNL Forms JEE]](#install-and-configure-aem-forms-jee).
1. Installez la dernière version du CFP AEM 6.3.3.x
1. Installez le package de module complémentaire [!DNL Forms] pour AEM CFP [6.3.3.x](aem-forms-releases.md).

### Installez le package des lots AEM [!DNL Forms JEE]  {#install-aem-forms-jee-bundles-package}

Le package AEM [!DNL  Forms JEE] (aemfd-jee-bundles-package-6.3CFP1 ; version 1.0.2) apporte à l’utilisateur ou à l’utilisatrice de [!DNL Forms] sur AEM [!DNL Forms JEE] les mêmes droits et capacités que sur AEM [!DNL Forms OSGi]. Vérifiez les packages installés dans le gestionnaire de modules et installez le package s’il ne l’a pas déjà été.

### Instructions supplémentaires pour CQ-4208044 {#additional-instructions-for-cq}

Si vous utilisez le serveur AEM 6.3 [!DNL Forms JEE] avec la base de données Oracle, configurez les paramètres suivants après le déploiement de CFP1, c’est-à-dire après l’exécution de Configuration Manager. Ce paramètre est nécessaire pour synchroniser les utilisateurs, les groupes et les membres de groupes lors de l’exécution de la synchronisation du domaine d’entreprise.

1. Connectez-vous à l’interface utilisateur d’**Administration**.
1. Accédez à **[!UICONTROL Paramètres]** > **[!UICONTROL Gestion des utilisateurs]** > **[!UICONTROL Configuration]** > **[!UICONTROL Importer et exporter des fichiers de configuration]**
1. Exportez le fichier config.xml.
1. Modifiez l’entrée « `groupMemberDBQueryBatchSize` » de vos configurations de domaine dans *config.xml*. Exemple d’entrée :

   &lt;entry key=&quot;groupMemberDBQueryBatchSize&quot; value=&quot;999&quot;/>

1. Importez à nouveau le fichier modifié, puis relancez la synchronisation.

## Installer le CFP sur AEM 6.2 [!DNL  Forms JEE] {#install-cfp-on-aem-62-forms-jee}

Pour installer le pack de correctifs cumulatifs sur AEM 6.2 [!DNL Forms JEE], effectuez la séquence d’étapes suivante.

1. Pour obtenir le programme d’installation AEM 6.2 [!DNL Forms JEE]pour le CFP, contactez l’[assistance technique d’Adobe](https://experienceleague.adobe.com/?support-solution=General&amp;lang=fr&amp;support-tab=home#support).
1. Exécutez le programme d’installation du CFP et configurez AEM [!DNL Forms JEE] comme décrit dans [Installation et configuration d’AEM [!DNL Forms JEE]](install-cfp-aem-forms-jee.md#install-and-configure-aem-forms-jee).
1. Installez AEM Hotfix 12785 version 7.0.
1. Installez AEM 6.2 Service Pack 1.
1. Installez la dernière version de release-notes-aem-6-2-cumulative-fix-pack.md.
1. Installez le package de module complémentaire [!DNL Forms] pour AEM 6.2 Service Pack 1 CFP.

### Installez le package des bundles AEM [!DNL Forms JEE] {#install-aem-forms-jee-bundles-package-1}

Le package AEM Forms JEE (aemfd-jee-bundles-package-6.2CFP5 ; version 1.0.2) apporte à l’utilisateur ou à l’utilisatrice de [!DNL Forms] sur AEM [!DNL Forms JEE] les mêmes droits et capacités que sur AEM [!DNL Forms OSGi]. Vérifiez les packages installés dans le gestionnaire de modules et installez le package s’il ne l’a pas déjà été.

### Configuration du délai d’expiration pour les opérations au niveau du composant (NPR-16774) {#configuring-timeout-for-operations-at-component-level-npr}

>[!NOTE]
>
>Après application des correctifs AEM 6.2 CFP4, vous pouvez utiliser les instructions suivantes pour configurer le délai d’expiration des opérations DSC en cas de problème lié à ce délai au cours du processus de mise à niveau.

Le déploiement de DSC prend un temps variable, ce qui peut entraîner son échec. Pour modifier le délai d’expiration des opérations DSC (notamment Installation, Chargement, Démarrage, Arrêt), vous devez définir `adobe.component.registry.timeout` à l’aide de l’argument JVM avec l’option -D.

Spécifiez la valeur de la clé en secondes. Par exemple : `-Dadobe.component.registry.timeout=300`

Vous pouvez également modifier les délais d’expiration au niveau du composant à l’aide des trois propriétés suivantes :

1. `adobe.all-component.timeout` : remplace les délais d’expiration de tous les services du produit.
1. `adobe.<serviceName>.timeout` : remplace le délai d’expiration uniquement pour le service (&lt;serviceName>) mentionné dans la clé. Si la valeur est définie au niveau du service, l’utilisation de cette commande remplace uniquement la valeur du délai d’expiration du service spécifié si elle est définie au niveau de l’application.
1. `adobe.<serviceName>.<operationName>.timeout` : remplace uniquement le délai d’expiration pour l’opération (&lt;serviceName>) du service spécifique.&lt;operationName>) mentionné dans la clé. Si la valeur est définie au niveau de l’opération, l’utilisation de cette commande remplace uniquement la valeur du délai d’expiration du service spécifié si elle est définie au niveau de l’application ou du service.

**Exemples :**

Utilisez les commandes suivantes pour définir le délai d’expiration au niveau du composant :

1. Pour définir le délai d’expiration de toutes les opérations de service sur 600 s :

   set &quot; `JAVA_OPTS=%JAVA_OPTS% -Dadobe.all-component.timeout=600`&quot;

1. Pour définir le délai d’expiration des valeurs d’opération `DesigntimeService` sur 500 s, utilisez :

   set &quot; `JAVA_OPTS=%JAVA_OPTS% -Dadobe.DesigntimeService.timeout=500`&quot;

1. Pour définir le délai d’expiration des valeurs d’opération `DesigntimeService's previewLCA` sur 700 s, utilisez :

   set `"JAVA_OPTS=%JAVA_OPTS% -Dadobe.DesigntimeService.previewLCA.timeout=700`&quot;

1. Pour définir les `DSC operations` telles que le chargement et l’installation, à 600 s, utilisez :

   set &quot; `JAVA_OPTS=%JAVA_OPTS% -Dadobe.component.registry.timeout=600`&quot;

## Installation et configuration d’AEM [!DNL Forms JEE]  {#install-and-configure-aem-forms-jee}

1. Effectuez une sauvegarde du dossier /deploy. Cela est nécessaire si vous décidez de désinstaller le Quick Fix.
1. Arrêtez le serveur d’applications.
1. Extrayez le fichier d’archive du programme d’installation de correctif sur votre disque dur.
1. Dans le répertoire, dont le nom dépend du système d’exploitation que vous utilisez :

   **Windows**

   Localisez le répertoire approprié sur le support d’installation ou dans le dossier du disque dur dans lequel vous avez copié le programme d’installation :

   * (`Windows 32-bit`) : `Disk1\InstData\Windows\VM`
   * (`Windows 64-bit`) : `Disk1\InstData\Windows_64bit\VM`

   Double-cliquez ensuite sur le fichier nommé :

   * aemforms63_cfp_install.exe **(AEM [!DNL Forms] 6.3**)
   * aemforms62_cfp_install.exe **(AEM [!DNL Forms] 6.2**)
   * aemforms61_cfp_install.exe (**AEM [!DNL Forms] 6.1**)

   **Linux®, Solaris™, AIX®**

   Accédez au répertoire concerné :

   * (Linux®) : Disk1/InstData/Linux/ NoVM
   * (Solaris™) : Disk1/InstData/Solaris/ NoVM
   * (AIX®) : Disk1/InstData/AIX/VM

   Dans une invite de commande, tapez :

   * ./aemforms63_cfp_install.bin (**AEM [!DNL Forms] 6.3**)
   * ./aemforms62_cfp_install.bin (**AEM [!DNL Forms] 6.2**)
   * ./aemforms61_cfp_install.bin (**AEM [!DNL Forms] 6.1**)

   L’assistant d’installation est lancé pour vous guider tout au long de l’installation.

1. Dans le panneau Introduction, cliquez sur **[!UICONTROL Suivant]**.
1. Sur l’écran Choisir le dossier d’installation, vérifiez que l’emplacement par défaut affiché est correct pour votre installation existante. Ou, cliquez sur **[!UICONTROL Parcourir]** pour sélectionner l’autre dossier dans lequel AEM [!DNL Forms] est installé, puis cliquez sur **[!UICONTROL Suivant]**.
1. Lisez le résumé du correctif Quick Fix, puis cliquez sur **[!UICONTROL Suivant]**.
1. Lisez le résumé relatif à la pré-installation, puis cliquez sur **[!UICONTROL Installer]**.
1. Lorsque l’installation est terminée, cliquez sur **[!UICONTROL Suivant]** pour appliquer les mises à jour du Quick Fix à vos fichiers installés.
1. La case à cocher Exécuter Configuration Manager est sélectionnée par défaut. Cliquez sur **[!UICONTROL Terminé]** pour exécuter le gestionnaire de configuration.

   Pour exécuter Configuration Manager ultérieurement, désélectionnez l’option **[!UICONTROL Démarrer Configuration Manager]** avant de cliquer sur **[!UICONTROL Terminé]**. Vous pourrez démarrer Configuration Manager ultérieurement à l’aide du script approprié dans le répertoire *`[AEM_forms_root]`/configurationManager/bin*.

1. En fonction de votre serveur d’applications, sélectionnez l’un des documents suivants et suivez les instructions de la section *Configuration et déploiement d’AEM [!DNL Forms]*.

   Pour AEM [!DNL Forms] 6.3, voir :

   * Installation et déploiement d’AEM [!DNL Forms] pour JBoss®
   * Installation et déploiement d’AEM [!DNL Forms] pour WebSphere®
   * Installation et déploiement d’AEM [!DNL Forms] pour WebLogic

1. Redémarrez le serveur AEM [!DNL Forms] JEE.
