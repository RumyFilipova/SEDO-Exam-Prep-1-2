pipeline{
    agent any
    stages{
        stage("Restor dependencies"){
            when{
                anyOf{
                    branch "main"
                    branch "feature"
                }
            }
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build the project"){
            when{
                anyOf{
                    branch "main"
                    branch "feature"
                }
            }
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Run tests"){
            when{
                anyOf{
                    branch "main"
                    branch "feature"
                }
            }
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}