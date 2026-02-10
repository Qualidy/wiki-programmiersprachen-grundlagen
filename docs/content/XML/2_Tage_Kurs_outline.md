# XML 2-Tage Kurs für Einsteiger

## Kursbeschreibung

Dieser Kurs führt Teilnehmende mit grundlegenden Kenntnissen in HTML, CSS und JavaScript in die Welt der XML ein. Nach Abschluss des Kurses können Teilnehmende XML-Dokumente erstellen, validieren und grundlegend verarbeiten.

**Voraussetzungen:** Grundlegende Kenntnisse in HTML/CSS/JavaScript
**Dauer:** 2 Tage (ca. 16 Stunden)
**Zielgruppe:** Entwickler, Webentwickler, Datenverarbeiter

---

## Tag 1: XML Grundlagen

### Lernziele
- XML verstehen und anwenden
- Well-formed XML erstellen
- Unterschiede zwischen XML und HTML kennen
- DTD und XML Schema basics beherrschen
- Validierung durchführen

---

### Stunde 1: Einführung in XML (2 Stunden)

#### Themen
- Was ist XML?
  - Definition und Geschichte
  - Anwendungsbereiche (Konfigurationen, Datenaustrausch, Web Services)
  - Vergleich mit HTML
- XML vs. HTML Vergleichstabelle

#### Content aus `1.md`
- Zeilen 1-32: Einführung, XML vs. HTML Tabelle
- Beispiele: Konfigurationsdateien, Datenstrukturen

#### Praktische Übung
- Erstellen eines einfachen XML-Dokuments
- Unterschiede zu HTML identifizieren

---

### Stunde 2: XML Syntax-Regeln (2 Stunden)

#### Themen
- Wurzelelement (genau ein)
- Geschlossene Tags
- Groß-/Kleinschreibung (case-sensitive)
- Attribute in Anführungszeichen
- Korrekte Verschachtelung
- Kommentare und CDATA

#### Content aus `1.md`
- Zeilen 47-137: XML-Syntax-Regeln (alle 7 Punkte)

#### Praktische Übung
- Syntax-Validierung von XML-Dokumenten
- Fehlersuche: Wohlgeformtes vs. nicht wohlgeformtes XML

---

### Stunde 3: XML-Dokument-Struktur (1.5 Stunden)

#### Themen
- XML-Deklaration (`<?xml ... ?>`)
- Elemente und Attribute
- Textinhalt
- CDATA-Sektionen für Sonderzeichen

#### Content aus `1.md`
- Zeilen 139-165: Dokument-Struktur

#### Content aus `1.md`
- Zeilen 126-135: CDATA-Sektionen

#### Praktische Übung
- Erstellen verschiedener XML-Strukturen (Elemente, Attribute, Text)

---

### Stunde 4: Praktische Beispiele (1.5 Stunden)

#### Themen
- Einfaches Adressbuch
- Konfigurationsdatei
- Produktliste
- Attribute vs. Elemente: Wann welches verwenden?

#### Content aus `1.md`
- Zeilen 168-247: Alle 3 Beispiele

#### Content aus `1.md`
- Zeilen 253-285: Attribute vs. Elemente

#### Praktische Übung
- Eigenes XML-Dokument erstellen (z.B. Bibliothek, Task-Liste, Rezeptbuch)

---

### Stunde 5: Well-formed XML & Validierung (1.5 Stunden)

#### Themen
- Definition von "well-formed"
- Checkliste für XML-Dokumente
- Grundlagen der Validierung
- XML vs. Well-formed vs. Valid

#### Content aus `1.md`
- Zeilen 289-321: Well-formed XML und Beispiele

#### Content aus `2.md`
- Zeilen 14-23: Validierung und DTD/XSD Vergleich

---

### Stunde 6: DTD Basics (1.5 Stunden)

