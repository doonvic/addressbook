Pipeline{
    Agent jenkins-tomcat-node
    Stages {
        stage ('compilation') {
            Step {
                git 'https://github.com/doonvic/addressbook.git'
            }
            sh 'mvn -B compile'
        }
    }
}
