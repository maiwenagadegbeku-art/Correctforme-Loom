# CorrectForme Loom

**Assistant de correction · English LV1**

CorrectForme Loom est un outil standalone HTML qui aide les enseignants d'anglais LV1 à corriger des copies d'élèves en s'appuyant sur l'IA. Il s'intègre avec les grilles CECRL exportées depuis [Lesson Loom](https://lessonloom.fr) et produit des fiches de retour pré-remplies, des PDF distribuables et un CSV de suivi.

Fait partie de la **Lesson Loom Suite** aux côtés de Lesson Loom, QuizLoom, WordSmith Profs et The Loom Arcade.

---

## Fonctionnalités

### Import de grille Lesson Loom
- Drag & drop du fichier HTML de distribution généré par Lesson Loom
- Extraction automatique de la grille CECRL (compétences, paliers, barème) et des noms d'élèves
- Aucune ressaisie nécessaire

### Une note calculée à partir de vos paliers
- L'IA situe la copie sur chaque compétence de la grille, en choisissant l'un de ses paliers (A2+/B1, Niveau 2…)
- **CorrectForme calcule la note** à partir de ces paliers, avec les points de la grille et la même règle que Lesson Loom
- Mêmes paliers, même note, partout : écran, PDF, CSV et grille Lesson Loom pré-remplie
- « à calculer » s'affiche quand le calcul est impossible (palier non reconnu, grille sans points par niveau) : jamais de note inventée

### Deux modes de correction

**✂️ Sans clé API — Copier · Coller · Gratuit**

1. Sélectionner un élève ayant une copie (photos, scans ou pages du PDF Scanner)
2. Cliquer "Générer le prompt" → le prompt est prêt à copier
3. Ouvrir l'IA de son choix (Claude est proposé : le prompt a été testé avec lui), coller le prompt et joindre les pages de la copie — le bouton « ⬇ Pages de la copie » les réunit en un seul PDF
4. Copier la réponse et la coller dans CorrectForme
5. La correction s'affiche, passer à l'élève suivant

Idéal pour toutes les collègues : zéro installation, zéro coût.

**⚡ Batch automatique — Clé API Anthropic**

1. Saisir sa clé API une seule fois (sauvegardée dans le navigateur)
2. Associer les copies scannées aux élèves
3. Cliquer "Corriger le lot automatiquement"
4. Les copies se corrigent automatiquement avec barre de progression
5. Tableau récapitulatif + exports en une fois
6. Une copie qui n'a pas pu être analysée — connexion coupée, clé refusée, aucune réponse au bout de trois minutes — est signalée **« Échec technique »**, avec sa cause en clair, et comptée à part dans le bilan. Une réponse inutilisable de l'IA (refus, réponse coupée) est marquée **« À reprendre »** : rien n'est exporté tant qu'elle n'est pas relancée. Une copie sans aucune page lisible n'est pas envoyée.

Coût : la clé API est un service payant d'Anthropic, réglé directement auprès d'Anthropic et à l'usage — l'autrice de l'outil ne touche rien. Comptez environ 3 à 5 centimes par copie, soit 1 à 2 € pour une classe de 35 (l'estimation de 5 € par an donnée jusqu'ici était trop basse). Un guide intégré explique comment obtenir une clé ; 5 € de crédit suffisent pour une centaine de copies.

### PDF Scanner intégré
- Import d'un PDF multi-pages depuis le scanner/photocopieuse du lycée
- Découpage automatique page par page avec miniatures
- Association de chaque page à un élève via menu déroulant
- **Une copie peut compter plusieurs pages** : attribuez-en autant que nécessaire au même élève, elles partent ensemble et dans l'ordre du PDF. Le compteur du haut annonce le total (« 12 copies · 28 pages »), et chaque case affiche ses pages numérotées, retirables une par une.

**Un devoir tapé sur ordinateur ?** Enregistrez-le en PDF depuis Word ou LibreOffice, puis passez-le par le PDF Scanner : chaque page devient une image exploitable. Le champ « Ajouter scan » n'accepte que des images : un PDF ou un document texte déposé directement est refusé, avec un message qui renvoie au PDF Scanner.

