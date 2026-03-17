# 🚀 Kit Chatbot — Vercel + Groq (100% gratuit)

Un chatbot IA complet, hébergé gratuitement, sans carte bancaire.

---

## Structure du projet

```
kit-vercel-groq/
├── api/
│   └── chat.js        ← Backend (tourne sur Vercel, clé API sécurisée)
├── public/
│   └── index.html     ← Frontend (interface du chatbot)
├── vercel.json        ← Configuration Vercel
└── README.md
```

---

## Étape 1 — Obtenir une clé API Groq (gratuit)

1. Va sur https://console.groq.com
2. Crée un compte (gratuit, sans carte bancaire)
3. Dans le menu : **API Keys** → **Create API Key**
4. Copie la clé (elle ressemble à `gsk_xxxxxxxxxxxx`)

---

## Étape 2 — Mettre le projet sur GitHub

1. Crée un compte sur https://github.com si tu n'en as pas
2. Crée un **nouveau dépôt** (bouton vert "+ New")
3. Nomme-le par exemple `mon-chatbot`
4. Upload les fichiers : glisse le dossier `kit-vercel-groq` dans l'interface GitHub
   (ou utilise Git en ligne de commande si tu préfères)

---

## Étape 3 — Déployer sur Vercel (gratuit)

1. Va sur https://vercel.com
2. Crée un compte **avec ton compte GitHub** (connexion en 1 clic)
3. Clique sur **"Add New Project"**
4. Sélectionne ton dépôt `mon-chatbot`
5. Clique sur **"Deploy"** — Vercel détecte tout automatiquement

---

## Étape 4 — Ajouter ta clé API (IMPORTANT)

Dans ton projet Vercel :
1. Va dans **Settings** → **Environment Variables**
2. Clique **Add New**
3. Remplis :
   - **Name** : `GROQ_API_KEY`
   - **Value** : `gsk_xxxxxxxxxxxx` (ta clé copiée à l'étape 1)
4. Clique **Save**
5. Va dans **Deployments** → clique les 3 points → **Redeploy**

C'est tout ! Ton chatbot est en ligne à l'adresse `https://mon-chatbot.vercel.app`

---

## Utiliser ce backend dans d'autres projets

Pour n'importe quel autre projet HTML, appelle simplement :

```js
fetch('https://mon-chatbot.vercel.app/api/chat', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    messages: [{ role: 'user', content: 'Bonjour !' }],
    system: 'Tu es un assistant utile.'
  })
})
```

**C'est ton IA centralisée** — un seul backend, tous tes projets s'en servent.

---

## Limites du tier gratuit Groq

| Ressource              | Limite gratuite         |
|------------------------|-------------------------|
| Requêtes / minute      | 30                      |
| Tokens / minute        | 6 000                   |
| Tokens / jour          | 500 000 (~1000 messages)|
| Coût                   | 0 € / mois              |

Largement suffisant pour des projets personnels.

---

## Changer de modèle

Dans `api/chat.js`, ligne `model:`, tu peux remplacer par :

| Modèle                    | Qualité  | Vitesse |
|---------------------------|----------|---------|
| `llama-3.3-70b-versatile` | ⭐⭐⭐⭐⭐ | Rapide  |
| `llama-3.1-8b-instant`    | ⭐⭐⭐    | Très rapide |
| `gemma2-9b-it`            | ⭐⭐⭐⭐  | Rapide  |
