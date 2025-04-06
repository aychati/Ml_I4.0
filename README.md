# Ml_I4.0
 Ce projet vise à développer une solution d’intelligence  artificielle permettant de prédire les arrêts de protection d’un cobot UR3 à partir de ses données  de capteurs. 

## 🎯 Objectif
Développer un système de maintenance prédictive pour anticiper les arrêts de protection d'un cobot UR3 à partir des données de capteurs (courants, températures, vitesses) sur une séquence de **10 timesteps**.

## 📋 Prérequis
- Python 3.8
- Docker (pour le déploiement)
- Librairies Python : Voir `requirements.txt`

## Lancer l'API Flask en local
python src/app.py

## Tester l'API
curl -X POST http://localhost:5000/predict \
-H "Content-Type: application/json" \
-d '{"sequence": [[0.1, 0.2, ...], [0.3, 0.4, ...], ...]}'

## Déploiement avec Docker
docker build -t cobot-api .
docker run -p 5000:5000 --name cobot-container cobot-api
docker stop cobot-container

