# --- Build Stage ---
FROM node:20-alpine AS build

# Arbeitsverzeichnis im Container festlegen
WORKDIR /app

# Abhängigkeiten kopieren und installieren
COPY package*.json ./
RUN npm install

# Restlichen Quellcode kopieren und die App bauen
COPY . .
RUN npm run build

# --- Production Stage ---
FROM nginx:alpine

# Das fertig gebaute Verzeichnis aus der Build-Stage in den Nginx-Webordner kopieren
COPY --from=build /app/dist /usr/share/nginx/html

# Port 80 freigeben
EXPOSE 4000

# Nginx starten
CMD ["nginx", "-g", "daemon off;"]