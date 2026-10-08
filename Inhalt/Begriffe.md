# Begriffe

## Mitarbeiter

Ein Mitarbeiter ist eine Person, die einen Arbeitsvertrag mit der Sonnenschein AG
geschlossen hat und im NGHR-System geführt wird.

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## Person

Eine Person ist ein Mensch, der mit der Sonnenschein AG in Kontakt tritt, ohne
notwendigerweise einen Arbeitsvertrag zu haben.

> *Erläuterung:* Der Begriff „Person" wird im Fallbeispiel ausschließlich im Kontext des
> Vertragsabschlusses verwendet: „eine Person schließt einen Arbeitsvertrag mit der
> Sonnenschein AG ab." Sobald der Vertrag besteht, wird die Person als Mitarbeiter geführt.

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## Personalnummer

Eine Personalnummer ist eine eindeutige Kennung, die einem Mitarbeiter bei seiner
Anlage im System dauerhaft zugewiesen wird.

> *Erläuterung:* Die Personalnummer wird bei Vertragsabschluss vergeben. Sie wird nie
> wiederverwendet: wenn dieselbe Person ein zweites Mal eingestellt wird, erhält sie eine
> neue Personalnummer.

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## Arbeitsvertrag

Ein Arbeitsvertrag ist eine rechtliche Vereinbarung zwischen einer Person und der
Sonnenschein AG, die ein Arbeitsverhältnis begründet und dessen Beginn- sowie
ggf. Enddatum festlegt.

> *Erläuterung:* Der Arbeitsvertrag enthält auch die Gehaltsklasse des Mitarbeiters. Es gab
> Fälle, in denen der Vertrag erst am ersten Arbeitstag geschlossen wurde.

*Quelle: Lara Lässig (Unternehmensprozesse), Werner Wuchtig (Lohnbuchhaltung)*

---

## Arbeitsverhältnis

Ein Arbeitsverhältnis ist der durch einen Arbeitsvertrag begründete Zustand zwischen
einem Mitarbeiter und der Sonnenschein AG, der mit dem Vertragsbeginn aktiv wird
und mit dem Vertragsende endet.

> *Erläuterung:* Lara Lässig betont ausdrücklich: „Hier müssen wir genau unterscheiden
> zwischen der Kündigung oder dem Zustandekommen eines Auflösungsvertrags und der
> tatsächlichen Beendigung des Arbeitsverhältnisses. Das darf man nicht
> durcheinanderbringen."

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## Vertragsbeginn

Der Vertragsbeginn ist das im Arbeitsvertrag festgelegte Datum, ab dem das
Arbeitsverhältnis aktiv wird.

> *Erläuterung:* Mit dem Vertragsbeginn wird der Mitarbeiter im System automatisch auf
> „aktiv" gesetzt. Analog dazu wird am Vertragsende der Status geändert.

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## Kündigungsdatum

Das Kündigungsdatum ist das im Arbeitsvertrag oder in der Kündigung festgelegte
Datum, an dem das Arbeitsverhältnis endet.

> *Erläuterung:* Das Kündigungsdatum ist nicht das Datum der Kündigung selbst, sondern
> das Datum der tatsächlichen Beendigung. Bis zu diesem Datum bleibt der Mitarbeiter in
> seinem aktuellen Status und erhält weiterhin Gehalt.

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## Auflösungsvertrag

Ein Auflösungsvertrag ist eine Vereinbarung zwischen Mitarbeiter und Sonnenschein
AG, die das Arbeitsverhältnis zu einem festgelegten Enddatum einvernehmlich
beendet.

> *Erläuterung:* Der Auflösungsvertrag ist neben der Arbeitgeber- und Arbeitnehmerkündigung
> einer der drei Beendigungsgründe eines Arbeitsverhältnisses. Das im Auflösungsvertrag
> festgehaltene Enddatum des Arbeitsverhältnisses löst den Übergang in den Status
> „ehemalig" aus.

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## Letzte Gehaltszahlung

Die letzte Gehaltszahlung ist die zeitlich zuletzt erfolgte Gehaltszahlung der
Sonnenschein AG an einen Mitarbeiter.

> *Erläuterung:* Das Datum der letzten Gehaltszahlung ist relevant für die
> Datenschutzlöschfrist: alle personenbezogenen Daten eines Mitarbeiters werden gelöscht,
> wenn seit der letzten Gehaltszahlung mindestens zehn Jahre vergangen sind.

*Quelle: Ingmar Intim (Datenschutzbeauftragter)*

