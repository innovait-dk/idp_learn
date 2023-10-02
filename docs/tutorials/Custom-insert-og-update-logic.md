# Custom insert og update logik

Hvis man vil ændre på den logik der sker ved eksempelvis tilføjelse eller opdatering af en entitet kan det gøres på forskellige niveauer - alt efter hvad man gerne vil opnå.
Generelt anbefales det dog at laver logikken så langt "nede" som muligt, hvor hierarkiet er entiteten nederst og så følger repository, viewmodel og view op efter.

## Logik ændret i repository
Hvis man som eksempel vil sikre sig, at hver gang der bliver tilføjet en `Customers`, at `CompanyName` er stavet med stort, så kunne det på følgende måde:

```csharp
//Custom insert/update logic
public override void Add(Customers entity)
{
	if (entity != null && !string.IsNullOrEmpty(entity.CompanyName))
	{
		entity.CompanyName = entity.CompanyName.ToUpper();
	}
	base.Add(entity);
}
```

## Logik ændret i ViewModel

Vil man derimod sende en fax, hver gang en `Customers` er blevet opdateret, så kunne det gøres:

```csharp
//Custom insert/update logic
protected override void OnSave()
{
	base.OnSave();
	if (this.MainEntity != null && !string.IsNullOrEmpty(this.MainEntity.Fax))
	{
		//Kald service som sender fax med information omkring den opdaterede Customer
	}

}
```