#### Themen
- Was ist eine DTD?
- Interne DTD
- Externe DTD
- Element-Definitionen
- Attribut-Definitionen

#### Content aus `2.md`
- Zeilen 26-79: DTD Grundlagen und Beispiele

#### Content aus `2.md`
- Zeilen 91-164: Element- und Attribut-Definitionen

#### Praktische Übung
- DTD für Adressbuch erstellen und dokument.xml validieren

---

### Stunde 7: XML Schema (XSD) Basics (1 Stunde)

#### Themen
- Was ist XML Schema (XSD)?
- Grundlegende Struktur
- Einfache Typen
- Komplexe Typen

#### Content aus `2.md`
- Zeilen 170-299: XSD Grundlagen und vollständiges Beispiel

#### Praktische Übung
- XSD für Adressbuch erstellen

---

## Tag 2: XML Verarbeitung & Validierung

### Lernziele
- XML-Validierung durchführen
- XML in Anwendungen verarbeiten
- XPath Basics anwenden
- Best Practices kennen

---

### Stunde 1: Validierung (1 Stunde)

#### Themen
- Validierung mit DTD (xmllint)
- Validierung mit XSD (xmllint)
- Java-Validierung (optional)

#### Content aus `2.md`
- Zeilen 326-371: Validierung mit DTD/XSD und Java-Beispiel

#### Content aus `3.md`
- Zeilen 100-134: XPath-Beispiele für Validierung

#### Praktische Übung
- Validieren von XML-Dokumenten mit verschiedenen DTD/XSD

---

### Stunde 2: XPath Basics (1.5 Stunden)

#### Themen
- Was ist XPath?
- XPath-Syntax (Pfad-Ausdrücke)
- Attribute auswählen
- Einfache Bedingungen
- XPath-Funktionen

#### Content aus `3.md`
- Zeilen 29-99: XPath Grundlagen

#### Content aus `3.md`
- Zeilen 100-118: Praktische Adressbuch-Abfragen

#### Praktische Übung
- Verschiedene XPath-Abfragen für Adressbuch erstellen

---

### Stunde 3: XSLT Einführung (1.5 Stunden)

#### Themen
- Was ist XSLT?
- XSLT-Struktur
- Grundlegende XSLT-Elemente:
  - `<xsl:template>`
  - `<xsl:value-of>`
  - `<xsl:for-each>`
  - `<xsl:if>`

#### Content aus `3.md`
- Zeilen 139-242: XSLT Einführung und Elemente

#### Praktische Übung
- XML → HTML Transformation (Adressbuch zu HTML-Seite)

---

### Stunde 4: XSLT Anwendungen (1.5 Stunden)

#### Themen
- XML → HTML Transformation
- XML → CSV Export
- Dynamische HTML-Generierung

#### Content aus `3.md`
- Zeilen 260-371: Praktische XSLT-Beispiele

#### Praktische Übung
- XSLT für verschiedene Ausgabeformate (HTML, CSV)

---

### Stunde 5: XML-Parsing Basics (1 Stunde)

#### Themen
- DOM Parsing (Java)
- SAX Parsing (Java)
- Python (ElementTree)
- JavaScript (xmldom)

#### Content aus `4.md`
- Zeilen 252-353: XML-Parsing in verschiedenen Sprachen

#### Praktische Übung
- XML in einer Programmiersprache auslesen

---

### Stunde 6: Best Practices & Sicherheit (1 Stunde)

#### Themen
- Häufige Fehler vermeiden
- Performance-Tipps
- XML-Sicherheit (XXE Basics)

#### Content aus `1.md`
- Zeilen 412-451: Häufige Fehler & Best Practices

#### Content aus `4.md`
- Zeilen 358-396: XXE-Sicherheit (Grundlagen)

#### Content aus `4.md`
- Zeilen 421-418: Schematron (optional für Fortgeschrittene)

---

### Stunde 7: Praktischer Workshop (1.5 Stunden)

