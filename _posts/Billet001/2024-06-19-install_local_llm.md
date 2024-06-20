---
title: "Installer et utiliser un LLM chez soi"
date: 2024-20-06
---

Pour héberger et faire tourner notre LLM (Large Language Model), nous allons devoir installer et utiliser plusieurs outils.\
Voyons ça dans l'ordre:

# Ollama
Cet outil va héberger notre modèle et le rendre facilement accessible.
Si vous êtes sur windows, ouvrez une invite de commande et tapez :
```
winget install Ollama.Ollama
```

# Choisir et installer un LLM
Ollama est compatible avec beaucoup de LLM, la liste complète est disponible sur cette page : https://ollama.com/library\
Ici, nous allons utiliser le modèle llama3 en version 8b, pour cela, saisissez la commande suivante :
```
ollama run llama3:8b
```

Cette commande va faire plusieurs choses parmi lesquelles :
- Télécharger le modèle si vous ne l’avez pas
- Démarrer une conversation avec ce modèle dans l’invite de commande

![installation llama](/blog/assets/billet001/install_llama3.png)

Vous pouvez donc déjà discuter avec votre machine dans une invite de commande ! C’est sympa mais pas super moderne… La première bonne nouvelle c’est que ollama expose une api qui vous permet d’interagir avec le LLM, la seconde bonne nouvelle c’est que pleins de gens ont déjà créer des projets pour utiliser cette api et qu’il suffit d’en installer un !

# Open WebUI
Il s’agit donc là d’une UI web (oui je ne me suis pas foulé !) qui sera hébergée en local et va nous permettre d’échanger avec le LLM. Pour l’installer, nous allons utiliser docker (si vous ne l’avez pas encore sur votre machine, il est temps de l’installer !) et cette commande :
```
docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```
Il vous suffit maintenant de vous rendre sur la page http://localhost:3000/ pour y trouver une interface sympa à utiliser avec votre modèle, le tout en local !
A vous les discussions profondes... Ou pas !

![discussion avec llama](/blog/assets/billet001/discussion_llama3.png)
