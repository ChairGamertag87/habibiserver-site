# habibiserver.dev

Page d'accueil statique du HabibiServer.

## Contenu

- `index.html` : la page principale
- `error.html` : page d'erreur (404/50x)
- `face.png` : favicon

## Deploiement

Le site tourne en Docker derriere le reverse proxy Caddy du serveur :

```bash
docker compose up -d --build
```

Le conteneur `habibiserver-web` ecoute sur `127.0.0.1:8092` (debug) et est joint
par Caddy via le reseau Docker partage. Sur le serveur, un cron tire le main de
ce repo toutes les 5 minutes et rebuild si un nouveau commit est present
(`~/habibiserver-site/auto-update.sh`).
