# Exercice 2

## 1. Méthodologie et Git

### A — User Story
En tant qu'utilisateur inscrit, je veux pouvoir souscrire à un abonnement Premium afin d'accéder à des fonctionnalités avancées de DevOpsGPT, comme une historique illimité ou des modèles plus puissants.

### B — Commandes Git

**1. Créer la branche feature et faire un commit :**
git checkout -b feature-premium-subscription
git add .
git commit -m "feat: ajout de l'abonnement Premium"

**2. Fusionner sur main et créer un tag v1.0.0 :**
git checkout main
git merge feature-premium-subscription
git tag v1.0.0

**3. Pousser le tag sur GitHub :**
git push origin v1.0.0


# Exercice 3

## 2. Sécurité et Secrets

### A — Où enregistrer le secret sur GitHub
Sur l'interface web GitHub :
1. Aller dans l'onglet **Settings** du dépôt.
2. Dans le menu gauche, cliquer sur **Secrets and variables > Actions**.
3. Cliquer sur **New repository secret**.
4. Nommer le secret `OPENAI_API_KEY` et coller la valeur.
5. Cliquer sur **Add secret**.

### B — Syntaxe pour injecter le secret dans le workflow
Dans le fichier `.github/workflows/main.yml`, dans l'étape de déploiement :

```yaml
- name: Déploiement
  if: startsWith(github.ref, 'refs/tags/v')
  run: echo "Déploiement en cours..."
  env:
    OPENAI_API_KEY: ${{ secrets.OPENAI_API_KEY }}