# Unit Converter

Bouw een eenvoudige HTTP website die eenheden kan omzetten. Gebruik JavaScript en NodeJS met de [`net api`](https://nodejs.org/api/net.html) om zelf een HTTP server te bouwen.

Heel vaak wanneer er met afmetingen gewerkt wordt maakt met gebruik van millimeter en inches. Afhankelijk van de regio geeft men een voorkeur voor ofwel mm ofwel inch. Deze afmetingen door elkaar gebruiken zorgt vaak voor verwarring. Daarom zou het handig zijn als we een website hebben die voor ons de omrekening kan maken.

Voorbeelden:

| Van | Naar |
|---|---|
| 5 mm | 0,19685 inch |
| 3 inch | 76,2 mm |
| 7,5 mm | 0,295276 inch|

Per definitie is 1 inch == 25,4 mm. Gebruik deze ratio om de juiste berekeningen te maken.

## Doel

Bouw een HTTP server die kan antwoorden op de 2 volgende 'routes':

* `GET` `/mm/[number]`: Accepteert een getal met daarin een afmeting in mm en geeft een response terug met als resultaat de afmeting in inch.
* `GET` `/inch/[number]`: Accepteert een getal met daarin een afmeting in inch en geeft een response terug met als resultaat de afmeting in mm.

## Voorbeelden

* **mm naar inch**:  Als je surft naar `http://localhost/mm/7.5` dan krijg je in de browser de waarde `0.295276` te zien
* **inch naar mm**:  Als je surft naar `http://localhost/inch/0.295276` dan krijg je in de browser de waarde `7.5` te zien

## Extra

Als je met REST client zoals, [Postman](https://www.postman.com/), [Insomnia](https://insomnia.rest/) of [rest-client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) de waarden zou opvragen, dan kan je een HTTP header `Content-Type` instellen. Hiermee zou je kunnen vragen aan de sever om een antwoord te geven in `JSON` in plaats van HTML. Dit kan gedaan worden door de `Content-Type` in te stellen op de waarde `application/json`.

Een antwoord van de sever kan er dan bvb zo uitzien:

```json
{ 
  "from": {
    "unit": "mm",
    "value": 7.5
  },
  "to": {
    "unit": "inch",
    "value": 0.295276
  }
}
```

## Vereisten

* Maak correct gebruik van `let` en `const`
* Splits code met verschillende doelen of verantwoordelijkheden op in verschillende bestanden. Gebruik `ES6 modules` syntax om de code in andere bestanden te gebruiken
* Gebruik *arrow functions* waar nodig
* Gebruik *template literals* waar nodig
* Maak de implementatie zo *object oriented* mogelijk. Gebruik zoveel als mogelijk klassen.
* Zorg dat callbacks gecapsuleerd worden in Promises zodat je overal de `.then()` of `async/await` syntax kunt gebruiken.
* Zorg dat de `package.json` correct gebruikt wordt en voorzie de nodige `scripts` om de applicatie eenvoudig te starten
* Zorg voor een correcte `.gitignore`
