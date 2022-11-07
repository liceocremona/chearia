## NGINX proxy

- ### progettochearia.it
  - risorse: /srv/www/chearia/public/landing
  - descrizione: sito statico che descrive il progettto
- ### web.progettochearia.it
  - risorse: /srv/www/chearia/public/webapp
  - descrizione: Webapp dinamica con client per vedere i grafici e i dati raccolti
- ### storage.progettoceharia.it
   - risorse: /srv/www/media
   - descrizione: Storage destinato in teoria alle foto
 - ### api.progettochearia.it
   - risorse: unix:chearia_backend.sock
   - descrizione: endpoint delle api principali  del server, le api usate in questo momento si basano FAST api e sono servite su /v1/
   - da fare: riaggiungere su /v0/ le vecchie api basate in flask
- ### rstudio.progettochearia.it
  - risorse: http://localhost:xxxx
  - descrizione: pannello di gestione di Rstudio server

- ### docs.progettochearia.it
  - descrizione: documentazione completa del progetto generata dai file MD con markdown-folder-to-html
  - risorse: /srv/www/docs

## Service Systemd importanti
- ### chearia-backend.service
  - descrizione: Gestisce il server Uvicorn-Python delle API FastAPI 