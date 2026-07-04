# Local-Musik-Indexer
Music Indexer
/music-organizer
├── /scripts
│ ├── indexer.ts # Liest Ordner, generiert Fingerprint
│ ├── tagger.ts # Schreibt Tags mittels 'music-metadata' lib
│ └── renamer.ts # Verschiebt Dateien nach /Artist/Album/Track.mp3
├── /data
│ └── library.db # Deine lokale SQLite/JSON Datenbank
├── /api
│ └── scanner.ts # Dein Endpunkt, um den Scan zu triggern
└── package.json
Der "Bequemlichkeits-Workflow" (So baust du es effektiv)
Anstatt alles manuell zu machen, baust du dir drei kleine Funktionen:
Scanner (music-metadata + chromaprint):
Du nutzt die Node-Bibliothek music-metadata. Sie liest die Dateien ein.
Wenn Tags fehlen, nutzt du die acoustid npm-Library, um einen digitalen Fingerabdruck an den Webdienst zu senden. Du bekommst sofort den Songtitel, Artist und das Album zurück.
Die "Sichtungs-Logik":
Lass das Skript eine Tabelle in deinem Dashboard füllen:
Duplicate Finder added
