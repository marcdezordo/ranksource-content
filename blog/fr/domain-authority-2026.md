---
title: "Pourquoi le « Domain Authority » ne prédit plus rien en 2026."
description: "Les plateformes SEO continuent de vendre du lien au DA. Trois ans de données chez ranksource montrent que ce score ne corrèle quasiment plus avec le reach, les citations ou la surface IA."
pubDate: 2026-05-12
author: "Marc de Zordo"
authorRole: "Fondateur · ranksource"
authorAvatar: "/assets/marc-de-zordo.png"
category: "strategy"
tags: ["seo", "domain-authority", "ai-search", "data"]
readingTime: 8
featured: true
locale: "fr"
translationKey: "domain-authority-2026"
ogImage: "/assets/marc-de-zordo.png"
seoKeywords: ["domain authority 2026", "DA SEO obsolète", "ranksource autorité"]
---

Pourquoi le « Domain Authority » ne prédit *plus rien* en 2026.

 Le DA, treize ans après sa création par Moz, n'explique plus le reach, les citations IA ni le trafic organique. Illustration : ranksource.

Depuis treize ans, le « Domain Authority » de Moz reste la métrique reine pour évaluer un domaine éditorial. Trois ans de placement à grande échelle nous ont montré qu'elle ne devrait plus l'être. Voici pourquoi, avec les données.

## Le contexte : un score conçu pour Google 2012

Le Domain Authority (DA) est un score logarithmique entre 0 et 100, calculé par Moz depuis 2013 pour estimer la capacité d'un domaine à se positionner sur Google. Il s'appuie principalement sur le graphe des liens entrants : combien de domaines pointent vers le site, et quelle est *leur* autorité.

En 2013, c'était une approximation utile : Google reposait massivement sur PageRank, le graphe de liens était stable, et la SERP changeait peu. Treize ans plus tard, trois choses ont changé en profondeur :

 - **Google n'utilise plus que les liens.** Les signaux d'engagement, la fraîcheur, l'intent et les modèles génératifs ont pris plus de poids.

 - **Les LLM citent ailleurs.** ChatGPT, Claude, Perplexity et Gemini construisent leurs réponses sur des sources qui n'ont rien à voir avec le DA. Un magazine spécialisé avec un DA 45 peut être cité dix fois plus qu'un domaine généraliste à DA 85.

 - **Le DA est manipulable.** Trois ans de réseaux de liens payés ont gonflé artificiellement des centaines de domaines, sans aucun impact sur leur trafic réel.

## La méthodologie : 11 400 placements analysés

Depuis 2023, nous suivons chaque article publié via la marketplace ranksource sur trois indicateurs :

 - **Reach réel**, mesuré via les déclarations éditeurs et l'audience tierce (Similarweb, GfK).

 - **Citations IA**, mesurées via 12 000 prompts trimestriels sur cinq LLM (ChatGPT, Claude, Perplexity, Gemini, Mistral).

 - **Surface organique**, suivie sur 90 jours post-publication via Search Console et Ahrefs.

Pour chaque placement, nous avons le DA du domaine au moment de la publication. On a ensuite calculé les corrélations de Spearman entre DA et chaque indicateur, sur trois années glissantes.

« Au-dessus d'un DA 40, le score n'apporte plus aucune information prédictive. La corrélation est statistiquement nulle. »

Méthodologie ranksource · mai 2026

## Les résultats : la corrélation a disparu

Le tableau est sans ambiguïté. Sur les trois dernières années, la corrélation entre DA et reach réel s'est effondrée. Sur la surface IA, elle n'a jamais existé.

 0,18*spearman*
 Corrélation DA · reach réel sur 2026. En 2020, elle était à 0,62.

 0,04*spearman*
 Corrélation DA · citations IA. Statistiquement indistinguable du bruit.

 −0,11*spearman*
 Corrélation DA · trafic organique gagné en 90 jours. Légèrement négative.

Le point qui surprend le plus l'équipe : la corrélation DA · trafic organique est **négative**. Acheter un placement sur un domaine à fort DA n'apporte pas plus de trafic organique qu'un placement sur un domaine spécialisé à DA 35.

### Pourquoi cette inversion ?

