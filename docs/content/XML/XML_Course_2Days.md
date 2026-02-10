# XML 2-Tage-Kurs für Anfänger

!!! abstract "Zielgruppe"
    - Teilnehmer mit grundlegenden Kenntnissen in HTML, CSS und JavaScript
    - Keine XML-Erfahrung erforderlich

!!! abstract "Lernziele"
    Nach diesem Kurs kannst du …
    - XML-Dokumente korrekt erstellen und strukturieren
    - XML-Validierung mit DTD und XML Schema verstehen
    - XML-Daten lesen und verarbeiten
    - XML in Anwendungen (Java, Python) nutzen
    - XML für echte Anwendungen einsetzen

---

## Kurs-Übersicht

| Tag | Thema | Zeit | Schwerpunkt |
|-----|-------|------|------------|
| **Tag 1** | XML Grundlagen | 6-7 Stunden | Syntax, Struktur, Well-formedness |
| **Tag 2** | XML Validierung & Verarbeitung | 6-7 Stunden | DTD/XSD, XPath, XML in Code |

---

## Tag 1: XML Grundlagen

### 09:00 - 09:30: Einführung

**Lernziele:**
- Was ist XML und wofür wird es verwendet?
- XML vs. HTML: Die wichtigsten Unterschiede

**Themen:**
1. **XML Überblick**
   - Definition und Anwendungsbereiche
   - Konfigurationsdateien (pom.xml, config.xml)
   - Datenaustausch (REST API, SOAP)
   - Dokumentformate (SVG, DOCX)

2. **XML vs. HTML**
   - Vergleichstabelle (siehe Kursmaterial)

**Praktische Übung:**
- Unterschiede zwischen HTML und XML identifizieren

---

### 09:30 - 10:45: XML-Syntax

**Lernziele:**
- XML-Syntax-Regeln anwenden
- Wohlgeformtes XML erstellen

**Themen:**
1. **Grundlegende Syntax**
   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <root>
     <!-- Inhalt -->
   </root>
   ```

2. **Wichtige Regeln**
   - ✅ Genau ein Wurzelelement
   - ✅ Alle Tags müssen geschlossen werden
   - ✅ Groß-/Kleinschreibung beachten
   - ✅ Attribute in Anführungszeichen
   - ✅ Korrekte Verschachtelung
   - ✅ Kommentare mit `<!-- -->`

3. **Attribute vs. Elemente**
   ```xml
   <!-- Metadaten → Attribute -->
   <person id="1" status="aktiv">

   <!-- Strukturierte Daten → Elemente -->
   <adresse>
     <strasse>Hauptstraße 1</strasse>
     <stadt>Berlin</stadt>
     <plz>10115</plz>
   </adresse>
   ```

**Praktische Übung:**
- XML-Beispiele korrigieren (5-10 Übungen)
- Eigene XML-Datei erstellen

---

### 10:45 - 11:00: Kaffeepause

---

### 11:00 - 12:15: XML-Struktur & Praxis

**Lernziele:**
- XML-Dokumentstruktur verstehen
- Praktische Beispiele erstellen

**Themen:**
1. **Dokumentstruktur**
   - XML-Deklaration (version, encoding)
   - Wurzelelement
   - Elemente und Text
   - CDATA für Sonderzeichen

2. **Praktische Beispiele**
   ```xml
   <!-- Adressbuch -->
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
   </adressbuch>

   <!-- Produktliste -->
   <?xml version="1.0" encoding="UTF-8"?>
   <produktliste>
     <produkt id="1001" kategorie="elektronik">
       <name>Laptop</name>
       <preis>1299.99</preis>
     </produkt>
   </produktliste>
   ```

3. **Häufige Fehler**
   - Fehlendes Wurzelelement
   - Falsche Verschachtelung
   - Fehlende Anführungszeichen
   - Ungültige Zeichen in Attributen

**Praktische Übung:**
- Adressbuch XML erstellen
- Konfigurationsdatei erstellen
- Produktliste erstellen

---

### 12:15 - 13:30: Mittagspause

---

### 13:30 - 14:45: Well-formedness & Validierung (Grundlagen)

**Lernziele:**
- Well-formed XML erkennen
- Einfache Validierung verstehen

**Themen:**
1. **Well-formed XML Checkliste**
   - [ ] Genau ein Wurzelelement
   - [ ] Alle Tags geschlossen
   - [ ] Groß-/Kleinschreibung beachtet
   - [ ] Attribute in Anführungszeichen
   - [ ] Korrekte Verschachtelung

2. **Validierung Grundlagen**
   - Was ist Validierung?
   - Unterschied: Well-formed vs. Valid
   - DTD vs. XML Schema

**Praktische Übung:**
- XML-Dateien validieren (6-10 Übungen)
- Fehler identifizieren und korrigieren

---

### 14:45 - 15:00: Kaffeepause

---

### 15:00 - 16:00: Zusammenfassung Tag 1

**Themen:**
- Wiederholung der wichtigsten Regeln
- Q&A
- Hausaufgabe: 2-3 eigene XML-Dateien erstellen

---

## Tag 2: XML Validierung & Verarbeitung

### 09:00 - 10:15: DTD (Document Type Definition)

**Lernziele:**
- DTD für einfache Validierung nutzen
- Elemente und Attribute definieren

**Themen:**
1. **Was ist eine DTD?**
   - Definition der erlaubten Struktur
   - Unterschied zu XML Schema

2. **Interne DTD**
   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE adressbuch [
     <!ELEMENT adressbuch (kontakt+)>
     <!ELEMENT kontakt (name, email, telefon, adresse)>
     <!ELEMENT name (#PCDATA)>
     <!ELEMENT email (#PCDATA)>
     <!ELEMENT telefon (#PCDATA)>
     <!ELEMENT adresse (strasse, stadt, plz)>
     <!ELEMENT strasse (#PCDATA)>
     <!ELEMENT stadt (#PCDATA)>
     <!ELEMENT plz (#PCDATA)>
     <!ATTLIST kontakt id CDATA #REQUIRED>
   ]>
   ```

