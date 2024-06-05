def gv

pipeline {
    agent any

    parameters{
        string(name: "name", defaultValue: "mina", description: "name of owner")
    }

    stages {
        stage('load') {
          steps {
            script {
                gv = load 'script.groovy'
            }

            echo "branch name is ${env.BRANCH_NAME}"
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
