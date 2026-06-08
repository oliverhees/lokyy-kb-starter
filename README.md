# Lokyy-Wissensbasis — Starter

Dein zweites Gehirn als einfache Markdown-Wissensbasis: Du wirfst Quellen hinein,
nachts destilliert dein KI-Mitarbeiter sie zu verlinkten Artikeln, vernetzt sie und
meldet dir morgens den Stand. Keine Datenbank, kein Code — nur Ordner, Markdown und
ein paar geplante Abläufe.

> **Das ist eine Vorlage.** Lege deine eigene Wissensbasis daraus an (in Forgejo:
> „Dieses Template verwenden") — du bekommst Struktur **und** die vier Abläufe
> sofort, inklusive Zeitsteuerung.

---

## Einmal pro Konto einrichten

Das machst du **einmal** in deinem Forgejo-Konto — danach erbt jede neue
Wissensbasis alles automatisch.

1. **Zugriffstoken (PAT) erstellen:** Avatar → *Einstellungen → Anwendungen →
   Zugriffstoken* → Scopes `repository` (Read/Write) und `issue` (Read/Write) →
   Token kopieren.
2. **Geheimnisse auf Benutzer-Ebene** (Avatar → *Einstellungen → Actions →
   Geheimnisse*):
   - `FOJO_TOKEN` = dein gerade erstellter Token
     *(der Name darf nicht mit `FORGEJO_` beginnen — das ist reserviert)*
   - `BASE_URL` = z. B. `https://openrouter.ai/api/v1`
   - `API_KEY` = dein Modell-Key (bei OpenRouter den kontoweiten PII-Block aus!)
   - `MODELL` = z. B. `openrouter/auto`
   - `MELDE_WEBHOOK` *(optional)* = ein [ntfy.sh](https://ntfy.sh)-Topic für die
     Push-Meldung aufs Handy, z. B. `https://ntfy.sh/mein-geheimes-topic`
3. Ein **Actions-Runner** mit Label `docker` muss online sein (siehe `lokyy-runner`).

Danach: neue Wissensbasis aus der Vorlage anlegen, Actions aktivieren — fertig.
Die Abläufe laufen ab sofort zeitgesteuert von selbst.

---

## Die drei Dinge, die du wissen musst

**1. Füttere es** — wirf eine Quelle in `RAW/` (oder sag deinem Sparringspartner
„add this"). Nachts wird sie zu einem Artikel im `Wiki/`. Was du nur im Chat
besprochen hast, sicherst du mit „save this session".

**2. Frag es** — „what do I know about ___" beantwortet deine Frage aus dem Wiki,
mit Quellen. Gefällt dir eine Antwort, sag „save that" — sie wird ein neuer Artikel.

**3. Es pflegt sich selbst** — Bibliothekar (destilliert), Veredler (vernetzt) und
Tagesimpuls (meldet) laufen nach Zeitplan. Saubere Läufe werden automatisch
übernommen; nur echte Entscheidungen warten als Pull Request auf dich.

Die vier Befehle im Alltag: **„add this" · „save this session" ·
„what do I know about ___" · „save that"**.

---

## Was schon drin ist

- `RAW/`, `Wiki/`, `Outputs/`, `00_meta/` — die Grundstruktur.
- `AGENTS.md` — das Betriebshandbuch (Themenfokus dort anpassen).
- `00_meta/KONVENTIONEN.md` — der lesbare Schema-Vertrag.
- `.forgejo/workflows/` — die vier Abläufe (Bibliothekar, Veredler, Wochen-Review,
  Tagesimpuls).
- **Zwei Beispiel-Quellen** in `RAW/`, damit dein Gehirn an Tag eins nicht leer ist
  und der erste Lauf sofort sichtbar etwas tut. **Lösch sie**, sobald du eigene
  Quellen hast.
