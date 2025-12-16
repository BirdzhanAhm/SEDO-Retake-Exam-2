pipeline{
    agent any
    
    stages{
        stage("Restore .Net Packages"){
            when {branch pattern: "(main|develop|feature/.*)" , comparator: "REGEXP"}
            steps{
                bat 'dotnet restore' //For Windows
                
              }
           
        }
        stage("Build.Net Project"){
            when {branch pattern: "(main|develop|feature/.*)" , comparator: "REGEXP"}
                bat 'dotnet build --no restore' //For Windows
              }

        stage("Run Unit and Integration Test"){
            when {branch pattern: "(main|develop|feature/.*)" , comparator: "REGEXP"}
            steps{
                bat 'dotnet test -- no-build --verbosity normal' // For Windows
            }
        }   
    }
   
}