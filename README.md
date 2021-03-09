# dockerdotnetapp
containerize a .NET Core application with docker.

# Create .NET Core app

dotnet new console -o App -n NetCore.Docker

# Publish .NET Core app
dotnet publish -c Release

#Create the Dockerfile
docker build -t counter-image -f Dockerfile .

# Create a container
docker create --name corecounter counter-image

# Manage the container
docker start corecounter

docker stop corecounter
