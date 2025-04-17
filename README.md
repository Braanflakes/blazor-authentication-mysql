# blazor-mysql-info
Some helpful info on setting up .NET 8 Blazor to use MySQL instead of MSSQL for Single-User Authentication

Info originally came from: https://www.youtube.com/watch?v=tbkNNVr4Pto

1. Create Blazor Server Web App with Single-User Authentication enabled
2. NuGetPackage Manager - Install Pomelo.EntityFrameworkCore.MySql
3. Add using Pomelo.EntityFrameworkcore.MySql; to the top of Program.cs
4. Change DefaultConnection string in appsettings.json to the format: "Server=server_ip_or_name;Database=database_name;User id=changeme;Password=changeme;"
5. Replace all text inside of 00000000000_CreateIdentitySchema.cs with the replacement.txt file in this repository
6. Update the namespace in this file
7. Open cmd to project location
8. Run dotnet ef database update
9. Profit
