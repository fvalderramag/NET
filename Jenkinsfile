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
           echo "${WORKSPACE}"
           //bat " dotnet nuget push ${WORKSPACE}\\nupkgs\\fvgprojectone.1.0.0.nupkg --api-key oy2hl3n7i6ixwybtyxla6hdg6jtm27vubpqlaw7vnr3dv4 --source https://api.nuget.org/v3/index.json --skip-duplicate"                         
           bat "dotnet nuget push ${WORKSPACE}\\nupkgs\\fvgprojectone.1.0.0.nupkg -k cmVmdGtuOjAxOjE3MzI3NDY5OTE6TXRxZTRyNmVIc0hUanZVWDBtVE5mWWNxeTA0 -s https://fvg.jfrog.io/artifactory/api/nuget/simpleclifvg"
       }
   }
 }
}
