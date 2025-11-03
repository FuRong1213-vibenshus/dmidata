# Vejr-app med DMI’s “Friedata”

## Overordnet idé

I skal udvikle en desktop-vejrapp, som henter data fra DMI’s åbne API (Friedata) og viser f.eks.:

- Aktuelt vejr (temperatur, vind, sky, nedbør)
- 24-timers eller 7-dages prognose
- Graf over temperaturudvikling
- Valg af by eller koordinater 

Evt. mulighed for at sammenligne flere steder

De kan bruge `PySide6 (Qt)` som GUI-framework og `requests` + `pandas`/`matplotlib`/`Cartopy` til datahåndtering og visualisering.



## Opbygning (MVC)

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




