FROM ubuntu:latest

# Mise à jour du système
RUN apt-get update
RUN apt-get upgrade -y

# Installation de Python et pip
RUN apt-get install -y python3 python3-pip

# Suppression du verrou de gestion externe (si erreur pip)
RUN rm -f /usr/lib/python*/EXTERNALLY-MANAGED

# Installation de Flask
RUN pip3 install flask

# Nettoyage des caches
RUN rm -rf /var/lib/apt/lists/*

# Définit le répertoire de travail
WORKDIR /app

# Copie le fichier Python dans l'image
COPY ./api.py /app/api.py

# Lance le serveur Flask au démarrage
CMD ["python3", "api.py"]