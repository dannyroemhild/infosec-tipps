# Zugriff auf Windows Systeme schützen

## Zugriff auf Windows-Systeme über das Netzwerk per (Gruppen)-Richtlinie einschränken

Gruppenrichtlinie

- Computer Configuration\Windows Settings\Security Settings\Local Policies\User Rights Assignment --> Access this computer from the network

### Empfohlene Einstellungen von Microsoft:

- Für Desktopsysteme (PCs / Notebooks), den Zugriff nur einer ausgewählten Mitarbeitergruppe (IT) gewähren
- Für Mitgliedsserver einer Domäne, nur den Gruppen "Benutzer" und "Administratoren" gewähren
- Für Domänencontroller,  den Zugriff nur den Gruppen "Authentifizierte Benutzer", "Enterprise Domain Controllers" und Administratoren gewähren.
- Für Failover Cluster, den Zugriff nur auf der Gruppe "Authentifizierte Benutzer" gewähren.

### Die Default Einstellungen können im nachfolgenden Artikel eingesehen werden, die Gruppen "Everyone" und "Pre-Windows 200 kompatible Gruppe" sollten sinnvollerweise entfernt werden
 
Quelle: https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/access-this-computer-from-the-network

## Gast-Zugriff einschränken

Gruppenrichtlinie

- Computer Configuration -> Windows Settings -> Security Settings -> Local Policies -> Security Options -> "Network access: Do not allow anonymous enumeration of SAM accounts and shares" to "Enabled"

Registrierung

- HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\ -> RestrictAnonymous (REG_DWORD) = 1
- HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\ -> RestrictAnonymousSam (REG_DWORD) = 1

Quelle: http://www.winfaq.de/faq_html/Content/tip0500/onlinefaq.php?h=tip0912.htm
Quelle: https://www.stigviewer.com/stig/microsoft_windows_server_20122012_r2_member_server/2021-10-18/finding/V-225493



