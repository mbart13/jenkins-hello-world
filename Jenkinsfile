pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('Maven Version') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('Build') {
            steps {
                // Run Maven on a Unix agent.
                sh 'mvn clean package -DskipTests=true'

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
        
        stage('Test') {
          steps {
            sh 'mvn test'
          }
        }
    }
}
