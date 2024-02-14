"Innova Developer Platform" er en avanceret platform, skabt for at optimere udviklingsprocesserne for softwareudviklere, ved at tilbyde værktøjer og metoder, der forenkler udviklingsarbejdet. Den består af to primære komponenter:

- **Innova Application Designer** 
- **Innova Frameworks**

## Innova Application Designer

Innova Application Designer (IAD) er et udviklingsværktøj, der integrerer med Microsoft Visual Studio. Med IAD kan udviklere let konfigurere de forskellige lag i applikationsarkitekturen. Efter den nødvendige konfiguration kan kode genereres direkte i Visual Studio, hvilket bidrager til en mere strømlinet og effektiv udviklingsproces.

Med IAD får udviklere mulighed for visuelt at udforske og definere hvilke arkitekturelementer de ønsker at inkludere i deres applikation, og justere dem efter behov. Når et arkitekturelement er valgt, som f.eks. "Entity Framework", kan udviklere specificere, hvilke databasetabeller der skal inkluderes i applikationens entitetslag.

![iad](media/product_2022-05-24-10-00-45.png)

 Bemærk, at "Solution Explorer" er placeret til højre, mens IAD er i venstre side. Et enkelt dobbeltklik på filen "ApplicationDesigner.iad" fra "Solution Explorer" åbner IAD-interfacet.

Den yderste venstre kolonne af IAD viser de valgte arkitekturelementer. Efter valg af et specifikt arkitekturelement, kan man konfigurere og tilpasse arkitekturelementet. 

Som eksemplificeret, ved valg af "Entity Framework" bliver det muligt at specificere hvilke databasetabeller, der skal integreres i applikationens entitetslag. Efter fuldførelse af konfigurationen klikkes på "Create code"-knappen, som genere C# kode for hele entitetslaget. Denne kode kan derefter ses, og om nødvendigt tilpasses, via solution explorer.

Hvert arkitekturelement bruger metadata fra underliggende elementer og automatisere konfigurationen, hvilket letter konfigurationsprocessen.

### Tilpasning af den genererede kode

Den genererede kode er designet til at være så fleksibel som muligt. Da koden genereres som "partial class", kan udviklere nemt skræddersy koden til en specifik applikations behov. Yderligere vejledning kan findes i vores How-To-Guides.

## Innova Framework

Innova Framework tilbyder en omfattende samling af udviklingsværktøjer og frameworks designet til at udvide og komplementere populære .NET-frameworks.:

- [Entity Framework](https://github.com/dotnet/efcore)
- [Fluentvalidation](https://docs.fluentvalidation.net/en/latest/)
- [AutoMapper](https://automapper.org/)
- [Microsoft.Extensions.Logging](https://learn.microsoft.com/en-us/dotnet/core/extensions/logging?tabs=command-line)
- [.NET dependency injection](https://learn.microsoft.com/en-us/dotnet/core/extensions/dependency-injection)
- [Prism](https://prismlibrary.com/docs/)
- [Telerik](https://www.telerik.com/)
- [Infragistics](https://www.infragistics.com/)

