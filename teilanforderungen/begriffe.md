# Begriffe (Modellbildung)

Dieses Dokument definiert die fachlichen Begriffe der Domäne NGHR gemäß Methodik aus
Kapitel 03 „Spezifikation" (Modellbildung: Begriffe):

- **Sprachschablone:** „Ein X ist ein Y, das [Eigenschaften]". Dabei ist *Y* ein bereits
  definierter Begriff; *X* wird über seine wesentlichen Eigenschaften von *Y* abgegrenzt.
- **Gute Definition:** minimal (nur Wesentliches), präzise (zweifelsfrei entscheidbar),
  knapp (ein bis drei Sätze).
- Eine Definition ist **keine Aussage** – sie kann weder wahr noch falsch sein.
- **Regeln** sind *nicht* Teil einer Definition. Sie werden unabhängig formuliert
  (siehe [Regeln.md](Regeln.md)), damit die Begriffe stabil bleiben.
- *Erläuterungen* sind kursiv und von der Definition abgegrenzt.

Die Begriffe sind so geordnet, dass jeder verwendete Begriff *Y* zuvor definiert ist.

## Quellen-Legende

Jeder Begriff ist mit *Quelle:* der Stellungnahme(n) im Fallbeispiel „00 Fallbeispiel NGHR"
versehen, aus der er abgeleitet ist – zur manuellen Nachprüfung.

| Stellungnahme / Abschnitt | Seite |
|---|---|
| Hintergrund / Das Projekt | S. 1 |
| Sabine Schaffmeier – Personalvorstand | S. 1 |
| Richard Reich – Leiter Lohnbuchhaltung | S. 2 |
| Barbara Baumeister – Enterprise Architekt | S. 2–4 |
| Werner Wuchtig – Lohnbuchhaltung | S. 4–5 |
| Lara Lässig – Unternehmensprozesse | S. 5 |
| Ingmar Intim – Datenschutzbeauftragter | S. 5–6 |
| Paul Pinke – Controlling | S. 6–7 |
| Hella Helfer – Allgemeines Personalwesen | S. 7 |
| Karola Kohle – Buchhaltung und Steuern | S. 8 |

---

## 1. Grundbegriffe

### Person

Eine Person ist ein Mensch, mit dem die Sonnenschein AG einen Arbeitsvertrag geschlossen hat
oder geschlossen hatte.

*Quelle: Lara Lässig (Unternehmensprozesse)*

> *Erläuterung:* Dieselbe Person kann im Laufe ihres Lebens mehrfach eingestellt werden und
> ist dann mehreren Mitarbeitern mit je eigener Personalnummer zugeordnet.

### Arbeitsvertrag

Ein Arbeitsvertrag ist eine Vereinbarung zwischen der Sonnenschein AG und einer Person über
ein Arbeitsverhältnis, die insbesondere den Vertragsbeginn und die Gehaltsklasse festlegt.

*Quelle: Lara Lässig (Unternehmensprozesse), Werner Wuchtig (Lohnbuchhaltung)*

> *Erläuterung:* Das Vertragsende wird durch Kündigung oder Auflösungsvertrag bestimmt.

### Mitarbeiter

Ein Mitarbeiter ist eine Person, mit der die Sonnenschein AG genau einen Arbeitsvertrag
geschlossen hat und die dafür durch eine eindeutige Personalnummer identifiziert wird.

*Quelle: Hintergrund / Das Projekt, Lara Lässig (Unternehmensprozesse)*

> *Erläuterung:* Ein Mitarbeiter bleibt auch nach Beendigung des Arbeitsverhältnisses ein
> Mitarbeiter (z. B. als ehemaliger Mitarbeiter oder Rentner). Wird dieselbe Person erneut
> eingestellt, entsteht ein neuer Mitarbeiter mit neuer Personalnummer.

### Personalnummer

Eine Personalnummer ist ein eindeutiger Bezeichner, der einen Mitarbeiter dauerhaft
identifiziert.

*Quelle: Lara Lässig (Unternehmensprozesse), Barbara Baumeister (Enterprise Architekt)*

