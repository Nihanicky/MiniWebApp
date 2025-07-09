pipeline {
         agent none
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Nihanicky/MiniWebApp.git', branch: 'main'
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive WAR') {
            steps {
                archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
            }
        }
    }
}