3. **DTD-Elemente**
   - `<!ELEMENT name (#PCDATA)>` - Textinhalt
   - `<!ELEMENT br EMPTY>` - Leeres Element
   - `<!ELEMENT artikel (titel, autor)>` - Unterelemente
   - `<!ELEMENT liste (item+)>` - Wiederholung (min. 1x)
   - `<!ELEMENT option (titel?)>` - Optional (0 oder 1x)

4. **DTD-Attribute**
   - `<!ATTLIST kontakt id CDATA #REQUIRED>` - Pflicht-Attribut
   - `<!ATTLIST kontakt status CDATA #IMPLIED>` - Optional
   - `<!ATTLIST kontakt aktiv (ja | nein) "ja">` - Aufzählung mit Standard

**Praktische Übung:**
- Eigene DTD erstellen und verwenden
- Validierung von XML mit DTD

---

### 10:15 - 10:30: Kaffeepause

---

### 10:30 - 11:45: XML Schema (XSD)

**Lernziele:**
- XSD für komplexe Validierung nutzen
- Datentypen verstehen

**Themen:**
1. **Was ist XML Schema?**
   - Moderner als DTD
   - Bessere Typsicherheit
   - Namespace-Support

2. **Grundlegende Struktur**
   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">

     <xs:element name="adressbuch">
       <xs:complexType>
         <xs:sequence>
           <xs:element name="kontakt" maxOccurs="unbounded"/>
         </xs:sequence>
       </xs:complexType>
     </xs:element>

   </xs:schema>
   ```

3. **Einfache Typen**
   - `xs:string` - Zeichenkette
   - `xs:integer` - Ganzzahl
   - `xs:decimal` - Dezimalzahl
   - `xs:dateTime` - Datumszeit

4. **Einschränkungen (Restrictions)**
   ```xml
   <!-- Bereich -->
   <xs:simpleType name="alterType">
     <xs:restriction base="xs:integer">
       <xs:minInclusive value="0"/>
       <xs:maxInclusive value="120"/>
     </xs:restriction>
   </xs:simpleType>

   <!-- Aufzählung -->
   <xs:simpleType name="statusType">
     <xs:restriction base="xs:string">
       <xs:enumeration value="neu"/>
       <xs:enumeration value="aktiv"/>
       <xs:enumeration value="inaktiv"/>
     </xs:restriction>
   </xs:simpleType>

   <!-- Muster -->
   <xs:simpleType name="emailType">
     <xs:restriction base="xs:string">
       <xs:pattern value="[^@]+@[^\.]+\..+"/>
     </xs:restriction>
   </xs:simpleType>
   ```

**Praktische Übung:**
- XSD für Adressbuch erstellen
- Validierung von XML mit XSD

---

### 11:45 - 12:00: Kaffeepause

---

### 12:00 - 13:15: XML-Parsing Grundlagen

**Lernziele:**
- XML in Java und Python auslesen
- Grundlegende Parsing-Techniken

**Themen:**
1. **DOM Parsing (Java)**
   ```java
   import javax.xml.parsers.*;
   import org.w3c.dom.*;

   public class XMLParser {
       public static void main(String[] args) throws Exception {
           DocumentBuilderFactory factory =
               DocumentBuilderFactory.newInstance();
           Document doc = factory.newDocumentBuilder()
               .parse(new File("adressbuch.xml"));

           NodeList kontakte = doc.getElementsByTagName("kontakt");

           for (int i = 0; i < kontakte.getLength(); i++) {
               Element kontakt = (Element) kontakte.item(i);
               String name = kontakt.getElementsByTagName("name")
                   .item(0).getTextContent();
               System.out.println("Name: " + name);
           }
       }
   }
   ```

2. **ElementTree (Python)**
   ```python
   import xml.etree.ElementTree as ET

   tree = ET.parse('adressbuch.xml')
   root = tree.getroot()

   for kontakt in root.findall('kontakt'):
       name = kontakt.find('name').text
       email = kontakt.find('email').text
       print(f"{name}: {email}")
   ```

**Praktische Übung:**
- XML mit Java auslesen
- XML mit Python auslesen

---

### 13:15 - 14:30: Mittagspause

---

### 14:30 - 15:30: XPath Grundlagen

**Lernziele:**
- XPath für XML-Abfragen verwenden
- Selektoren verstehen

**Themen:**
1. **XPath-Syntax**
   ```xpath
   /              # Wurzelelement
   //             # Alle Elemente im Dokument
   @              # Attribut-Referenz
   .              # Aktuelles Element
   ..             # Eltern-Element
   ```

2. **Beispiele**
   ```xpath
   /adressbuch/kontakt          # Alle Kontakte unter adressbuch
   //kontakt                    # Alle Kontakte im Dokument
   //kontakt[@id='1']           # Kontakt mit id='1'
   //kontakt/name               # Alle Namen aller Kontakte
   /adressbuch/kontakt[1]       # Erster Kontakt
   //kontakt[last()]            # Letzter Kontakt
   //kontakt[status='aktiv']    # Alle aktiven Kontakte
   ```

3. **XPath in Java**
   ```java
   import javax.xml.xpath.*;

   XPath xpath = XPathFactory.newInstance().newXPath();
   String expression = "//kontakt[@id='1']/name";
   NodeList nodes = (NodeList) xpath.evaluate(
       expression, doc, XPathConstants.NODESET);

   for (int i = 0; i < nodes.getLength(); i++) {
       System.out.println(nodes.item(i).getTextContent());
   }
   ```

**Praktische Übung:**
- 10 verschiedene XPath-Abfragen schreiben
- XPath in Java ausprobieren

---

### 15:30 - 16:00: Einfache XSLT Transformation

**Lernziele:**
- XML in HTML transformieren
- Einfache XSLT-Elemente nutzen

**Themen:**
1. **XSLT Grundstruktur**
   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <xsl:stylesheet version="1.0"
     xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

     <xsl:output method="html" indent="yes"/>

     <xsl:template match="/">
       <html>
         <body>
           <h1>Adressbuch</h1>
           <xsl:apply-templates select="adressbuch/kontakt"/>
         </body>
       </html>
     </xsl:template>

     <xsl:template match="kontakt">
       <div class="kontakt">
         <h2><xsl:value-of select="name"/></h2>
         <p>Email: <xsl:value-of select="email"/></p>
         <xsl:if test="telefon">
           <p>Telefon: <xsl:value-of select="telefon"/></p>
         </xsl:if>
       </div>
     </xsl:template>

   </xsl:stylesheet>
   ```

