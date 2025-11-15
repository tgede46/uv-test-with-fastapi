
# Test Uvicorn (uv) pour FastAPI

Ce dépôt contient une petite application FastAPI (`main.py`) utilisée pour tester le serveur ASGI `uvicorn` (souvent appelé "uv"). Ce fichier explique comment installer, démarrer et vérifier rapidement le serveur.

**But :** vérifier que `uvicorn` démarre correctement et sert l'application FastAPI.

**Prérequis**
- Python 3.8+ installé
- `git` (optionnel)

**Étapes rapides**

1. Ouvrir un terminal dans le dossier du projet :
```bash
cd /home/gedeonkp/Tool/ToolPy/fastApi/test-uv/python-project
```

2. Créer et activer un environnement virtuel (Linux / zsh) :
```bash
python3 -m venv .venv
source .venv/bin/activate
```

3. Mettre pip à jour et installer les dépendances :
```bash
pip install --upgrade pip
pip install "fastapi[standard]" "uvicorn[standard]"
```

4. Lancer le serveur avec `uvicorn` :
```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

- Ouvrez ensuite `http://127.0.0.1:8000/` dans votre navigateur ; vous devriez voir `hello world`.
- La documentation interactive est disponible à `http://127.0.0.1:8000/docs`.

Explications rapides

- **Qu'est-ce que "uv" / `uvicorn` ?**
	- `uvicorn` est un serveur ASGI (Asynchronous Server Gateway Interface) léger et rapide pour exécuter des applications Python asynchrones comme FastAPI ou Starlette. "uv" est parfois utilisé comme diminutif familier.
	- Il prend en charge des connexions performantes et asynchrones, et peut être utilisé en développement (avec `--reload`) ou en production (avec des configurations et gestion de processus adéquates).

- **Que permet `uvicorn` ?**
	- Exécuter l'application FastAPI et répondre aux requêtes HTTP.
	- Supporter la concurrence asynchrone pour de meilleures performances.
	- Recharger automatiquement le code en développement avec l'option `--reload`.

Conseils et dépannage

- Si vous voyez `ModuleNotFoundError: No module named 'main'`, vérifiez que vous êtes dans le répertoire contenant `main.py` ou lancez `uvicorn python_project.main:app` en ajustant le module path.
- Si l'installation bloque, vérifiez votre version de Python (exécutez `python --version`).
- En production, utilisez un processus manager (systemd, Docker, gunicorn + uvicorn workers, etc.) et désactivez `--reload`.

Contact

Si vous voulez que j'exécute la commande `uvicorn` ici et que je vous montre les logs, dites-le et j'exécuterai la commande dans un terminal.
