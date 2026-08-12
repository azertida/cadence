# Cadence

Un carnet qui compte **quand** on mange, pas ce qu'on mange.

Quatre cases par jour — matin, midi, une ancre en fin d'après-midi, soir. L'app ne pèse
rien, ne compte aucune calorie, et n'a rien à dire sur le contenu de l'assiette. Elle
affiche une seule chose : le nombre de fenêtres restées vides sur les six derniers jours,
et une bande de sept jours pour voir la forme du rythme.

D'où le nom : ce qui est mesuré ici est une régularité, pas un volume.

## Trois natures d'information, jamais mélangées

Sous les quatre cases, le reste de l'interface est rangé en trois groupes qui ne se
parlent pas — aucune addition, aucun solde, aucun score.

**Ce qui brouille la balance** (repas salé, restaurant, chaleur) n'aggrave rien : ces
étiquettes signalent que le corps retient de l'eau et que le chiffre du pèse-personne est
illisible pendant quarante-huit heures. Ce sont des avertissements de lecture, pas des
fautes.

**Ce qui a été dépensé** (padel, aquagym, 8000 pas) est le seul groupe de facteurs au sens
propre. Formulé en plein : cocher veut dire « j'ai bougé », jamais l'inverse.

**Le soir a rattrapé** n'est ni l'un ni l'autre — c'est une conséquence, ce qui arrive
quand les fenêtres de la journée sont restées vides. Il vit donc à côté des repas, pas
dans le contexte, et se lit comme un constat.

Rien de tout cela ne produit de note. Pas de récompense, qui pousse à l'excès ; pas de
punition, qui pousse à mentir au carnet. Les étiquettes servent à comprendre une bande
bizarre après coup, pas à juger la journée.

## Où vont les données

Elles ne vont nulle part. Tout est écrit dans le stockage local de votre navigateur
(`localStorage`, clé `carnet_fenetres_v1`). Pas de compte, pas de serveur, pas de
statistiques, pas de mouchard. Aucun appel réseau, à aucun moment : les polices sont
embarquées dans le fichier, il n'y a pas une seule requête vers un tiers. Personne —
y compris l'auteure — ne peut voir ce que vous cochez.

La contrepartie est réelle : effacer les données du site, changer de navigateur ou
réinitialiser l'appareil efface le carnet. Le bouton **Exporter (JSON)** produit un
fichier de sauvegarde ; **Importer** le relit. Faites-le avant toute manipulation
d'appareil.

## Installation

Ouvrez la page, puis ajoutez-la à l'écran d'accueil.

- **iPhone / iPad (Safari)** — bouton Partager, puis « Sur l'écran d'accueil »
- **Android (Chrome)** — menu ⋮, puis « Installer l'application »

Installée, elle fonctionne hors ligne et échappe à l'effacement automatique des données
de site après sept jours d'inactivité sur iOS.

## Ce que ce carnet n'est pas

C'est une méthode personnelle, née d'une situation personnelle : dans mon cas, le levier
n'était pas la quantité mais la répartition — d'où l'ancre de fin d'après-midi, qui existe
pour que le soir n'ait rien à rattraper. Rien ne garantit que cette logique s'applique à
quelqu'un d'autre.

Ce n'est ni un outil médical, ni un conseil nutritionnel, ni un dispositif de suivi de
poids. Si votre rapport à l'alimentation vous inquiète, un professionnel de santé vous
sera plus utile qu'une grille de quatre cases.

## Réutilisation

Le code est court et volontairement lisible. Tout ce qui se règle est déclaré en haut du
`<script>` : `MEALS` (les fenêtres et l'horaire de l'ancre), `BROUILLEURS` et `DEPENSE`
(les deux groupes d'étiquettes), `OBS` (l'observation du soir). C'est là qu'on adapte
l'app à un autre rythme que le mien. Les commentaires sont en français.

## Fichiers

| Fichier | Rôle |
|---|---|
| `index.html` | l'application entière, polices comprises |
| `manifest.json` | métadonnées d'installation |
| `sw.js` | service worker (hors ligne) — incrémenter `VERSION` à chaque mise à jour |
| `icon-192.png`, `icon-512.png` | icônes du manifeste |
| `icon-512-maskable.png` | icône adaptative Android |
| `icon.png` | `apple-touch-icon`, 180×180 opaque |

## Licence

MIT — voir [LICENSE](LICENSE). Faites-en ce que vous voulez.
