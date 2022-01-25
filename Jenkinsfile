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
                sh 'sudo cp ./target/addressbook-2.0.war /var/lib/tomcat9/webapps/addressbook.war'
            }
        }
           stage ('Send Mail') {
            steps{
                mail bcc: '', body: 'The build is finished', cc: '', from: '', replyTo: '', subject: 'Build Email', to: 'frusv2@gmail.com'
            }
       }
     
    }
}
post{
    failure {
        sh 'echo the build failed'
    }
    success {
        sh 'echo the build is successful'
    }
    always {
        sh 'echo the build is complete'
    }
}
