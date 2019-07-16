pipeline {
    agent { label 'vm-int-jenkins-slave' }
    stages {
        stage ('deploy') {
            steps {
                sh 'mvn -B clean deploy'
            }
        }
    }
}