---
tags: [Testing, værktøj]
title: Fluent Assertions
created: '2020-10-28T08:04:45.007Z'
modified: '2020-10-28T09:21:15.273Z'
---

# Fluent Assertions
## Den gode test
* Hurtig
* parallelt
* uafhængig af IO
* Robust
  - SOLID principperne
* Lav minimalt setup
* Test kun på relevante output
  - hav fokuserede test: Hvis der skal undersøges om en persons alder **ikke** er negativ, så er det ligegyldigt at teste om navnet er sat.

I den gode test:
- Gør det tydeligt hvad der testes. skriv variabler med sigende navne. 
  - Overskuelige test sikrer højere kodekvalitet.
  - gode test gør det nemmere at udføre reviews
- tests giver informative fejlbeskeder.

```csharp 
public class NumberGeneratorTests
{
  [Fact]
  public void GetNumber_zeroSeed_BeLessThan42() // metodenavn_condition_forventetResultat
  {
    // Arrange
    var seed = 0;
    var generator = new NumberGenerator(seed);
    // Act
    int number = generator.GetNumber();
    // Assert
    number.Should().BeLessThan(42, "because 42 is a special number");
  }
}
```

Jonas' boganbefalinger:
- THe art of Unit Testing
- Dependency Injection Principles, Practices, and Patterns
