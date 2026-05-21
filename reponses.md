# Réponses — Exercice 2

## 1. Méthodologie et Git

### A — User Story
En tant qu'utilisateur inscrit, je veux pouvoir souscrire à un abonnement Premium afin d'accéder à des fonctionnalités avancées de DevOpsGPT, comme une historique illimité ou des modèles plus puissants.

### B — Commandes Git

**1. Créer la branche feature et faire un commit :**
```bash
git checkout -b feature-premium-subscription
# ... développement ...
git add .
git commit -m "feat: ajout de l'abonnement Premium"
```

**2. Fusionner sur main et créer un tag v1.0.0 :**
```bash
git checkout main
git merge feature-premium-subscription
git tag v1.0.0
```

**3. Pousser le tag sur GitHub :**
```bash
git push origin v1.0.0
```
