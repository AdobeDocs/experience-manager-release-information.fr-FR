---
source-git-commit: 10cbece451b46e8d4dbf473d728a20994a5e42cd
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 56%

---
# Instructions relatives à la contribution à la documentation d’Adobe Experience Manager

## Philosophie de la documentation

Les utilisateurs et utilisatrices d’Adobe Experience Manager travaillent dans des environnements très concurrentiels et font de leur mieux afin de créer des expériences numériques qui les distingueront de la concurrence. Par conséquent, lorsque Adobe introduit de nouveaux outils avancés dans AEM, ils fournissent une documentation précise et claire. Cette approche permet aux clients d’utiliser immédiatement leur investissement AEM et maximiser le retour sur investissement.

L’objectif de la documentation AEM est de la placer entre les mains des utilisateurs et utilisatrices d’AEM dès que possible. Par conséquent, une documentation précise et utilisable est créée et continuellement mise à jour et améliorée.

## Contributions à la documentation

Afin d’améliorer continuellement la documentation d’AEM, toute la communauté des utilisateurs d’AEM peut apporter sa contribution. Qu’il s’agisse de demandes d’extraction ou de problèmes, les améliorations apportées à la documentation peuvent être des corrections, des clarifications, des extensions, et d’autres exemples.

## Normes de la documentation

Adobe accueille favorablement les contributions à la documentation. Toute contribution à la documentation d’AEM, qu’il s’agisse d’une requête d’extraction ou d’un problème, doit être conforme aux normes de contribution et de documentation d’Adobe.

Les contributions qui ne satisfont pas à ces normes peuvent être rejetées.

### Adobe écrit sur les cas d’utilisation standard.

La documentation d’AEM couvre les cas d’utilisation standard. Les cas d’utilisation au-delà de la portée de l’installation et de l’utilisation standard du produit ne font pas partie de la documentation AEM.

### En général, Adobe ne documente pas les bugs ni leurs solutions de contournement.

La documentation d’AEM couvre les cas d’utilisation standard. Pour cette raison, les bugs, les effets qu’ils causent et leurs solutions de contournement ne sont pas documentés.

Les exceptions à cette règle s’appliquent aux notes de mise à jour qui répertorient les problèmes connus ainsi que les solutions possibles approuvées par AEM Product Management.

### Les contributions à la documentation ne sont pas destinées à répondre aux questions techniques.

Toute opinion susceptible d’améliorer la documentation AEM est la bienvenue sous forme de contributions. Toutefois, les commentaires, les problèmes et les requêtes d’extraction sont destinés uniquement aux *contributions*. Elles ne sont pas destinées à répondre à vos questions sur l’utilisation d’AEM, la mise en oeuvre de votre projet AEM ou la résolution de problèmes techniques.

Signalez toute question relative à l’utilisation d’AEM ou d’erreurs techniques à l’aide de la variable [Portail d’assistance aux entreprises Experience Cloud](https://experienceleague.adobe.com/fr?support-solution=General#support). Ou, utilisez le [Communauté des Experience Manager](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/ct-p/adobe-experience-manager-community?profile.language=fr).

***Les contributions à la documentation d’AEM ne remplacent pas l’assistance clientèle Adobe***, et toute contribution de ce type qui recherche des réponses aux questions liées au support technique sera refusée.

### Les contributions doivent clairement référencer les pages de documentation concernées.

Si vous créez un problème pour suggérer des améliorations à la documentation, incluez des liens vers les pages concernées. Si vous créez un problème à l’aide de la variable **Modifier cette page** sur une page de documentation, le problème est automatiquement créé avec un lien vers la page.

Ce processus ne s’applique pas aux requêtes d’extraction, car les requêtes d’extraction, par nature, référencent la ou les pages concernées.

## Directives relatives à la documentation

Toute contribution à la documentation doit respecter certaines directives de style.

Suivez ces instructions pour simplifier la révision de votre contribution et, par conséquent, l’intégration dans la documentation est plus rapide.

### Langue et style

#### Langue

* La documentation AEM est créée et conservée en anglais américain.
* Veillez à ce que les expressions restent le plus simple possible.
* Restez clair et concis.

Souvenez-vous que les lecteurs et lectrices de la documentation AEM sont internationaux et peuvent ne pas être des locuteurs et locutrices anglais natifs ou bilingues. Évitez les expressions familières et restez aussi clair et simple que possible.

#### Suivre le guide de style Microsoft®

[Le guide de style Microsoft®](https://learn.microsoft.com/en-us/style-guide/welcome/) est gratuit et concerne la documentation logicielle. Il s’applique à la documentation AEM, dans la mesure du possible.

### Mise en forme

| Élément | Style |
|---|---|
| Élément ou option de l’interface utilisateur | **gras** |
| Nom de fichier, chemin, entrée utilisateur, paramètre-valeurs | `monospaced` |
| Code, ligne de commande | ```Code Block``` |

### Captures d’écran

Les captures d’écran doivent être utilisées de manière judicieuse et uniquement lorsqu’une description textuelle est insuffisante.

Les marqueurs ou autres annotations dans les captures d’écran (comme les cadres rouges, les flèches ou le texte) ne doivent pas être utilisés. Ainsi, les captures d’écran sont plus faciles à réutiliser ou à répliquer dans les versions localisées de la documentation.

### Références spécifiques à la version

Dans l’idéal, évitez les références directes à une version spécifique dans le contenu de la documentation chaque fois que cela est possible. Cette approche rend la documentation plus flexible et extensible pour les versions ultérieures.

### Utiliser Day, AEM, CQ, CRX

Lorsque vous mentionnez le produit pour la première fois dans un article, utilisez toujours son nom complet, **Adobe Experience Manager**. Après cela, vous pouvez vous y référer comme **AEM**.

Day, le logiciel Day, CQ et CRX ne doivent pas être utilisés, sauf lorsqu’il est impossible de faire autrement, par exemple dans les noms de classe ou en faisant référence à l’historique d’AEM.