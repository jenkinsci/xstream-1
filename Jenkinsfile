pipeline {
    agent { docker 'maven:3-alpine' } // checking
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -U -e clean install -Dmaven.test.failure.ignore=true'
            }
        }
    }
    post {
        always {
            junit '**/surefire-reports/**/*.xml'
        }
    }
}
