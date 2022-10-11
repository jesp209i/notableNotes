---
tags: [Database, Eksamen]
title: DB Exam Question 2
created: '2020-12-05T08:20:43.480Z'
modified: '2020-12-09T11:06:50.114Z'
---

# DB Exam Question 2
```
Describe stored procedures and how are they created. Elaborate on scenarios where they should be used/not used.
How do stored procedures differ from Views, Triggers and Functions?
```
Opret en Stored Procedure
```SQL
CREATE PROC spGetVisitsByPetType (
  @petType VARCHAR(255)
)
AS
BEGIN
BEGIN TRY
  SELECT VisitDateTime, PetName, LOWER(PetType) Type, DateBirth, Firstname, Lastname, Phone, Email
  FROM Visit
    LEFT JOIN Pet
    ON Pet.ID = Visit.PetID
      LEFT JOIN PetOwner
      ON PetOwner.ID = Pet.PetOwnerID
	      LEFT JOIN PetType
	      ON Pet.PetTypeID = PetType.ID
  WHERE PetType = LOWER(@petType)
IF @@ROWCOUNT < 1
  PRINT N'No Animals of type: ' + @petType
END TRY
BEGIN CATCH
  PRINT ERROR_MESSAGE();
END CATCH
END
```  
Samme logik i C#
```csharp
Public List<Visits> GetVisitsByPetType(string petType)
{
  Try {
    var visits = context.Visits.Where(x=>x.PetType == petType)
      .Include(x=>x.Pet)
        .ThenInclude(x=>x.PetOwner)
      .Include(x=>x.Pet)
        .ThenInclude(x=>x.PetType)
      .Select(x=> new Visit(x.VisitDateTime, x.Pet.PetName, x.PetType.Type.ToLower(), x.Pet.DateBirth, x.PetOwner.FirstName, x.PetOwner.LastName, x.PetOwner.Phone, x.PetOwner.Email)).ToList();
    If (visits.Count < 1)
    {
      Console.WriteLine($“No animals of type: {petType}”);
    }
	} catch (SqlException e){
	  Console.WriteLine(e.ToString());
	}
	Return visits;
}
```
__Stored Procedures, fordele:__  
-	Logikken er indkapsuleret
  *	hvis implementationen skal ændres, skal dette kun gøres et sted
-	Giver bedre kontrol med sikkerheden
  *	Man kan give brugere adgang til at bruge en SP, uden at give brugeren lov til at udføre de ”rå statements” direkte. Måske indeholder SP’en noget validering som brugeren ikke nødvendigvis overvejer at undersøge inden.
  *	SP med parametre kan hjælpe med at undgå SQL-injection
-	Man kan indbygge fejlhåndtering
  * SP’en kan indeholde logik der fanger og retter fejl, så brugeren ikke skal tage stilling
-	Performance fordele
  * SP’er udnytter cached execution plans = hurtigere forespørgsler
  * Mindsker netværkstrafik

__Triggers:__  
Triggers bliver invoked ved at der sker et event i databasen. Triggeren er forbundet til et bestemt event.  
”After” og ”Instead of” virker med DML statements (crud på tabel)  
”After” virker med DDL (database scope (opret slet, ændre) og server scope)  

__Functions:__  
Kan bearbejde data baseret på input, minder i princippet om en stored procedure, men behøver ikke udføre arbejde på rækkerne fra en tabel:   Eksempel fra bog: function beregner alder ud fra fødselsdato og nuværende dato  

__Views:__  
Virtuelle tabeller som man kan query op imod. Det kan være et udsnit af en eller flere joinede tabeller.  
Man kan kun lave dataudtræk i et view.  
Da Viewet er gemt på serveren kan man opnår sikkerhed og performance som med SP.


# Fra klassen:
```
- Hvordan bygger man en Stored procedure + eksempel
  - parametre, retur værdier
- forskelle mellem SP og Views og Trigger og fuctions (programmering inden i SQL Server)
  - hvornår bruger man hvad?
  - fordele og ulemper om de forskellige muligheder
```

