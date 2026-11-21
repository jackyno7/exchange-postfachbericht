# Exchange-Postfachbericht – PowerShell-Skript: Postfächer in Exchange Server prüfen

PowerShell-Skript für Exchange Server (lokal installiert), das alle Postfächer in 15 Punkten prüft: Weiterleitungen und Posteingangsregeln nach extern, Vollzugriff und „Senden als“, inaktive, deaktivierte und fast volle Postfächer sowie veraltete Exchange-Versionen und fehlende Datenbanksicherungen. Ergebnis: ein übersichtlicher HTML-Bericht auf Deutsch oder Englisch mit Erklärung und Empfehlung zu jedem Befund.

**Dieses Verzeichnis enthält kein Skript, nur Bilder der Funktionen.** Die Vollversion gibt es hier:

➜ **[Vollversion auf Gumroad](https://mueller86.gumroad.com/l/gkdllj)** · **[Vollversion auf Etsy](https://www.etsy.com/listing/4614916333)** · **[alle Skripte im Shop](https://www.etsy.com/shop/ITAdminToolsbyMM)**

Alle Bilder stammen aus einer Testumgebung mit erfundenen Daten.

## Übersicht und Kennzahlen

Kennzahlen im Kopf und alle Prüfpunkte auf einen Blick, nach Dringlichkeit bewertet.

![Übersicht und Kennzahlen](bilder/01_uebersicht.png)

## Ein Befund mit Erklärung und Empfehlung

Jeder Befund mit Erklärung, Empfehlung und den betroffenen Objekten.

![Ein Befund mit Erklärung und Empfehlung](bilder/02_befund.png)

## Weitere Befunde

Die Befunde im Detail.

![Weitere Befunde](bilder/03_weitere-befunde.png)

## Eckdaten

- 15 Prüfpunkte, nur lesend, HTML-Bericht auf Deutsch oder Englisch (`-Language de|en`)
- Windows PowerShell 5.1 (in Windows Server ab 2016 enthalten)
- Exchange Server 2016, 2019 oder SE (lokal installiert, nicht Exchange Online)
- Ein Konto mit den Rollen „View-Only Recipients“ und „View-Only Configuration“ (z. B. über die Rollengruppe „View-Only Organization Management“) liest Postfächer, Berechtigungen, Server und Datenbanken sowie die Posteingangsregeln (im Test mit Exchange SE belegt). Fehlt einer Rolle das Recht dafür, erscheinen die Regelprüfungen im Bericht als „nicht geprüft“. „Senden als“ und gesperrte Konten liest das Skript direkt im Active Directory, dafür genügen normale Leserechte

<!-- querverweis:anfang -->
## Alle Skripte und Vorlagen

Übersicht aller Prüfskripte und Vorlagen: **[github.com/jackyno7](https://github.com/jackyno7)**

Vollversionen:

- Active Directory Prüfbericht: [Etsy](https://www.etsy.com/listing/4588853943) · [Gumroad](https://mueller86.gumroad.com/l/fcneoc)
- Domänencontroller-Gesundheitsbericht: [Etsy](https://www.etsy.com/listing/4593087246) · [Gumroad](https://mueller86.gumroad.com/l/bseljr)
- DNS- und DHCP-Bericht: [Etsy](https://www.etsy.com/listing/4593096270) · [Gumroad](https://mueller86.gumroad.com/l/sthgh)
- Kerberos- und Altlasten-Check: [Etsy](https://www.etsy.com/listing/4593092377) · [Gumroad](https://mueller86.gumroad.com/l/zptvct)
- Berechtigungsbericht Active Directory: [Etsy](https://www.etsy.com/listing/4593113568) · [Gumroad](https://mueller86.gumroad.com/l/xyjmdr)
- GPO-Bericht: [Etsy](https://www.etsy.com/listing/4593129111) · [Gumroad](https://mueller86.gumroad.com/l/wdosl)
- Anmelde- und Sperrbericht: [Etsy](https://www.etsy.com/listing/4593157082) · [Gumroad](https://mueller86.gumroad.com/l/ztktaaq)
- Rechner-Inventar aus Active Directory: [Etsy](https://www.etsy.com/listing/4593088535) · [Gumroad](https://mueller86.gumroad.com/l/zzycdd)
- Dateiserver-Bericht: [Etsy](https://www.etsy.com/listing/4612420692) · [Gumroad](https://mueller86.gumroad.com/l/wbbwj)
- Dateiserver-Rechte-Bericht: [Etsy](https://www.etsy.com/listing/4616706194) · [Gumroad](https://mueller86.gumroad.com/l/ijrkb)
- Windows-Rechnerbericht: [Etsy](https://www.etsy.com/listing/4616020701) · [Gumroad](https://mueller86.gumroad.com/l/wmhfk)
- Exchange-Postfachbericht: [Etsy](https://www.etsy.com/listing/4614916333) · [Gumroad](https://mueller86.gumroad.com/l/gkdllj)
- Exchange-Kalenderrechte-Bericht: [Etsy](https://www.etsy.com/listing/4614799790) · [Gumroad](https://mueller86.gumroad.com/l/iabfb)
- Exchange-Nachrichtenverfolgung: [Etsy](https://www.etsy.com/listing/4614785975) · [Gumroad](https://mueller86.gumroad.com/l/msria)
- Active Directory Prüfskript-Paket: [Etsy](https://www.etsy.com/listing/4611942401) · [Gumroad](https://mueller86.gumroad.com/l/awzjtc)

Kostenlose Skripte: [Zertifikate-Bericht](https://github.com/jackyno7/zertifikate-bericht) ([Gumroad](https://mueller86.gumroad.com/l/zsfvec)) · [Privilegierte-Konten-Check](https://github.com/jackyno7/privilegierte-konten-check) ([Gumroad](https://mueller86.gumroad.com/l/pamjky))

Vorlagen und Checklisten (Notfallplan, Backup, Passwortrichtlinie, Onboarding, Homeoffice, Netzwerk-Dokumentation): [Etsy](https://www.etsy.com/shop/ITAdminToolsbyMM) · [Gumroad](https://mueller86.gumroad.com)
<!-- querverweis:ende -->

## Hinweise

- Bei der Ausarbeitung wurden KI-Werkzeuge unterstützend eingesetzt; Inhalte und Skripte wurden fachlich geprüft und im Testlab getestet.
- Nutzung auf eigene Verantwortung.

---

### English

PowerShell script for Exchange Server (locally installed) that checks all mailboxes across 15 points: forwarding and inbox rules to external, Full Access and "Send As", inactive, disabled, and nearly full mailboxes, as well as outdated Exchange versions and missing database backups. Result: a clear HTML report in German or English with explanation and recommendation for each finding. This repository contains screenshots only. Full version: https://mueller86.gumroad.com/l/gkdllj

<!-- querverweis-en:anfang -->
#### All scripts and templates

Overview of all check scripts and templates: **[github.com/jackyno7](https://github.com/jackyno7)**

Full versions:

- Active Directory Audit Report: [Etsy](https://www.etsy.com/listing/4588853943) · [Gumroad](https://mueller86.gumroad.com/l/fcneoc)
- Domain Controller Health Report: [Etsy](https://www.etsy.com/listing/4593087246) · [Gumroad](https://mueller86.gumroad.com/l/bseljr)
- DNS and DHCP Report: [Etsy](https://www.etsy.com/listing/4593096270) · [Gumroad](https://mueller86.gumroad.com/l/sthgh)
- Kerberos and Legacy Check: [Etsy](https://www.etsy.com/listing/4593092377) · [Gumroad](https://mueller86.gumroad.com/l/zptvct)
- Active Directory Permissions Report: [Etsy](https://www.etsy.com/listing/4593113568) · [Gumroad](https://mueller86.gumroad.com/l/xyjmdr)
- GPO Report: [Etsy](https://www.etsy.com/listing/4593129111) · [Gumroad](https://mueller86.gumroad.com/l/wdosl)
- Logon and Lockout Report: [Etsy](https://www.etsy.com/listing/4593157082) · [Gumroad](https://mueller86.gumroad.com/l/ztktaaq)
- Computer Inventory from Active Directory: [Etsy](https://www.etsy.com/listing/4593088535) · [Gumroad](https://mueller86.gumroad.com/l/zzycdd)
- File Server Report: [Etsy](https://www.etsy.com/listing/4612420692) · [Gumroad](https://mueller86.gumroad.com/l/wbbwj)
- File Server Permissions Report: [Etsy](https://www.etsy.com/listing/4616706194) · [Gumroad](https://mueller86.gumroad.com/l/ijrkb)
- Windows Computer Report: [Etsy](https://www.etsy.com/listing/4616020701) · [Gumroad](https://mueller86.gumroad.com/l/wmhfk)
- Exchange Mailbox Report: [Etsy](https://www.etsy.com/listing/4614916333) · [Gumroad](https://mueller86.gumroad.com/l/gkdllj)
- Exchange Calendar Permissions Report: [Etsy](https://www.etsy.com/listing/4614799790) · [Gumroad](https://mueller86.gumroad.com/l/iabfb)
- Exchange Message Tracking: [Etsy](https://www.etsy.com/listing/4614785975) · [Gumroad](https://mueller86.gumroad.com/l/msria)
- Active Directory Check Script Bundle: [Etsy](https://www.etsy.com/listing/4611942401) · [Gumroad](https://mueller86.gumroad.com/l/awzjtc)

Free scripts: [Zertifikate-Bericht](https://github.com/jackyno7/zertifikate-bericht) ([Gumroad](https://mueller86.gumroad.com/l/zsfvec)) · [Privilegierte-Konten-Check](https://github.com/jackyno7/privilegierte-konten-check) ([Gumroad](https://mueller86.gumroad.com/l/pamjky))

Templates and checklists (emergency plan, backup, password policy, onboarding, home office, network documentation): [Etsy](https://www.etsy.com/shop/ITAdminToolsbyMM) · [Gumroad](https://mueller86.gumroad.com)
<!-- querverweis-en:ende -->
