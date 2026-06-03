# CONZANOV 🚄☭

> *Le camarade contrôleur ne s'arrête jamais.*

Jeu de course infinie en **pixel art**, façon Flappy Bird, sur le thème d'une
affiche de propagande soviétique. Tu incarnes **Conzanov**, un contrôleur SNCF
bien dodu qui court sur les rails, saute par-dessus hérissons et caravanes,
ramasse des fagots de cuivre pour récupérer des cœurs — pendant que le train
accélère et que le paysage se transforme de zone en zone.

---

## ▶️ Jouer

Le plus simple : **ouvrir `conzanov-jeu.html`** dans n'importe quel navigateur
(double-clic). C'est un fichier unique et autonome, sans installation ni
connexion : il fonctionne sur ordinateur comme sur téléphone, et même hors ligne.

---

## 🎮 Commandes

| Plateforme | Action | Touche / Geste |
|-----------|--------|----------------|
| **Ordinateur** | Sauter | **Espace** (ou clic souris) |
| **Mobile / tablette** | Sauter | **Toucher l'écran** |
| **Menus** | Démarrer / Recommencer | Espace, clic, ou bouton |

Chaque appui = un saut immédiat. En l'air, tu peux appuyer **2 fois de plus**
pour un **triple saut** (idéal pour franchir une caravane ou attraper un fagot
en hauteur).

---

## 📜 Règles

- Tu as **3 vies** (❤️). Chaque obstacle touché en coûte une.
- 🦔 **Hérissons** — obstacles au sol, à sauter. Certains **bondissent en l'air** :
  passe dessous quand ils sont hauts, ou esquive entre deux de leurs bonds.
- 🚐 **Caravanes** — obstacles hauts et larges, demandent un grand saut.
- 🟧 **Fagot de cuivre** — flotte en l'air ; l'attraper **redonne un cœur**
  (il n'apparaît que si tu as perdu une vie).
- Plus tu enchaînes d'obstacles franchis, plus ton **combo** et ton score montent.
- Le train **démarre lentement** puis **accélère à chaque niveau**, et de
  nouveaux **patterns d'obstacles** se débloquent au fil de la partie.

---

## 🌍 Le monde qui évolue

Tous les ~1500 points, tu changes de niveau, et le **paysage se métamorphose**
progressivement à travers 5 zones :

1. **Banlieue rouge** — crépuscule, drapeaux et cheminées
2. **Plaines de blé** — ciel bleu, champs dorés
3. **Cité industrielle** — ambiance enfumée
4. **Steppe enneigée** — neige qui tombe
5. **Nuit des soviets** — ciel étoilé

Les couleurs du ciel, des montagnes, de la ville et du sol se fondent en douceur
d'une zone à l'autre.

---

## ✨ Fonctionnalités

- Pixel art entièrement dessiné au code (aucune image externe).
- Personnage animé : il court vraiment, jambes et bras en mouvement, pieds au sol.
- Gameplay nerveux façon Flappy Bird + triple saut.
- Démarrage doux et accélération progressive par niveaux.
- Patterns d'obstacles de plus en plus complexes + hérissons sauteurs.
- Décor multi-couches en parallaxe, météo, soleil de propagande, drapeaux.
- 5 zones de paysage qui défilent et se fondent entre elles.
- Système de vies, combos, score, et bonus de cuivre.
- Effets : particules, tremblement d'écran, flash, squash & stretch.
- **Affichage responsive** : la zone de jeu s'adapte au format de l'écran
  (large en paysage sur ordinateur, vertical sur mobile).
- Règles affichées sur l'écran d'accueil **et** sur l'écran de fin.

---

## 🗂️ Structure du projet

Le jeu existe sous deux formes :

- **`conzanov-jeu.html`** — version compilée en un seul fichier, prête à jouer.
- **Projet source multi-fichiers** — pour lire et modifier le code proprement :

```
conzanov/
├── conzanov-jeu.html   ← version autonome (pour jouer)
├── index.html          page + interface (HUD, overlay, règles)
├── style.css           styles (typo propagande, HUD, overlay)
├── README.md           ce fichier
└── js/
    ├── config.js       constantes globales + zones + dimensions adaptatives
    ├── utils.js        helpers : dessin pixel, lignes, couleurs, particules
    ├── background.js   décor parallaxe + météo + sol/rails
    ├── player.js       Conzanov : rendu, course, sauts
    ├── obstacles.js    hérissons (dont sauteurs), caravanes, fagots
    ├── game.js         moteur : boucle, niveaux, patterns, collisions, score
    └── main.js         point d'entrée : DOM, contrôles, responsive
```

> ℹ️ Le projet multi-fichiers se lance idéalement via un petit serveur local
> (les navigateurs bloquent souvent le chargement de plusieurs fichiers en
> `file://`). Par exemple, depuis le dossier :
> ```
> python3 -m http.server
> ```
> puis ouvre l'adresse affichée. Pour juste jouer, `conzanov-jeu.html` suffit.

---

## 🔧 Personnaliser

Tout se règle dans **`js/config.js`** :

| Réglage | Variable | Effet |
|---------|----------|-------|
| Vitesse de départ | `SPEED_START` | Lenteur du début de partie |
| Accélération | `SPEED_PER_LEVEL` | Gain de vitesse par niveau |
| Durée d'un niveau | `LEVEL_DIST` | Points avant de changer de niveau / zone |
| Force des sauts | `JUMP`, `DBL_JUMP`, `TRIPLE_JUMP` | Hauteur de chaque saut |
| Nombre de sauts | `MAX_JUMPS` | Sauts enchaînables (3 = triple saut) |
| Gravité | `GRAV` | Plus bas = vol plus flottant |
| Taille des obstacles | `HEDGEHOG`, `CARAVAN`, `FAGOT` | Dimensions |
| Paysages | tableau `ZONES` | Couleurs, météo, niveau de déclenchement |

- Les **patterns d'obstacles** se modifient dans `js/game.js` (`_queuePattern`).
- L'**apparence du personnage** se trouve dans `js/player.js` (`draw`).

> Après avoir modifié les fichiers source, régénère `conzanov-jeu.html` en
> recollant le CSS et les scripts dans `index.html`, ou continue simplement à
> travailler avec le projet multi-fichiers.

---

## 🎨 Crédits

Jeu conçu sur mesure, personnage inspiré d'un véritable contrôleur SNCF.
Tout le pixel art, le décor et les animations sont générés par le code, sans
ressource externe (hormis les polices Google *Press Start 2P* et *Oswald*).

*Bon voyage, camarade !* ☭
