pipeline{
    agent any
    stages{
        stage("Restor dependencies"){
            when{
                any of{
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
                any of{
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
                any of{
                    branch "main"
                    branch "feature"
                }
            }
            steps{
                bat "dornet test --no-build --verbosity normal"
            }
        }
    }
}