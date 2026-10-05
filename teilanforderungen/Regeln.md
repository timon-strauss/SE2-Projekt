# Regeln (Modellbildung)

Dieses Dokument spezifiziert die fachlichen Regeln der Domäne NGHR gemäß Methodik aus
Kapitel 03 „Spezifikation" (Modellbildung: Regeln, S. 22–29).

## Methodik (belegbar aus der Spezifikation)

- **Definition (S. 24):** „Eine fachliche Regel ist ein atomares Stück wiederverwendbarer
  Entscheidungslogik, das deklarativ in fachlicher Sprache spezifiziert ist."
  - *atomar* – nicht weiter reduzierbar ohne Bedeutungsverlust
  - *wiederverwendbar* – an vielen Stellen und in Systemen nutzbar
  - *deklarativ* – beschreibt **nicht** das Wie/Wo/Wann der Umsetzung (nicht prozedural)
  - *fachliche Sprache* – Sprache der Anwender, kein Code
- Regeln sind **Aussagen** und können wahr oder falsch sein – anders als Begriffe. Sie sind
  **nicht Teil der Definitionen** (S. 23); die Begriffe stehen in [begriffe.md](begriffe.md).
- **Formulierungsregeln (S. 27–29):**
  - **Indikativ, Präsens, Aktiv** – das handelnde Subjekt wird benannt (S. 27).
  - **Begriffe exakt referenzieren**, nicht abkürzen (S. 27).
  - „oder"/„und" **explizit** auflösen; **„Wenn … dann" vermeiden** (sonst prozedural) (S. 28).
  - **Kein „Können"** (das ist eine Option, keine Regel); keine impliziten/fehlenden Fakten;
    kein „Overkill" (S. 29). *Ausnahme:* Lese-/Zugriffsrechte werden als „dürfen … einsehen"
    formuliert – so wie es die Spezifikation selbst auf S. 26 vormacht.

## Quellen-Legende (Fallbeispiel „00 Fallbeispiel NGHR")

| Stellungnahme / Abschnitt | Seite |
|---|---|
| Sabine Schaffmeier – Personalvorstand | S. 1 |
| Richard Reich – Leiter Lohnbuchhaltung | S. 2 |
| Barbara Baumeister – Enterprise Architekt | S. 2–4 |
| Werner Wuchtig – Lohnbuchhaltung | S. 4–5 |
| Lara Lässig – Unternehmensprozesse | S. 5 |
| Ingmar Intim – Datenschutzbeauftragter | S. 5–6 |
| Paul Pinke – Controlling | S. 6–7 |
| Hella Helfer – Allgemeines Personalwesen | S. 7 |
| Karola Kohle – Buchhaltung und Steuern | S. 8 |

> Regel-IDs (A1, B2, …) dienen der Nachverfolgung und der späteren Zuordnung zu
> Zustandsübergängen im Zustandsautomaten.

---

## A. Lebenszyklus des Mitarbeiters

> Dies ist die Grundlage für den **Zustandsautomaten**. Die Zustände sind in
> [begriffe.md](begriffe.md) Abschnitt 2 definiert.

**A1** – Der Recruiter legt bei Abschluss eines Arbeitsvertrags einen Mitarbeiter an; der
Mitarbeiter erhält den Status *angelegt*.
*Quelle: Lara Lässig (S. 5), Hella Helfer (S. 7)*

**A2** – NGHR benachrichtigt I&B bei Vertragsabschluss, damit I&B einen User für den
Mitarbeiter erzeugt.
*Quelle: Barbara Baumeister (S. 3)*

**A3** – NGHR setzt einen angelegten Mitarbeiter am Vertragsbeginn auf den Status *aktiv*.
*Quelle: Lara Lässig (S. 5)*

