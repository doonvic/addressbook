pipeline{
    agent {'jenkins-tomcat-node'}
    stages {
        stage ('Compilation') {
            steps{
                sh 'mvn -B compile'
            }
        }
    }
}
