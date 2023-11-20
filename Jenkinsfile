pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clonar el repositorio desde Git
                //git url: 'https://github.com/fvalderramag/NET.git'   

                 // The below will clone your repo and will be checked out to master branch by default.
           git credentialsId: '', url: 'https://github.com/fvalderramag/NET.git'
           // Do a ls -lart to view all the files are cloned. It will be clonned. This is just for you to be sure about it.
           sh "ls -lart ./*" 
           // List all branches in your repo. 
           sh "git branch -a"
           // Checkout to a specific branch in your repo.
           sh "git checkout main"

            }
        }
/*
        stage('Restore and Build') {
            steps {
                // Restaurar paquetes y compilar el proyecto
                script {
                    def dotnetCmd = sh(script: 'which dotnet', returnStatus: true).trim()
                    if (dotnetCmd == 0) {
                        sh 'dotnet restore'
                        sh 'dotnet build'
                    } else {
                        error "dotnet no encontrado. Asegúrate de tener .NET SDK instalado."
                    }
                }
            }
        }

        stage('Test') {
            steps {
                // Ejecutar pruebas
                script {
                    def dotnetCmd = sh(script: 'which dotnet', returnStatus: true).trim()
                    if (dotnetCmd == 0) {
                        sh 'dotnet test'
                    } else {
                        error "dotnet no encontrado. Asegúrate de tener .NET SDK instalado."
                    }
                }
            }
        }

        stage('Publish') {
            steps {
                // Publicar la aplicación
                script {
                    def dotnetCmd = sh(script: 'which dotnet', returnStatus: true).trim()
                    if (dotnetCmd == 0) {
                        sh 'dotnet publish -c Release -o ./publish'
                    } else {
                        error "dotnet no encontrado. Asegúrate de tener .NET SDK instalado."
                    }
                }
            }
        }*/
    }
}

/*
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}*/

