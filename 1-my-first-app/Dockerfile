# Si je dois faire ou veux faire ma propre install python
# FROM alpine:...

# En général on prend un env clé en main
# (si ok par rapport à nos attentes) 
FROM python:3.12-slim-bookworm

# répertoire par défaut pour ttes les commandes
# (~~ meme principe que le home) 
WORKDIR /app

# copy all => bad for  build cache 
# COPY . . # + dockerginore ...

# COPY / RUN ORDER FOR CACHE
COPY requirements.txt .
  
# RUN => executer une commande 
# RUN apt-get install -y ...
# RUN groupadd ...
RUN pip install -r requirements.txt

# COPY <source> <dest>
# COPY src/* (tous les fichiers de src) <dest>
# COPY src (le dossier src) . /app
# COPY src . ( par defaut on est ds /app)
COPY src/index.py src/index.py

# optionnal => declarative only => Documentation
# HTTP SERVER 
EXPOSE 80

# CMD => avec forme normal [] 
CMD [ "python", "src/index.py" ]