> *Erläuterung:* Eine Personalnummer wird nie wiederverwendet.

### Arbeitsverhältnis

Ein Arbeitsverhältnis ist die durch einen Arbeitsvertrag begründete Beziehung zwischen der
Sonnenschein AG und einem Mitarbeiter, die mit dem Vertragsbeginn beginnt und mit dem
Vertragsende endet.

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## 2. Lebenszyklus-Status des Mitarbeiters

> Diese Begriffe sind die möglichen Werte des **Mitarbeiterstatus** und damit die Grundlage
> für den Zustandsautomaten.

### Mitarbeiterstatus

Der Mitarbeiterstatus ist eine Eigenschaft eines Mitarbeiters, die seine aktuelle Stellung im
Lebenszyklus des Arbeitsverhältnisses angibt.

*Quelle: Lara Lässig (Unternehmensprozesse), Hella Helfer (Personalwesen), Paul Pinke (Controlling)*

### angelegter Mitarbeiter

Ein angelegter Mitarbeiter ist ein Mitarbeiter, dessen Arbeitsvertrag geschlossen, dessen
Vertragsbeginn aber noch nicht erreicht ist.

*Quelle: Lara Lässig (Unternehmensprozesse)*

### aktiver Mitarbeiter

Ein aktiver Mitarbeiter ist ein Mitarbeiter, dessen Arbeitsverhältnis läuft und für dessen
Gehaltszahlung die Sonnenschein AG selbst (nicht eine ausländische Tochtergesellschaft)
aufkommt.

*Quelle: Lara Lässig (Unternehmensprozesse), Richard Reich (Lohnbuchhaltung)*

> *Erläuterung:* Im aktuellen Projektumfang sind das die Mitarbeiter in Deutschland. Die
> Gehaltsabrechnung für lokal im Ausland angestellte Mitarbeiter ist erst ab Release ≥4
> vorgesehen (siehe Roadmap in [ziele.md](ziele.md)); der Lebenszyklus-Status ändert sich
> dadurch nicht.

### inaktiver Mitarbeiter

Ein inaktiver Mitarbeiter ist ein Mitarbeiter, dessen Arbeitsverhältnis besteht, aber
vorübergehend ruht.

*Quelle: Lara Lässig (Unternehmensprozesse)*

> *Erläuterung:* Gründe sind z. B. Sabbatical, Freistellung aus familiären Gründen oder
> längere Krankheit.

### entsendeter Mitarbeiter

Ein entsendeter Mitarbeiter ist ein Mitarbeiter mit gültigem Arbeitsvertrag in Deutschland,
der befristet ins Ausland entsendet ist und dessen Gehalt währenddessen von einer
ausländischen Tochtergesellschaft gezahlt wird.

*Quelle: Richard Reich (Lohnbuchhaltung)*

> *Erläuterung:* Ein entsendeter Mitarbeiter wird in allen übrigen Belangen wie ein aktiver
> Mitarbeiter behandelt, gilt aber nicht als aktiv, weil die Sonnenschein AG kein Gehalt zahlt.

### ehemaliger Mitarbeiter

Ein ehemaliger Mitarbeiter ist ein Mitarbeiter, dessen Arbeitsverhältnis beendet ist.

*Quelle: Lara Lässig (Unternehmensprozesse), Hella Helfer (Personalwesen)*

> *Erläuterung:* Die Beendigung tritt am Vertragsende ein (nach Kündigung, Auflösungsvertrag
> oder Renteneintritt). Ein ehemaliger Mitarbeiter wird nie mit derselben Personalnummer
> reaktiviert.

### Rentner

Ein Rentner ist ein ehemaliger Mitarbeiter, der in den Ruhestand getreten ist.

*Quelle: Lara Lässig (Unternehmensprozesse), Paul Pinke (Controlling)*

