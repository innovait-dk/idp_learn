**Krav**: På forskellige steder i applikationen skal det fulde navn på en "Employees" vises. 

**Opgave**: Opret en property på Employees-klassen, der kan kombinere FirstName og LastName.

**Udførelse**: 

1. Vælg "Entity Framework".
2. Vælg "Employees".
3. Under "Code Tasks" vælges "Entity" og klikke på "Add Code". Der vil nu blive genereret en fil ved navn Employees.cs, som kan tilpasses som ønsket, som det er illustreret nedenfor. (Bemærk attributten [NotMapped](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.schema.notmappedattribute?view=net-7.0))

```cs
    public partial class Employees
    {
        private string _fullName;

        [NotMapped]
        public string FullName
        {
            get { return _fullName; }
            set { _fullName = value; }
        }
    }
```

Nu er denne property klar til at blive anvendt i applikationen. (Se et eksempel på tilpasning i [Mapper](../UI/Mapper.md)).

Alternativt, det kan også gøres på denne måde:

```cs
      [NotMapped]
      public string FullName { get { return $"{FirstName} {LastName}"; } }
```

Vær dog opmærksom på, at hvis property'en bruges sammen med AutoMapper (se senere under User Interface), vil Entity Framework inkludere alle felter i SELECT-statementet og vil alt andet lige give en dårligere performance. Specielt hvis der er "store" felter i tabellen f.eks. bytes/text felter.
