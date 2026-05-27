# Cheatsheet 1: Data Science Concepten (Theorie)

## 1. Variabelen & Meetniveaus

Een **variabele** is een eigenschap van een onderzocht object die kan variëren. Ze worden opgedeeld in twee hoofdgroepen:

* **Kwalitatieve (categorische) variabelen:** Bevatten labels of categorieën.
* **Nominaal:** Categorieën *zonder* logische volgorde (bijv. kleur, geslacht, herkomsthaven).
* **Ordinaal:** Categorieën *met* een logische volgorde of rangorde (bijv. opleidingsniveau, klanttevredenheid).


* **Kwantitatieve (numerieke) variabelen:** Resultaten van tellingen of metingen (discreet of continu).
* **Interval:** Numerieke waarden waarbij verschillen betekenisvol zijn, maar er is *geen* absoluut nulpunt (bijv. temperatuur in °C).
* **Ratio:** Numerieke waarden *met* een absoluut nulpunt, waardoor verhoudingen kloppen (bijv. leeftijd, gewicht, inkomen).



## 2. Populaties & Steekproeven

* **Populatie:** De volledige groep die je wilt onderzoeken.
* **Steekproef (Sample):** Een deelverzameling van de populatie.
* **Observatie:** Één enkel object of individu binnen de steekproef/populatie.
* **Steekproefkader (Sampling frame):** Een complete lijst van alle individuen in de populatie (nodig voor een perfecte aselecte steekproef).

> 💡 **Een goede steekproef is:**
> 1. **Willekeurig (Random):** Iedereen heeft een gelijke kans om gekozen te worden (vermindert bias).
> 2. **Groot genoeg:** Zorgt voor betrouwbare schattingen.
> 3. **Representatief:** Weerspiegelt nauwkeurig de kenmerken van de totale populatie.
> 
> 
> *Bij een **gestratificeerde steekproef** verdeel je de populatie in subgroepen (bijv. leeftijd/geslacht) en neem je pro rata een steekproef per subgroep om representativiteit te garanderen.*

## 3. Foutenbronnen (Sampling Errors)

Fouten die optreden bij het verzamelen en analyseren van data vallen uiteen in:

| Type fout | Willekeurig (Random) | Systematisch (Systematic) ⚠️ |
| --- | --- | --- |
| **Steekproeffouten** *(Door de manier van trekken)* | **Toevalsfouten:** Onvermijdelijk, elke steekproef is net anders. | **Selectiebias:** Bepaalde groepen worden uitgesloten (bijv. online enquête sluit mensen zonder internet uit). |
| **Niet-steekproeffouten** *(Tijdens meting/analyse)* | **Menselijke fout:** Respondent vult per ongeluk een verkeerd vakje in. | **Meetbias:** Ongekalibreerd apparaat; of respondenten die bewust liegen (bijv. over alcoholgebruik). |

## 4. Data-analyse & Relaties

* **Univariate analyse:** Analyse van één enkele variabele (gemiddelde, mediaan, histogram, boxplot).
* **Bivariate analyse:** Onderzoek naar de samenhang tussen twee variabelen.
* **Onafhankelijke variabele:** De voorspellende variabele (de "oorzaak" of de variabele die informatie geeft).
* **Afhankelijke variabele:** De te voorspellen of te verklaren variabele (het "gevolg").

> ⚠️ **Cruciaal:** *Correlatie is geen causatie!* Een statistisch verband betekent niet automatisch dat de ene variabele de andere veroorzaakt (denk aan schijverbanden of *spurious correlations*).