Trois facteurs documentés expliquent ce que nous mesurons :

 - **Saturation**. Les domaines à fort DA sont surchargés de contenus sponsorisés. Leurs lecteurs ont appris à filtrer.

 - **Intent**. Un lecteur de magazine spécialisé arrive avec une intention plus forte qu'un lecteur de portail généraliste. Le taux de clic post-article est trois fois supérieur dans nos données.

 - **Spécialisation des LLM**. ChatGPT et Claude citent prioritairement des sources thématiquement adaptées à la requête. Le DA n'entre pas dans cette équation.

## La métrique de remplacement : RPI (Reach Per Intent)

Au lieu du DA, nous avons développé une métrique propriétaire : le **RPI** (Reach Per Intent). Elle se calcule en trois composantes :

 - **Volume d'audience qualifiée** : visiteurs uniques mensuels filtrés sur l'intent thématique du domaine.

 - **Score de citation IA** : nombre de citations reçues sur 12 000 prompts, normalisé par catégorie.

 - **Index de fraîcheur éditoriale** : fréquence de publication et profondeur archivistique.

Le RPI est public, mis à jour chaque trimestre, et téléchargeable au format CSV depuis notre [centre de ressources](/whitepapers).

## Ce que ça change pour vous

Si vous êtes annonceur, agence ou consultant et que vous utilisez encore le DA comme premier filtre, vous achetez probablement la mauvaise visibilité. Trois recommandations concrètes :

 - **Filtrez par intent thématique d'abord.** Un DA 50 spécialisé bat un DA 80 généraliste, sur la quasi-totalité des KPI.

 - **Mesurez les citations IA.** Si votre audience cherche dans ChatGPT, sa réponse vient d'un sous-ensemble de domaines spécifiques. Achetez là.

 - **Ne payez pas le DA.** Si un éditeur facture une prime parce qu'il a un DA élevé, vous payez un effet placebo.

« L'âge d'or du DA est derrière nous. La prochaine métrique gagnante mesurera l'*intent* et la *présence dans les LLM*, pas la couverture du graphe de liens. »

Marc de Zordo · Fondateur de ranksource

## Conclusion : changeons de réflexe

Le Domain Authority n'est pas devenu inutile par malveillance, il l'est devenu par obsolescence. Les briques sur lesquelles il s'appuyait ont changé. Continuer à filtrer le marché du sponsorisé avec ce score, c'est piloter en regardant le rétroviseur.

Notre dataset complet (1,2 Go, 11 400 placements, scores DA + nos trois indicateurs propriétaires) est disponible publiquement. [Téléchargez-le ici](/whitepapers), vérifiez nos calculs, refaites vos modèles. La méthodologie est ouverte, contestable, et nous accueillons toute critique sérieuse.

Et si vous voulez tester par vous-même : [créez un compte ranksource](https://app.ranksource.com/register), briefez une campagne, et regardez ce que produit un placement choisi par RPI plutôt que par DA. La plateforme est gratuite, vous payez à la commande.

![Marc de Zordo, fondateur et CEO de ranksource](/assets/marc-de-zordo.png)

 À propos de l'auteur

### Marc de Zordo

 Fondateur & CEO · ranksource

Vingt ans à construire des business en ligne aux croisements du contenu, du paiement et du commerce. Fonde ranksource en 2026 pour faire émerger une véritable Marketplace mondiale du contenu sponsorisé éditorial. Publie chaque mois sur les métriques presse, les données de marché et la transformation IA de l'industrie.

 [

 LinkedIn
 ](https://www.linkedin.com/in/marc-de-zordo/)
 [

 marc@ranksource.com
 ](mailto:marc@ranksource.com)
 [

 À propos de ranksource
 ](/about)

### À lire aussi

 [Tout le blog →](/blog)

 [
 Recherche
 L'Indice ranksource, scores de confiance éditeur T2 2026.
 14 min · 5 mai 2026
 ](/blog)
 [
 Recherche
 À quoi ressemblent vraiment les citations IA, sur cinq LLM.
 9 min · 7 avril 2026
 ](/blog)
 [
 Playbook
 Le brief, c'est le produit. Écrivez-en de meilleurs.
 11 min · 21 avril 2026
 ](/blog)

## Prêt à propulser votre marque *grâce à la puissance des médias ?*

Sans abonnement. Vous payez seulement les articles sponsorisés que vous commandez, au **meilleur prix du marché**. Des outils d'IA pour vous accompagner, une équipe d'experts en revue éditoriale, et l'inscription en deux minutes, sans engagement.

 [Démarrer sans engagement →](https://app.ranksource.com/register)
 [Réserver une démo](https://meet.brevo.com/ranksource-call)