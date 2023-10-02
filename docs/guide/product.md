# Produktet

"Innova Developer Platform" er en kombination af to værktøjer:

- **Innova Application Designer** (En addin til Microsoft Visual Studio)
- **Innova Frameworks**

## Innova Application Designer

Innova Application Designer (IAD) er et  udviklingsværktøj, der er integreret med Microsoft Visual Studio's miljø.
Med IAD får udviklere muligheden for at nøje konfigurere de forskellige lag i en applikations arkitektur. Efter denne nøje konfiguration bliver det muligt at autogenerere kode direkte i Visual Studio.

Ved at benytte IAD får udviklere en håndgribelig visuel præsentation af, hvilke arkitekturelementer de ønsker at inkludere i applikationen, som illustreret nedenfor.

![iad](elements/media/product_2022-05-24-10-00-45.png)

Dette skærmbillede er et øjebliksbillede direkte fra Visual Studio. Bemærk, at "Solution Explorer" er placeret til højre, mens IAD dominerer venstre side. Et enkelt dobbeltklik på filen "ApplicationDesigner.iad" fra "Solution Explorer" åbner IAD-interface.

Den yderste venstre kolonne af IAD fremviser de valgte arkitekturelementer. Efter valg af et specifikt arkitekturelement, kan man dykke dybere og tilpasse det. Som eksemplificeret, ved valg af "Entity Framework" bliver det muligt at specificere hvilke databasetabeller, der skal integreres i applikationens entitetslag. Efter fuldførelse af konfigurationen aktiverer et simpelt klik på "Create code"-knappen autogenereringen af C# kode for hele entitetslaget. Denne kode kan derefter ses, og om nødvendigt tilpasses, via solution explorer.

IAD er konstant i vækst; nye arkitekturelementer tilføjes, og eksisterende elementer opdateres, især når nyere teknologiske rammer, såsom Entity Framework/Entity Core/Entity 6.0, bliver tilgængelige.

Hvert arkitekturelement indhenter metadata fra underliggende elementer, hvilket letter konfigurationsprocessen.

### Tilpasning af den genererede kode

Den genererede kode er designet til at være så fleksibel som muligt. Da koden genereres som "partial class", kan udviklere nemt skræddersy koden til en specifik applikations behov. Yderligere vejledning kan findes i vores How-To-Guides.

## Innova Framework

Innova Framework er en kulmination af Innova IT's mange års erfaring, skræddersyet til at komplementere og udvide de mest populære .NET-rammer:

- Entity Framework
- Fluentvalidation
- Microsoft.Extensions.Logging
- Microsoft.Extensions.DependencyInjection
- Prism
- Windows UI: WPF

Dette rammeværk er grundlaget for alle Innova IT's applikationer og modtager regelmæssige opdateringer for at sikre, at det forbliver på forkant med branchens bedste praksis.