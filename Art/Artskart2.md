# Dataformat og nedlasting

##Funndataene som er tilgjengelig i Artskart distribueres på en åpen standard for deling av informasjon om biodiversitet som kalles Darwin Core. Standarden er utviklet og vedlikeholdes av TDWG.

Darwin Core er primært laget for å kunne utveksle stedfestet informasjon om arter og andre taksa. Standarden inkludere et sett parametere med tilhørende vokabular. En introduksjon til Darwin Core er gitt på TDWGs [Quick Reference Guide](http://rs.tdwg.org/dwc/terms/index.htm). GBIF har beskrevet [her](https://www.gbif.org/data-quality-requirements) hvilke felter som er påkrevd. Artsdatabanken tilbyr en Excel importmal som viser hvilke felter er påkrevd eller valgfri. Det er også mulig å levere data til Artskart på en standard som kalles [Sampling Event Data](https://github.com/gbif/ipt/wiki/samplingEventData) som er tilpasset overvåkningsdata.

Mange av feltene/parametrene i Darwin Core er fritekstfelt. For at vi skal kunne sorter og filtrere på slike data har vi laget noen regler for gruppering av data. «Aktivitet» er et slik felt hvor det er laget regler for gruppering av egenskaper. I Artskart slås mange ulike aktiviteter som rapporteres til Artsobservasjoner sammen til et sett aktivitetskategorier. For eksempel blir aktivitetene "reir med egg" og "reirbygging" slått sammen til aktivitetskategorien "sikker reproduksjon".

## Koordinater

Når du laster ned data fra Artskart, blir koordinatene for stedfesting av artsfunn inkludert i to formater. Breddegrad (Latitude) og Lengdegrad (Longitude), og 'Øst' og 'Nord'. Disse siste to felt gir koordinatene i UTM zone 33 - euref89. Merk at sone 33 blir brukt til hele Norge, også til lokaliteter som er i sone 32, 34, 35 eller 36.

## Laste ned data

WMS/WFS er åpne kart/GIS standarder som gjør at data fra tjenesten kan benyttes direkte i kart/GIS-verktøy. Data på rødlistede arter i Artskart eksporteres hver natt til en tjeneste for WMS/WFS publisering av disse dataene. Utvalget representerer arter i rødlistekategoriene RE, CR, EN, VU, DD og NT, med en oppgitt geografisk presisjon bedre enn 1 km eller geografisk presisjon ikke oppgitt (0 m). Merk at disse tjenestene henter data i Artskart 1,6 databasen.

Tilsvarende tjeneste er tilgjengelig for fremmede arter, med basisurl: http://kart.artsdatabanken.no/WMS/artskartfa.aspx?version=1.3.0&service=WMS&REQUEST=GetCapabilities

Shapefiler med alle data knytt til denne tjenesten er tilgjengelig her (oppdateres hver natt): http://kart.artsdatabanken.no/WMS/kartdata/artskart/artskart.zip

Tjenesten er tilgjengelig via url: http://kart.artsdatabanken.no/WMS/artskart.aspx?version=1.3.0&service=WMS&REQUEST=GetCapabilities

For tjenesteinfo knyttet til WFS: http://kart.artsdatabanken.no/WMS/artskart.aspx?version=1.3.0&service=WFS&REQUEST=GetCapabilities

## API-tjenesten

Artsdatabanken har utviklet en API-tjeneste for maskin til maskin kommunikasjon. En API-tjeneste gjør det f.eks. mulig for andre brukere av artsdata å lage egne kartløsninger med data fra Artskart. Les mer API-tjenesten [her](https://artsdatabanken.no/Pages/180954).

## Hent data med R

R er et mye brukt statistikkverktøy som også gjør det mulig å søke og hente data fra GBIF globalt. [rgbif](https://cran.r-project.org/web/packages/rgbif/index.html) er en R-pakke som henter data og informasjon fra GBIF-API-et. Med rgbif er det bl.a. mulig å:

- hente data om enkeltfunn
- hente mange poster/funn
- søke etter artsnavn
- lage forekomstkart
- filtrere data
- Funksjonaliteten er beskrevet på [hjelpesiden](https://ropensci.org/tutorials/rgbif_tutorial/).

Det er verdt å merke seg at det vil være forskjeller mellom Artskart og GBIF, f.eks. knyttet til taksonomi. Artskart har også noen kvalitetsfiltre som avviser noe flere poster enn GBIF. I Artskart knytter vi også rødliste- eller fremmedartskategori til funnene, norsk artsnavn, taksonomi i samsvar med Artsnavnebasen og fylke og kommune der hvor det ikke er oppgitt.

Om Artskart
Bidragsytere
Retningslinjer for bruk og sitering
Kort om bruk av bilder
Kvalitetssikring og foredling av dataene
Dataformat og nedlasting
Kunngjøringer
