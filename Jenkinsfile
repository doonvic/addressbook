pipeline{
    agent {label 'jenkins-tomcat-node'}
    stages {
        stage ('Compilation') {
            steps{
                sh 'mvn -B compile'
            }
        }
     stage ('Static Code Analysis') {
            steps{
                sh '/opt/sonar-scanner-4.6.2.2472-linux/bin/sonar-scanner'
            }
        }
    }
}
