**Designerens Arkitekturelementer**

Nedenfor er en oversigt over nøgleelementerne i designeren, og hvordan de fungerer inden for applikationsstruktur:

| **Element**  | **Funktionalitet** |
|--------------|--------------------|
| **Database** | Central meta-data lagring af databasen, fundamentet for andre elementer. |
| **Entity Framework** | Genererer kode ud fra databasens meta-data. |
| **Validation** | Skaber kode for validering, optimeret med FluentValidation-frameworket, ud fra databasens meta-data. |
| **Resx** | Muliggør flersproget support i applikationen. |
| **Resx Syncing EntityCaptions** | Tilpassede tekstbeskrivelser for entiteter i brugergrænsefladen. |
| **User Interface** | Genererer brugergrænsefladekode for hver entitet baseret på meta-data. |
| **AppSettings** | Globale applikationsparametre opbevaret i SQL-databasen. |
| **UserSettings** | Brugerspecifikke parametre gemt i SQL-databasen. |
| **Revision** | Genererer kode til revisionssporing og SQL-scripts for detaljeret tabelrevision og præsentation i brugergrænsefladen. |
| **Security** | Giver funktionalitet til at definere roller og operationer for sikkerhedsstyring. |


Disse beskrives næremere under "Arkitektur elementer".