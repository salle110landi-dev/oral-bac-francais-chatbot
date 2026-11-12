# Oral Bac Français – Entraînement

Agent conversationnel d'entraînement à l'oral du bac de français (épreuve anticipée de
français), construit avec le [Mistral Agents SDK](https://docs.mistral.ai/agents-sdk).
L'agent est défini dans `main.py`.

## Ce que fait l'agent

- **Examen blanc** : simulation complète de l'épreuve (20 minutes) dans les conditions réelles.
- **Explication linéaire** : travail guidé d'un extrait, étape par étape, sans donner la réponse.
- **Grammaire** : questions type examen (fonctions, propositions, valeurs des temps et des modes).
- **Entretien** : questions sur l'œuvre étudiée, le parcours et la lecture personnelle.
- **Méthode** : conseils sur le déroulé, la gestion du temps et la grille d'évaluation officielle.

À la fin de chaque exercice, l'agent note avec la grille officielle (lecture 2 pts,
explication 8 pts, grammaire 2 pts, entretien 8 pts), souligne deux points forts et
deux priorités de travail.

## Utilisation

Définissez `MISTRAL_API_KEY` dans `.env` avec une clé créée sur la page
[API keys](https://console.mistral.ai/api-keys) de Mistral Studio. `.env` est ignoré par git :
ne le commitez jamais. Ensuite :

```bash
uv run --env-file .env agents info     # vérifier ce que le CLI charge
uv run --env-file .env agents chat     # discuter avec l'agent dans le terminal
uv run --env-file .env agents serve    # exécuter l'agent comme worker durable
uv run --env-file .env agents deploy   # déployer l'agent comme agent géré
```

`agents deploy` construit l'image à partir du commit poussé : le projet doit être dans un
dépôt GitHub et le connecteur GitHub activé sur votre compte Mistral dans Studio.
