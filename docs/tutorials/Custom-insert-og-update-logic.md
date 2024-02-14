# Custom insert og update logik

Hvis man vil ændre på den logik der sker ved eksempelvis tilføjelse eller opdatering af en entitet kan det gøres på forskellige niveauer - alt efter hvad man gerne vil opnå.
Generelt anbefales det dog at laver logikken så langt "nede" som muligt, hvor hierarkiet er entiteten nederst og så følger entityservice,viewmodelservice, viewmodel og view op efter.

## Logik ændret i EntityService
Hvis man som eksempel vil sikre sig, at hver gang der bliver tilføjet en `Customers`, at `CompanyName` er stavet med stort, så kunne det på følgende måde:

```csharp
//Custom insert logic
    public partial class CustomersEntityService
    {
        protected override Task<List<PrimaryKeys<Customers>>> InsertToDatabase(List<Customers> entities, CancellationToken cancellationToken = default)
        {
            entities.ForEach(e => e.CompanyName = e.CompanyName?.ToUpper());
            return base.InsertToDatabase(entities, cancellationToken);
        }
    }
```

## Logik ændret i ViewModelService

Vil man derimod sende en fax, hver gang en `Customers` er blevet opdateret, så kunne det gøres:

```csharp
//Custom update logic
    public partial class CustomersEditViewModelService
    {
        public override Task<PrimaryKeys<Data.Entity.Customers>> Update(CustomersEdit entity, CancellationToken cancellationToken = default)
        {
            return base.Update(entity, cancellationToken);
            //Kald service som sender fax med information omkring den opdaterede Customer
        }
    }
```
