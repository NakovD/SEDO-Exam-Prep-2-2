pipeline {
    stages {
        stage('Setup .NET') {
            steps {
                // Assuming .NET is installed on your Windows agent
                // Otherwise, you could use a script to install it
                bat "dotnet --version"
            }
        }

        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished'
        }
    }
}
