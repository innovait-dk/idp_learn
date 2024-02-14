# Opret quickfind

QuickFinds laves i shell'ens viewmodel. 

Nedenstående er der vist, hvordan man kan lave QuickFinds på to forskellige måder i constructoren på MainViewModel.cs.

## Eksempel 1 - QuickFind på et felt
Det første eksempel viser, hvordan man laver en QuickFind på feltet `CompanyName` på entiteten `Customers`. 

I designeren:

Vælg "User Interface"

Vælg "Customers"

Vælg feltet "CompanyName"

I "Code Tasks" vælg "QuickFind" og klik "Add Code". Der bliver nu genereret en QuickFindCompanyName.cs fil, som frit kan tilpasses, som vist nedenfor.

Implementer koden som beskrevet i TODO:-kommentaren.
```csharp
  //TODO: this should be added to the servicecollection like this:
  //serviceCollection.AddTransient<Innova.Prism.Library.Search.ISearchItemViewModel, QuickFindCompanyName>();
  //or in the search module like this:
      //public override void RegisterTypes(IContainerRegistry containerRegistry)
      //{
      //   base.RegisterTypes(containerRegistry);
      //   containerRegistry.Register<Innova.Prism.Library.Search.ISearchItemViewModel, QuickFindCompanyName>("QuickFindCompanyName");
      //}

  public class QuickFindCompanyName : QuickFindSearchItemViewModel<Northwind.Data.Entity.Customers>, ISearchItemViewModel
  {
      public QuickFindCompanyName(IQuickFindNavigationService<Northwind.Data.Entity.Customers> findNavigationService) : base(findNavigationService, e => e.CompanyName)
      {

      }

      public override Expression<Func<Northwind.Data.Entity.Customers, bool>> GetSearchExpression()
      {
          return e => e.CompanyName.Contains(this.SearchText);
      }
  }
```

## Eksempel 2 - QuickFind på flere felter
Det andet eksempel viser, hvordan man laver en QuickFind, som søger på flere felter på entiteten `Employees`.

I designeren:

Vælg "User Interface"

Vælg "Employees"

Vælg feltet "LastName"

I "Code Tasks" vælg "QuickFind" og klik "Add Code". Der bliver nu genereret en QuickFindLastName.cs fil, som frit kan tilpasses, som vist nedenfor.

```csharp
    public class QuickFindNavne : QuickFindSearchItemViewModel<Northwind.Data.Entity.Employees>, ISearchItemViewModel
    {
        public QuickFindNavne(IQuickFindNavigationService<Northwind.Data.Entity.Employees> findNavigationService) : 
            base(findNavigationService, e => e.LastName)
        {
            this.Title = "Navne";
        }

        public override Expression<Func<Northwind.Data.Entity.Employees, bool>> GetSearchExpression()
        {
            return e =>
            e.LastName.Contains(this.SearchText) ||
            e.FirstName.Contains(this.SearchText);
        }
    }
```
