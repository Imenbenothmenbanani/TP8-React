# ⚛️ React Hooks Mastery Project

> **"Three hooks, infinite possibilities. Master state management from basics to advanced."**

[![React](https://img.shields.io/badge/React-18.x-61DAFB?logo=react&logoColor=white)](https://reactjs.org/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Ce projet propose une exploration complète des trois hooks React fondamentaux à travers des applications pratiques et interactives. Chaque application démontre une approche différente de la gestion d'état avec persistance locale.

---

## 🎯 Philosophie du Projet

Dans React moderne, trois hooks dominent la gestion d'état :

- **useState** – La base : état local simple et direct
- **useEffect** – Le pont : synchronisation avec le monde extérieur
- **useReducer** – L'architecture : logique complexe et prévisible

Ce projet vous permet de les maîtriser tous les trois dans des contextes réels.

---

## 📋 Table des Matières

1. [Vue d'ensemble](#-vue-densemble)
2. [Applications incluses](#-applications-incluses)
3. [Comparaison technique](#-comparaison-technique)
4. [Installation rapide](#-installation-rapide)
5. [Structure et architecture](#-structure-et-architecture)
6. [Guide d'utilisation](#-guide-dutilisation)
7. [Concepts React abordés](#-concepts-react-abordés)
8. [Quand utiliser quel hook ?](#-quand-utiliser-quel-hook-)
9. [Ressources et documentation](#-ressources-et-documentation)

---

## 🌟 Vue d'ensemble

### Objectifs d'apprentissage

Ce projet vous permet de maîtriser :

✅ **Gestion d'état** : Du simple compteur aux structures complexes  
✅ **Effets de bord** : API, timers, localStorage, événements  
✅ **Reducers** : Architecture flux et logique métier organisée  
✅ **Immutabilité** : Mises à jour d'état sécurisées et performantes  
✅ **Persistance** : Sauvegarde automatique des données  
✅ **Inputs contrôlés** : Formulaires React professionnels

### Technologies utilisées

| Technologie | Version | Utilisation |
|------------|---------|-------------|
| React | 18.x | UI Library |
| JavaScript | ES6+ | Langage principal |
| localStorage | Native | Persistance |
| CSS3 | - | Styling |
| Vite/CRA | Latest | Build tool |

---

## 🚀 Applications incluses

### 1️⃣ Todo App avec useReducer

**Concept** : Gestionnaire de tâches avec architecture reducer avancée

**Fonctionnalités clés :**
- ✏️ CRUD complet sur les tâches
- 🔄 Système de filtres (toutes/actives/complétées)
- 💾 Sauvegarde automatique localStorage
- 🎯 Actions typées et prévisibles
- 📊 Statistiques en temps réel

**Hook principal** : `useReducer` pour une logique d'état structurée

```javascript
// Architecture reducer
dispatch({ type: 'ADD_TODO', payload: 'Nouvelle tâche' });
dispatch({ type: 'TOGGLE_TODO', payload: id });
dispatch({ type: 'DELETE_TODO', payload: id });
```

**Résultat** : ![Todo App](./screenshots/todo.png)

---

### 2️⃣ Shopping List + Pomodoro Timer

**Concept** : Double fonctionnalité avec gestion de timers

**Fonctionnalités clés :**
- 🛒 Gestion de liste de courses
- ⏱️ Timer Pomodoro (25 min focus)
- 🔔 Notifications de fin de session
- 🧹 Nettoyage automatique des intervalles
- 💾 Persistance multi-états

**Hook principal** : `useEffect` pour la gestion de timers et cleanup

```javascript
// Gestion avancée des intervalles
useEffect(() => {
  let interval = null;
  if (isActive) {
    interval = setInterval(() => {
      // Logique timer
    }, 1000);
  }
  return () => clearInterval(interval); // Cleanup
}, [isActive, minutes, seconds]);
```

**Résultat** : ![Shopping List](./screenshots/shopping.png)

---

### 3️⃣ Interactive Blog

**Concept** : Plateforme de blogging complète

**Fonctionnalités clés :**
- 📝 Création et gestion d'articles
- 👍👎 Système de likes/dislikes
- 🔍 Recherche en temps réel
- 🔀 Tri multi-critères (date, likes, titre)
- 👤 Filtrage par auteur
- 🗑️ Suppression d'articles
- 💾 Persistance complète

**Hook principal** : `useState` avec lazy initialization

```javascript
// Lazy initialization pour performance
const [articles, setArticles] = useState(() => {
  const saved = localStorage.getItem('blog-articles');
  return saved ? JSON.parse(saved) : [];
});
```

**Résultat** : ![Blog App](./screenshots/blog.png)

---

## 🧪 Comparaison technique

### useState vs useReducer vs useEffect

| Critère | useState | useReducer | useEffect |
|---------|----------|------------|-----------|
| **Complexité état** | Simple | Complexe | N/A |
| **Logique métier** | Inline | Centralisée | Side effects |
| **Testabilité** | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| **Lignes de code** | Minimal | Moyen | Variable |
| **Cas d'usage** | Compteurs, toggles | Todo, formulaires | API, timers |
| **Performance** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ |

### Détails par hook

#### 🔵 useState

**Quand l'utiliser :**
- État local simple (string, number, boolean)
- Pas de logique métier complexe
- Peu de transformations d'état
- Prototypage rapide

**Forces :**
- API ultra simple
- Parfait pour débuter
- Minimal en code

**Limites :**
- Difficile à tester
- Logique dispersée
- Moins adapté aux gros états

---

#### 🟢 useReducer

**Quand l'utiliser :**
- État avec plusieurs sous-propriétés
- Logique métier importante
- Actions multiples sur l'état
- État partagé entre composants

**Forces :**
- Logique centralisée
- Facilement testable
- Actions prévisibles
- Pattern Redux familier

**Limites :**
- Plus verbeux
- Courbe d'apprentissage

---

#### 🟠 useEffect

**Quand l'utiliser :**
- Appels API
- Timers/intervalles
- localStorage sync
- Abonnements événements
- Modifications DOM

**Forces :**
- Synchronisation externe
- Cleanup automatique
- Dépendances explicites

**Limites :**
- Risque de boucles infinies
- Gestion des dépendances délicate

---

## 💻 Installation rapide

### Prérequis

- Node.js ≥ 14.x
- npm ≥ 6.x ou yarn ≥ 1.22

### Étapes d'installation

```bash
# 1. Cloner le repository
git clone https://github.com/USERNAME/react-hooks-mastery.git
cd react-hooks-mastery

# 2. Installer les dépendances
npm install

# 3. Lancer en développement
npm start

# 4. Ouvrir le navigateur
# → http://localhost:3000
```

### Scripts disponibles

```bash
npm start          # Mode développement
npm run build      # Build production
npm test           # Lancer les tests
npm run lint       # Vérifier le code
```

---

## 📁 Structure et architecture

```
react-hooks-mastery/
│
├── 📂 public/
│   ├── index.html
│   └── favicon.ico
│
├── 📂 src/
│   │
│   ├── 📂 components/          # Composants applicatifs
│   │   ├── TodoApp.jsx         # App avec useReducer
│   │   ├── ShoppingListApp.jsx # App avec useEffect
│   │   └── BlogApp.jsx         # App avec useState
│   │
│   ├── 📂 reducers/            # Logique reducer
│   │   └── todoReducer.js      # Reducer de la Todo App
│   │
│   ├── 📂 styles/              # Fichiers CSS
│   │   ├── TodoApp.css
│   │   ├── ShoppingList.css
│   │   └── BlogApp.css
│   │
│   ├── 📂 utils/               # Fonctions utilitaires
│   │   └── localStorage.js
│   │
│   ├── App.jsx                 # Point d'entrée principal
│   ├── App.css
│   └── index.js
│
├── 📂 screenshots/             # Captures d'écran
├── package.json
├── README.md
└── .gitignore
```

### Architecture par application

#### Todo App (Reducer Pattern)

```
TodoApp
├── State (via useReducer)
├── Reducer (logique pure)
├── Actions (dispatchers)
└── Components (UI)
```

#### Shopping List (Effect Pattern)

```
ShoppingListApp
├── Multiple useState
├── useEffect (timer)
├── Cleanup logic
└── localStorage sync
```

#### Blog App (State Pattern)

```
BlogApp
├── Lazy initialization
├── Derived state
├── Complex updates
└── localStorage persistence
```

---

## 🎓 Guide d'utilisation

### 1. Todo App - Approche Reducer

```javascript
// 1. Définir l'état initial
const initialState = {
  todos: [],
  filter: 'all'
};

// 2. Créer le reducer
function todoReducer(state, action) {
  switch(action.type) {
    case 'ADD_TODO':
      return {
        ...state,
        todos: [...state.todos, {
          id: Date.now(),
          text: action.payload,
          completed: false
        }]
      };
    case 'TOGGLE_TODO':
      return {
        ...state,
        todos: state.todos.map(todo =>
          todo.id === action.payload
            ? { ...todo, completed: !todo.completed }
            : todo
        )
      };
    default:
      return state;
  }
}

// 3. Utiliser dans le composant
const [state, dispatch] = useReducer(todoReducer, initialState);
```

---

### 2. Shopping List - Approche Effect

```javascript
// Gestion du timer Pomodoro
const [minutes, setMinutes] = useState(25);
const [seconds, setSeconds] = useState(0);
const [isActive, setIsActive] = useState(false);

useEffect(() => {
  let interval;
  
  if (isActive) {
    interval = setInterval(() => {
      if (seconds === 0) {
        if (minutes === 0) {
          setIsActive(false);
          alert('Session terminée !');
        } else {
          setMinutes(m => m - 1);
          setSeconds(59);
        }
      } else {
        setSeconds(s => s - 1);
      }
    }, 1000);
  }
  
  // Cleanup crucial
  return () => clearInterval(interval);
}, [isActive, minutes, seconds]);
```

---

### 3. Blog App - Approche State

```javascript
// Lazy initialization
const [articles, setArticles] = useState(() => {
  const saved = localStorage.getItem('articles');
  return saved ? JSON.parse(saved) : [];
});

// Synchronisation automatique
useEffect(() => {
  localStorage.setItem('articles', JSON.stringify(articles));
}, [articles]);

// Update immutable
const handleLike = (id) => {
  setArticles(articles.map(article =>
    article.id === id
      ? { ...article, likes: article.likes + 1 }
      : article
  ));
};
```

---

## 🧠 Concepts React abordés

### 1. Immutabilité

**Principe** : Ne jamais modifier l'état directement

```javascript
// ❌ MAUVAIS
state.todos.push(newTodo);
setState(state);

// ✅ BON
setState({
  ...state,
  todos: [...state.todos, newTodo]
});
```

### 2. Dépendances useEffect

**Principe** : Déclarer toutes les dépendances utilisées

```javascript
// ⚠️ Risque de stale closure
useEffect(() => {
  console.log(count); // count peut être obsolète
}, []); // Dépendances manquantes

// ✅ Correct
useEffect(() => {
  console.log(count);
}, [count]); // Dépendance déclarée
```

### 3. Cleanup des effets

**Principe** : Toujours nettoyer les ressources

```javascript
useEffect(() => {
  const interval = setInterval(() => {
    // logique
  }, 1000);
  
  // Cleanup obligatoire
  return () => clearInterval(interval);
}, []);
```

### 4. Lazy Initialization

**Principe** : Initialiser l'état de manière paresseuse

```javascript
// ❌ Calculé à chaque render
const [data] = useState(expensiveComputation());

// ✅ Calculé une seule fois
const [data] = useState(() => expensiveComputation());
```

---

## 🎯 Quand utiliser quel hook ?

### Guide de décision

```
Ai-je besoin de gérer un état ?
│
├─ NON → Pas de hook nécessaire
│
└─ OUI → Continue
    │
    ├─ État simple (string, number, boolean) ?
    │   └─ OUI → useState
    │
    ├─ Plusieurs actions sur l'état ?
    │   └─ OUI → useReducer
    │
    └─ Synchronisation externe ?
        └─ OUI → useEffect
```

### Cas d'usage détaillés

| Scenario | Hook recommandé | Exemple |
|----------|----------------|---------|
| Toggle button | useState | `const [isOpen, setIsOpen] = useState(false)` |
| Form input | useState | `const [email, setEmail] = useState('')` |
| Todo list | useReducer | Actions: ADD, DELETE, TOGGLE |
| Fetch API | useEffect + useState | `useEffect(() => fetchData(), [])` |
| Timer | useEffect | Interval avec cleanup |
| localStorage | useEffect | Sync state ↔ storage |
| Complex form | useReducer | Validation, reset, submit |

---

## 📊 Comparaison synthétique

### Tableau récapitulatif

| Critère | useState | useReducer | useEffect |
|---------|----------|------------|-----------|
| **Simplicité** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
| **Scalabilité** | ⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| **Testabilité** | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| **Performance** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| **Learning curve** | Facile | Moyen | Moyen |
| **Use cases** | Nombreux | Spécifiques | Nombreux |

### Verdict final

- **Pour débuter** → useState
- **Pour structurer** → useReducer  
- **Pour synchroniser** → useEffect

**Tous les trois sont complémentaires et doivent être maîtrisés !**

---

## 📚 Ressources et documentation

### Documentation officielle

- 📘 [React Hooks](https://react.dev/reference/react) - Documentation complète
- 📗 [useState](https://react.dev/reference/react/useState) - API Reference
- 📕 [useReducer](https://react.dev/reference/react/useReducer) - API Reference
- 📙 [useEffect](https://react.dev/reference/react/useEffect) - API Reference

### Articles recommandés

- [When to use useReducer vs useState](https://react.dev/learn/extracting-state-logic-into-a-reducer)
- [Synchronizing with Effects](https://react.dev/learn/synchronizing-with-effects)
- [You Might Not Need an Effect](https://react.dev/learn/you-might-not-need-an-effect)

### Cours associé

📄 **Cours MERN - Semaine 7** : useState, useEffect & useReducer

---

## 🤝 Contribution

Les contributions sont encouragées ! Voici comment participer :

1. 🍴 Fork le projet
2. 🌿 Créez votre branche (`git checkout -b feature/NewFeature`)
3. ✍️ Commit vos changements (`git commit -m 'Add NewFeature'`)
4. 📤 Push vers la branche (`git push origin feature/NewFeature`)
5. 🔀 Ouvrez une Pull Request

---

## 👩‍💻 Auteur

**Imen BEN OTHMEN BANANI**

- 🎓 Étudiante en 4ème année Data Science
- 💻 Spécialisation : MERN Stack Development
- 📧 Email : [votre-email@exemple.com]
- 🔗 LinkedIn : [votre-profil]

---

## 📝 Licence

Ce projet est sous licence MIT. Consultez le fichier [LICENSE](LICENSE) pour plus de détails.

---

<div align="center">

### ⭐ Si ce projet vous aide, donnez-lui une étoile ! ⭐

**Made with ❤️ and ⚛️ React**

*"Master the hooks, master React."*

</div>
