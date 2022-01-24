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
        stage ('Package') {
            steps{
                sh 'mvn -B package'
            }
        }
        stage ('Deploy') {
            steps{
                sh 'sudo rm -Rf /var/lib/tomcat9/webapps/addressbook*'
                sh 'sudo cp /tmp/jenkins-data/workspace/Pipeline as code/target/addressbook-2.0.war home/root/var/lib/tomcat9/webapps/addressbook.war'
            }
        }
    }
}
