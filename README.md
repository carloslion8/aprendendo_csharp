# CSharp

| Comando                                                                      | O que faz?        | opc                                | param.                                                                                                                                                                                                                                |
|------------------------------------------------------------------------------|-------------------|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| dotnet new <opc> -o <nome> dotnet new -l dotnet new <opc> -lang F# -o <name> | Cria novo projeto | <web|react|console|angular|webapi> | -o nome do projeto -l lista de templates -lang <C#|F#|VB>                                                                                                                                                                             |
| dotnet build                                                                 | Compila o projeto | <nome projeto|nome solução>        | dotnet build -v - verbosidade  dotnet build -o <path> - Caminho do .exe  dotnet build --runtime <runtime> ex: dotnet build --runtime ubuntu.18.04-x64  dotnet build --source <path>  ex: dotnet build --source c:\packages\mypackages |
| dotnet run                                                                   | Roda o projeto    |                                    | dotnet run --project ./projects/proj1/proj1.csproj                                                                                                                                                                                    |
