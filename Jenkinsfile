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
                echo "Building Stage..."
                echo "Maven is installed, but no pom.xml found in repo."
                bat "mvn -version"
            }
        }

        stage('Test') {
            when {
                expression { return params.executeTests == true }
            }
            steps {
                echo "Test Stage..."
                echo "Skipping 'mvn test' because no pom.xml exists."
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
