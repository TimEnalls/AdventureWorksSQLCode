# AdventureWorksSQLCode

**INNER JOIN**
1
ALTER VIEW [dbo].[vAllHumanResourcesEmployee]
AS
SELECT
EDH.[BusinessEntityID]
,EDH.[Title]
,EDH.[FirstName]
,EDH.[MiddleName]
,EDH.[LastName]
,EDH.[Suffix]
,EDH.[Shift]
,EDH.[Department]
,EDH.[GroupName]
,EDH.[StartDate]
,EDH.[EndDate]

,ED.[JobTitle]

,E.[PhoneNumber]
,E.[PhoneNumberType]
,E.[EmailAddress]
,E.[EmailPromotion]
,E.[AddressLine1]
,E.[AddressLine2]
,E.[City]
,E.[StateProvinceName]
,E.[PostalCode]
,E.[CountryRegionName]
,E.[AdditionalContactInfo]

FROM [AdventureWorks].[HumanResources].[vEmployeeDepartmentHistory] AS EDH
INNER JOIN [AdventureWorks].[HumanResources].[vEmployeeDepartment] AS ED
ON EDH.BusinessEntityID = ED.BusinessEntityID
INNER JOIN [AdventureWorks].[HumanResources].[vEmployee] AS E
ON ED.BusinessEntityID = E.BusinessEntityID
GO
