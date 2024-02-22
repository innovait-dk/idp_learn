QueryModifier bruges til at sætte et "globalt" filter på IQueryable når EntityServicen henter data fra databasen.
QueryModifier'en bliver brugt i alle metoder på EntityServicen.

**Krav**: Applikationen skal kun vise Products, der ikke er "Discontinued"

**Opgave**: Opret en partial klasse til den kodegenererede ProductsQueryModifier og override metoden "Modify".

**Udførelse**: 

1. Vælg "Entity Framework".
2. Vælg "Products".
3. Under "Code Tasks", vælg "Entity QueryModifier" og klik på "Add Code". Der vil nu blive genereret en ProductsQueryModifier.cs fil, som kan tilpasses som ønsket, som det er vist nedenfor. 

```cs
    public partial class ProductsQueryModifier 
    {
        public override IQueryable<Products> Modify(IQueryable<Products> query)
        {
            return query.Where(e => e.Discontinued == false);
        }
    }
```

En QueryModifier kan også bruges til f.eks. at håndtere sikkerhed for en entititet. Så der f.eks. bliver injected en form for securityservice eller lignende ind i constructoren og så bliver Where-sætningen sat alt efter hvad den pågældende bruger har adgang til.
