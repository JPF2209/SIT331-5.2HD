# Why I Made My Choices For The Task
## Bounded Contexts Chosen
There are 4 bounded contexts that are in this project being Artifact, ArtifactType, Artist and Exhibition. The reasons why I chose these 4 are because they all tie in well together with the main context in this case being the Artifact context. This is because the Artifact context has a lot of information that can be found from the the Aboriginal Art website being the foundational context that allows for the other three to exist being Artist, ArtifactType and Exhibition where the Artifact context stores information relating to the other three contexts which helped me to build out the backend using this as a framework.

## Backend Process
With the backend process, it starts with program.cs initialising all the values before moving onto the controllers that allow on something like swagger to then view and interact with the controllers being the place where HTTP requests are handled. I then store the models being the framework of the data structure of the bounded contexts in the models folder to make the project neater and this framework helps with the controllers and the other functions. Then as I aim to do commands from the controller, I use a services layer to contain the business logic and to do operations checking data here that doesn’t need to be done in the persistence layer making another layer of separation and an example is checking if an artifact is available before retrieving it. Then my persistence layer handles the communication with the database where in this case, it’s MongoDB. Then setting is a configuration layer storing information related to the settings of the API. Then I have a test layer to ensure that every other layer operates correctly using Xunit tests to do so with the code logic that exists.

## Technologies Chosen
For my different technologies that I implemented, I chose to implement MongoDB because it vastly differs from SQL since PostgreSQL in general is relational and based on the SQL coding language but to introduce something that’s different yet still very user friendly, I chose MongoDB since it’s document stored and uses NoSQL. By being able to apply this technology into my project, it offers a different technology that handles the same things as PostgreSQL meanwhile using a more dynamic DB solution. I chose to implement Xunit tests because it’s the most popular and default testing framework for .NET Core having lots of tools and documentation to allow for an easy way to test the code before it’s produced and used elsewhere.
# Setup Guide
## Install MongoDB
1. Go to https://www.mongodb.com/try/download/community
2. Choose MongoDB Community Server
3. Install it with default settings (Install MongoDB Compass)
4. Open up MongoDB compass
5. If you see this, go to localhost:number and then choose create database
![Screenshot (103)](https://github.com/user-attachments/assets/3e05cd0c-c9a5-4226-ae55-4b1e3cf29c1b)
6. Then for making the DB, name the Database Name "Mongo" without the quotation marks and make the 1st collection name artists
![Screenshot (105)](https://github.com/user-attachments/assets/21bbee87-dc51-4731-83e9-a8f0a010a610)
7. Then for the other three, name them artifacts, artifacttypes and exhibitions
8. You are ready for the next steps

## Install Dotnet
1. This assumes you have installed vs code, if not go here (https://code.visualstudio.com/)
2. For DotNet, go to (https://dotnet.microsoft.com/en-us/download)
3. Under ".NET SDK" selete the latest stable version
4. Download the x64 installer for windows, the .pkg installer for macOS or for linux the commands below
   
### Register Microsoft package repo
(FYI, do not copy the numbers on the left, just copy and paste from dotnet onwards)
1. sudo apt update
2. sudo apt install -y wget apt-transport-https software-properties-common
3. wget https://packages.microsoft.com/config/ubuntu/$(lsb_release -rs)/packages-microsoft-prod.deb
4. sudo dpkg -i packages-microsoft-prod.deb

### Install SDK
sudo apt update
sudo apt install -y dotnet-sdk-8.0  # Replace 8.0 with latest if needed

5.  Then run the installer and follow instructions

## Setup Project Itself
### Automatic
1. On the terminal in VS code once you download the files, run "dotnet restore", this should do the trick
### Manual
If you need to install it manually, using dotnet download these libraries.
(FYI, do not copy the numbers on the left, just copy and paste from dotnet onwards)

1. dotnet add package FastMember.Signed --version 1.5.0
2. dotnet add package Microsoft.AspNetCore.OpenApi --version 7.0.7
3. dotnet add package Microsoft.NET.Test.Sdk --version 17.9.0
4. dotnet add package MongoDB.Driver --version 3.4.0
5. dotnet add package Moq --version 4.20.72
6. dotnet add package Newtonsoft.Json --version 13.0.1
7. dotnet add package Npgsql --version 6.0.5
8. dotnet add package Swashbuckle.AspNetCore --version 6.5.0
9. dotnet add package xunit --version 2.5.1
10. dotnet add package xunit.analyzers --version 1.18.0
11. dotnet add package xunit.runner.visualstudio --version 2.5.1

Once you do this, the project should then work and to verify it's worked, run the command below and see if all these libraries are installed
dotnet list package

