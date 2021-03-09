# dockerdotnetapp
containerize a .NET Core application with docker.

# Create .NET Core app

dotnet new console -o App -n NetCore.Docker

# Folder- tree
docker-working
    └──App
        ├──NetCore.Docker.csproj
        ├──Program.cs
        └──obj
            ├──NetCore.Docker.csproj.nuget.dgspec.json
            ├──NetCore.Docker.csproj.nuget.g.props
            ├──NetCore.Docker.csproj.nuget.g.targets
            ├──project.assets.json
            └──project.nuget.cache
# Publish .NET Core app
dotnet publish -c Release

#Create the Dockerfile
docker build -t counter-image -f Dockerfile .

# Create a container
docker create --name corecounter counter-image

#Manage the container
docker start corecounter

docker stop corecounter