### Résultats structurés et modifiables
- Tableau des **erreurs récurrentes** : jusqu'à 8, de la plus fréquente à la moins fréquente, avec leur nombre d'occurrences (« Grammaire ×3 »), un exemple dans la copie et sa correction
- Tableau des **points positifs** : catégorie, observation
- **Appréciation** personnalisée en français ou anglais, sans note chiffrée
- **Tout se modifie avant export** : un clic sur une case change le palier, les points de la case choisie s'ajustent (4 au lieu de 5), les erreurs, points positifs et appréciation se réécrivent ; la note se recalcule aussitôt

### Pour la classe
- **📋 Grille LL de la classe** : un seul fichier Lesson Loom pour toute la liste, élèves corrigés pré-remplis, autres à remplir à la main
- **📊 Bilan de classe** : paliers par compétence, erreurs les plus fréquentes (par catégorie, ou par thèmes de remédiation regroupés par l'IA avec une clé API), points forts, notes, élèves à accompagner, PDF d'une page avec ou sans les noms

### Exports

**📋 Grille Lesson Loom pré-remplie** — Fichier HTML de distribution avec les cases remplies à partir des paliers retenus et de vos ajustements, + bloc appréciation sous la grille. Chaque export a ses propres notes : rouvrir garde les retouches, regénérer reprend les paliers et garde le bonus. Existe aussi pour toute la classe en un fichier.

**PDF par élève** — Fiche propre à distribuer : note, CECRL observé, paliers (points en discret), erreurs, points positifs, appréciation. Tout se lit en entier, aucune section n'est coupée, une page le plus souvent. En mode entraînement : paliers seuls, sans note ni points. Sans mention technique ni footer IA.

**CSV de suivi** — Une ligne par élève : nom, classe, note, CECRL, erreurs récurrentes, points positifs, appréciation. Pour le suivi annuel.

### Paramétrage
- Niveau : Seconde, Première, Terminale, Autre (BTS, collège…)
- Type de tâche : PE, CO, CE, Interaction écrite, Traduction
- Niveau CECRL cible : A2 à C1+ (sert à situer l'élève dans l'appréciation)
- **Entraînement (sans note)** : retour avec paliers, erreurs et appréciation, sans aucun point ; basculable après la correction
- Consigne / sujet (optionnel)
- Style de bilan : coller 2 ou 3 de ses propres appréciations (gardées dans le navigateur) ou utiliser le style par défaut ; l'IA s'inspire du registre sans recopier les phrases
- Langue du bilan : français ou anglais

### Principes pédagogiques
- L'IA ne retranscrit pas la copie annotée — elle produit un tableau d'erreurs que l'élève utilise pour relire et corriger sa propre copie
- Les appréciations tutoient l'élève directement ("tu avances", "relis-toi")
- Le ton est direct et sympa, pas "bienveillant corporate"
- L'IA choisit les paliers d'après les descripteurs de la grille ; l'appli calcule la note avec le barème de la grille
- L'enseignant garde la main : tout est vérifiable et modifiable avant distribution

---

## Utilisation

1. Ouvrir `correctforme-loom.html` dans un navigateur (Chrome, Firefox, Edge)
2. Importer un fichier de distribution Lesson Loom (HTML)
3. Régler les paramètres de correction
4. Associer les copies scannées (JPEG/PNG) aux élèves — soit une par une, soit via le PDF scanner. Une copie peut compter plusieurs pages.
5. Choisir le mode de correction (sans clé ou batch)
6. Vérifier et ajuster les résultats : paliers, points, erreurs, appréciation
7. Exporter : grille LL pré-remplie (par élève ou pour la classe), PDF par élève, CSV de suivi, bilan de classe

Aucun serveur à installer, aucun compte à créer : le fichier s'ouvre directement dans votre navigateur, et vos réglages y restent.

> ### ⚠️ Où vont les copies
>
> **Le contenu des copies est envoyé à un service d'IA extérieur pour être analysé** — dans les deux modes. En mode sans clé, c'est vous qui collez le texte et joignez les pages dans l'IA de votre choix : vous voyez exactement ce qui part, et vous pouvez le modifier avant. En mode batch, l'outil les envoie lui-même à l'API Anthropic. Pour les thèmes du bilan de classe, l'IA reçoit les erreurs relevées avec des numéros d'élèves, jamais les noms.
>
> **Retirez les noms de famille avant de scanner**, ou n'utilisez que les prénoms. Les copies elles-mêmes ne sont conservées nulle part par l'outil, mais elles transitent bien hors de votre ordinateur.

---

## Formats acceptés

| Entrée | Formats |
|---|---|
| Grille | HTML de distribution Lesson Loom |
| Copies scannées | Images : JPEG, PNG, WebP (tout format d'image lu par le navigateur) |
| PDF scanner | PDF multi-pages (converti en JPEG par page via pdf.js) |

| Sortie | Formats |
|---|---|
| Grille pré-remplie | HTML Lesson Loom |
| Fiche élève | PDF (jsPDF) |
| Pages de la copie (mode sans clé) | PDF (jsPDF) |
| Bilan de classe | PDF (jsPDF) |
| Suivi classe | CSV (séparateur `;`, UTF-8 BOM) |

---

## Prérequis

- Un navigateur moderne (Chrome 90+, Firefox 90+, Edge 90+)
- Pour le mode sans clé : un compte gratuit chez un assistant IA (Claude.ai est proposé)
- Pour le mode batch : une clé API Anthropic (console.anthropic.com), environ 3 à 5 centimes par copie
- Lesson Loom pour générer les fichiers de distribution avec grille et noms d'élèves

---

## Stack technique

- HTML/CSS/JS standalone — aucun serveur à installer
- **Une connexion Internet est nécessaire** : la police et les outils PDF sont chargés
  depuis des services externes à l'ouverture. Sans connexion, l'application s'affiche
  et la correction en mode sans clé reste possible, mais le PDF Scanner et l'export
  PDF par élève ne fonctionnent pas
- Polices : Inter (Google Fonts)
- Palette : Lesson Loom (violet `#6c5ce7` / vert `#00b894`)
- pdf.js 3.11.174 — extraction des pages PDF en canvas
- jsPDF 2.5.1 — génération des PDF par élève
- API Anthropic (Claude Sonnet 5.5) — correction IA et thèmes du bilan (mode batch uniquement)
- Dark mode intégré

---

## Limites connues

À garder en tête :

- Les paliers et le niveau CECRL observé sont choisis par l'IA : **relisez-les toujours**
  avant de distribuer une fiche à un élève ; la note en découle
- Sur une copie entre deux paliers, le choix peut varier d'une correction à l'autre,
  ou selon le niveau visé, comme entre deux correcteurs différents : un clic suffit à trancher
- Les résultats ne sont pas conservés si la page est rechargée : téléchargez les PDF,
  les grilles et le bilan avant de fermer

---

## Licence

AGPLv3 — © Maïwena Gadegbeku

Ce logiciel est distribué sous licence [GNU Affero General Public License v3.0](https://www.gnu.org/licenses/agpl-3.0.html). Vous êtes libre de le copier, le modifier et le redistribuer sous les mêmes termes.

**Crédit obligatoire.** Le fichier [LICENSE](LICENSE) porte une condition
supplémentaire, au titre de l'article 7(b) de l'AGPLv3 : toute version modifiée
diffusée publiquement ou mise à disposition sur un serveur doit créditer
visiblement l'autrice originale, dans son interface ou dans sa documentation. Ce
crédit ne peut être ni retiré, ni dissimulé aux utilisateurs.

---

## Lesson Loom Suite

| Outil | Description |
|---|---|
| **Lesson Loom** | Planification pédagogique (séquences, séances, calendrier, grilles, export RTF/PDF) |
| **QuizLoom** | Générateur de QCM Pronote depuis des séances Lesson Loom |
| **WordSmith Profs** | Générateur d'appréciations de bulletins LV1 |
| **CorrectForme Loom** | Assistant de correction de copies avec IA |
| **The Loom Arcade** | Dix jeux de vocabulaire pour les élèves, à partir d'une liste de mots |
