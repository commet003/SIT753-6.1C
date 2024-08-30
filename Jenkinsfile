pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sleep time: 10, unit: 'SECONDS'
                echo 'Building the code'
                echo 'A tool like Maven or Gradle could be used at this stage'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests'
                echo 'A tool like JUnit or TestNG could be used at this stage'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis'
                echo 'A tool like SonarQube could be used at this stage '
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Running security scan'
                echo 'A tool like OWASP Dependency Check could be used at this stage'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server'
                echo 'A tool like SCP or Ansible could be used at this stage'
            }
        }
        stage('Integration Tests') {
            steps {
                echo 'Running integration tests on staging'
                echo 'A tool like Selenium could be used at this stage'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server'
                echo 'Again SCP or Ansible could be used at this stage'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
        always {
            emailext(
                to: 'corierhodes@yahoo.com.au',
                from: 's215186871@deakin.edu.au',
                subject: "Pipeline ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                body: """Pipeline ${currentBuild.fullDisplayName} has finished with status: ${currentBuild.currentResult}
                Logs: ${env.BUILD_URL}consoleText"""
            )
        }
    }
}