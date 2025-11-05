# Vejr-app med DMI’s “Friedata”

## Overordnet idé

I skal udvikle en desktop-vejrapp, som henter data fra DMI’s åbne API (Friedata) og viser f.eks.:

- Aktuelt vejr (temperatur, vind, sky, nedbør)
- 24-timers eller 7-dages prognose
- Graf over temperaturudvikling
- Valg af by eller koordinater 

Evt. mulighed for at sammenligne flere steder

De kan bruge `PySide6 (Qt)` som GUI-framework og `requests` + `pandas`/`matplotlib`/`Cartopy` til datahåndtering og visualisering.

Derudover skal I udarbejde en kort rapport, hvor I reflekterer over jeres softwarearkitektur, designprincipper og udviklingsproces.

## Krav 
### Opbygning (MVC)
Programmet skal være struktureret efter MVC-princippet:

- Model:
    - Henter og behandler data fra DMI Open Data API (temperatur, vind, nedbør etc.)
    - Gemmer evt. lokale data i pandas DataFrame
    - Leverer data klar til visning (koordinater, temperaturer, vindstyrke)

- View:
    - Bygget i PySide6 (QMainWindow, QWidget, QVBoxLayout)
    - Indeholder Matplotlib-Canvas, knapper, dropdowns mv.
    - Udsender signaler (fx “hent data”, “vis temperatur”, “opdater kort”)

- Controller:
    - Binder signaler fra View til Model-funktioner
    - Håndterer logik: henter data (fra modellen), opdaterer kort eller plots
    - Levere resultatet tilbage til View (fx “opdater kort” eller “tegn nyt plot”)

    Alle tre dele skal være adskilt i mindst tre (eller flere) python-filer. Navngiv fx: 
    `weather_model.py`, `weather_view.py`, `weather_controller.py`

### Funktionalitet

App’en skal som minimum kunne:

- Hente data fra DMI’s Friedata API (fx temperatur, vind eller nedbør).
- Vise data i GUI’en i tekst og grafisk form (f.eks. via matplotlib).
- Give brugeren mulighed for at vælge fx station, tidspunkt eller parameter.
- Håndtere fejl (fx hvis DMI’s API ikke svarer eller returnerer tomme data).

### Bruge af AI

I må gerne bruge AI som hjælperedskab til at:

- Forklare API’er eller syntaks
- Fejlfinde (debugge)
- Finde eksempler på at hente bestemte vejrdata fra API'er


    I skal i rapporten beskrive hvad AI har bidraget med, og hvordan I har vurderet dens output

## Rapporten

1. Indledning
    - Kort beskrivelse af appens formål og funktioner.
2. Arkitektur
    - Hvordan har I anvendt MVC i jeres produkt
    - Hvilke andre software designprincipper (**SOLID**) har i taget hensyn til 
3. Dataanalyse
    - Hvordan håndtere I data (transform, filtrering, visualisering)
4. AI som hjælperedskab
    - Hvordan har I brugt AI i projektet?
    - Hvordan har I vurderet, om AI's forslag var korrekte og passende?
5. Konklusion / refleksion
    - Hvad fungerer godt i jeres app?
    - Hvad kunne forbedres?

## Aflevering

- Koden skal afleveres i github.
- Rapporten skal afleveres i studica.
