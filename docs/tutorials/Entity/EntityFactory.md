# Entity Factory

**Krav**: Property'en "HireDate" på "Employees" skal have en standardværdi sat til dagens dato, når der oprettes en ny medarbejder.

**Opgave**: Opret en partial klasse til den kodegenererede EmployeesEntityFactory og implementer partial metoden "SetDefaults".

**Udførelse**: 

1. Vælg "Entity Framework".
2. Vælg "Employees".
3. Under "Code Tasks", vælg "EntityFactory" og klik på "Add Code". Der vil nu blive genereret en EmployeesEntityFactory.cs fil, som kan tilpasses som ønsket, som det er vist nedenfor. I dette eksempel er partial metoden "SetDefaults" implementeret.

```cs
    public partial class EmployeesEntityFactory
    {
        partial void SetDefaults(Employees employees)
        {
            employees.HireDate = DateTime.Now;
        }
    }
```

Nu vil standardværdien for "HireDate" blive sat til dagens dato, når en ny "Employees" oprettes.

![Billede](media/index.png)