> *Erläuterung:* Rentner werden wegen der Betriebsrente weitergeführt und sind der
> Sammelkostenstelle für Betriebsrenten („Ehem. Schaffer(meier)") zugeordnet.

### verstorbener Mitarbeiter

Ein verstorbener Mitarbeiter ist ein Mitarbeiter, dessen Ableben der Sonnenschein AG bekannt
ist.

*Quelle: Lara Lässig (Unternehmensprozesse), Ingmar Intim (Datenschutzbeauftragter)*

> *Erläuterung:* Das Ableben wird auch für ehemalige Mitarbeiter und Rentner erfasst (wegen
> der Betriebsrente).

---

## 3. Vorgänge am Arbeitsverhältnis

### Kündigung

Eine Kündigung ist die einseitige Erklärung des Mitarbeiters oder der Sonnenschein AG, das
Arbeitsverhältnis zu einem bestimmten Vertragsende zu beenden.

*Quelle: Lara Lässig (Unternehmensprozesse)*

### Auflösungsvertrag

Ein Auflösungsvertrag ist eine Vereinbarung zwischen Mitarbeiter und Sonnenschein AG, das
Arbeitsverhältnis zu einem bestimmten Vertragsende zu beenden.

*Quelle: Lara Lässig (Unternehmensprozesse)*

### Entsendung

Eine Entsendung ist die befristete Versetzung eines aktiven Mitarbeiters an eine ausländische
Tochtergesellschaft der Sonnenschein AG.

*Quelle: Richard Reich (Lohnbuchhaltung)*

---

## 4. Organisation und Controlling

### Kostenstelle

Eine Kostenstelle ist eine organisatorische Einheit, der Kosten zugeordnet werden und für die
genau ein Manager verantwortlich ist.

*Quelle: Paul Pinke (Controlling)*

> *Erläuterung:* Die Hierarchie der Kostenstellen bildet die Organisation ab, da NGHR keine
> eigenen Organisationsdaten kennt. Eine Sonder-Kostenstelle sammelt alle Empfänger von
> Betriebsrenten.

### Manager

Ein Manager ist ein Mitarbeiter, der für mindestens eine Kostenstelle verantwortlich ist und
an den andere Mitarbeiter berichten.

*Quelle: Paul Pinke (Controlling)*

### Manager-Flag

Das Manager-Flag ist eine Eigenschaft eines Mitarbeiters, die angibt, ob er Manager ist.

*Quelle: Hella Helfer (Personalwesen), Barbara Baumeister (Enterprise Architekt)*

### Lohnkostenplan

Ein Lohnkostenplan ist eine im ERP-System geführte Aufstellung, die pro Kostenstelle und
Kalendermonat die voraussichtlichen Lohnkosten enthält.

*Quelle: Paul Pinke (Controlling)*

---

## 5. Gehalt und Gehaltsbestandteile

### Gehaltsklasse

Eine Gehaltsklasse ist eine im Arbeitsvertrag vereinbarte Einstufung eines Mitarbeiters, die
festlegt, wie sich sein monatliches Bruttogehalt und etwaige weitere Zahlungen zusammensetzen.

*Quelle: Werner Wuchtig (Lohnbuchhaltung)*

> *Erläuterung:* Es gibt drei Gehaltsklassen – „Gehalt", „Gehalt und Provision",
> „Gehalt und Bonus". Jeder Mitarbeiter ist genau einer zugeordnet.

### monatliches Bruttogehalt

Das monatliche Bruttogehalt ist der im Arbeitsvertrag vereinbarte Geldbetrag, der einem
Mitarbeiter pro Monat vor Abzügen und Zusatzzahlungen zusteht.

*Quelle: Werner Wuchtig (Lohnbuchhaltung)*

### Vertriebsprovision

Eine Vertriebsprovision ist eine zusätzliche monatliche Zahlung an einen Vertriebsmitarbeiter
in Höhe von 3 % des Gesamtvolumens aller Verträge, die er zwischen dem 16. des Vormonats und
dem 15. des aktuellen Monats abgeschlossen hat.

*Quelle: Werner Wuchtig (Lohnbuchhaltung), Richard Reich (Lohnbuchhaltung)*

### Bonuszahlung

Eine Bonuszahlung ist eine einmal jährlich an einen Manager ausgezahlte Zusatzzahlung, deren
Höhe als Prozentsatz des monatlichen Bruttogehalts von der Geschäftsführung festgelegt wird.

*Quelle: Werner Wuchtig (Lohnbuchhaltung), Richard Reich (Lohnbuchhaltung)*

> *Erläuterung:* Der Prozentsatz wird zu Jahresbeginn für das vergangene Jahr festgelegt und
> mit dem Maigehalt ausgezahlt.

### Gehaltsdaten

Gehaltsdaten sind alle einem Mitarbeiter zugeordneten Daten, die zur Erstellung seiner
Gehaltsabrechnung nötig sind.

*Quelle: Ingmar Intim (Datenschutzbeauftragter), Werner Wuchtig (Lohnbuchhaltung)*

> *Erläuterung:* Dazu gehören insbesondere Gehaltsklasse und monatliches Bruttogehalt.

### Vertrag

Ein Vertrag ist ein im CRM-System erfasster, von einem Vertriebsmitarbeiter abgeschlossener
Kundenvertrag, der zur Berechnung der Vertriebsprovision herangezogen wird.

*Quelle: Richard Reich (Lohnbuchhaltung), Werner Wuchtig (Lohnbuchhaltung)*

---

## 6. Gehaltsabrechnung und Zahlung

### Gehaltsabrechnung

Eine Gehaltsabrechnung ist ein monatliches Dokument, das für einen Mitarbeiter die
Zusammensetzung seiner Bezüge vom Bruttogehalt bis zum Auszahlungsbetrag mit allen
Einzelpositionen ausweist.

*Quelle: Werner Wuchtig (Lohnbuchhaltung), Richard Reich (Lohnbuchhaltung)*

### Gehaltslauf

Ein Gehaltslauf ist die monatliche Verarbeitung, in der NGHR für alle Mitarbeiter die
Gehaltsabrechnungen erstellt und die Gehaltszahlungen auslöst.

*Quelle: Richard Reich (Lohnbuchhaltung), Sabine Schaffmeier (Personalvorstand)*

### Gehaltszahlung

Eine Gehaltszahlung ist die Auszahlung des Auszahlungsbetrags an einen Mitarbeiter am letzten
Wochentag eines Monats.

*Quelle: Werner Wuchtig (Lohnbuchhaltung)*

### Nettogehalt

Das Nettogehalt ist diejenige Position der Gehaltsabrechnung, die sich ergibt, wenn vom
Bruttogehalt die Steuern abgezogen werden.

*Quelle: Werner Wuchtig (Lohnbuchhaltung)*

### Auszahlungsbetrag

Der Auszahlungsbetrag ist diejenige Position der Gehaltsabrechnung, die den tatsächlich an den
Mitarbeiter zu überweisenden Betrag angibt.

*Quelle: Werner Wuchtig (Lohnbuchhaltung)*

> *Erläuterung:* Er ergibt sich aus dem Nettogehalt abzüglich der Sozialversicherungsbeiträge
> zuzüglich der Arbeitgeberanteile (siehe [Regeln.md](Regeln.md)).

### Zahlungsabfluss

Ein Zahlungsabfluss ist eine von NGHR ausgelöste Geldzahlung, aufgeschlüsselt nach
ausgezahltem Gehalt, Steuern oder Sozialversicherungsbeitragsart.

*Quelle: Karola Kohle (Buchhaltung und Steuern), Paul Pinke (Controlling)*

### Betriebsrente

Eine Betriebsrente ist eine Zahlung der Sonnenschein AG an einen Rentner.

*Quelle: Lara Lässig (Unternehmensprozesse), Paul Pinke (Controlling)*

---

## 7. Steuern und Sozialversicherung

### Einkommenssteuer

Die Einkommenssteuer ist eine gesetzliche Steuer, die vom Bruttogehalt eines Mitarbeiters
abgezogen wird.

*Quelle: Karola Kohle (Buchhaltung und Steuern)*

> *Erläuterung:* Grundfreibetrag 16.000 €/Jahr, darüber fester Steuersatz 25 %.

### Solidaritätszuschlag

Der Solidaritätszuschlag ist eine gesetzliche Steuer, die als Prozentsatz der Einkommenssteuer
erhoben wird.

*Quelle: Karola Kohle (Buchhaltung und Steuern)*

> *Erläuterung:* 5,5 % der Einkommenssteuer, erst ab einer jährlichen Einkommenssteuer von
> 18.000 €.

### Grundfreibetrag

Der Grundfreibetrag ist dasjenige Jahresbruttogehalt, das keiner Besteuerung unterliegt.

*Quelle: Karola Kohle (Buchhaltung und Steuern)*

### Sozialversicherungsbeitrag

Ein Sozialversicherungsbeitrag ist ein als Prozentsatz des Bruttoverdienstes bis zur
Beitragsbemessungsgrenze berechneter Abzug für eine gesetzliche Sozialversicherung.

*Quelle: Werner Wuchtig (Lohnbuchhaltung)*

> *Erläuterung:* Vier Arten – Kranken (14 %), Pflege (4,5 %), Arbeitslosen (5 %),
> Renten (21 %).

### Beitragsbemessungsgrenze (BBM)

Die Beitragsbemessungsgrenze ist das Jahresbruttogehalt, bis zu dem Sozialversicherungsbeiträge
zu zahlen sind.

*Quelle: Werner Wuchtig (Lohnbuchhaltung)*

> *Erläuterung:* Für jeden Euro bis einschließlich der BBM der jeweilige Prozentsatz, darüber
> nichts. Kranken-/Pflegeversicherung: 63.000 €; Arbeitslosen-/Rentenversicherung: 94.000 €.

### Arbeitgeberanteil

Der Arbeitgeberanteil ist der von der Sonnenschein AG getragene Anteil an einem
Sozialversicherungsbeitrag in Höhe der Hälfte des Beitrags.

*Quelle: Werner Wuchtig (Lohnbuchhaltung)*

### Gesamtlohnkosten

Die Gesamtlohnkosten eines Mitarbeiters sind die Summe aus seinem Bruttogehalt und den
Arbeitgeberanteilen der Sozialversicherungsbeiträge.

*Quelle: Werner Wuchtig (Lohnbuchhaltung)*

---

## 8. Benutzer, Rollen und Daten

### User

Ein User ist ein im Identity-Provider I&B geführter Benutzerzugang, der einem Mitarbeiter die
Anmeldung an den angebundenen Anwendungen ermöglicht.

*Quelle: Barbara Baumeister (Enterprise Architekt)*

### User ID

Eine User ID ist der eindeutige Bezeichner eines Users, der aus der Personalnummer des
Mitarbeiters durch Voranstellen des Buchstabens „U" gebildet wird.

*Quelle: Barbara Baumeister (Enterprise Architekt)*

### Rolle

Eine Rolle ist eine zentral in I&B gepflegte Berechtigungszuordnung, die festlegt, welche
Tätigkeiten ein User in den angebundenen Anwendungen ausführen darf.

*Quelle: Barbara Baumeister (Enterprise Architekt)*

> *Erläuterung:* Rollen sind u. a. Mitarbeiter, Manager, Personalwesen, Lohnbuchhaltung,
> Recruiting.

### unkritische Daten

Unkritische Daten sind diejenigen Mitarbeiterdaten, die ein Mitarbeiter selbst pflegen darf:
Adresse, Bankverbindung und Krankenkasse.

*Quelle: Hella Helfer (Personalwesen)*

---

## Abgrenzung

Systeme (z. B. I&B, ERP-System, CRM-System, Mitarbeiterportal) und Anwendergruppen
(z. B. Lohnbuchhaltung, Personalwesen, Recruiting) sind **Akteure** und gehören in den
[Kontext](kontext.md). Hier sind sie nur insoweit erwähnt, wie sie zur Definition eines
fachlichen Begriffs nötig sind.
