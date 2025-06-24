pipeline {
    agent any

    stages {
        stage('Checkout the repository') {
            steps {
                checkout scm
            }
        }

        stage('Restore the project') {
            steps {
                script {
        if (isUnix()) {
            sh 'dotnet restore'
        } else {
            bat 'dotnet restore'
        }
    }
            }
        }


        stage('Build the project') {
            steps {
                script {
                if (isUnix()) {
                    sh 'dotnet build'
                } else {
                    bat 'dotnet build'
                }
                    }
            }
        }

        stage('Run test 1') {
            steps {
                script {
                if (isUnix()) {
                    sh 'dotnet test TestProject1'
                } else {
                    bat 'dotnet test TestProject1'
                }
                    }
            }
        }

        stage('Run test 2') {
            steps {
                script {
                if (isUnix()) {
                    sh 'dotnet test TestProject2'
                } else {
                    bat 'dotnet test TestProject2'
                }
                    }
            }
        }

        stage('Run test 3') {
            steps {
                script {
                if (isUnix()) {
                    sh 'dotnet test TestProject3'
                } else {
                    bat 'dotnet test TestProject3'
                }
                    }
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed'
        }
        success {
            echo 'Build succeeded'
        }
        failure {
            echo 'Build failed'
        }
    }
}