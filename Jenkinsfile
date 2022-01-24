pipeline{
    agent {label 'jenkins-tomcat-node'}
    stages {
        stage ('Compilation') {
            steps{
                sh 'mvn -B compile'
            }
        }
    }
}
