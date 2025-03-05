# Artikelverwaltung mit Angular & Angular Material

## 📌 Projektbeschreibung
Dieses Projekt ist eine Webanwendung zur Verwaltung von Artikeln, die mit **Angular** und **Angular Material** entwickelt wurde. Die Anwendung ermöglicht das Anzeigen, Erstellen, Bearbeiten und Löschen von Artikeln über eine REST-Schnittstelle.

## ✨ Funktionen

### **1. Artikelliste**
- Zeigt eine Liste aller Artikel an.
- Artikel enthalten eine ID, Beschreibung, Anzahl, Preise und ein Einführungsdatum.
- Das erste Bild des Artikels wird als Miniaturbild angezeigt.
- Per Klick auf die Artikel-ID gelangt man zur Detailansicht bzw. Bearbeitung des Artikels.

### **2. Artikel-Formular**
- Ermöglicht das Erstellen und Bearbeiten von Artikeln.
- Validierungen für die Eingabefelder:
  - **ID**: Muss mit `IT` (gefolgt von 6 Ziffern) oder `DE` (gefolgt von 8 Ziffern) beginnen.
  - **Beschreibung**: Pflichtfeld.
  - **Anzahl**: Darf keine Dezimalzahlen enthalten und muss mindestens `0` sein.
  - **Einkaufspreis & Verkaufspreis**: Müssen größer oder gleich `0` sein. Der Einkaufspreis darf den Verkaufspreis nicht überschreiten.
  - **Einführungsdatum**: Pflichtfeld, Standardwert ist das heutige Datum.
  - **Bilder**:
    - Jeder Artikel muss mindestens ein Bild haben.
    - Alle Bild-URLs müssen eindeutig sein.
    - Bildtitel sind optional.
- Beim Bearbeiten eines Artikels kann die ID nicht mehr geändert werden.
- Der **Löschen**-Button ist nur sichtbar, wenn ein bestehender Artikel bearbeitet wird.

## ⚙️ Technologien
- **Angular** (Frontend-Framework)
- **Angular Material** (UI-Komponentenbibliothek)
- **TypeScript** (Programmiersprache)
- **REST API** für die Datenverwaltung

## 📂 Projektstruktur
```
src/
├── app/
│   ├── components/
│   │   ├── article-list/
│   │   ├── article-form/
│   ├── services/
│   │   ├── item.service.ts
│   ├── shared/
│   │   ├── item.ts
│   │   ├── image.ts
│   ├── app.module.ts
│   ├── app.component.ts
├── assets/
│   ├── placeholder.png (...)
```

## 🔧 Installation & Ausführung
1. **Projekt klonen:**
   ```bash
   git clone https://github.com/dein-repo/artikelverwaltung.git
   cd artikelverwaltung
   ```
2. **Abhängigkeiten installieren:**
   ```bash
   npm install
   ```
3. **Angular Development Server starten:**
   ```bash
   ng serve
   ```
4. **Anwendung im Browser öffnen:**
   ```
   http://localhost:4200/
   ```

## 🚀 API-Endpunkte
Das Backend läuft auf `http://localhost:3000/api/items`. Die verfügbaren REST-Endpunkte:

| Methode | Endpunkt                 | Beschreibung |
|---------|--------------------------|-------------|
| `GET`   | `/api/items`             | Alle Artikel abrufen |
| `GET`   | `/api/items/{id}`        | Einzelnen Artikel abrufen |
| `POST`  | `/api/items`             | Neuen Artikel erstellen |
| `PUT`   | `/api/items/{id}`        | Artikel aktualisieren |
| `DELETE`| `/api/items/{id}`        | Artikel löschen |
(...)

## 📌 Besonderheiten
- Fehlermeldungen werden über **Angular Material Snackbar** ausgegeben.
- Unterstützung für **deutsche Zahl-, Währungs- und Datumsformate** durch Angular Pipes (`LOCALE_ID: 'de'`). (Browser muss auf deutsch gesetzt werden!)
- Automatische **Validierung von IDs** über eine asynchrone Prüfung gegen die API.
- Benutzerfreundliche Buttons zum **Hinzufügen/Entfernen von Bildern**.

Autor:
Bozic Oliver, Klasse 5IB
