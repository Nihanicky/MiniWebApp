pipeline {
         agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Nihanicky/MiniWebApp.git', branch: 'main'
            }
        }

        stage('Build WAR') {
            steps {
                 sh 'mvn clean package -X || echo "Build may have failed"'
                     
            }
        }

        stage('Archive WAR') {
            steps {
                archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
            }
        }
    }
}
