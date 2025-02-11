# Bavar

Une interface vocale légère et rapide pour discuter localement avec vos modèles Ollama, grâce à Vosk ! Cette version préconfigurée en français est optimisée pour tourner sur CPU. Inspiré par [Dihydromonoxide](https://myusernamee.neocities.org/blog/realtime_ai).

> Poids :
> Temps d'éxécution : à

**Prérequis :** [Python](https://www.python.org/downloads/), [Ollama](https://ollama.com) et un [modèle](https://ollama.com/search) 👍

## **Utilisation**

Appuyez sur une touche (**²** par défaut) et posez une question.
Votre requête est transcrite en direct et le résultat final est envoyé au modèle de language, sa réponse est ensuite récupérée en temps réel et découpée en phrases qui sont prononcées au fur et à mesure.

## 1) Installation et premier lancement

```bash
git clone https://github.com/q718/bavar.git
cd bavar
```

**Ou télécharger**, dézipper et ouvrir ce répertoire dans un terminal.

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

> Colorama (UI), Vosk (STT/ASR), Ollama, pyttsx3 (TTS), pyaudio, keyboard

```bash
python bavar.py
```

## **2) Lancements suivants**

```
venv\Scripts\activate
python app.py
```

### CTRL+C POUR QUITTER

---

## 3) Personnaliser l'assistant, app.py !

Touche d'activation

```python
KEY = '²'
```

Contexte initial

```python
PROMPT = "En français. Utilisez un langage décontracté et rédigez des phrases courtes. Soyez direct et concis : Allez à l'essentiel ; supprimez les mots inutiles. Gardez un ton naturel : Écrivez comme vous parlez normalement. Évitez le langage marketing : N'utilisez pas de termes publicitaires ou promotionnels. Restez authentique : soyez honnête ; ne forcez pas l'amabilité. Évitez les fioritures : Évitez les adjectifs et les adverbes inutiles. Évitez les répétitions et ne demandez pas de retour sur vos réponses."
```

[Modèle Ollama](https://ollama.com/search) `ollama run nom-du-modèle`

```python
OLLAMA = 'hf.co/bartowski/gemma-2-2b-it-abliterated-GGUF:IQ4_XS'
```

[Langue de la reconnaissance](https://alphacephei.com/vosk/models), dossier dézippé à la racine

```python
STT = 'vosk-model-small-fr-0.22'
```

Vitesse et volume de la synthèse vocale

```python
SPEED = 225
VOL = 1.0
```

Si vous souhaitez contrôler la mémoire du modèle de language, ou que ses réponses ralentissent au fil de la conversation, vous pouvez décommentez le code pour activer la limitation de l'historique, définit par défaut aux 4 dernières intéractions (4 requêtes et 4 réponses). `HISTORY = 4`

---

### Améliorations possibles...

* [ ] Support GPU (switch faster-whisper ?)
* [X] Message d'erreur si la transcription reste vide trop longtemps (PartialResult)
* [ ] Meilleur TTS (erreur Piper)
* [ ] Ajouts de commandes vocales (réinitialisation, recherche web via llm-axe)
* [ ] GUI externe
* [ ] Éxécutable Windows

## Licence

Ce projet est placé sous la **Licence MIT**.
