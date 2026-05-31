# 🚀 Fubsi's Personal Space

Willkommen in meinem Web-Repository! Dies ist der Quellcode für meine persönliche Website und mein digitales Portfolio. 

Diese Seite dient als zentraler Anlaufpunkt für meine Projekte und Interessen – von Code-Basteleien und Softwareentwicklung bis hin zu meinen Home-Lab-Experimenten und Infrastruktur-Setups.

## 👨‍💻 Über mich & Meine Themen

Auf der Website präsentiere ich verschiedene Bereiche, mit denen ich mich aktiv beschäftige:
* **Softwareentwicklung:** Full-Stack-Projekte, Skripte und Automatisierungen (Python, JavaScript, SQL).
* **Self-Hosting & Sysadmin:** Verwaltung von Linux-Servern und Container-Deployments.

## 🛠 Tech-Stack der Website

Die Seite selbst ist bewusst schlank und performant gehalten:
- **Frontend:** Vue.js + Vite (für blitzschnelles HMR und flüssige UI)
- **Webserver:** Nginx (Alpine Linux Basis)
- **Deployment:** Multi-Stage Docker-Build

## 📦 Automatisches Deployment (via Portainer)

Die Website läuft live auf meiner eigenen Infrastruktur. Das Repository ist so aufgebaut, dass es nahtlos als Git-Stack in Portainer geladen werden kann.

1. In Portainer zu **Stacks** navigieren.
2. **Add stack** -> **Repository** auswählen.
3. Die URL dieses Repos eintragen: `https://github.com/fubsi/<DEIN-REPO-NAME>`
4. **Deploy the stack** klicken.

Dank der beiliegenden `docker-compose.yml` und dem `Dockerfile` wird die Vue-App automatisch kompiliert und ressourcenschonend im Nginx-Container gestartet.