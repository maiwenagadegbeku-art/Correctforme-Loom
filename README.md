# CorrectForme Loom

**Assistant de correction · English LV1**

CorrectForme Loom est un outil standalone HTML qui aide les enseignants d'anglais LV1 à corriger des copies d'élèves en s'appuyant sur l'IA. Il s'intègre avec les grilles CECRL exportées depuis [Lesson Loom](https://lessonloom.fr) et produit des fiches de retour pré-remplies, des PDF distribuables et un CSV de suivi.

Fait partie de la **Loom Suite** aux côtés de Lesson Loom, QuizLoom et WordSmith Profs.

---

## Fonctionnalités

### Import de grille Lesson Loom
- Drag & drop du fichier HTML de distribution généré par Lesson Loom
- Extraction automatique de la grille CECRL (compétences, paliers, barème) et des noms d'élèves
- Aucune ressaisie nécessaire

### Deux modes de correction

**✂️ Sans clé API — Copier · Coller · Gratuit**

1. Sélectionner un élève ayant une copie scannée
2. Cliquer "Générer le prompt" → le prompt est prêt à copier
3. Ouvrir Claude.ai, coller le prompt, joindre la ou les images de la copie
4. Copier la réponse de Claude.ai et la coller dans CorrectForme
5. La correction s'affiche, passer à l'élève suivant

Idéal pour toutes les collègues : zéro installation, zéro coût.

**⚡ Batch automatique — Clé API Anthropic**

1. Saisir sa clé API une seule fois (sauvegardée dans le navigateur)
2. Associer les copies scannées aux élèves
3. Cliquer "Corriger le lot automatiquement"
4. Les copies se corrigent automatiquement avec barre de progression
5. Tableau récapitulatif + exports en une fois

Coût estimé : environ 5 € par an pour 170 élèves × 10 devoirs. Un guide intégré explique comment obtenir une clé en 3 étapes.

### PDF Scanner intégré
- Import d'un PDF multi-pages depuis le scanner/photocopieuse du lycée
- Découpage automatique page par page avec miniatures
- Association de chaque page à un élève via menu déroulant
- **Une copie peut compter plusieurs pages** : attribuez-en autant que nécessaire au même élève, elles partent ensemble et dans l'ordre du PDF. Le compteur du haut annonce le total (« 12 copies · 28 pages »), et chaque case affiche ses pages numérotées, retirables une par une.

**Un devoir tapé sur ordinateur ?** Enregistrez-le en PDF depuis Word ou LibreOffice, puis passez-le par le PDF Scanner : chaque page devient une image exploitable. Le champ « Ajouter scan » n'accepte que des images — un PDF ou un document texte déposé directement ne serait pas lu.

### Résultats structurés
- Tableau des **erreurs récurrentes** : catégorie (grammaire, vocabulaire, orthographe…), exemple dans la copie, correction
- Tableau des **points positifs** : catégorie, observation
- **Appréciation** personnalisée en français ou anglais, dans le style de l'enseignant
- Appréciation **éditable** directement dans l'interface avant export

### Exports

**📋 Grille Lesson Loom pré-remplie** — Fichier HTML de distribution avec les cases CECRL remplies par l'IA + bloc appréciation stylé sous la grille. À ouvrir, vérifier, ajuster et imprimer.

**PDF par élève** — Fiche propre à distribuer : note, CECRL observé, grille, tableau erreurs/positifs, appréciation. Sans mention technique ni footer IA.

**CSV de suivi** — Une ligne par élève : nom, classe, note, CECRL, erreurs récurrentes, points positifs, appréciation. Pour le suivi annuel.

### Paramétrage
- Niveau : Seconde, Première, Terminale, Autre (BTS, collège…)
- Type de tâche : PE, CO, CE, Interaction écrite, Traduction
- Niveau CECRL cible : A2 à C1+
- Consigne / sujet (optionnel)
- Style de bilan : coller ses propres exemples ou utiliser le style par défaut
- Langue du bilan : français ou anglais

