def gv

pipeline {
    agent any

    stages {
        stage('load') {
          script {
            gv = load 'script.groovy'
          }
        }

        stage('build') {
          steps {
            gv.buildApp
          }
        }
    }
}
