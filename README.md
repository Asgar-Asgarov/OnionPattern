# OnionPattern
dotnet new sln --name PatternOnion
mkdir Core
dotnet new classlib -n PatternOnion.Domain -o Core/PatternOnion.Domain
dotnet sln PatternOnion.sln add Core/PatternOnion.Domain/PatternOnion.Domain.csproj
dotnet new classlib -n PatternOnion.Application -o Core/PatternOnion.Application
dotnet sln PatternOnion.sln add Core/PatternOnion.Application/PatternOnion.Application.csproj
mkdir Infrastructure
dotnet new classlib -n PatternOnion.Persistence -o Infrastructure/PatternOnion.Persistence
dotnet sln PatternOnion.sln add Infrastructure/PatternOnion.Persistence/PatternOnion.Persistence.csproj
dotnet new classlib -n PatternOnion.Infrastructure -o Infrastructure/PatternOnion.Infrastructure
dotnet sln PatternOnion.sln add Infrastructure/PatternOnion.Infrastructure/PatternOnion.Infrastructure.csproj
mkdir Presentation
dotnet new webapi -n PatternOnion.Presentation -o Presentation/PatternOnion.Presentation
dotnet sln PatternOnion.sln add Presentation/PatternOnion.Presentation/PatternOnion.Presentation.csproj
dotnet add Core/PatternOnion.Application/PatternOnion.Application.csproj reference Core/PatternOnion.Domain/PatternOnion.Domain.csproj

dotnet add Infrastructure/PatternOnion.Persistence/PatternOnion.Persistence.csproj reference Core/PatternOnion.Application/PatternOnion.Application.csproj 

dotnet add Presentation/PatternOnion.Presentation/PatternOnion.Presentation.csproj reference Infrastructure/PatternOnion.Persistence/PatternOnion.Persistence.csproj




