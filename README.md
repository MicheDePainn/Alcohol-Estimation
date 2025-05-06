# Simulateur d’Alcoolémie

Un petit outil front-end (HTML/CSS/JavaScript) permettant d’estimer rapidement votre taux d’alcoolémie en fonction de votre âge, de votre poids, de votre sexe et des boissons consommées.

---

## 📝 Description

Ce simulateur calcule le taux d’alcoolémie (en g/L) à partir :
- De l’**âge** (ans)
- Du **poids** (kg)
- Du **sexe** (facteur de diffusion)
- D’une liste de **boissons consommées** (type, quantité, volume et degré)

Le calcul utilise la formule :
```
Taux (g/L) = (Masse d’alcool absorbée en grammes) / (Poids × Coefficient de diffusion)
```
où la masse d’alcool est obtenue par  
_Masse = volume (mL) × degré (%) / 100 × 0,8 (densité de l’alcool) × nombre d’unités_

Le simulateur affiche en plus un commentaire selon le niveau d’ivresse et la tranche d’âge.

---

## 🚀 Fonctionnalités

- **Ajout dynamique** de plusieurs boissons  
- **Préréglages** pour : Bière, Vin rouge/blanc, Champagne, Cidre, Whisky, Vodka, Rhum, Tequila, Pastis, Liqueur, Cocktail, Autre  
- Validation des champs (âge, poids, sexe, quantité, volume, degré)  
- Affichage coloré du résultat selon quatre niveaux :  
  - Légers (vert)  
  - Ivresse modérée (jaune)  
  - Ivresse sévère (rouge)  
  - Danger (rouge foncé)  
- Message d’alerte si le taux dépasse la limite légale de 0,5 g/L pour la conduite  
- Boutons “Ajouter”, “Calculer” et “Réinitialiser”  

---

## 📁 Structure du projet

```
├── LICENSE
└── index.html
```

- **index.html** : page unique contenant la structure HTML, le style CSS et le script JavaScript.  
- **LICENSE** : licence MIT.

---

## 🔧 Installation

Aucun serveur ni compilation n’est nécessaire.  
1. **Cloner** ou **télécharger** le dépôt :  
   ```bash
   git clone https://github.com/MicheDePainn/Alcohol-Estimation.git
   ```
2. **Ouvrir** le fichier `index.html` dans votre navigateur.

Vous pouvez aussi héberger le répertoire sur GitHub Pages, Netlify, Vercel ou tout autre hébergeur statique.

---

## 💻 Utilisation

1. **Renseigner** votre âge, poids et sexe.  
2. Cliquer sur **➕ Ajouter** pour insérer une nouvelle boisson.  
3. Sélectionner le type de boisson (les presets remplissent automatiquement le volume et le degré, modifiables à la main).  
4. Indiquer le nombre d’unités consommées.  
5. Répéter l’opération pour chaque boisson.  
6. Cliquer sur **🧮 Calculer** pour afficher votre taux et un commentaire.  
7. Cliquer sur **🔄 Réinitialiser** pour vider le formulaire.

---

## 🤝 Contribution

Les contributions sont les bienvenues !  
1. Faites un fork du projet  
2. Créez une branche (`git checkout -b feature/ma-fonctionnalite`)  
3. Commitez vos changements (`git commit -m 'Ajout d’une nouvelle boisson'`)  
4. Pushez vers la branche (`git push origin feature/ma-fonctionnalite`)  
5. Ouvrez une Pull Request

---

## 📄 Licence

Ce projet est sous licence **MIT**.  
Voir le fichier [LICENSE](LICENSE) pour plus de détails.
