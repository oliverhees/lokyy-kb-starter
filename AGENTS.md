# Betriebshandbuch dieser Wissensbasis

> Diese Datei ist die **Dienstanweisung** für deinen KI-Mitarbeiter (den lokyy-mcp
> und jeden Sparringspartner, der ihn nutzt). Die allgemeine Doktrin liefert der
> Server selbst; hier steht nur, was für **diese** Wissensbasis gilt. Passe den
> Themenfokus an — den Rest lass stehen.

## Thema dieser Wissensbasis

**Alles, was für dich wichtig ist.** *(Ersetze diesen Satz durch dein Thema —
z. B. „meine Steuerkanzlei", „KI-Recherche", „mein Buch-Projekt". Ein klarer
Fokus macht die Destillate schärfer.)*

## Der Ordner ist die Anweisung

Du steuerst alles, indem du entscheidest, **wo** etwas liegt:

| Ablage | Bedeutung |
|---|---|
| **`Wiki/`** | fertiges Wissen — wird durchsucht und vernetzt, aber **nie** umgeschrieben |
| **`RAW/<ordner>/`** | Rohmaterial — wird nachts zu einem Wiki-Artikel **destilliert** |
| **`RAW/_<ordner>/`** | „Hände weg" — durchsuchbar, aber nie destilliert, nie geprüft (freies Archiv) |

Du suchst **nie** im RAW herum. Du fragst das **Wiki**, bekommst einen Artikel,
und der verweist zurück auf seine Quelle in RAW.

## Die drei Knöpfe (laufen zeitgesteuert von selbst)

- **🌙 Bibliothekar** (nachts) — destilliert neue RAW-Quellen zu Wiki-Artikeln.
  Saubere Läufe werden automatisch übernommen; nur bei einer echten Entscheidung
  bleibt ein Vorschlag (Pull Request) für dich offen.
- **✨ Veredler** (nachts) — ergänzt Querverweise und Tags im Wiki, **ohne**
  Inhalte anzutasten.
- **🔔 Tagesimpuls** (morgens) — eine kurze Meldung: gab es etwas zu entscheiden
  (mit Link) oder lief alles glatt.

## Die vier Befehle im Alltag

| Befehl | Was passiert |
|---|---|
| **„add this"** | Quelle aufnehmen → RAW → wird destilliert |
| **„save this session"** | Kernerkenntnisse dieses Chats sichern → `RAW/sessions/` |
| **„what do I know about ___"** | Frage ans Wiki, Antwort mit Quellen |
| **„save that"** | eine gute Antwort als neuen Wiki-Artikel sichern |
| **„neue Notiz"** | strukturierte persönliche Notiz in `RAW/_notizen/` (durchsuchbar, nie destilliert) |

## Regeln (vom Server erzwungen, hier zur Erinnerung)

- **Wörtlichkeit:** RAW-Quellen werden nie verschönert oder verändert.
- **Quellenpflicht:** Jede Aussage im Wiki führt auf eine RAW-Quelle zurück —
  sonst ist es höchstens eine *These*.
- **Status-Trias:** Jeder Artikel trägt seinen Reifegrad — *gesichert*,
  *im Aufbau* oder *These*.
- **Personendaten Dritter** werden verschlüsselt außerhalb des Repos abgelegt
  (Blob+Stub) und im Nachtlauf nie in die Cloud gegeben.

Die vollständigen Struktur- und Format-Konventionen stehen in `00_meta/KONVENTIONEN.md`.
