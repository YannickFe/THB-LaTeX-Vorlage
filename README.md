# LaTeX-Vorlage für die Technische Hochschule Brandenburg

Eine LaTeX-Vorlage für den persönlichen Gebrauch für Haus-, Seminar-, Bachelor- und Masterarbeiten an der [Technischen Hochschule Brandenburg](https://www.th-brandenburg.de/startseite/).

Wie das Ergebnis aussieht, könnt ihr in der Datei [THBVorlageMain.pdf](./THBVorlageMain.pdf) ansehen. Im ersten Kapitel finden sich auch einige Hinweise zur Nutzung dieser Vorlage.

**Achtung** Dies ist keine offizielle Vorlage der THB. Es besteht kein Anspruch auf Richtigkeit oder Vollständigkeit.

In dieser Vorlage wurde einiges von [dieser Seite](https://github.com/andygrunwald/FOM-LaTeX-Template) übernommen.

## Weitere Informationen zum Umgang mit der Vorlage

Im ersten Kapitel der Datei [THBVorlageMain.pdf](./THBVorlageMain.pdf) werden die meisten Funktionen dieser Vorlage beschrieben.
Das zweite Kapitel gibt zusätzlich eine Übersicht über grundlegende Funktionen von LaTeX.

Für tiefergehende Informationen empfehle ich die Dokumentationen der einzelnen Pakete durchzulesen, welche alle auf [CTAN](https://ctan.org/) zu finden sind.

## Lizenz

Dieses Projekt ist unter den Bedingungen der [MIT Lizenz](http://en.wikipedia.org/wiki/MIT_License) öffentlich verfügbar.

## Entwicklungsumgebung

Das nachstehende Snippet einer sublime-build Konfigurationsdatei kann in Sublime verwendet werden.
Dafür kann unter `Tools > Build System > New Build System ...` ein neuer Builder `LaTeX (Tectonic).sublime-build` erstellt werden. 
Tectonic ist eine schlanke TeX-Engine, basierend auf XeTeX, und wird unter OSX mit `brew install tectonic` installiert.

```sublime-build
{
  "shell_cmd": "tectonic \"$file\"",
  "file_patterns": ["*.tex"],
  "selector": "text.tex.latex",
  "working_dir": "$file_path",
  "variants": [
    {
      "name": "Clean",
      "shell_cmd": "rm \"$file_base_name.pdf\""
    },
    {
      "name": "Keep Intermediates",
      "shell_cmd": "tectonic --keep-intermediates \"$file\""
    },
    {
      "name": "Continue on Errors",
      "shell_cmd": "tectonic -Z continue-on-errors \"$file\""
    },
  ]
}
```
