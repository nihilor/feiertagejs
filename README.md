# feiertage

Tiny, simple and pure module to calculate the german non-business days.

[![NPM](https://nodei.co/npm/feiertage.png)](https://nodei.co/npm/feiertage/)

## How To Use

Simply download the package or install it from npm with `npm install feiertage`.

```js
var feiertage = require('feiertage');

// full list of all functions to retrieve the date for a specific non-business day of the current year
feiertage.Neujahr();
feiertage.HeiligeDreiKoenige();
feiertage.Karfreitag();
feiertage.Ostersonntag();
feiertage.Ostermontag();
feiertage.TagDerArbeit();
feiertage.ChristiHimmelfahrt();
feiertage.Pfingstsonntag();
feiertage.Pfingstmontag();
feiertage.Fronleichnam();
feiertage.MariaHimmelfahrt();
feiertage.TagDerDeutschenEinheit();
feiertage.Reformationstag();
feiertage.Allerheiligen();
feiertage.BußUndBettag();
feiertage.Heiligabend();
feiertage.ErsterWeihnachtsfeiertag();
feiertage.ZweiterWeihnachtsfeiertag();
feiertage.Silvester();

// every function accepts a year as a parameter
feiertage.Neujahr(2019);
feiertage.HeiligeDreiKoenige(2020);
...

// non-business days for the current year as a list of objects
// every objects has the properties id, label, date
feiertage.asList();

// non-business days for a given year as a list of objects
feiertage.asList(2020);
feiertage.asList(2021);

// asList also accepts a german state code, like BY, BE, SH or TH, so it returns only non-business days valid for these german states
feiertage.asList(2020, 'BY');
feiertage.asList(2021, 'BE');

// returns only non-business days falling on monday to friday
feiertage.asListOfWorkdays(2016, 'BY');
```

A list of the supported german state codes. There are five additional codes to specify special regulations for Friedensfest, Mariä Himmelfahrt and Fronleichnam. The code DE summarizes all german non-business days.

| Code  | Description                                                                            |
| ----- | -------------------------------------------------------------------------------------- |
| DE    | Deutschland (all known non-business days)                                              |
| BW    | Baden-Württemberg                                                                      |
| BY    | Bayern                                                                                 |
| BE    | Berlin                                                                                 |
| BB    | Brandenburg                                                                            |
| HB    | Bremen                                                                                 |
| HH    | Hamburg                                                                                |
| HE    | Hessen                                                                                 |
| NI    | Niedersachsen                                                                          |
| MV    | Mecklenburg-Vorpommern                                                                 |
| NW    | Nordrhein-Westfalen                                                                    |
| RP    | Rheinland-Pfalz                                                                        |
| SL    | Saarland                                                                               |
| SN    | Sachsen                                                                                |
| ST    | Sachsen-Anhalt                                                                         |
| SH    | Schleswig-Holstein                                                                     |
| TH    | Thüringen                                                                              |
| BY-FF | Bayern, Friedensfest, Augsburg only                                                    |
| BY-MH | Bayern, Mariä Himmelfahrt, predominantly catholic population                           |
| SN-FL | Sachsen, Fronleichnam, some communities in Bautzen                                     |
| TH-FL | Thüringen, Fronleichnam, some communities in Eichsfeld, Unstrut-Hainich, Wartburgkreis |

## Changelog

### 1.2.0

* Added special state codes for `BY-FF`, `BY-MH`, `SN-FL` and `TH-FL` covering the special rules for non-business days, that are only valid in some communities, like Friedensfest, Mariä-Himmelfahrt and Fronleichnam.

### 1.1.2

* The calculation of easter sunday is now based on the corrected Gauss formula by Lichtenberg

### 1.1.1

* `asListofWorkdays()` (new) returns only those non-business days, that fall on monday to friday

### 1.1.0

* `setYear()` was removed from the API
* `asList()` now accepts a state code as second parameter, e.g. BY, BE, SH or TH
* `asList()` now returns a list of objects instead of an object