#### Workshop-Thema: XML-Management-System
- Eigene XML-Struktur erstellen
- Validierung mit XSD
- XPath-Abfragen für verschiedene Daten
- XSLT für HTML-Ausgabe

#### Praktische Aufgabe
- Real-world XML-Projekt auswählen und umsetzen
- Optionen:
  - E-Shop-Katalog
  - Buchverwaltung
  - Projektmanagement
  - CRM-Daten

---

### Stunde 8: Abschluss & Q&A (0.5 Stunden)

- Zusammenfassung
- Offene Fragen
- Nächste Schritte & Ressourcen
- Abschluss-Übung (optional)

#### Content aus `1.md` bis `4.md`
- Zusammenfassungen und Checklisten aus allen Dateien

---

## Kursmaterialien

### Notwendige Dateien
- Alle `docs/content/XML/*.md` Dateien
- Beispiel-XML-Dateien (in Kurs-Repository)
- XSD- und DTD-Dateien
- XSLT-Transformationen
- Aufgaben-Dateien (YAML)

### Tools
- XML Editor (z.B. Oxygen, Notepad++, VS Code)
- Validierungstools (xmllint, Online-Validator)
- Browser zum Anzeigen von XML/XSLT-Ergebnissen

### Online-Ressourcen
- [MDN Web Docs - XML](https://developer.mozilla.org/de/docs/Web/XML)
- [W3Schools XML Tutorial](https://www.w3schools.com/xml/)
- [XML.com](https://www.xml.com/)

---

## Kurs-Ziel-Checkliste

### Tag 1 Erreichte Ziele
- [ ] XML-Syntax korrekt anwenden
- [ ] Well-formed XML erstellen
- [ ] XML vs. HTML unterscheiden
- [ ] DTD Basics verstehen
- [ ] XML Schema (XSD) Basics verstehen
- [ ] XML-Validierung durchführen

### Tag 2 Erreichte Ziele
- [ ] XPath für einfache Abfragen nutzen
- [ ] XSLT für XML → HTML Transformationen nutzen
- [ ] XML in Programmiersprachen verarbeiten
- [ ] Best Practices anwenden
- [ ] XML-Projekte eigenständig erstellen

---

## Empfohlene Reihenfolge für weitere Themen

Nach diesem 2-Tage-Kurs können Teilnehmende fortgeschrittene Themen lernen:
1. XQuery für komplexe Datenbank-Abfragen
2. XSLT 2.0/3.0 Fortgeschrittene Features
3. XML-Sicherheit (XXE, Sichere Parsing)
4. Schematron für komplexe Validierungsregeln
5. XML-Datenbanken (eXist-db, BaseX)
6. RESTful Web Services mit XML

---

## Zeitplan-Übersicht

| Tag | Stunde | Thema | Dauer | Content |
|-----|--------|-------|-------|---------|
| 1 | 1 | Einführung XML | 2h | 1.md Zeilen 1-32 |
| 1 | 2 | Syntax-Regeln | 2h | 1.md Zeilen 47-137 |
| 1 | 3 | Dokument-Struktur | 1.5h | 1.md Zeilen 139-165 |
| 1 | 4 | Praktische Beispiele | 1.5h | 1.md Zeilen 168-285 |
| 1 | 5 | Well-formed & Validierung | 1.5h | 1.md + 2.md Zeilen 14-23 |
| 1 | 6 | DTD Basics | 1.5h | 2.md Zeilen 26-164 |
| 1 | 7 | XML Schema (XSD) | 1h | 2.md Zeilen 170-299 |
| **Tag 1 Gesamt** | | | **11h** | |

| 2 | 1 | Validierung | 1h | 2.md + 3.md Zeilen 100-134 |
| 2 | 2 | XPath Basics | 1.5h | 3.md Zeilen 29-118 |
| 2 | 3 | XSLT Einführung | 1.5h | 3.md Zeilen 139-242 |
| 2 | 4 | XSLT Anwendungen | 1.5h | 3.md Zeilen 260-371 |
| 2 | 5 | XML-Parsing | 1h | 4.md Zeilen 252-353 |
| 2 | 6 | Best Practices | 1h | 1.md + 4.md Zeilen 358-418 |
| 2 | 7 | Workshop | 1.5h | - |
| 2 | 8 | Abschluss | 0.5h | - |
| **Tag 2 Gesamt** | | | **8h** | |

**Gesamtzeit:** 19 Stunden (mit Pausen)

---

## Hinweise für den Trainer

1. **Kursgeschwindigkeit anpassen** - Je nach Teilnehmerkenntnissen die Zeit variieren
2. **Praktische Übung priorisieren** - Theorie sollte kurz gehalten werden
3. **XML-Editor zeigen** - Professionelle XML-Editoren erleichtern das Lernen
4. **Vergleich mit HTML** - Nutzen Sie HTML-Vorkenntnisse der Teilnehmer
5. **Beispiele anpassen** - Anwendungsbeispiele an die Teilnehmergruppe anpassen
6. **Validierung demonstrieren** - Zeigen Sie die Fehler beim Validieren
7. **XSLT realistisch bleiben** - Begrenzen Sie XSLT auf HTML-Transformationen
8. **XPath-Beispiele einfach halten** - Fokus auf häufige Abfragen

---

## Anhang: Beispiel-Kursdaten

### Beispiel-XML: Adressbuch
```xml
<?xml version="1.0" encoding="UTF-8"?>
<adressbuch>
  <kontakt id="1">
    <name>Max Mustermann</name>
    <email>max@example.com</email>
    <telefon>+49 123 456789</telefon>
    <adresse>
      <strasse>Hauptstraße 1</strasse>
      <stadt>Berlin</stadt>
      <plz>10115</plz>
    </adresse>
  </kontakt>
  <!-- ... weitere Kontakte ... -->
</adressbuch>
```

### Beispiel-XSD: Adressbuch
```xml
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="adressbuch">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="kontakt" maxOccurs="unbounded">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="name" type="xs:string"/>
              <xs:element name="email" type="xs:string"/>
              <xs:element name="telefon" type="xs:string" minOccurs="0"/>
              <xs:element name="adresse">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="strasse" type="xs:string"/>
                    <xs:element name="stadt" type="xs:string"/>
                    <xs:element name="plz" type="xs:string"/>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
            </xs:sequence>
            <xs:attribute name="id" type="xs:string" use="required"/>
          </xs:complexType>
        </xs:element>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

### Beispiel-XSLT: Adressbuch zu HTML
```xml
<xsl:stylesheet version="1.0"
                xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:output method="html" indent="yes"/>

  <xsl:template match="/">
    <html>
      <head>
        <title>Adressbuch</title>
        <style>
          .kontakt { border: 1px solid #ccc; margin: 10px; padding: 10px; }
          .name { font-weight: bold; color: #333; }
          .label { color: #666; font-weight: bold; }
        </style>
      </head>
      <body>
        <h1>Adressbuch</h1>
        <xsl:apply-templates select="adressbuch/kontakt"/>
      </body>
    </html>
  </xsl:template>

  <xsl:template match="kontakt">
    <div class="kontakt">
      <p class="name"><xsl:value-of select="name"/></p>
      <p><span class="label">Email:</span> <xsl:value-of select="email"/></p>
      <p><span class="label">Telefon:</span> <xsl:value-of select="telefon"/></p>
      <p><span class="label">Adresse:</span></p>
      <ul>
        <li><xsl:value-of select="adresse/strasse"/></li>
        <li><xsl:value-of select="adresse/stadt"/></li>
        <li><xsl:value-of select="adresse/plz"/></li>
      </ul>
    </div>
  </xsl:template>
</xsl:stylesheet>
```