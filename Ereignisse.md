# Ereignisse

## Start -> angelegt

- **E1**: eine Person schließt einen Arbeitsvertrag mit der Sonnenschein AG ab

## angelegt -> aktiv

- **E2**: Der Vertragsbeginn des Arbeitsverhältnisses ist das heutige Datum

## aktiv -> inaktiv

- **E3**: Mitarbeiter beginnt ein Sabatical
- **E4**: Mitarbeiter wird freigestellt
- **E5**: Mitarbeiter meldet sich länger krank

## inaktiv -> aktiv

- **E6**: Mitarbeiter kehrt zurück aus Sabatical
- **E7**: Freistellung des Mitarbeiters ist abgelaufen
- **E8**: Krankheitszeitraum des Mitarbeiters ist abgelaufen
- **E9**: Mitarbeiter kehrt vorzeitig zurück zur Arbeit

## aktiv -> entsendet

- **E10**: Mitarbeiter zieht ins Ausland, um bei einem ausländischen Tochterunternehmen der Sonnenschein AG zu arbeiten

## entsendet -> aktiv

- **E11**: Mitarbeiter zieht zurück nach Deutschland, um bei der Sonnenschein AG zu arbeiten

## aktiv -> ehemalig

- **E12**: Mitarbeiter hat gekündigt und Kündigungsdatum des Mitarbeiters ist heute
- **E13**: Mitarbeiter wurde gekündigt und Kündigungsdatum des Mitarbeiters ist heute
- **E14**: Enddatum des Arbeitsverhältnisses im Auflösungsvertrag ist Heute

## inaktiv -> ehemalig

- **E12** 
- **E13**
- **E14**

## entsendet -> ehemalig

- **E12** 
- **E13**
- **E14**

## ehemalig -> Rente

- **E15**: Mitarbeiter tritt in den Ruhestand

## aktiv, inaktiv, entsendet -> Rente

- **E15**

## inaktiv, entsendet, ehemalig, Rente -> gelöscht

- **E16**: Differenz des Datums der Letzte Gehaltszahlung und heute ist größer/gleich 10 Jahre

## aus jedem Zustand -> verstorben

- **E17**: Über das Ableben einer Person wird die Sonnenschein AG informiert

## verstorben -> gelöscht

- **E18**: Differenz des Ablebedatums und heute ist größer/gleich 5 Jahre