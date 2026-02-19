# Draft Kulur-rapport

Detta är ett Quarto-projekt som visualiserar och analyserar kulturarbetet i Uppsala län, men med enkla inställningsförändringar så kan den anpassas till alla län i Sverige.

## Struktur

-   `index.qmd` – startsida för webbplatsen
-   `Data/` – alla datakällor
-   `Script/` – R-skript för laddning och bearbetning
-   `Figurer/` – alla visualiseringar utom interaktiva grafer

## Hur man bygger webbplatsen

# Det finns en del manuella nedladdningar som hittas i 'Script/create_save_plots'

## Följ sedan

-   I Script/settings sätt kommunnamn, kommunkod, län och länskod till det som önskas. Sätt också färgkoder för kommuner här.

-   En del färger sätts i Script/create_save_plot, kör ctrl F och sök efter 'färg' för att hitta de ställen där färg används

-   Kör Script/run_all_functions för att ladda ner all data och spara grafer

-   Här hittas också kommentarer om eventuell manuell nedladdning av filer vilket för denna rapport är:

    -   Inloggning till MONA krävs för att köra kulturkoden för den senaste datan och sedan ladda ned alla filer sparat som MyFiles.zip och lägga den i mappen "Data".

    -   Tillgång till SCBs företagsregister-API krävs för köra scriptet: api_call_foretagsregister_ae.R .

        -   För att få tillgång till API så följ : [scb-företagsregistret](https://www.scb.se/vara-tjanster/bestall-data-och-statistik/foretagsregistret/avgiftsfria-uppgifter-i-foretagsregistret/) och sök tillgång för företag och arbetsställe, alla variabler. De tillhandahåller sedan instruktioner om hur du går vidare.

    -   Filen KBD-Uppsala är skickad från J.E(Kulturstrateg) på Kultur och bildning och tas ut från kulturdatabasen, maila om uttag av data för kommande år

    -   Filen kulturdatabasen.xlsx är skickad från kulturanalys/kulturdatabasen och fås genom att maila kdb\@kulturanalys.se och efterfråga data för deras nyaste data, skriv vilket år vi har som senaste.

        -   Skriv att ni vill ha data för Museer, scenkonst över tid, med variabler som antal besökare, föreställningar, och ekonomivariabler(som bidrag) för alla kommuner och verksamheter i länet. De ger ut datan för offentliga verksamheter!
        -   När nu fil fås ska den slås ihop med den befintliga filen så att resterande kod fungerar, kod för att slå ihop dataset måste skapas själv.

-   I terminalen skriv \* quarto render

då skapas mappen "\_site" där index.html hittas, öppna den

-   Gå till index.qmd och uppdatera analysen

## Bilder

Dessa bilder kommer behöva bytas ut om andra län ska skapa en rapport, då dessa tillhör Region Uppsala.

Alla grafer är sparade och finns i mappen figurer, de flesta sparas genom att köra dess funktion från scriptet create_save_plots.R, vissa är sparade genom plotlys interaktiva funktion.

För att rendera rapporten så behöver bilder från regionens mediabank laddas ned, dessa läses in i rapporterna med samma namn som de laddas ner med. Alla nedladdade bilder från mediabanken ska sparas i en mapp som heter 'Mediabank', i .gitignore så ställs det in så att dessa inte laddas upp på github utan sparas endast lokalt från nedladdningen på Region Uppsalas mediabank.

# Paket

Gamla eller uppdaterade versioner av paket kan göra så att funktioner i denna kod inte fungerar.
