# **README 2**

## **Anleitung**

### Klonen des Repository

- Fork erstellen auf [docker-nodejs-sample](https://github.com/ICT-BLJ/docker-nodejs-sample)
**Fork -> Create a new Fork -> Create Fork**
- In Git Bash diese Befehle ausführen:

1. `cd [Projektordner Pfad]`
1. `clone  git clone https://github.com/[dein username]/docker-nodejs-sample.git`
1. `cd docker-nodejs-sample`

### Installation der notwendigen Pakete

Mit `npm install` oder `npm ci` installiert man alle Pakete die in **package.json** gelistet sind:

```javascript
"dependencies": {
  "express": "^4.18.2",
  "pg": "^8.11.2",
  "sqlite3": "^5.1.2",
  "uuid": "^9.0.0",
  "wait-port": "^1.0.4"
  },
  ```

  und

  ```javascript
  "devDependencies": {
    "jest": "^29.6.2",
    "nodemon": "^3.0.1",
    "prettier": "^2.7.1"
  }
  ```

  Der Unterschied von `npm install` & `npm ci` ist, dass `npm ci` gebraucht wird wenn ein **package-lock.json** existiert, für einen _clean install_, `npm install` wird öfter gebraucht und ist flexibler.

  Wenn ein **package-lock.json** existiert, werden auch Pakete die dort gelistet sind installiert.

### Docker-Konfiguration und -Installation

Um eine ToDo-Applikation in einem Docker-Container bereitzustellen muss man in seinem Projekt-Root-Verzeichnis drei Dateien erstellen:

>**Dockerfile**

In diesem File wird beschrieben wie das _Image_ gebaut wird. Man installiert die Abhängigkeiten aus **package.json** und **package-lock.json** und man legt fest welcher _Command_ beim Start des Containers ausgeführt wird.

>**compose.yaml**

Dieses File ermöglicht das starten mit einem einzigen Befehl und definiert den Port.

>**.dockerignore**

In diesem File werden Ordner und Dateien aufgelistet die beim Bauen des _Images_ nicht mitkopiert werden sollen.

### Starten der Applikation in einem Docker-Container

Man startet die Applikation in einem Docker-Container indem man diesen Command `docker compose up --build` im Projekt-Ordner in Powershell ausführt.
