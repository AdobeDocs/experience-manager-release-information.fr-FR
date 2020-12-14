---
title: Mettre à jour les définitions de véhicule de version
description: Cet article détaille les différents types de  [!DNL Experience Manager] versions, y compris les versions complètes, les packs de fonctionnalités et les packs de services.
contentOwner: AK
translation-type: tm+mt
source-git-commit: 11ff4f7d66038a80697afe5f104c560137e130f4
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 33%

---


# [!DNL Experience Manager] mettre à jour les définitions de véhicule  {#update-release-vehicle-definitions}

Ce document comprend des détails sur les différents types de versions de [!DNL Adobe Experience Manager], y compris les versions complètes, les packs de fonctionnalités et les Service Packs que [!DNL Adobe] fournit à ses clients.

>[!NOTE]
>
>Pour connaître le calendrier de mise à jour de [!DNL Experience Manager] versions, consultez le [[!DNL Experience Manager] plan de mise à jour des versions](update-releases-roadmap.md).

## Version intégrale {#full-release}

| Eléments | Description |
|-------|------|
| Définition | <ul> <li> Version planifiée </li> <li> Prend en charge les chemins de mise à niveau pour des versions spécifiques, définis dans les notes de mise à jour </li> </ul> |
| Dénomination | <ul> <li> Les numéros de version pour les versions majeures augmentent en fonction de la formule X+1.Y.Z. </li> <li> Les numéros de version pour les versions mineures augmentent en fonction de la formule X.Y+1.Z </li> </ul> Où X est le numéro de version Principal, Y est le numéro de version secondaire et Z le numéro de correctif. |
| Inclusions | <ul> <li> Nouvelles fonctionnalités </li> <li>  Améliorations </li> <li>  Correctifs </li> </ul> |
| Documentation | <ul> <li> Les notes de mise à jour sont disponibles sur le portail de documentation. </li> <li> La documentation sur les fonctionnalités, les améliorations et les correctifs est disponible sur le portail de documentation. </li> </ul> |
| Fréquence | Annuel |
| Disponibilité et installation | <ul> <li> Livré en tant que programme d’installation de produit autonome </li> <li>  Disponible sur le site Web de gestion des licences et Managed Services </li> <li> Le site Web de licence peut nécessiter la migration du référentiel de contenu </li> </ul> |
| Niveau de test | Entièrement validé par le contrôle qualité |

## Service Pack {#service-pack}

| Item | Description |
|-----|-----|
| Définition | <ul> <li> Version planifiée </li> <li> Actuellement, la restauration est impossible </li> </ul> |
| Dénomination | <ul> <li> Le numéro de version du correctif est un numéro à un chiffre. </li> <li> Après l&#39;installation, augmentera le chiffre de correctif du numéro de version installé, en fonction de la formule X.Y.Z.SPx </li> </ul> Où X est le numéro de version Principal, Y est le numéro de version secondaire et Z le numéro de correctif. x est le numéro du Service Pack.  |
| Inclusions | <ul> <li> Nouvelles fonctionnalités</li> <li>  Améliorations </li> <li> Correctifs </li> <li> Packs de fonctionnalités d’intérêt commun (le cas échéant) </li> </ul> |
| Documentation | <ul> <li> Notes de mise à jour disponibles sur le portail de documentation </li> <li> Documentation sur les fonctionnalités, les améliorations et les correctifs de bogues sur le portail de documentation </li> </ul> |
| Fréquence | Trimestriel |
| Disponibilité et installation | <ul> <li> Livré sous la forme d’un module. </li> <li> Disponible sur la distribution de logiciels</li> <li>  Nécessite une installation fonctionnelle existante </li> </ul> |
| Niveau de test | <ul> <li> Tous les correctifs ont été validés par l’assurance qualité </li> <li>  Fonctionnement général des packages avec les exécutions d’automatisation </li> </ul> |

## Pack de correctifs cumulés {#cumulative-fix-pack-aem}

