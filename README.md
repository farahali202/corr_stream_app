# Application de Correction de Texte
 
Cette fiche de documentation présente l'application Streamlit qui utilise un modèle T5 fine-tuné pour corriger les erreurs grammaticales dans un texte saisi. Elle fournit une interface conviviale permettant aux utilisateurs d'entrer du texte et de recevoir les corrections en temps réel.

## Fonctionnalités

- Zone de saisie de texte pour les phrases comportant des erreurs grammaticales.
- Correction en temps réel via un modèle T5 pré-entraîné.
- Affichage immédiat du texte corrigé après avoir cliqué sur le bouton "Obtenir la correction".

## Table des matières

- [Prérequis](#prérequis)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Fonctionnement](#fonctionnement)
- [Déploiement](#déploiement)
- [Contribution](#contribution)
- [Licence](#licence)

## Prérequis

L'application nécessite les packages Python suivants avec les versions spécifiées :

- `streamlit==1.39.0`
- `transformers==4.45.1`
- `torch==2.4.1`
- `gdown`
- `nltk`
- `rouge`
- `sentencepiece`

Les versions exactes peuvent également être trouvées dans le fichier `requirements.txt`.

## Installation

Pour configurer l'application localement, suivez ces étapes :

1. Clonez le dépôt :
   ```bash
   git clone <url-du-repository>
   cd my_streamlit_app
   ```

2. Installez les packages requis :
   ```bash
   pip install -r requirements.txt
   ```

3. Assurez-vous que les fichiers du modèle fine-tuné sont placés dans le répertoire `fine_tuned_model/`.

## Utilisation

Pour exécuter l'application, utilisez la commande suivante :

```bash
streamlit run src/kk.py
```

Cela démarrera le serveur Streamlit et vous pourrez accéder à l'application dans votre navigateur à l'adresse `http://localhost:8501`.

### Saisie du texte

Saisissez le texte contenant des erreurs grammaticales dans la zone de texte, puis cliquez sur le bouton **Obtenir la correction** pour voir le texte corrigé.

## Fonctionnement

L'application utilise le **modèle T5** de la bibliothèque Hugging Face Transformers, qui a été fine-tuné pour les tâches de correction grammaticale. Lorsqu'un utilisateur entre du texte, l'application :

1. Prépare l'entrée en ajoutant un préfixe (`"correct: "`) pour signaler au modèle de procéder à la correction.
2. Génère une sortie corrigée à l'aide du modèle.
3. Affiche le texte corrigé à l'utilisateur.

## Déploiement

L'application peut être déployée facilement sur des plateformes cloud telles que [Streamlit Cloud](https://streamlit.io/cloud) ou [Heroku](https://www.heroku.com).

### Étapes de déploiement pour Streamlit Cloud

1. Poussez votre code vers un dépôt GitHub.
2. Connectez-vous à [Streamlit Cloud](https://streamlit.io/cloud) et liez votre compte GitHub.
3. Sélectionnez le dépôt contenant votre application.
4. Streamlit Cloud installera automatiquement les dépendances listées dans `requirements.txt` et déploiera votre application.

## Contribution

Les contributions sont les bienvenues ! Si vous avez des suggestions d'améliorations ou de nouvelles fonctionnalités, n'hésitez pas à forker le dépôt et à soumettre une pull request.

1. Forkez le dépôt.
2. Créez votre branche de fonctionnalité :
   ```bash
   git checkout -b feature/nouvelle-fonctionnalité
   ```
3. Commitez vos changements :
   ```bash
   git commit -m "Ajout d'une nouvelle fonctionnalité"
   ```
4. Poussez vers la branche :
   ```bash
   git push origin feature/nouvelle-fonctionnalité
   ```
5. Ouvrez une pull request.

## Licence

Ce projet est sous licence MIT. Consultez le fichier [LICENSE](LICENSE) pour plus de détails.
