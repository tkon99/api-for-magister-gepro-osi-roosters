Inleiding
===============
Deze API is om gegevens op te halen van http://roosters5.gepro-osi.nl/roosters/rooster.php, mocht je school dit gebruiken dan kun je deze API hiervoor gebruiken.

Voor een C# implementatie zie: https://github.com/lieuwex/GEPRO_OSIsharp

Hoe te gebruiken
===============
De API is simpel te gebruiken in PHP, ik geef je een voorbeeld:

```PHP
<?php
include 'rooster.class.php'; //De nieuwste versie van de API laden.
$rooster = new rooster(123,'vwo1',1234567,10); //Nieuw rooster aanmaken, tussen haakjes: Schoolnummer, richting, leerling, aantal lesuren.
                                          //Zijn te vinden in de url.
?>

<bla bla bla een hoop html>

<?php //Php oproepen op het moment dat je het rooster wilt tonen
$rooster->getArray(0);                    //API oproepen, dat hij rooster moet geven
$dag=$rooster->getDay(1,"ma");            //Zeggen welke dag de API op moet halen
$counter=1;                               //Zorgen dat er een nummer voor de lessen komt
foreach($dag as $uur) {                   //Voor iedere dag een uur
  foreach($uur as $les){                  //Voor ieder uur een les
		echo "".$counter." <br> ".$les["teacher"]." - ".$les["room"]." - ".$les["lesson"]."\n <br>"; //Uitvoeren in HTML
	}
	$counter++;                             //1 Optellen bij de couter
}
?>
```

Meer functies
==============
Deze library/API kan enkel roosters ophalen, wil je meer functies zoals:
- Lijsten van Klassen/Docenten/Lokalen/Leerlingen/Richtingen ophalen
- Het zoeken van iemand's richting aan de hand van het leerlingnummer
- Meerdere lessen per uur
- Mooie opbouw response
- JSON compatibility (voor apps)

Gebruik dan de uitgebreide API van [tkon99](https://github.com/tkon99): [API-gepro-osi](https://github.com/tkon99/API-gepro-osi)

Huidige Magister
=================
De huidige Magister 6 is in HTML5.

Voor JavaScript kan je hiervoor [Magister.js](http://simplygits.github.io/MagisterJS/) gebruiken.

FAQ
====
V:

Waarom doet de API het bij mijn school niet?


A:

Sinds 0.9.1 zouden alle scholen het moeten doen, omdat er geen hardcoded waardes meer zijn, werkt het toch niet neem gerust contact met me op.

Vragen
=======
Je kunt vragen altijd aan mij stellen:

[stipmonster](https://github.com/stipmonster)

Copyright
==========
Originele API door Stipmonster

De API is licensed onder de GNU LESSER GENERAL PUBLIC LICENSE, zie de LICENSE file voor meer informatie.

Documentatie, wiki & uitleg door tkon99 & stipmonster

