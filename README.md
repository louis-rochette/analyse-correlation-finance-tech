# Bitcoin : un actif « tech » ? Analyse de corrélation et d'économétrie financière

Projet personnel d'analyse de données explorant une question devenue centrale sur les
marchés : **le Bitcoin se comporte-t-il désormais comme une valeur technologique ?**
L'étude mesure les liens statistiques entre le BTC et un panier d'actifs tech et de
référence (NVIDIA, Tesla, Apple, Microsoft, Google, Amazon, Meta, Ethereum et l'indice
S&P 500), puis teste s'il est possible d'en tirer un pouvoir prédictif.

## Objectif

- Quantifier la corrélation entre le Bitcoin et les principales valeurs tech, et son
  évolution dans le temps.
- Identifier quels actifs influencent réellement les mouvements du BTC.
- Caractériser le couple rendement / risque du Bitcoin face aux actions et indices.
- Évaluer, de façon critique, si ces relations permettent de prédire la direction du BTC.

## Données

- **Source :** Yahoo Finance
- **Période :** 5 dernières années
- **Actifs étudiés :** BTC-USD, ETH-USD, NVDA, TSLA, AAPL, MSFT, GOOGL, AMZN, META, ^GSPC

## Méthodologie

1. **Récupération et nettoyage** des séries de prix et calcul des rendements.
2. **Corrélation roulante** pour observer l'évolution du lien BTC / valeurs tech dans le temps.
3. **Analyse des distributions** (histogrammes, volatilité, asymétrie et risque de queue).
4. **Test de stationnarité** (ADF) sur les séries de rendements.
5. **Régression multi-actifs** pour expliquer les mouvements du BTC à partir du panier.
6. **Test de causalité de Granger** pour évaluer un éventuel pouvoir prédictif.
7. **Analyse des résidus** du modèle de régression.
8. **Étude rendement / volatilité** et **clustering** pour regrouper les actifs par profil de risque.
9. **Tentative de modèle prédictif** (classification de la direction du BTC).

## Principaux résultats

- **Le BTC évolue de plus en plus comme un actif tech.** La corrélation avec NVIDIA est
  marquée sur la période, avec des pics d'« euphorie » ou de « panique » (mi-2022, début 2026)
  où les actifs montent ou chutent ensemble, et des phases de découplage ponctuel.
- **Le panier de valeurs tech explique ~18 % des mouvements quotidiens du BTC** (régression) —
  faible au sens absolu, mais notable en finance : le S&P 500 et Tesla ressortent comme les
  variables les plus influentes, tandis que d'autres (ex. Google) n'ont pas d'impact significatif.
- **Un actif à très haut risque.** Le BTC est nettement plus volatil que les actions, avec des
  événements extrêmes plus fréquents que ne le prévoit une loi normale (kurtosis élevée, fat tails).
  Rapporté au risque pris, son rendement est inférieur à celui de NVIDIA sur la période.
- **Le clustering** sépare nettement les actifs « prudents » (S&P 500, Apple, Microsoft, Google,
  Amazon) des actifs « agressifs » (Meta, NVIDIA, BTC, Tesla, Ethereum).
- **Pas de pouvoir prédictif exploitable.** Le test de Granger et une tentative de modèle de
  classification ne permettent pas de prédire la direction du BTC mieux que le hasard — un
  résultat cohérent avec l'hypothèse d'efficience des marchés : l'information est intégrée
  quasi instantanément dans les prix.

## Conclusion

Le Bitcoin apparaît aujourd'hui davantage comme un actif « macro » sensible au sentiment du
secteur tech que comme une classe d'actifs indépendante. En revanche, expliquer ses
mouvements *a posteriori* ne permet pas de les *anticiper* : les relations mises en évidence
sont descriptives, pas prédictives.

## Stack technique

Python · pandas · NumPy · Matplotlib · Seaborn · statsmodels · scikit-learn · Jupyter Notebook

## Auteur

Louis Rochette 
