# 🛒 Geteilte Einkaufsliste

Eine moderne, echtzeitfähige Einkaufslisten-WebApp zum Teilen mit Familie oder Mitbewohnern. Änderungen werden sofort synchronisiert - egal ob am Handy im Supermarkt oder am Computer zuhause.

![Einkaufsliste Screenshot](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)
![Firebase](https://img.shields.io/badge/Firebase-Realtime%20Database-orange)
![React](https://img.shields.io/badge/React-18.2.0-blue)

## ✨ Features

- ✅ **Echtzeit-Synchronisation** - Alle Änderungen werden sofort bei allen Nutzern angezeigt
- 🔄 **Drag & Drop Sortierung** - Produkte per Maus oder Touch verschieben
- ✓ **Produkte abhaken** - Gekaufte Artikel werden automatisch nach unten sortiert
- 🗑️ **Einfaches Löschen** - Einzelne Produkte oder alle gekauften auf einmal entfernen
- 📱 **Responsive Design** - Optimiert für Smartphones und Desktop
- 🔐 **Sichere Authentifizierung** - Anonyme Firebase-Anmeldung ohne Passwörter
- 🌐 **Offline-fähig** - Funktioniert auch ohne Internetverbindung (mit Caching)
- 💯 **Kostenlos** - Keine versteckten Kosten

## 🚀 Demo

**Live-Demo:** https://felixthe.github.io/Einkaufsliste/

## 📋 Voraussetzungen

- Ein Google-Konto für Firebase
- Ein moderner Webbrowser (Chrome, Firefox, Safari, Edge)
- Optional: GitHub Account für Hosting

## 🔧 Installation & Setup

### 1. Firebase Projekt erstellen

1. Gehe zu [Firebase Console](https://console.firebase.google.com)
2. Klicke auf **"Projekt hinzufügen"**
3. Gib einen Projektnamen ein (z.B. "Einkaufsliste")
4. Google Analytics kann deaktiviert werden
5. Klicke auf **"Projekt erstellen"**

### 2. Firebase Realtime Database aktivieren

1. Im Firebase-Projekt: **Build** → **Realtime Database**
2. Klicke auf **"Datenbank erstellen"**
3. Wähle einen Standort (z.B. Europe - eur3)
4. Starte im **Testmodus** (wird später angepasst)
5. Klicke auf **"Aktivieren"**

### 3. Firebase Authentication aktivieren

1. **Build** → **Authentication**
2. Klicke auf **"Get started"**
3. Gehe zum Tab **"Sign-in method"**
4. Aktiviere **"Anonymous"**
   - Klicke auf "Anonymous" → Enable → Save

### 4. Database Security Rules setzen

1. Gehe zu **Realtime Database** → Tab **"Rules"**
2. Ersetze die Regeln mit folgendem Code:

```json
{
  "rules": {
    "items": {
      ".read": "auth != null",
      ".write": "auth != null"
    }
  }
}
```

3. Klicke auf **"Publish"**

### 5. Web-App zu Firebase hinzufügen

1. In der Projektübersicht: Klicke auf das **Web-Icon** (`</>`)
2. App-Spitzname: "Einkaufsliste Web"
3. Firebase Hosting muss **nicht** aktiviert werden
4. Klicke auf **"App registrieren"**
5. **Kopiere die Firebase-Konfiguration** - sie sieht so aus:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "projekt-id.firebaseapp.com",
  databaseURL: "https://projekt-id-default-rtdb.europe-west1.firebasedatabase.app",
  projectId: "projekt-id",
  storageBucket: "projekt-id.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc..."
};
```

### 6. App konfigurieren

1. Lade die `index.html` herunter oder klone dieses Repository
2. Öffne die Datei in einem Browser
3. Klicke auf **"Firebase einrichten"**
4. Füge alle Werte aus der Firebase-Konfiguration ein
5. Klicke auf **"Speichern und Verbinden"**

**Fertig!** Die App ist jetzt einsatzbereit 🎉

## 📱 Installation auf dem Smartphone

### Android (Chrome/Edge)

1. Öffne die App im Browser
2. Tippe auf die **drei Punkte** (⋮) oben rechts
3. Wähle **"Zum Startbildschirm hinzufügen"**
4. Die App erscheint wie eine native App auf deinem Homescreen

### iOS (Safari)

1. Öffne die App in Safari
2. Tippe auf das **Teilen-Symbol** (□ mit Pfeil)
3. Scrolle runter und wähle **"Zum Home-Bildschirm"**
4. Bestätige mit **"Hinzufügen"**

## 🌐 Hosting Optionen

### Option 1: GitHub Pages (empfohlen)

1. Erstelle ein neues GitHub Repository
2. Benenne die Datei in `index.html` um
3. Lade sie hoch
4. Gehe zu **Settings** → **Pages**
5. Wähle **"Deploy from a branch"** → **main** → **/ (root)**
6. Deine App ist verfügbar unter: `https://username.github.io/repository-name/`

### Option 2: Netlify Drop

1. Gehe zu [Netlify Drop](https://app.netlify.com/drop)
2. Ziehe die `index.html` ins Browserfenster
3. Du bekommst sofort eine URL

### Option 3: Vercel

1. Installiere die [Vercel CLI](https://vercel.com/download)
2. Im Projektordner: `vercel deploy`
3. Folge den Anweisungen

## 📖 Verwendung

### Produkte hinzufügen
- Gib den Produktnamen in das Eingabefeld ein
- Drücke Enter oder klicke auf das **Plus-Symbol**

### Produkte abhaken
- Klicke auf den **Kreis** vor dem Produktnamen
- Abgehakte Produkte rutschen automatisch nach unten

### Reihenfolge ändern
- Halte das **Griff-Symbol** (⋮⋮) gedrückt
- Ziehe das Produkt an die gewünschte Position
- Lass los zum Platzieren

### Produkte löschen
- **Einzeln:** Klicke auf das **Papierkorb-Symbol**
- **Alle gekauften:** Klicke auf **"Gekaufte Produkte löschen"**

### Mit anderen teilen
- Beide Nutzer müssen die **gleiche Firebase-Konfiguration** eingeben
- Die Synchronisation erfolgt automatisch in Echtzeit
- Keine Registrierung oder Freigabe nötig

## 🛠️ Technologie-Stack

- **Frontend:** React 18.2.0 (ohne Build-Prozess, direkt im Browser)
- **Styling:** Tailwind CSS 3.x
- **Backend:** Firebase Realtime Database
- **Authentication:** Firebase Anonymous Auth
- **Hosting:** Statische HTML-Datei (kann überall gehostet werden)

## 🔒 Sicherheit

- Alle Nutzer werden automatisch anonym authentifiziert
- Datenbankzugriff nur für authentifizierte Nutzer
- Keine Passwörter oder persönliche Daten erforderlich
- Firebase Security Rules verhindern unbefugten Zugriff

## 💰 Kosten

Die App ist im Firebase **Spark Plan (kostenlos)** nutzbar:
- 1 GB Speicher
- 10 GB/Monat Download
- 100 gleichzeitige Verbindungen

Für normale Haushalte ist das mehr als ausreichend!

## 🐛 Bekannte Einschränkungen

- Die App benötigt eine Internetverbindung für die Synchronisation
- Firebase-Konfiguration muss manuell eingegeben werden
- Keine Mehrbenutzer-Verwaltung (alle haben gleiche Rechte)

## 🤝 Beitragen

Contributions sind willkommen! 

1. Forke das Projekt
2. Erstelle einen Feature Branch (`git checkout -b feature/NeuesFunktion`)
3. Committe deine Änderungen (`git commit -m 'Füge neue Funktion hinzu'`)
4. Pushe zum Branch (`git push origin feature/NeuesFunktion`)
5. Öffne einen Pull Request

## 📝 Lizenz

Dieses Projekt ist unter der MIT-Lizenz lizenziert - siehe [LICENSE](LICENSE) für Details.

## 👨‍💻 Autor

[Dein Name]

## 🙏 Danksagungen

- Firebase für die kostenlose Realtime Database
- Tailwind CSS für das moderne Design
- React für das reaktive UI-Framework

## 📞 Support

Bei Fragen oder Problemen:
- Öffne ein [Issue](https://github.com/username/repository/issues)
- Kontaktiere mich über [deine E-Mail]

---

**Viel Spaß beim Einkaufen! 🛒**
