---
title: Définitions des véhicules de version de mise à jour
description: Cet article décrit les différents types de versions d’ [!DNL Experience Manager] , y compris les versions complètes, les packs de fonctionnalités et les packs de services.
contentOwner: AK
exl-id: 936b8136-9edb-4e11-9c29-f0c3108c35bd
source-git-commit: 10cbece451b46e8d4dbf473d728a20994a5e42cd
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 85%

---

# Définitions des véhicules de version de mise à jour d’[!DNL Experience Manager] {#update-release-vehicle-definitions}

Ce document contient des informations à propos des différents types de versions d’[!DNL Adobe Experience Manager], dont les versions intégrales, les Feature Packs et les Service Packs mis par [!DNL Adobe] à la disposition des clients.

>[!NOTE]
>
>Pour connaître le calendrier des mises à jour d’[!DNL Experience Manager], consultez la [[!DNL Experience Manager] feuille de route des versions](update-releases-roadmap.md).

## Version intégrale {#full-release}

| Eléments | Description |
|-------|------|
| Définition | <ul> <li> Version programmée </li> <li> Prend en charge les chemins de mise à niveau pour des versions spécifiques définies dans les notes de mise à jour. </li> </ul> |
| Dénomination | <ul> <li> Les numéros de version pour les versions majeures augmentent selon la formule X+1.Y.Z. </li> <li> Les numéros de version pour les versions mineures augmentent selon la formule X.Y+1.Z </li> </ul> Où X est le numéro de version principal, Y est le numéro de version secondaire et Z le numéro de correctif. |
| Inclusions | <ul> <li> Nouvelles fonctionnalités </li> <li>  Améliorations </li> <li>  Correctifs </li> </ul> |
| Documentation | <ul> <li> Les notes de mise à jour sont disponibles sur le portail de documentation. </li> <li> La documentation sur les fonctionnalités, les améliorations et les correctifs est disponible sur le portail de documentation </li> </ul> |
| Fréquence | Annuelle |
| Disponibilité et installation | <ul> <li> Livré en tant que programme d’installation de produit autonome </li> <li>  Disponible sur le site web de gestion des licences et Managed Services </li> <li> Le site web de gestion des licences peut nécessiter la migration du référentiel de contenu </li> </ul> |
| Niveau de test | Entièrement validé par le contrôle qualité |

## Service Pack {#service-pack}

| Élément | Description |
|-----|-----|
| Définition | <ul> <li> Version programmée </li> <li> Actuellement, il ne peut pas être restauré. </li> </ul> |
| Dénomination | <ul> <li> Le numéro de version du correctif est un numéro à un chiffre. </li> <li> Après l’installation, il fait augmenter le numéro de correctif du numéro de la version installée selon la formule X.Y.Z.SPx </li> </ul> Où X est le numéro de version principal, Y est le numéro de version secondaire et Z le numéro de correctif. x est le numéro du Service Pack. |
| Inclusions | <ul> <li> Nouvelles fonctionnalités</li> <li>  Améliorations </li> <li> Correctifs </li> <li> Feature Packs d’intérêt commun (le cas échéant) </li> </ul> |
| Documentation | <ul> <li> Les notes de mise à jour sont disponibles sur le portail de documentation. </li> <li> Documentation sur les fonctionnalités, les améliorations et les correctifs de bogues sur le portail de documentation </li> </ul> |
| Fréquence | Trimestrielle |
| Disponibilité et installation | <ul> <li> Livré sous la forme d’un package. </li> <li> Disponible sur la distribution logicielle</li> <li>  Nécessite une installation fonctionnelle existante </li> </ul> |
| Niveau de test | <ul> <li> Tous les correctifs ont été validés par le contrôle qualité </li> <li>  Fonctionnement général des packages avec les exécutions d’automatisation </li> </ul> |

## Pack de correctifs cumulatif {#cumulative-fix-pack-aem}

