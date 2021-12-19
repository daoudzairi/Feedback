# TEGEN DEMO 2

### Evaluatiecriteria wachtwoorden en aanmelden
**X** Wachtwoord kan minder dan 8 tekens bevatten. \

### Evaluatiecriteria HTTPS
- Pagina’s enkel beschikbaar over https (301 Moved Permanently).
- Rechtstreekse toegang via IP (104.21.9.158) niet mogelijk.
- ssl labs report grade: A.

### Conclusie/Aanbevelingen
1.	**Controle bij de creatie van een nieuw wachtwoord moet aangepast worden zodat dit controlleert op een minimale lenge van 8 karakters.**


### Applications on Webserver enumeration
-	https://ehbdefendersblog.com:8443/login geeft een 522 response
-	Open poorten: 80, 443, 8080, 8443

### Webpage Content Information Leakage	
-	Wanneer een aangemelde gebruiker op één van de volgende links klikt komt een debug pagina tevoorschijn waar een deel van de source code te lezen is: \
		- 'Workspace' in de navigation bar \
		- 'Find out more' op de home pagina


### Conclusie/aanbevelingen
1.	**APP_DEBUG op false zodat de debug pagina niet meer zichtbaar is**
3.	**CSFR token kan eventueel als variabele worden meegeven, bijvoorbeeld als volgt: ```<input type="hidden" name="_token" value="{{ csrf_token() }}"/>``` in plaats van hard coded in de html te plaatsen.**
4.	**https://ehbdefendersapp.azurewebsites.net eventueel laten redirecten naar https://ehbdefendersblog.com**
5.	**Niet gebruikte poorten op de server te sluiten, of open laten mits gebruik van IP whitelisting.**


### CVE 
Een overzicht van de CVE voor Laravel is beschikbaar op https://www.opencve.io/cve?vendor=laravel.
De laatste (CVE-2021-43617) dateert van 2021-11-18 en heeft een rating van 9.8. Deze vulnerability maakt de applicatie gevoelig voor het opladen van uitvoerbare php content.


### Conclusie/aanbevelingen
1.	Het framework steeds up to date houden met de laatst stabiele versie
2.	Opencve.io opvolgen om zich bewust te zijn van de laatste exploits en van welke vulnerabilities deze gebruik maken.

### Daartoe sluiten we alle poorten van de meest voorkomende aanvallen, zoals beschreven in de verschillende evaluatiecriteria:

HTTPS,
wachtwoorden,
aanmelden,
beveiliging tegen typische web vulnerabilities,
REST APIs.

De toepassing is ook in grote lijnen conform met de Europese privacy regelgeving. 

ADMIN PANNEL AANMAKEN

ACCEPTATIE C. AANPASSEN
THREAD MODEL AANPASSEN