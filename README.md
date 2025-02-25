# Helsinki Paikkatieto - Karttasovellus

Tämä on tekoälyä hyödyntäen rakennettu paikkatietosovellus, joka visualisoi Helsingin kaupungin WFS-rajapinnasta haettuja karttatasoja Leaflet-kartalla. Sovellus on toteutettu Pythonilla Flask-kehyksen avulla ja se on suunniteltu helposti laajennettavaksi. Sovelluksen käyttöliittymässä voit valita ja ladata haluamasi WFS-tasot kartalle. Tasot haetaan Helsingin kaupungin WFS-rajapinnasta osoitteesta https://kartta.hel.fi/ws/geoserver/avoindata/wfs.

## Ominaisuudet

- Mahdollisuus valita ja ladata erilaisia Helsingin kaupungin tarjoamia WFS-tasoja.
- Leaflet-kartta, jossa WFS-tasot renderöidään dynaamisesti.

## Sovelluksen toiminta kuvina

![Sovelluksen näkymä selaimessa.](images/yleiskuva.png)

Tältä sovellus näyttää selaimessa.

![Valikko](images/valikko.png)

Karttaa on zoomattu: siinä näkyy Johanneksenkirkko ja Tähtitorninvuori. Pudotusvalikosta voidaan valita, mikä karttataso halutaan ladata kartalle, tässä tapauksessa YLRE_Viheralue_alue.

![Karttataso ladattuna](images/karttataso.png)

Klikkaamalla "Lataa valittu taso" sovellus ottaa yhteyden Helsingin kaupungin WFS-rajapintaan, hakee karttatason ja lataa sen kartalle.

## Asennus ja käyttöönotto paikallisesti

### 1. Kloonaa repositorio

Avaa komentokehote (terminaali) ja suorita seuraava komento:

```
git clone https://github.com/isagimos/helsinki-karttatasot.git
cd helsinki-karttatasot
```

### 2. Luo ja aktivoi virtuaaliympäristö (suositeltavaa)

#### Windows (PowerShell)

```
python -m venv venv
venv\Scripts\activate
```


#### Mac/Linux

```
python3 -m venv venv
source venv/bin/activate
```

### 3. Asenna tarvittavat riippuvuudet

```
pip install -r requirements.txt
```

Tarvittaessa varmista vielä pyproj-moduulin asennus:

```
pip install pyproj
```

### 4. Käynnistä sovellus

```
flask run
```

Sovellus on nyt käynnissä osoitteessa: [http://127.0.0.1:5000/](http://127.0.0.1:5000/)

### 6. WFS-tasojen lataaminen

Sovelluksen käyttöliittymässä voit valita ja ladata haluamasi WFS-tasot kartalle. Tasot haetaan Helsingin kaupungin WFS-rajapinnasta osoitteesta https://kartta.hel.fi/ws/geoserver/avoindata/wfs.

## Ylläpito ja jatkokehityksen aiheita

- Sovellus tukee dynaamisia karttatasoja, joita voidaan helposti laajentaa lisäämällä uusia WFS-tasoja valikkoon.
- Paikkatieto-analyysit voidaan toteuttaa PyQGISin avulla suoraan sovelluksessa.