| Élément | Description |
|-----|-----|
| Définition | <ul> <li> Modèle de diffusion unique des correctifs de publication </li> <li> Package d’agrégation de contenu contenant le package de contenu de composants individuels </li> <li>  Les CFP remplacent les correctifs et ne comportent aucune amélioration.  </li> </ul> |
| Dénomination | X.Y.Z.CFPx <br> Où X est le numéro de version principal, Y est le numéro de version secondaire et Z le numéro de correctif. x est le numéro cumulé du Service Pack. |
| Inclusions | CFP est un pack de correctifs cumulatif contenant des correctifs de tous les composants pour les dates spécifiées. Par exemple, si un client applique CFP3, alors CFP3 = CFP1 + CFP2. |
| Documentation | Les notes de mise à jour sont disponibles sur le portail de documentation. |
| Fréquence | Trimestrielle |
| Disponibilité et installation | <ul> <li> Livré sous la forme d’un package. </li> <li>  Disponible sur la distribution logicielle </li> <li>  Dépendant du dernier Service Pack publié </li> <li>  Le pack de correctifs cumulés est autonome. Les clients et les clientes n’ont pas à se soucier de trouver/résoudre des dépendances. Le CFP doit être installé sur le dernier Service Pack publié. </li> <li>  Le pack de correctifs cumulés peut être installé en tant que package unique, ce qui améliore l’expérience client.  </li> </ul> |
| Niveau de test | Contrôle qualité validé au niveau de l’intégration et test de régression |

## Recouvrement {#overlay}

| Élément | Détails |
|-------|--------|
| Dénomination | recouvrement-&lt;ID de ticket> |
| Inclusions | Correctif pour un fichier JS ou JSP |
| Documentation | Aucune |
| Fréquence | Selon les besoins |
| Disponibilité et installation | <ul> <li> Livré sous forme de package par le service d’assistance clientèle [!DNL Experience Manager]  </li> <li> Pas nécessairement inclus dans les Service Packs ou les versions complètes </li> </ul> |
| Niveau de test | Validé par le service d’assistance clientèle |

## Feature Pack {#feature-pack}

| Eléments | Détails |
|--------|-----|
| Définition | <ul> <li>Les Feature Packs sont des fonctionnalités de module complémentaire qui sont fournies par le biais d’un Service Packs. Si [!DNL Experience Manager] version a publié son dernier Service Pack, Adobe ne livrera plus aucun Feature Pack pour elle à l’avenir. </li> <li> Les Feature Packs contiennent des améliorations de produit, prévues pour une version ultérieure du produit, mais diffusées rapidement en fonction de la décision des responsables des produits d’[!DNL Adobe's].</li> <li>  Les fonctionnalités sont toujours fusionnées avec la prochaine version majeure. Ils sont ensuite transférés vers le [!DNL Experience Manager] version requise par le client </li> <li>  Les Feature Packs d’intérêt commun et de disponibilité générale (GA) sont fusionnés dans le prochain Service Pack.  </li> </ul> |
| Dénomination | `cq-<Release Version>-featurepack-<feature pack ID>-<feature pack version>` |
| Inclusions | <ul> <li> Nouvelles fonctionnalités </li> <li> Améliorations </li> <li> Correctifs de bugs (mises à jour incrémentielles des produits) </li> </ul> |
| Documentation | La documentation est disponible sur adobe.com. |
| Fréquence | Varie en fonction du domaine du produit. |
| Disponibilité et installation | <ul> <li>Livré par le biais de Service Packs </li> <li> Disponible sur la distribution logicielle. Les clients acceptent les Termes et conditions [!DNL Adobe's] par le biais de la distribution logicielle. </li> </ul> |
| Niveau de test | Les Feature Packs de disponibilité générale (GA) sont validés par le contrôle qualité. |

* 1 : les correctifs Oak ne sont pas fournis en tant que correctifs individuels. Toutefois, ils sont inclus dans le correctif cumulatif Oak. Si nécessaire, un diagnostic intégré avec le dernier pack de correctifs cumulatifs Oak peut être mis à votre disposition. Condition préalable : le client possède le dernier pack de correctifs cumulés Oak. Les builds de diagnostic fournissent uniquement le même niveau d’assurance qualité qu’un correctif. Par conséquent, ils ne fournissent pas le même niveau d’assurance qualité qu’un pack de correctifs cumulatif, un Service Pack ou une version de produit. Le correctif final est fourni avec le prochain pack de correctifs cumulatifs.
