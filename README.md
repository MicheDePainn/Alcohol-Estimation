# Simulateur d’Alcoolémie

Un petit outil front-end (HTML/CSS/JavaScript) permettant d’estimer rapidement votre taux d’alcoolémie en fonction de votre âge, de votre poids, de votre sexe et des boissons consommées, tout en tenant compte du temps écoulé depuis la consommation.

---

## 📝 Description

Ce simulateur calcule le taux d’alcoolémie (en g/L de sang) à un instant T à partir :
- De l’**âge** (ans)
- Du **poids** (kg)
- Du **sexe** (qui influence le coefficient de diffusion de Widmark)
- D’une liste de **boissons consommées** (type, quantité, volume, degré et heure de consommation)

Le calcul du taux d'alcoolémie instantané est basé sur la formule de Widmark, en prenant en compte la quantité d'alcool pur ingérée et son élimination progressive par l'organisme au fil du temps.
La masse d'alcool pur (en grammes) pour chaque boisson est calculée comme suit :
`Masse d'alcool (g) = Volume (mL) × (Degré d'alcool / 100) × Densité de l'éthanol (0.8) × Nombre d'unités`

L'alcool est ensuite éliminé par le corps à un taux approximatif (par exemple, 0.10 à 0.15 g/L/heure, ou une certaine quantité de grammes d'alcool pur par heure en fonction du poids). Le simulateur estime le taux restant en fonction de l'heure actuelle et de l'heure de consommation de chaque boisson.

Le simulateur affiche également :
- Un commentaire sur le niveau d'alcoolémie.
- Une estimation du temps nécessaire pour que le taux redescende sous un seuil pertinent (par exemple, 0.5 g/L).

---

## 🚀 Fonctionnalités

- **Saisie des informations utilisateur** : âge, poids, sexe.
- **Ajout dynamique** de plusieurs boissons avec détails : type, quantité, volume (ml), degré d'alcool (%), date et heure de consommation.
- **Préréglages** pour des boissons courantes (Bière, Vin, Spiritueux, etc.) remplissant automatiquement volume et degré, modifiables manuellement.
- **Calcul du taux d'alcoolémie estimé** en temps réel, en tenant compte de l'élimination de l'alcool depuis l'heure de consommation.
- **Validation des champs** pour assurer la cohérence des données.
- **Affichage coloré et descriptif du résultat** selon plusieurs niveaux d'alcoolémie (ex: faible, modéré, sévère, critique).
- **Estimation du temps de retour** à un taux inférieur à 0.5 g/L (ou 0.2 g/L si déjà en dessous).
- **Sauvegarde automatique des données** :
    - Les informations utilisateur (âge, poids, sexe) sont sauvegardées dans les cookies.
    - Les boissons consommées sont également sauvegardées dans les cookies.
    - Les données sont rechargées automatiquement à la prochaine visite.
- **Gestion des données** :
    - Bouton **➕ Ajouter** : pour une nouvelle consommation.
    - Bouton **🧮 Calculer** : pour obtenir l'estimation.
    - Bouton **🔄 Réinitialiser** : pour vider tous les champs du formulaire et supprimer les cookies de données utilisateur et de boissons.
    - Bouton **📤 Exporter JSON** : pour sauvegarder la liste des boissons consommées dans un fichier `consommations_alcool.json`.
    - Bouton **📥 Importer JSON** : pour charger une liste de boissons depuis un fichier JSON, remplaçant les boissons existantes (les données importées sont ensuite sauvegardées dans les cookies).
- **Avertissement initial** sur la nature estimative du calcul.

---

## 📁 Structure du projet

```bash
├── LICENSE
├── README.md
└── index.html
```
- **LICENSE** : licence MIT du projet.
- **README.md** : les informations sur ce projet.
- **index.html** : page unique contenant la structure HTML, le style CSS et le script JavaScript de l'application.

---

## 🔧 Installation

Aucun serveur ni étape de compilation n’est nécessaire pour utiliser ce simulateur.
1.  **Cloner** ou **télécharger** le dépôt :
    ```bash
    git clone [https://github.com/MicheDePainn/Alcohol-Estimation.git](https://github.com/MicheDePainn/Alcohol-Estimation.git)
    ```
2.  **Ouvrir** le fichier `index.html` directement dans votre navigateur web préféré (Chrome, Firefox, Safari, Edge, etc.).

Vous pouvez également héberger le fichier `index.html` sur n'importe quel service d'hébergement statique (GitHub Pages, Netlify, Vercel, etc.).

---

## 💻 Utilisation

1.  **Renseigner** votre âge, poids et sexe dans les champs prévus. Ces informations seront sauvegardées automatiquement.
2.  Pour chaque boisson consommée :
    a. Cliquer sur **➕ Ajouter** pour insérer une nouvelle ligne de boisson.
    b. Sélectionner le **Type** de boisson. Les champs "Volume" et "Degré" se rempliront avec des valeurs prédéfinies, mais vous pouvez les modifier.
    c. Ajuster la **Quantité**, le **Volume (ml)**, le **Degré (% vol.)** et la **Date & Heure** de consommation si nécessaire.
    d. Les modifications apportées aux boissons sont sauvegardées automatiquement.
3.  Répéter l'étape 2 pour chaque boisson consommée.
4.  Cliquer sur **🧮 Calculer** pour afficher votre taux d'alcoolémie estimé, un commentaire sur votre état et une estimation du temps pour revenir sous le seuil légal.
5.  Pour exporter vos consommations :
    - Cliquer sur **📤 Exporter JSON**. Un fichier `consommations_alcool.json` sera téléchargé.
6.  Pour importer des consommations :
    - Cliquer sur **📥 Importer JSON**.
    - Sélectionner un fichier JSON précédemment exporté par ce simulateur. Les boissons du fichier remplaceront celles affichées.
7.  Cliquer sur **🔄 Réinitialiser** pour effacer toutes les informations du formulaire (âge, poids, sexe, boissons) et supprimer les données sauvegardées dans les cookies. Une nouvelle boisson vide sera ajoutée par défaut.
8.  Vos données (informations personnelles et boissons) sont conservées dans les cookies de votre navigateur et seront rechargées lors de votre prochaine visite sur la page.

---

## 🤝 Contribution

Les contributions sont les bienvenues ! Si vous souhaitez améliorer ce simulateur :
1.  Faites un fork du projet.
2.  Créez une nouvelle branche pour votre fonctionnalité ou correction (`git checkout -b feature/ma-super-fonctionnalite`).
3.  Effectuez vos modifications et commitez-les (`git commit -m 'Ajout de ma-super-fonctionnalite'`).
4.  Pushez vos modifications vers votre branche (`git push origin feature/ma-super-fonctionnalite`).
5.  Ouvrez une Pull Request pour discussion et intégration.

---

## 📄 Licence

Ce projet est distribué sous la licence **MIT**.
Voir le fichier `LICENSE` pour plus de détails.