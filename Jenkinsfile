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
           bat "dotnet nuget push **\\nupkgs\\*.nupkg -s https://fvg.jfrog.io/artifactory/api/nuget/simpleappfvg -username fvalderramag@gmail.com -password cmVmdGtuOjAxOjE3MzIzODM0NDc6V0FhU0V2SDZDNFI5ZnRicW00d2tqcmM4NU1m" 
       }
   }
 }
}
