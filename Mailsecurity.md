# Mailsecurity

## SPF einrichten

- Einfachstes Beispiel: v=spf1 mx -all
--> SPF Version 1, Server die in der DNS-Zone der Domain als MX-Eintrag vorhanden sind dürfen Mails dieser Maildomain versenden, für alle anderen wird ein Hard Fail generiert

- https://www.spf-record.de/generator

## DKIM und DMARC einrichten

Auf dem Mailgateway ein Zertifikat für die Signierung erstellen für einen passenden Eintrag 

https://www.digicomp.ch/blog/2019/02/18/spf-dkim-und-dmarc-verstaendlich-erklaert

## Dateiendungen auf Mailgateway blockieren oder Mailanhänge in Outlook blockieren / nicht anzeigen

https://www.mdsec.co.uk/2021/02/farming-for-red-teams-harvesting-netntlm/
https://www.blackhillsinfosec.com/rogue-rdp-revisiting-initial-access-methods/

*.lnk
*.url
*.searchConnector-ms
*.library-ms
*.rdp


