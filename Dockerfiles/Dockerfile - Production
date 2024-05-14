FROM node:22-slim

RUN mkdir -p /app
WORKDIR /app

# Erstelle das Dokugloss-Verzeichnis im Container
RUN npx create-docusaurus@latest dokugloss classic --javascript

# Setze das erstellte Verzeichnis als Docker-Volume
VOLUME /app/dokugloss

WORKDIR /app/dokugloss

# Kopiere den Inhalt von Dokugloss
COPY . .

RUN npm install
RUN npm run build

EXPOSE 3000

CMD ["npm", "run", "serve", "--", "--build", "--port", "6969", "--host", "0.0.0.0"]