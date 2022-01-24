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
                sh 'sonar-scanner'
            }
        }
        stage ('Package') {
            steps{
                sh 'mvn -B package'
            }
        }
        stage ('Deploy') {
            steps{
                sh 'sudo rm -Rf /var/lib/tomcat9/webapps/addressbook*'
                sh 'sudo cp ./target/addressbook-2.0.war /var/lib/tomcat9/webapps/addressbook.war'
            }
        }
    }
}
