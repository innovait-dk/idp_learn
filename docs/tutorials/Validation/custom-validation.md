# Andre Eksempeler



```csharp
    public partial class OrderDetailsValidator
    {
        partial void AfterInitialize()
        {
            RuleSet(RuleSetNames.PropertyRuleSetName, () =>
            {
                //Opret simpel validering for et enkelt felt
                RuleFor(ent => ent.UnitPrice).GreaterThanOrEqualTo((decimal)1)
                    .WithName(nameof(OrderDetails));
                //Opret kompleks validering for et felt
                RuleFor(ent => ent.Discount).Must(ValidateDiscount)
                    .WithMessage("Discount må ikke være højere end samlet pris")
                    .WithName(nameof(OrderDetails));
            });
        }

        private bool ValidateDiscount(IOrderDetails obj, float arg)
        {
            //The discount must not ex
            return (obj.Discount > 0) && (obj.UnitPrice * obj.Quantity) > (decimal)obj.Discount;
        }
    }
```

Hvilket vil resultere i valideringen vil blive vist i UI som følgende eksempel:

Simpel validering på UnitPrice

 ![image.png](media/custom-validation_0.png)

Kompleks validering på Discount

 ![image.png](media/custom-validation_1.png)