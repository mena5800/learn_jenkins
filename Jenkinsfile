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

            if (env.BRANCH_NAME == "main"){
              echo "branch name is ${env.BRANCH_NAME}"

            } else {
              echo "not main branch"
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