### Principes pédagogiques
- L'IA ne retranscrit pas la copie annotée — elle produit un tableau d'erreurs que l'élève utilise pour relire et corriger sa propre copie
- Les appréciations tutoient l'élève directement ("tu avances", "relis-toi")
- Le ton est direct et sympa, pas "bienveillant corporate"
- La notation s'appuie strictement sur le barème de la grille CECRL importée
- L'enseignant garde la main : tout est vérifiable et modifiable avant distribution

---

## Utilisation

1. Ouvrir `correctforme-loom.html` dans un navigateur (Chrome, Firefox, Edge)
2. Importer un fichier de distribution Lesson Loom (HTML)
3. Régler les paramètres de correction
4. Associer les copies scannées (JPEG/PNG) aux élèves — soit une par une, soit via le PDF scanner. Une copie peut compter plusieurs pages.
5. Choisir le mode de correction (sans clé ou batch)
6. Vérifier et ajuster les résultats
7. Exporter : grille LL pré-remplie, PDF par élève, ou CSV de suivi

Aucun serveur à installer, aucun compte à créer : le fichier s'ouvre directement dans votre navigateur, et vos réglages y restent.

> ### ⚠️ Où vont les copies
>
> **Le contenu des copies est envoyé à un service d'IA extérieur pour être analysé** — dans les deux modes. En mode sans clé, c'est vous qui collez le texte et joignez les images dans Claude.ai : vous voyez exactement ce qui part, et vous pouvez le modifier avant. En mode batch, l'outil les envoie lui-même.
>
> **Retirez les noms de famille avant de scanner**, ou n'utilisez que les prénoms. Les copies elles-mêmes ne sont conservées nulle part par l'outil, mais elles transitent bien hors de votre ordinateur.

---

## Formats acceptés

| Entrée | Formats |
|---|---|
| Grille | HTML de distribution Lesson Loom |
| Copies scannées | JPEG, PNG, WebP |
| PDF scanner | PDF multi-pages (converti en JPEG par page via pdf.js) |

| Sortie | Formats |
|---|---|
| Grille pré-remplie | HTML Lesson Loom |
| Fiche élève | PDF (jsPDF) |
| Suivi classe | CSV (séparateur `;`, UTF-8 BOM) |

---

## Prérequis

- Un navigateur moderne (Chrome 90+, Firefox 90+, Edge 90+)
- Pour le mode sans clé : un compte Claude.ai (gratuit)
- Pour le mode batch : une clé API Anthropic (console.anthropic.com, ~5 €/an)
- Lesson Loom pour générer les fichiers de distribution avec grille et noms d'élèves

---

## Stack technique

- HTML/CSS/JS standalone — aucune dépendance serveur
- Polices : Inter (Google Fonts)
- Palette : Lesson Loom (violet `#6c5ce7` / vert `#00b894`)
- pdf.js 3.11.174 — extraction des pages PDF en canvas
- jsPDF 2.5.1 — génération des PDF par élève
- html2canvas 1.4.1 — capture des grilles pour l'export
- API Anthropic (Claude Sonnet) — correction IA (mode batch uniquement)
- Dark mode intégré

---

## Licence

AGPLv3 — © Maïwena Gadegbeku

Ce logiciel est distribué sous licence [GNU Affero General Public License v3.0](https://www.gnu.org/licenses/agpl-3.0.html). Vous êtes libre de le copier, le modifier et le redistribuer sous les mêmes termes.

---

## Loom Suite

| Outil | Description |
|---|---|
| **Lesson Loom** | Planification pédagogique (séquences, séances, calendrier, grilles, export RTF/PDF) |
| **QuizLoom** | Générateur de QCM Pronote depuis des séances Lesson Loom |
| **WordSmith Profs** | Générateur d'appréciations de bulletins LV1 |
| **CorrectForme Loom** | Assistant de correction de copies avec IA |
