pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                // Here you can define commands for your build, e.g.,
                // sh 'make build' or bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                // Here you can define commands for your tests, e.g.,
                // sh 'make check'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // Here you can define commands for your deployment, e.g.,
                // sh 'make publish'
            }
        }
    }
    post{
        always{
            echo 'post build condition running'
        }
        failure{
            echo 'post action if build failed'
        }
    }
}
