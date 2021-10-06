 FROM python:2.7-stretch
 # Maintainer
 LABEL org.opencontainers.image.author="CHERIF BACHIR <bachir_c@etna-alternance.net>"

# update package
RUN apt-get update -y --allow-unauthenticated

# Install python packages and dependencies
RUN apt-get install python-dev libldap2-dev libsasl2-dev python-dev libssl-dev python3-dev -y --allow-unauthenticated 
RUN pip install flask flask_httpauth flask_simpleldap python-dotenv

# Copie the student api at the root of the image OS
COPY ./student_age.py /

# Créer un bind mount à /data/
VOLUME [ "/data/" ]

# Ouvrir le port d'écoute au lancement du conteneur 
EXPOSE 5000

# Lancer l'application
CMD [ "python", "/data/student_age.py" ]
