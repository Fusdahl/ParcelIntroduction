# ParcelIntroduction

Parcel lover at vi kan kaste all konfigurasjon ut av vinduet, men hvordan leverer det?

I denne workshopen skal vi se på Parcel og utforske hvordan man kan få til frontendbygging uten konfigurering. Vi skal gjøre dette ved å følge den offisielle introdksjonen til Parcel samtidig som vi ser på hvordan Parcel sine abstraksjoner gjør at den skjønner utrolig mye av byggeoppsettet dit out of the box.

Til å begynne med er det greit å klone ned prosjektet og kjøre npm install.

En kjapp tur innom terminalen eller filsystem vårt viser oss at vi har et minimalt oppsett. En index.html og en index.js fil for å komme i gang, en package.json uten noe særlig i og en readme fil. Parcel kommer med en egen utviklingsserver og vi kan enkelt skrive
`parcel index.html` for å kjøre opp en enkel server som server frontendfilene våre. Gå til `http://localhost:1234` hvor du vil se en liten velkomstmelding både i html'en og i konsollen. Dersom du foretrekker en annen port kan du kjøre opp serveren med `parcel index.html -p <port number>` 

Parcel fungerer ved å tenke på filer som *Assets*. Alle filer er en asset for Parcel og man har spesialhåndtering for Javascript, HTML og CSS. Ved å analysere hvordan filer avhenger av hverandre bygger Parcel et Asset-tre som kan analyseres for å konstruere den endelige bundelen som leveres til brukeren sin nettleser. For å leke litt med dette skal vi inkludere litt javascript og annet snacks i vårt sålangt minimale oppsett: 

Lag en ny fil som heter `goodies.js`
```
export function areYouThereParcel() {
  console.log("Can you find me Parcel?")
}
```
og importer denne i index.js med ES6 syntax 
```
import {areYouThereParcel} from "./goodies.js"
areYouThereParcel()
``` 
eller CommonJs syntax 
```
const dependency = require('./goodies.js')
dependency.areYouThereParcel()
```

Kjør opp parcel serveren igjen med `parcen index.js` og du burde se en ny linje i konsollen. Tilsvarende fungerer også med vanlig CSS og diverse kompiler-til-css varianter som LESS og SASS.

EKSEMPEL

Parcel takler også HTML assets veldig godt og man kan f.eks referere direkte til andre html filer sin lokasjon og Parcel vil forstå sammenhengen.

EKSEMPEL

Ikke noe behov for å kontrollere transformering. Dersom Parcel finner config filer vil transformeringene kjøres. 

EKSEMPEL MED BABEL

Ting som typescript automatisk uten noe konfigurasjon.

TS Eksempel

Code splitting og raskere sidevisninger.

Nå som vi har sett på hvordan code splitting fungerer skal vi ta en liten tur innom hvordan Parcel fungerer igjen. Etter at Parcel har konstruert et Asset tre lager man en plan for hvordan man skal konstruere bundles avhengig av bruken av code splitting og hvilken JS som skal lastes når. UTDYP HER.

Sjekk ut og eksperimenter litt med Hot Module Replacement -> Raskere utvikling ved automatisk reloading av relevante filer.

La oss få inn litt react.

Bygge en produksjonsversjon med react.