| Elément | Description |
|-----|-----|
| Définition | <ul> <li> Modèle diffusion unique de correctifs de publication </li> <li> Package de contenu agrégé contenant le package de contenu de composants individuels </li> <li>  Les CFP remplacent les correctifs et aucune amélioration n’en fait partie.  </li> </ul> |
| Dénomination | X.Y.Z.CFPx <br> Où X est le numéro de version Principal, Y est le numéro de version secondaire et Z le numéro de correctif. x est le numéro cumulé du Service Pack.  |
| Inclusions | CFP est un pack de correctifs cumulatif contenant des correctifs de tous les composants au cours de dates spécifiées. Par exemple, si un client applique CFP3, alors CFP3 = CFP1 + CFP2.  |
| Documentation | Notes de mise à jour disponibles sur le portail de documentation |
| Fréquence | Trimestriel |
| Disponibilité et installation | <ul> <li> Livré sous la forme d’un module. </li> <li>  Disponible sur la distribution de logiciels </li> <li>  Dépendant du dernier Service Pack publié </li> <li>  La PCP est indépendante. Les clients n’ont pas à se soucier de trouver/résoudre des problèmes de dépendances. Le pack de correctifs cumulatif doit être installé sur le dernier Service Pack publié. </li> <li>  Le CFP peut être installé sous la forme d’un package unique, ce qui améliore l’expérience des clients.  </li> </ul> |
| Niveau de test | Contrôle qualité validé au niveau de l’intégration et test de régression |

## Incrustation {#overlay}

| Elément | Détails |
|-------|--------|
| Dénomination | overlay-&lt;ID de ticket> |
| Inclusions | Correction de bogues pour un fichier JS ou JSP |
| Documentation | Aucune |
| Fréquence | Si nécessaire |
| Disponibilité et installation | <ul> <li> Livré sous forme de package par le service d’assistance clientèle [!DNL Experience Manager]  </li> <li> Pas nécessairement inclus dans les Service Packs ou les versions complètes </li> </ul> |
| Niveau de test | Validée par le service à la clientèle |

## Feature Pack {#feature-pack}

| Eléments | Détails |
|--------|-----|
| Définition | <ul> <li>Les Feature Packs sont des fonctionnalités ajoutées et sont fournis par l’intermédiaire des Service Packs. Si une version [!DNL Experience Manager] a publié son dernier Service Pack, l&#39;Adobe ne lui livrera plus aucun Feature Pack. </li> <li> Les FP contiennent des améliorations de produit, planifiées pour une prochaine version de produit, mais livrées tôt sur la base de la décision de [!DNL Adobe's] Gestion des produits.</li> <li>  Les fonctionnalités sont toujours fusionnées avec la prochaine version majeure, puis portées à la version [!DNL Experience Manager] requise par le client. </li> <li>  L’intérêt commun et les packs de fonctionnalités (feature packs) de disponibilité générale (GA) sont fusionnés dans le prochain Service Pack.  </li> </ul> |
| Dénomination | `cq-<Release Version>-featurepack-<feature pack ID>-<feature pack version>` |
| Inclusions | <ul> <li> Nouvelles fonctionnalités </li> <li> Améliorations </li> <li> Correctifs de bogues (mises à niveau incrémentielles du produit) </li> </ul> |
| Documentation | La documentation est disponible sur adobe.com. |
| Fréquence | Varie en fonction du domaine du produit. |
| Disponibilité et installation | <ul> <li>Livré par le biais de Service Packs </li> <li> Disponible sur Distribution de Logiciels. Les clients acceptent les [!DNL Adobe's] termes et conditions par le biais de la distribution de logiciels. </li> </ul> |
| Niveau de test | Les packs de fonctionnalités de disponibilité générale sont validés par contrôle qualité. |

* 1 : Les correctifs OAK ne sont pas fournis en tant que correctifs logiciels. Toutefois, ils sont inclus dans le correctif cumulatif OAK. Si nécessaire, un diagnostic intégré avec le dernier pack de correctifs cumulatif Oak peut être mis à votre disposition. Condition préalable : le client possède le dernier pack de correctifs cumulatif Oak. Les diagnostics intégrés fournissent le même niveau d’assurance qualité qu’un correctif. Par conséquent, ils ne proposent pas le même niveau d’assurance qualité qu’un pack de correctifs cumulatif, un Service Pack ou une version de produit. Le correctif final est fourni avec le prochain CFP.