2. **Wichtige XSLT-Elemente**
   - `<xsl:value-of>` - Wert ausgeben
   - `<xsl:for-each>` - Schleife über Elemente
   - `<xsl:if>` - Bedingte Ausgabe
   - `<xsl:apply-templates>` - Templates anwenden

**Praktische Übung:**
- XSLT für Adressbuch erstellen
- XML → HTML Transformation durchführen

---

### 16:00 - 16:30: Abschluss & Präsentation

**Themen:**
- Wiederholung der wichtigsten Konzepte
- Kurze Präsentationen der Ergebnisse
- Q&A
- Kurs-Zertifikate

---

## Abschlusspraktische Aufgabe

### Aufgabe 1: Adressbuch XML & XSD
- [ ] XML-Datei mit 5 Kontakten erstellen
- [ ] XSD-Datei für das Adressbuch erstellen
- [ ] XML validieren

### Aufgabe 2: Datenvalidierung
- [ ] E-Mail-Prüfung im XSD (Pattern)
- [ ] Alter zwischen 0-120
- [ ] Telefonnummer Format prüfen

### Aufgabe 3: XPath Abfragen
- [ ] Alle Kontakte aus Berlin
- [ ] Alle Kontakte mit E-Mail
- [ ] Kontakte älter als 25

