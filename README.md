# Correctforme Loom
CorrectForme Loom

Assistant de correction pour professeurs de langues, pensé pour Lesson Loom.

CorrectForme Loom transforme la correction de copies en un flux simple : tu importes tes copies scannées et ta grille d'évaluation, l'IA analyse les productions, et tu récupères des grilles CECRL pré-remplies ainsi que des fiches de feedback individuelles prêtes à distribuer.

C'est une application web en fichier HTML unique, qui tourne entièrement dans ton navigateur. Pas d'installation, pas de compte, pas de serveur.

Ce qu'il fait
Importe une distribution Lesson Loom : la grille CECRL et la liste des élèves sont récupérées automatiquement depuis le fichier exporté.
Découpe un PDF de scan : un PDF multi-pages issu du scanner est séparé en une page par élève, prête à être analysée.
Corrige de deux façons :
Mode manuel — tu copies-colles dans Claude.ai (gratuit).
Mode automatique — correction par lot via une clé API Anthropic (quelques euros par an).
Produit un feedback structuré : tableau d'erreurs et points positifs, en s'adressant directement à l'élève.
Exporte :
une grille Lesson Loom pré-remplie,
une fiche de feedback par élève en PDF,
un fichier CSV de suivi.
Utilisation
Télécharge le fichier correctforme-loom.html.
Ouvre-le dans ton navigateur (double-clic).
Importe ta distribution Lesson Loom, puis tes copies scannées.
Choisis ton mode de correction (manuel ou automatique).
Vérifie, ajuste, puis exporte les grilles et les fiches de feedback.

Confidentialité — En mode manuel, aucune donnée ne quitte ton navigateur. En mode automatique, seules les copies à corriger sont envoyées à l'API Anthropic pour l'analyse ; la clé API reste stockée localement dans ton navigateur.

Bibliothèques tierces

CorrectForme Loom charge depuis un CDN (elles ne sont pas redistribuées ici) :

pdf.js — licence Apache 2.0
jsPDF — licence MIT
html2canvas — licence MIT
Licence

Ce projet est distribué sous licence GNU Affero General Public License v3.0 (AGPLv3).

Tu es libre de l'utiliser, de l'étudier, de le modifier et de le redistribuer, à condition que tout dérivé — y compris s'il est proposé comme service en ligne — reste sous la même licence. Voir le fichier LICENSE pour le texte complet.

Soutenir le projet

CorrectForme Loom fait partie de la suite Lesson Loom, une collection d'outils gratuits pour les professeurs de langues.

Si ces outils te sont utiles, tu peux m'offrir un café ☕ : buymeacoffee.com/maiwena.gadegbeku

Créé par Maïwena Gadegbeku.