---

## Ablebedatum

Das Ablebedatum ist das Datum, an dem der Sonnenschein AG das Ableben eines
Mitarbeiters oder ehemaligen Mitarbeiters bekannt wird.

> *Erläuterung:* Das Ablebedatum löst den Übergang in den Status „verstorben" aus. Es ist
> zudem Startpunkt der Datenschutzlöschfrist von fünf Jahren.

*Quelle: Ingmar Intim (Datenschutzbeauftragter), Lara Lässig (Unternehmensprozesse)*

---

## ERP-System

Das ERP-System ist ein unternehmensweites IT-System der Sonnenschein AG, das
für Controlling, Buchhaltung und Kostenstellenverwaltung zuständig ist und bei
Zustandswechseln eines Mitarbeiters von NGHR benachrichtigt wird.

> *Erläuterung:* Das ERP-System empfängt von NGHR Informationen zu jedem
> Zustandswechsel eines Mitarbeiters, damit die aktiven Mitarbeiter tagesgenau den
> Kostenstellen zugeordnet werden können.

*Quelle: Paul Pinke (Controlling), Barbara Baumeister (Enterprise Architekt)*

---

## I&B (Identität und Berechtigungen)

I&B ist ein zentraler Identity-Provider der Sonnenschein AG, der für die
Authentifizierung, das Single-Sign-On und die Verteilung von Benutzerrollen an
alle angebundenen Anwendungen zuständig ist.

> *Erläuterung:* NGHR ruft I&B auf, um bei Vertragsabschluss einen User anzulegen, bei
> Vertragsbeginn den User zu aktivieren und bei Vertragsende den User zu deaktivieren.
> Die User ID wird in I&B aus der Personalnummer erzeugt, indem der Buchstabe „U"
> vorangestellt wird.

*Quelle: Barbara Baumeister (Enterprise Architekt)*

---

## Gehaltslauf

Ein Gehaltslauf ist die monatliche Berechnung und Auszahlung der Gehälter aller
aktiven Mitarbeiter der Sonnenschein AG.

> *Erläuterung:* Aktive Mitarbeiter werden in den Gehaltslauf aufgenommen; beim Verlassen
> des Status „aktiv" werden sie daraus entfernt. Der Gehaltslauf erfolgt am letzten
> Wochentag eines Monats.

*Quelle: Werner Wuchtig (Lohnbuchhaltung), Richard Reich (Leiter Lohnbuchhaltung)*

---

## Sabbatical

Ein Sabbatical ist eine befristete Freistellung eines Mitarbeiters vom Dienst, die von
der Sonnenschein AG angeboten wird und das Arbeitsverhältnis vorübergehend ruhen
lässt.

> *Erläuterung:* Ein Mitarbeiter im Sabbatical wechselt in den Status „inaktiv". Bei Rückkehr
> aus dem Sabbatical wird er wieder „aktiv".

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## Freistellung

Eine Freistellung ist die vorübergehende Befreiung eines Mitarbeiters von seiner
Arbeitspflicht bei fortbestehendem Arbeitsverhältnis.

> *Erläuterung:* Lara Lässig nennt als Beispiel familiäre Gründe. Eine Freistellung versetzt
> den Mitarbeiter in den Status „inaktiv". Das Arbeitsverhältnis besteht weiter; der Mitarbeiter
> kehrt nach Ablauf der Freistellung zurück.

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## Längere Krankheit

Eine längere Krankheit ist eine Erkrankung eines Mitarbeiters, die das
Arbeitsverhältnis vorübergehend ruhen lässt.

> *Erläuterung:* Das Fallbeispiel nennt „längere Krankheit" als einen der Gründe, warum ein
> Mitarbeiter in den Status „inaktiv" wechselt. Eine genaue Mindestdauer ist im Fallbeispiel
> nicht definiert.

*Quelle: Lara Lässig (Unternehmensprozesse)*

---

## Tochtergesellschaft (ausländisch)

Eine ausländische Tochtergesellschaft ist eine rechtlich selbstständige
Niederlassung der Sonnenschein AG im Ausland, die für entsendete Mitarbeiter die
Gehaltszahlung übernimmt.

> *Erläuterung:* „Bei entsendeten Mitarbeitern übernimmt unsere Tochtergesellschaft im
> Ausland die Gehaltszahlung." Dies ist der ausschlaggebende Unterschied zwischen dem
> Status „entsendet" und dem Status „aktiv".

*Quelle: Richard Reich (Leiter Lohnbuchhaltung)*
