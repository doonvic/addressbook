Pipeline{
    Agent any
    Stages {
        stage ('compilation') {
            Step {
                git 'https://github.com/doonvic/addressbook.git'
            }
            sh 'mvn -B compile'
        }
    }
}
