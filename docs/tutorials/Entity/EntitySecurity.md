**Krav**: Der må ikke kunne slettes Categories i applikationen.

**Opgave**: Sæt entitysecurity "CanDelete" til false.

**Udførelse**: 

1. Vælg "Entity Framework".
2. Vælg "Categories".
3. Under "Code Tasks" vælges "Entity Security" og klikke på "Add Code". Der vil nu blive genereret en fil ved navn CategoriesSecurity.cs, som kan tilpasses som ønsket, som det er illustreret nedenfor.

```cs
     public partial class CategoriesSecurity
    {
        public override bool CanDelete()
        {
            return false;
        }
    }
```

Nu vil slet-knappen ikke blive vist i værktøjslinen.