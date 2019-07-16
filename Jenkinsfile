pipeline {
    agent { node { label 'vm-int-jenkins-slave' } }
    environment {
      ARTIFACT_VERSION = readMavenPom().getVersion()
      ARTIFACT_ID    = readMavenPom().getArtifactId()()
    }
    stages {
        stage('deploy') {
            steps {
                sh 'mvn -B clean deploy'
            }
            when {
              not { branch 'master' }
            }
        }
        stage('install') {
            steps {
                sh 'mvn -B clean install'
            }
            when {
              branch 'master'
            }
        }
    }
}