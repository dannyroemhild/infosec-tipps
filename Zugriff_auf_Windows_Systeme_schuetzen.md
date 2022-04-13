# Zugriff auf Windows Systeme schützen

## Zugriff auf Windows-Systeme über das Netzwerk per (Gruppen)-Richtlinie einschränken

Gruppenrichtlinie

- Computer Configuration\Windows Settings\Security Settings\Local Policies\User Rights Assignment

### Empfohlene Einstellungen von Microsoft:

- Für Desktopsysteme (PCs / Notebooks), den Zugriff nur einer ausgewählten Mitarbeitergruppe (IT) gewähren
- Für Mitgliedsserver einer Domäne, nur den Gruppen "Benutzer" und "Administratoren" gewähren
- Für Domänencontroller,  den Zugriff nur den Gruppen "Authentifizierte Benutzer", "Enterprise Domain Controllers" und Administratoren gewähren.
- Für Failover Cluster, den Zugriff nur auf der Gruppe "Authentifizierte Benutzer" gewähren.

### Die Default Einstellungen können im nachfolgenden Artikel eingesehen werden, die Gruppen "Everyone" und "Pre-Windows 200 kompatible Gruppe" sollten sinnvollerweise entfernt werden

Quelle: https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/access-this-computer-from-the-network
