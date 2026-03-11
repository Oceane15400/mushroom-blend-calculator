# Mushroom Blend Calculator

# Mushroom Blend Calculator

Un outil JavaScript puissant pour calculer les proportions optimales de champignons adaptogènes dans les mélanges de café. Conçu pour les producteurs et formulateurs souhaitant créer des blends équilibrés avec les bonnes concentrations de principes actifs selon les objectifs santé visés.

## Description

Mushroom Blend Calculator simplifie la formulation de mélanges café-champignons en automatisant le calcul des proportions. L'outil tient compte des propriétés spécifiques de chaque champignon adaptogène (reishi, chaga, cordyceps) et génère des fiches nutritionnelles détaillées, des recommandations de dosage et des recettes reproductibles.

Que vous cherchiez à optimiser l'énergie, la concentration ou la récupération, cette librairie offre une base de données complète de champignons et une API intuitive pour créer des formulations précises.

## Installation

```bash
npm install mushroom-blend-calculator
```

Ou avec yarn :
```bash
yarn add mushroom-blend-calculator
```

## Utilisation

### Calcul simple d'un mélange

```javascript
const { BlendCalculator } = require('mushroom-blend-calculator');

const calculator = new BlendCalculator();

const blend = calculator.createBlend({
  baseWeight: 500, // grammes de café
  objectives: ['energie', 'concentration'],
  budget: 'premium'
});

console.log(blend);
// {
//   composition: { reishi: 50, chaga: 75, cordyceps: 40 },
//   totalWeight: 665,
//   activeCompounds: { beta-glucans: 12.5, polysaccharides: 18.2 },
//   recommendedDosage: '8-10g par tasse'
// }
```

### Génération de fiche nutritionnelle

```javascript
const { RecipeGenerator } = require('mushroom-blend-calculator');

const recipe = new RecipeGenerator();

const nutritionSheet = recipe.generateNutritionFacts({
  blend: blend,
  servingSize: 10, // grammes
  language: 'fr'
});

recipe.exportPDF(nutritionSheet, 'fiche-nutritionnelle.pdf');
```

### Accès à la base de données de champignons

```javascript
const { MushroomDatabase } = require('mushroom-blend-calculator');

const db = new MushroomDatabase();
const reishi = db.getMushroom('reishi');

console.log(reishi.benefits);
// ['stress', 'sommeil', 'immunité']
```

## Caractéristiques principales

- **Base de données complète** : Propriétés, bénéfices et dosages des principaux champignons adaptogènes
- **Calculs précis** : Algorithmes d'optimisation des proportions selon les objectifs
- **Export de recettes** : Génération de formules reproductibles et documentées
- **Fiches nutritionnelles** : Génération de documents détaillés pour l'étiquetage
- **API flexible** : Utilisation en tant que librairie ou CLI

Cet outil a été développé initialement pour soutenir les producteurs de [https://cafe-champignon-adaptogene.fr](https://cafe-champignon-adaptogene.fr), une plateforme proposant des cafés enrichis en champignons adaptogènes pour une meilleure énergie et concentration.

## Configuration

Vous pouvez personnaliser les paramètres par défaut en créant un fichier `config.json` :

```json
{
  "defaultMushrooms": ["reishi", "chaga", "cordyceps"],
  "maxCaffeineContent": 150,
  "qualityStandards": "organic"
}
```

## License

MIT