### Aufgabe 4: XSLT Transformation
- [ ] XML → HTML Tabelle erstellen
- [ ] Sortierung nach Name
- [ ] Formatierung mit CSS

---

## Assessment-Kriterien

### Erfolgreich absolviert, wenn du …

**Tag 1:**
- ✅ XML-Syntax-Regeln korrekt anwendest
- ✅ Wohlgeformtes XML erstellst
- ✅ Attribute vs. Elemente richtig zuordnest
- ✅ Häufige Fehler vermeidest

**Tag 2:**
- ✅ DTD/XSD erstellen und nutzen kannst
- ✅ XML mit Java oder Python auslesen kannst
- ✅ XPath-Abfragen schreibst
- ✅ XML in HTML transformieren kannst

---

## Zeitplanübersicht

| Block | Zeit | Thema | Art |
|-------|------|-------|-----|
| Tag 1 | 09:00-09:30 | Einführung | Theorie |
| Tag 1 | 09:30-10:45 | XML-Syntax | Theorie + Praxis |
| Tag 1 | 11:00-12:15 | XML-Struktur | Praxis |
| Tag 1 | 13:30-14:45 | Validierung Grundlagen | Theorie + Praxis |
| Tag 1 | 15:00-16:00 | Zusammenfassung | Review |
| Tag 2 | 09:00-10:15 | DTD | Theorie + Praxis |
| Tag 2 | 10:30-11:45 | XML Schema | Theorie + Praxis |
| Tag 2 | 12:00-13:15 | XML-Parsing | Praxis |
| Tag 2 | 14:30-15:30 | XPath | Theorie + Praxis |
| Tag 2 | 15:30-16:00 | XSLT | Theorie + Praxis |
| Tag 2 | 16:00-16:30 | Abschluss | Präsentation |

**Gesamtzeit: 12-14 Stunden (2 Tage)**

---

## Ressourcen

### Dokumentation
- [MDN Web Docs - XML](https://developer.mozilla.org/de/docs/Web/XML)
- [W3Schools XML Tutorial](https://www.w3schools.com/xml/)

### Tools
- XML Validator Online
- Online XML Formatter

### Beispiele
- Adressbuch XML-Beispiele
- Produktlisten
- Konfigurationsdateien

---

## Notizen

### Tag 1 Notizen
<!-- Platz für Notizen -->

### Tag 2 Notizen
<!-- Platz für Notizen -->

---

**Kursautor:** [Dein Name]
**Datum:** [Datum]
**Dauer:** 2 Tage
**Teilnehmer:** [Anzahl]
**Status:** [In Planung / Ausgebucht / Abgehalten]