pipeline {
    agent any

    tools {
        maven 'Maven'     // must match Jenkins Tools name
    }

    parameters {
        booleanParam(
            name: 'executeTests',
            defaultValue: true,
            description: 'Run Test Stage'
        )
    }

    stages {
        stage('Build') {
            steps {
                echo "Building using Maven..."
                bat "mvn -version"
                
            }
        }

        stage('Test') {
            when {
                expression { return params.executeTests == true }
            }
            steps {
                echo "Running tests..."
                bat "mvn test"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy Stage..."
            }
        }
    }

    post {
        always {
            echo "Post-build actions..."
        }
    }
}
