def gv

pipeline {
    agent any

    stages {
        stage('load') {
          steps {
            script {
                gv = load 'script.groovy'
            }
          }
        }

        stage('build') {
          steps {
            script {
                gv.buildApp()
            }
          }
        }
    }
}