**A4** – Liegt der Vertragsbeginn am Tag des Vertragsabschlusses oder davor, setzt NGHR den
Mitarbeiter unmittelbar bei der Anlage auf *aktiv*.
*Quelle: Lara Lässig (S. 5 – „Vertrag am ersten Arbeitstag geschlossen")*

**A5** – NGHR benachrichtigt I&B am Vertragsbeginn, den User des Mitarbeiters zu aktivieren.
*Quelle: Barbara Baumeister (S. 3)*

**A6** – Das Personalwesen setzt einen aktiven Mitarbeiter bei Sabbatical, familiärer
Freistellung oder längerer Krankheit auf den Status *inaktiv*.
*Quelle: Lara Lässig (S. 5)*

**A7** – Das Personalwesen setzt einen aktiven Mitarbeiter bei Beginn einer Entsendung auf den
Status *entsendet*.
*Quelle: Richard Reich (S. 2)*

**A8** – Ein entsendeter Mitarbeiter wird in allen Belangen wie ein aktiver Mitarbeiter
behandelt, mit Ausnahme der Gehaltszahlung, die die ausländische Tochtergesellschaft
übernimmt.
*Quelle: Richard Reich (S. 2)*

**A9** – Bei Kündigung oder Auflösungsvertrag behält der Mitarbeiter bis zum Vertragsende
seinen aktuellen Status; bis dahin bezieht er weiter Gehalt und behält seinen User.
*Quelle: Lara Lässig (S. 5)*

**A10** – NGHR setzt den Mitarbeiter am Vertragsende auf den Status *ehemaliger Mitarbeiter*.
*Quelle: Lara Lässig (S. 5)*

**A11** – NGHR benachrichtigt I&B am Vertragsende, den User des Mitarbeiters zu deaktivieren.
*Quelle: Barbara Baumeister (S. 3)*

**A12** – Das Personalwesen führt einen ehemaligen Mitarbeiter als *Rentner*, sobald dieser
den Eintritt in den Ruhestand mitteilt.
*Quelle: Lara Lässig (S. 5)*

**A13** – NGHR reaktiviert keinen ehemaligen Mitarbeiter; eine erneut eingestellte Person
erhält einen neuen Mitarbeiter mit neuer Personalnummer.
*Quelle: Lara Lässig (S. 5)*

**A14** – Das Personalwesen setzt einen Mitarbeiter bei Bekanntwerden seines Todes auf den
Status *verstorben*; dies gilt für aktive wie für ehemalige Mitarbeiter.
*Quelle: Lara Lässig (S. 5)*

**A15** – NGHR löscht alle Daten eines Mitarbeiters zum jeweils späteren der beiden
Zeitpunkte: fünf Jahre nach dem Ableben oder zehn Jahre nach der letzten Gehaltszahlung.
*Quelle: Ingmar Intim (S. 6)*

**A16** – NGHR sperrt keine Mitarbeiterdaten.
*Quelle: Ingmar Intim (S. 6)*

### Offene Punkte zum Lebenszyklus (mit Fachexperten zu klären)

Diese Übergänge sind für einen vollständigen Zustandsautomaten nötig, im Fallbeispiel aber
**nicht ausdrücklich** geregelt (vgl. Spezifikation S. 29 „Fehlende Fakten vermeiden"):

- **O1** – Rückkehr aus *inaktiv* nach *aktiv* (Ende von Sabbatical/Freistellung/Krankheit):
  Auslöser und zuständige Rolle sind nicht benannt.
- **O2** – Rückkehr aus *entsendet* nach *aktiv* (Ende der Entsendung): durch „für die Dauer
  der Entsendung" (Reich, S. 2) impliziert, aber nicht ausformuliert.
- **O3** – Ob Kündigung/Auflösung (A9) auch aus *inaktiv* und *entsendet* heraus möglich ist
  (A9 nennt nur „aktuellen Status").
- **O4** – Ob *Rentner* nur aus *ehemaliger Mitarbeiter* erreicht wird (A12) oder auch direkt
  am Vertragsende bei gleichzeitigem Renteneintritt.

---

## B. Identität, User und Rollen (I&B)

**B1** – I&B erzeugt die User ID eines Mitarbeiters aus dessen Personalnummer, indem es den
Buchstaben „U" voranstellt.
*Quelle: Barbara Baumeister (S. 3)*

**B2** – I&B vergibt bei Anlage eines Users für einen Mitarbeiter die Rolle „Mitarbeiter".
*Quelle: Barbara Baumeister (S. 3)*

**B3** – I&B pflegt alle Rollen zentral und verteilt sie regelmäßig an die angebundenen
Anwendungen; NGHR bezieht die Rollen aus I&B.
*Quelle: Barbara Baumeister (S. 3)*

**B4** – NGHR teilt I&B mit, ob ein Mitarbeiter Manager ist.
*Quelle: Barbara Baumeister (S. 3)*

**B5** – I&B leitet die Rollen „Personalwesen" und „Lohnbuchhaltung" aus der Kostenstelle des
Mitarbeiters ab und erhält Kostenstellenänderungen vom ERP-System.
*Quelle: Barbara Baumeister (S. 3)*

---

## C. Organisation und Kostenstellen

**C1** – Genau ein Manager ist für jede Kostenstelle verantwortlich.
*Quelle: Paul Pinke (S. 6)*

**C2** – Jeder nicht-leitende aktive Mitarbeiter ist genau der Kostenstelle des Managers
zugeordnet, an den er berichtet.
*Quelle: Paul Pinke (S. 6)*

**C3** – Jeder Manager ist der Kostenstelle zugeordnet, für die er verantwortlich ist.
*Quelle: Paul Pinke (S. 6)*

**C4** – Das Personalwesen pflegt in NGHR, wer Manager ist und wer der Manager eines
Mitarbeiters ist.
*Quelle: Paul Pinke (S. 6), Hella Helfer (S. 7)*

**C5** – Das ERP-System meldet die Kostenstelle eines Mitarbeiters an NGHR zurück.
*Quelle: Paul Pinke (S. 6)*

**C6** – NGHR ordnet jeden Rentner der Sammelkostenstelle für Betriebsrenten zu.
*Quelle: Paul Pinke (S. 7)*

---

## D. Gehalt und Gehaltsabrechnung

**D1** – Jeder Mitarbeiter ist genau einer Gehaltsklasse zugeordnet.
*Quelle: Werner Wuchtig (S. 4)*

**D2** – Ein Mitarbeiter der Gehaltsklasse „Gehalt" erhält sein monatliches Bruttogehalt.
*Quelle: Werner Wuchtig (S. 4)*

**D3** – Ein Mitarbeiter der Gehaltsklasse „Gehalt und Provision" erhält zusätzlich eine
Vertriebsprovision von 3 % des Gesamtvolumens aller Verträge, die er zwischen dem 16. des
Vormonats und dem 15. des aktuellen Monats abgeschlossen hat.
*Quelle: Werner Wuchtig (S. 4)*

**D4** – Ein Mitarbeiter der Gehaltsklasse „Gehalt und Bonus" erhält einmal jährlich mit dem
Maigehalt einen Bonus in Höhe eines von der Geschäftsführung festgelegten Prozentsatzes seines
monatlichen Bruttogehalts.
*Quelle: Werner Wuchtig (S. 4)*

**D5** – NGHR zahlt alle Gehälter am letzten Wochentag eines Monats aus.
*Quelle: Werner Wuchtig (S. 4)*

**D6** – NGHR ermittelt das Nettogehalt, indem es vom Bruttogehalt die Einkommenssteuer und
den Solidaritätszuschlag abzieht.
*Quelle: Werner Wuchtig (S. 4)*

**D7** – NGHR ermittelt den Auszahlungsbetrag, indem es vom Nettogehalt die
Sozialversicherungsbeiträge abzieht und die Arbeitgeberanteile hinzurechnet.
*Quelle: Werner Wuchtig (S. 4)*

**D8** – NGHR berechnet die Einkommenssteuer mit einem jährlichen Grundfreibetrag von
16.000 € und einem festen Satz von 25 % auf den darüber liegenden Betrag.
*Quelle: Karola Kohle (S. 8)*

**D9** – NGHR erhebt den Solidaritätszuschlag mit 5,5 % der Einkommenssteuer, sobald die
jährliche Einkommenssteuer 18.000 € übersteigt.
*Quelle: Karola Kohle (S. 8)*

**D10** – NGHR berechnet je Sozialversicherung einen Beitrag als Prozentsatz des
Bruttoverdienstes bis zur Beitragsbemessungsgrenze: Kranken 14 %, Pflege 4,5 %,
Arbeitslosen 5 %, Renten 21 %.
*Quelle: Werner Wuchtig (S. 4)*

**D11** – NGHR berücksichtigt je Euro bis einschließlich der Beitragsbemessungsgrenze den
Beitragssatz und darüber nichts; die Grenze beträgt für Kranken- und Pflegeversicherung
63.000 € und für Arbeitslosen- und Rentenversicherung 94.000 €.
*Quelle: Werner Wuchtig (S. 4)*

**D12** – NGHR setzt jeden Arbeitgeberanteil auf die Hälfte des jeweiligen
Sozialversicherungsbeitrags.
*Quelle: Werner Wuchtig (S. 4)*

**D13** – NGHR ermittelt die Gesamtlohnkosten eines Mitarbeiters als Summe aus Bruttogehalt
und Arbeitgeberanteilen.
*Quelle: Werner Wuchtig (S. 4)*

**D14** – Die Lohnbuchhaltung pflegt die Gehaltsdaten eines Mitarbeiters, also Gehaltsklasse
und monatliches Bruttogehalt.
*Quelle: Werner Wuchtig (S. 4)*

**D15** – NGHR ruft die CRM-Schnittstelle für die Verträge vor jedem Gehaltslauf auf.
*Quelle: Richard Reich (S. 2)*

---

## E. Zahlungen und externe Schnittstellen

**E1** – NGHR löst die Überweisungen der Gehälter und Sozialabgaben selbst über das Bankkonto
aus.
*Quelle: Karola Kohle (S. 8), Barbara Baumeister (S. 3)*

**E2** – NGHR meldet das Bruttoeinkommen jedes Mitarbeiters einmal pro Quartal per Elster an
das Betriebsfinanzamt, spätestens am 10. Tag nach Quartalsende.
*Quelle: Karola Kohle (S. 8)*

**E3** – NGHR informiert das ERP-System mit jeder erstellten Gehaltsabrechnung über die
berechneten Steuern.
*Quelle: Karola Kohle (S. 8)*

**E4** – NGHR meldet jeden Zahlungsabfluss an das ERP-System, pro Mitarbeiter aufgeschlüsselt
nach ausgezahltem Gehalt und je Sozialversicherungsbeitragsart.
*Quelle: Karola Kohle (S. 8)*

**E5** – NGHR übermittelt die Zahlungsabflüsse an das ERP-System gebündelt höchstens einmal
pro Tag und stellt sicher, dass keine Information verloren geht.
*Quelle: Karola Kohle (S. 8)*

**E6** – NGHR informiert das ERP-System bei jedem Zustandswechsel eines Mitarbeiters über die
Mitarbeiterdaten.
*Quelle: Paul Pinke (S. 6)*

**E7** – NGHR stellt dem ERP-System die voraussichtlichen Gesamtlohnkosten der aktiven
Mitarbeiter je Kostenstelle und Monat für die nächsten 12 Monate bereit, ohne
Vertriebsprovisionen.
*Quelle: Paul Pinke (S. 7)*

**E8** – NGHR stellt dem Mitarbeiterportal eine Schnittstelle bereit, über die das Portal
Änderungen der Mitarbeiterdaten abfragt.
*Quelle: Barbara Baumeister (S. 3)*

---

## F. Berechtigungen und Datenschutz

**F1** – Personenbezogene Daten eines Mitarbeiters sind Privatadresse, Bankverbindung und
Gehaltsdaten.
*Quelle: Ingmar Intim (S. 5–6); Spezifikation S. 26*

**F2** – Mitarbeiter der Lohnbuchhaltung dürfen die Gehaltsdaten und Gehaltsabrechnungen aller
Mitarbeiter einsehen.
*Quelle: Ingmar Intim (S. 5–6); Spezifikation S. 26*

**F3** – Mitarbeiter des Personalwesens dürfen alle Personaldaten aller Mitarbeiter einsehen
außer Gehaltsdaten und Gehaltsabrechnung.
*Quelle: Ingmar Intim (S. 6); Spezifikation S. 26*

**F4** – Mitarbeiter der Lohnbuchhaltung sind Mitarbeiter des Personalwesens.
*Quelle: Ingmar Intim (S. 5–6); Spezifikation S. 26*

**F5** – Ein Manager darf die Gehaltsdaten seiner Mitarbeiter einsehen, aber nicht deren
Gehaltsabrechnung.
*Quelle: Ingmar Intim (S. 6)*

**F6** – Ein Mitarbeiter pflegt seine unkritischen Daten (Adresse, Bankverbindung,
Krankenkasse) selbst.
*Quelle: Hella Helfer (S. 7)*

**F7** – Das Personalwesen pflegt die unkritischen Daten eines Mitarbeiters, wenn dieser sie
nicht selbst pflegen kann.
*Quelle: Hella Helfer (S. 7)*

**F8** – Nur die Personalabteilung pflegt die identifizierenden Daten eines Mitarbeiters
(Name, Geburtsdatum), den Mitarbeiterstatus und das Manager-Flag.
*Quelle: Hella Helfer (S. 7)*

**F9** – Das Recruiting legt Mitarbeiter neu an und pflegt dabei die Gehaltsdaten initial.
*Quelle: Hella Helfer (S. 7)*

**F10** – Nach der Anlage eines Mitarbeiters greift das Recruiting nicht mehr auf dessen
Datensatz zu, auch nicht lesend; dies gilt für interne wie externe Recruiting-Mitarbeiter.
*Quelle: Hella Helfer (S. 7)*

**F11** – Ein Mitarbeiter sieht im Employee Self-Service seine eigenen Daten und ab dem
Zahltag seine Gehaltsabrechnungen.
*Quelle: Barbara Baumeister (S. 2–3)*

**F12** – NGHR stellt Name und User ID eines Mitarbeiters im Mitarbeiterportal bereit.
*Quelle: Ingmar Intim (S. 6)*

---

## Abgrenzung

Dieses Dokument enthält die fachlichen Regeln. Die daraus abgeleiteten **Zustände und
Zustandsübergänge** werden im Zustandsautomaten (Diagramm + Zustandsübergangstabelle,
Spezifikation S. 33–35) dargestellt. Abschnitt A liefert dafür die maßgeblichen Regeln.
