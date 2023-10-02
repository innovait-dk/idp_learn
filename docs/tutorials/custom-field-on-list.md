## Opret den nye property

Opret en ny partial fil, indeholdende list objektet i samme namespace som det kodegenererede tilsvarende list objekt, og tilføj den ønskede property. 

eks:

```csharp
namespace NorthwindClient.Entity
{
    public partial class EmployeesList
    {
        //Opret custom felt på Liste
        //Ny custom property
        public System.String FullName
        {
            get
            {
                return $"{FirstName} {LastName}";
            }
        }
    }
}
```

## Tilføj det nye custom felt i listen

Opret en partial fil til List kontrollen, i samme namespace som den kodegenererede List kontrol (For den valgte entitetstype), og tilføj det nye kolonne.

eks:

```csharp
namespace NorthwindClient.UI.Employees.Controls
{
    public partial class EmployeesList
    {
        partial void AfterInitializeColumns()
        {
            //Opret custom felt på list:
            //Tilføj  det nye felt, bemærk at EmployeesList, bliver benyttet til T og TResult generic typerne for at kunne vælge de nye felt.
            this.AddColumn<NorthwindClient.Entity.EmployeesList, NorthwindClient.Entity.EmployeesList>(e => e.FullName, e => e.FullName, e => e.FullName);
        }
    }
}

```

## Tilføj caption til det nye felt
For at kunne få den korrekte kolonne header, åbnes IAD filen, og i Entity Captions tilføjes en ny række. Sammensæt Name ud fra <EntityName>_<PropertyName> 

eks. EmployeesList_FullName. og indtast den ønskede caption.

 ![image.png](../media/opret-custom-felt-på-liste_0.png)
