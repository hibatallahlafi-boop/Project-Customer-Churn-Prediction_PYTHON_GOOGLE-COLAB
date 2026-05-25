# 📌 Introduction

Le churn client représente le fait qu’un client quitte une entreprise ou arrête d’utiliser ses services.
Ce phénomène est très important pour les entreprises car conserver un client coûte moins cher que d’en acquérir un nouveau.

L’objectif de ce projet est d’analyser le comportement des clients et de construire un modèle de Machine Learning capable de prédire si un client va quitter l’entreprise ou rester.

---

# 📊 Description du Dataset

Le dataset utilisé contient plusieurs informations sur les clients :

| Variable               | Description                           |
| ---------------------- | ------------------------------------- |
| Monthly_Usage          | Utilisation mensuelle du service      |
| Customer_Support_Calls | Nombre d’appels au support client     |
| Subscription_Length    | Durée d’abonnement en mois            |
| Payment_Delay          | Nombre de jours de retard de paiement |
| Churn                  | 0 = Client reste / 1 = Client quitte  |

Le fichier utilisé est :
`customer_churn_dataset.csv`

---

# 🔍 Exploration des Données

La première étape consiste à explorer les données avec la bibliothèque Pandas.

Les fonctions utilisées :

```python
df.head()
df.info()
df.describe()
```

Ces fonctions permettent de :

* afficher les premières lignes du dataset,
* vérifier les types de données,
* détecter les valeurs manquantes,
* obtenir des statistiques générales.

Après vérification, les données sont propres et ne contiennent pas de valeurs manquantes importantes.

---

# 📈 Visualisation des Données

Afin de mieux comprendre les relations entre les variables et le churn, plusieurs graphiques ont été réalisés.

## 1️⃣ Distribution du Churn

Un graphique en barres montre le nombre de clients qui restent et ceux qui quittent l’entreprise.

### Observation :

On peut facilement comparer les deux catégories de clients.

---

## 2️⃣ Monthly Usage vs Churn

Un graphique scatter plot permet de visualiser la relation entre l’utilisation mensuelle et le churn.

### Observation :

Les clients ayant une faible utilisation du service semblent plus susceptibles de quitter l’entreprise.

---

## 3️⃣ Customer Support Calls vs Churn

Un boxplot montre la relation entre les appels au support et le churn.

### Observation :

Les clients qui contactent fréquemment le support client ont tendance à quitter davantage l’entreprise.

---

# 🤖 Préparation des Données

Les données ont été séparées en :

* Variables explicatives `X`
* Variable cible `y`

```python
X = df.drop('Churn', axis=1)
y = df['Churn']
```

Ensuite, les données ont été divisées en :

* 80% pour l’entraînement
* 20% pour le test

```python
train_test_split()
```

---

# 🧠 Modèle de Machine Learning

Le modèle utilisé est :

# Logistic Regression

Ce modèle est adapté aux problèmes de classification binaire :

* 0 → Client reste
* 1 → Client quitte

Le modèle a été entraîné avec :

```python
model.fit(X_train, y_train)
```

---

# 📊 Évaluation du Modèle

Après l’entraînement, le modèle a été testé sur les données de test.

## Accuracy

L’accuracy mesure le pourcentage de prédictions correctes.

```python
accuracy_score()
```

### Résultat :

Le modèle atteint une bonne précision pour prédire le churn des clients.

---

## Confusion Matrix

La matrice de confusion permet d’analyser :

* les bonnes prédictions,
* les erreurs du modèle.

Elle montre combien de clients ont été correctement classés.

---

# 🔮 Prédictions

Le modèle peut maintenant prédire le comportement de nouveaux clients.

## Exemple :

```python
new_customer = [[45, 8, 6, 15]]
```

Ce client :

* utilise peu le service,
* contacte souvent le support,
* paie avec retard.

➡ Le modèle peut prédire que ce client risque de quitter l’entreprise.

---

# 📌 Interprétation des Résultats

Les clients les plus susceptibles de quitter l’entreprise sont ceux qui :

* ont beaucoup de retards de paiement,
* utilisent peu le service,
* contactent souvent le support client.

Les variables les plus importantes semblent être :

* Payment_Delay
* Customer_Support_Calls

Même si le modèle donne de bons résultats, il n’est pas fiable à 100% car certains comportements des clients ne sont pas présents dans les données.

---

# 💡 Recommandations pour Réduire le Churn

L’entreprise peut réduire le churn en :

* améliorant le service client,
* offrant des récompenses aux clients fidèles,
* détectant rapidement les clients à risque,
* réduisant les problèmes de paiement.

---

# ✅ Conclusion

Ce projet a permis :

* d’explorer un dataset réel,
* de visualiser les données,
* de construire un modèle de Machine Learning,
* de prédire le churn client.

Le modèle Logistic Regression donne des résultats satisfaisants et peut aider l’entreprise à prendre de meilleures décisions pour fidéliser ses clients.

---

# 🛠 Technologies Utilisées

* Python
* Google Colab
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn

