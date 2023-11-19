pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clonar el repositorio desde Git
                git 'https://github.com/fvalderramag/NET.git'
            }
        }

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
        }
    }
}

