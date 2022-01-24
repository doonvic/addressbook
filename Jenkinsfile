Pipeline{
    agent any
    stages {
        stage ('compilation') {
            step {
                git 'https://github.com/doonvic/addressbook.git'
            }
            sh 'mvn -B compile'
        }
    }
}
