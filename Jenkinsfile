flag=true
pipeline {
    agent any
    environment{
        NEW_VERSION='1.3.0'
    }
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
                when{
                    expression{
                        flag==false
                    }
                }
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
