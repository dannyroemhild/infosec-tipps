# Windows Clients härten

## LAPS einsetzen

https://www.microsoft.com/en-us/download/details.aspx?id=46899

https://www.frankysweb.de/einfache-massnahmen-fuer-mehr-sicherheit-im-ad-teil-3-laps/

## Bitlocker einsetzen

- GPOs entsprechend erstellen
- Bitlocker kann via Powershell oder per GUI aktiviert werden (immer mit Selbsttest und "Gesamtes Laufwerk verschlüsseln) durchführen)
- Wiederherstellungsschlüssel wird am Computerobjekt im AD gespeichert
- Zugriff auf das Attribut msFVE-RecoveryInformation des Computerobjekts im AD muss ggf. sein um den Wiederherstellungsschlüssel auslesen zu können
- auf einer Administrations-Workstation oder einem Administrations-Desktop muss neben der "AD-Verwaltungskonsole" auch noch das "Verwaltungsprogramm für die Bitlocker-Laufwerksverschlüsselung" installiert sein

Powershell Befehle:
Enable-Bitlocker -Mountpoint C:
Disable-Bitlocker -Mountpoint C:
Get-BitlockerVolume -C:

CMD Befehle:
manage-bde.exe -on C:
manage-bde.exe -off C:
manage-bde.exe -status C:

*HINWEIS: Beim Verkauf eines Unternehmenssystem im Windows TPM löschen (in TPM Verwaltungskonsole)

## Mitglieder der lokalen Gruppe "Administratoren" verwalten

GPO: Computerkonfiguration --> Einstellungen --> Systemsteuerungseinstellungen --> Lokale Benutzer und Gruppen

## Vorinstallierte Windows Anwendungen / Apps entfernen

per Powershellskript kann dies durchgeführt werden --> neo42 bietet dafür eine eigene Anwendung an

## OneDrive deinstallieren / deaktivieren

https://www.deskmodder.de/wiki/index.php/Onedrive_deinstallieren_windows_10

Zum Deinstallieren muss die OneDriveSetup.exe mit dem Schalter /uninstall entfernt und die Run-Einträge in der Registry (vorallem auch im HKEY Default entfernt werden).

Zum Deaktivieren kann eine GPO genutzt werden:

GPO: Computerkonfiguration --> Richtlinien --> Administrative Vorlagen --> Windows Komponenten --> OneDrive --> Verwendung von Onedrive für die Dateispeicherung verhindern

## Cortana deaktivieren

GPO: Computerkonfiguration --> Richtlinien --> Administrative Vorlagen --> Windows Komponenten --> Suche --> Cortana auf dem Sperrbildschirm zulassen = DEAKTIVIEREN
GPO: Computerkonfiguration --> Richtlinien --> Administrative Vorlagen --> Windows Komponenten --> Suche --> Cortana zulassen = DEAKTIVIEREN
GPO: Computerkonfiguration --> Richtlinien --> Administrative Vorlagen --> Windows Komponenten --> Suche --> Cortana-Seite auf Windows Willkommensbildschirm für AAD-Konten zulassen = DEAKTIVIEREN

GPO: Computerkonfiguration --> Richtlinien --> Administrative Vorlagen --> Windows Komponenten --> Suche --> Nicht im Web suchen und keine Webergebnisse in der Suche anzeigen = AKTIVIEREN
GPO: Computerkonfiguration --> Richtlinien --> Administrative Vorlagen --> Windows Komponenten --> Suche --> Websuche nicht zulassen = AKTIVIEREN

## ISO und andere Image-Files nicht per Explorer-Menü mounten

https://winaero.com/remove-mount-context-menu-windows-10/


