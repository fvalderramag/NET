pipeline {
agent any
environment {
dotnet = 'path\\to\\dotnet.exe'
}
stages {
stage ('Checkout') {
            steps {
                 git credentialsId: 'userId', url: 'https://github.com/fvalderramag/NET.git',branch: 'main'
            }
}
stage ('Restore PACKAGES') {     
         steps {
             bat "dotnet restore"
          }
        }
stage('Clean') {
      steps {
            bat 'dotnet clean'
       }
    }
stage('Build') {
     steps {
            bat 'dotnet build --configuration Release'
      }
   }
stage('Pack') {
     steps {
           bat 'dotnet pack --no-build --output nupkgs'
      }
   }
stage('Publish') {
      steps {
           bat "dotnet nuget push **\\nupkgs\\*.nupkg -k yourApiKey -s https://fvg.jfrog.io/artifactory/api/nuget/v3/net-nuget"            
       }
   }
 }
}
