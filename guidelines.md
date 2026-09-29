---
source-git-commit: 10cbece451b46e8d4dbf473d728a20994a5e42cd
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 3%
---
# Recommandations pour la contribution à la documentation de Adobe Experience Manager

## Philosophie de la documentation

Les utilisateurs de Adobe Experience Manager travaillent dans des environnements hautement compétitifs et s’efforcent de créer des expériences digitales qui les distinguent de leurs concurrents. Par conséquent, lorsqu’Adobe introduit de nouveaux outils avancés dans AEM, ils fournissent une documentation précise et claire. Cette approche permet aux clients d’utiliser immédiatement leur investissement AEM et d’optimiser le retour sur investissement.

L’objectif de la documentation d’AEM est de la mettre entre les mains des utilisateurs d’AEM dès que possible. Par conséquent, une documentation précise et utilisable est créée et continuellement mise à jour et améliorée.

## Contributions à la documentation

Dans le but d’améliorer continuellement la documentation d’AEM, l’ensemble de la communauté des utilisateurs d’AEM est invitée à contribuer à la documentation. Que ce soit par le biais de demandes ou de problèmes d’extraction, les améliorations apportées à la documentation peuvent être des corrections, des clarifications, des extensions, etc.

## Normes de documentation

Adobe est ouvert aux contributions à la documentation. Toute contribution à la documentation d’AEM, qu’il s’agisse d’une demande d’extraction ou d’un problème, doit être conforme aux normes de contribution et de documentation d’Adobe.

Les contributions qui ne répondent pas à ces normes peuvent être refusées.

### Adobe présente les cas d’utilisation standard.

La documentation d’AEM couvre les cas d’utilisation standard. Les cas d’utilisation ne relevant pas de l’installation et de l’utilisation standard du produit ne font pas partie de la documentation d’AEM.

### Adobe ne documente généralement pas les bogues ou leurs solutions.

La documentation d’AEM couvre les cas d’utilisation standard. Pour cette raison, les bogues, les effets causés par les bogues et les solutions de contournement des bogues ne sont pas documentés.

Les exceptions à cette règle s’appliquent aux notes de mise à jour dans lesquelles les problèmes connus peuvent être répertoriés avec les solutions possibles approuvées par la gestion des produits AEM.

### Les contributions à la documentation ne sont pas destinées à répondre à des questions techniques.

Toutes les idées que vous pourriez avoir pour améliorer la documentation d’AEM sont les bienvenues en tant que contributions. Cependant, les commentaires, les problèmes et les demandes d’extraction sont destinés uniquement aux *contributions*. Ils ne sont pas destinés à répondre à vos questions sur l’utilisation d’AEM, la mise en œuvre de votre projet AEM ou la résolution de problèmes techniques.

Signalez toute question relative à l’utilisation d’AEM ou toute erreur technique à l’aide du [portail d’assistance aux entreprises Experience Cloud](https://experienceleague.adobe.com/fr?support-solution=General#support). Vous pouvez également utiliser la [communauté &#x200B;](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/ct-p/adobe-experience-manager-community?profile.language=fr).

***Les contributions à la documentation d’AEM ne remplacent pas l’assistance clientèle d’Adobe*** et toute contribution de ce type visant à obtenir des réponses à des questions d’assistance est refusée.

### Les contributions doivent clairement faire référence aux pages de documentation concernées.

Si vous créez un problème pour suggérer des améliorations à la documentation, incluez des liens vers les pages affectées. Si vous créez un problème à l’aide du lien **Modifier cette page** sur une page de documentation, le problème est automatiquement créé avec un lien vers la page.

Ce processus ne s’applique pas aux demandes d’extraction, car les demandes d’extraction, de par leur nature, font référence à la ou aux pages affectées.

## Instructions de documentation

Toute contribution à la documentation doit respecter certaines instructions de style.

Le respect de ces instructions facilite la révision de votre contribution et accélère donc l’intégration à la documentation.

### Langue et style

#### Langue

* La documentation d’AEM est rédigée et conservée en anglais (États-Unis).
* Veillez à ce que les phrases soient aussi simples que possible.
* Gardez le langage clair et concis.

Souvenez-vous que les lecteurs de la documentation d’AEM sont internationaux et ne peuvent pas être des locuteurs anglais natifs ou bilingues. Évitez les termes familiers et veillez à ce qu&#39;ils soient aussi clairs et simples que possible.

#### Suivez le Manuel de style de ®

Le [Manuel de style de Microsoft®](https://learn.microsoft.com/en-us/style-guide/welcome/) est un guide de style de documentation disponible gratuitement qui se concentre sur la documentation logicielle et la documentation AEM suit ce guide dans la mesure du possible.

### Mise en forme

| Élément | Style |
|---|---|
| Élément ou option de l’interface utilisateur | **gras** |
| Nom de fichier, chemin, entrée utilisateur, valeurs de paramètre | `monospaced` |
| Code, ligne de commande | ```Code Block``` |

### Copies d’écran

Les captures d’écran doivent être utilisées de manière judicieuse et uniquement lorsqu’une description textuelle est insuffisante.

Les marques ou autres annotations dans les captures d’écran (cadres rouges, flèches ou texte) ne doivent pas être utilisées. Ainsi, les captures d’écran sont plus faciles à réutiliser ou à répliquer dans les versions localisées de la documentation.

### Références spécifiques à la version

Idéalement, évitez autant que possible toute référence directe à une version spécifique dans le contenu de la documentation. Cette approche rend la documentation plus flexible et extensible pour les versions ultérieures.

### Utilisation de Day, AEM, CQ, CRX

Lorsque vous mentionnez le produit pour la première fois dans un article, utilisez toujours son nom complet, **&#x200B;**. Ensuite, vous pouvez l’appeler **&#x200B;**.

Day, Day Software, CQ et CRX ne doivent pas être utilisés, sauf lorsqu’ils sont inévitables, comme dans les noms de classe ou en référence à l’historique d’AEM.