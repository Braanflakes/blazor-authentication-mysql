# blazor-mysql-info
Some helpful info on setting up .NET 8 Blazor to use MySQL instead of MSSQL for Single-User Authentication

Info originally came from: https://www.youtube.com/watch?v=tbkNNVr4Pto

1. Create Blazor Server Web App with Single-User Authentication enabled
2. NuGetPackage Manager - Install Pomelo.EntityFrameworkCore.MySql
3. Change DefaultConnection string in appsettings.json to the format: "Server=server_ip_or_name;Database=database_name;User id=changeme;Password=changeme;"
4. Add using Pomelo.EntityFrameworkcore.MySql; to the top of Program.cs
5. Update builder.Services.AddDbContext line to use MySQL instead: builder.Services.AddDbContext<ApplicationDbContext>(options =>
    options.UseMySql(connectionString, ServerVersion.AutoDetect(connectionString)));
7. Replace all text inside of 00000000000_CreateIdentitySchema.cs with the replacement.txt file in this repository
8. Update the namespace in this file
9. Open cmd to project location
10. Run dotnet ef database update
11. Profit
