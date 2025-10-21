E-Commerce Commercial Controller Rechner

Dieses Tool dient E-Commerce Controllern zur dynamischen Berechnung und Sensitivitätsanalyse der Logistik- und Versandkosten in Relation zum Nettoumsatz. Es nutzt eine Netto-Basis-Logik, d.h., das Ziel sind die netto verkauften Artikel, aus denen die benötigten Brutto-Lieferungen und Retouren abgeleitet werden.

🚀 Installation und Start

Da das gesamte Projekt in einer einzigen HTML-Datei (ecommerce_controller_tool.html) enthalten ist und keine externen Abhängigkeiten (außer Tailwind CSS via CDN) hat:

Repository klonen: Laden Sie die Datei herunter oder klonen Sie das Repository von GitHub.

Datei öffnen: Öffnen Sie die Datei ecommerce_controller_tool.html direkt in Ihrem Browser (Chrome, Firefox etc.).

Die Berechnungen erfolgen sofort und dynamisch, sobald Sie einen Wert in den Eingabefeldern ändern.

⚙️ Kernlogik und Berechnungen

Das Tool basiert auf der Eingabe des Netto-Verkaufsziels und der Retourenquote (auf Brutto-Basis):

Abgeleitete Metriken

Metrik

Formel

Brutto bestellte Artikel

Netto-Ziel / (1 - Retourenquote)

Bestellvolumen (Sendungen)

Brutto bestellte Artikel / Artikel pro Bestellung (IPO)

Zahl der Retouren (Artikel)

Brutto bestellte Artikel - Netto-Ziel

Anzahl Retourensendungen

Zahl der Retouren (Artikel) / Artikel pro Retourensendung (IPR)

Detaillierte Kostenberechnung

Die Gesamtkosten setzen sich aus 7 Einzelpositionen zusammen, die auf den oben abgeleiteten Brutto- und Sendungswerten basieren:

Kostenposition

Basis

Berechnung

Versand (Outbound)

Bestellvolumen

Bestellvolumen * Kosten pro Bestellung

Versand (Retouren)

Retourensendungen

Retourensendungen * Kosten pro Sendung

Auftragsverarbeitung / Kartonage

Bestellvolumen

Bestellvolumen * Kosten pro Bestellung

Pick & Pack

Brutto bestellte Artikel

Brutto-Artikel * Kosten pro Artikel

Warenannahme

Brutto bestellte Artikel

Brutto-Artikel * Kosten pro Artikel

Retoure inkl. Aufbereitung

Retouren (Artikel)

Retouren-Artikel * Kosten pro retourniertem Artikel

Lagerung

Brutto bestellte Artikel

Brutto-Artikel * Kosten pro Artikel * Lagerdauer (Monate)

📊 Sensitivitätsanalyse

Die Matrix am Ende des Tools zeigt, wie sich die Logistikkosten in Prozent des Nettoumsatzes verändern, wenn sich die zwei wichtigsten Hebel (Durchschnitts-VK und Retourenquote) verändern.

Farbkodierung:

Blau: Basis-Szenario (Ihre eingegebenen Werte).

Grün: Besser als das Basis-Szenario (niedrigere prozentuale Kosten).

Rot: Schlechter als das Basis-Szenario (höhere prozentuale Kosten).

💡 Ausblick: Business Case Builder (Modulare Erweiterung)

Für die nächste Stufe (den allgemeinen Business Case Builder) wird dringend empfohlen, die gesamte Logik aus dem <script>-Block in eine separate Datei (calculator.js) auszulagern, um die Funktion getLogisticsCostPercent() einfacher in andere Berechnungen einzubinden (z.B. in einen Gesamt-Deckungsbeitrag-Rechner).
